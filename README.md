# University-Teaching-Materials
A repo for my students to fetch class materials. Mostly scripts to speed up class sessions, exemplary malware, etc.

&nbsp;

# (Boomer) Recovering Quarantined Files

Windows Key, type "CMD" -> Hit "Run as Administrator"

Run the following commands in order:
- mkdir C:\Temp\Infected
- "%ProgramFiles%\Windows Defender\MpCmdRun.exe" -Restore -ListAll
- "%ProgramFiles%\Windows Defender\MpCmdRun.exe" -Restore -All -Path "C:\Temp\Infected"

Malware will be moved to C:\Temp\Infected. Use a zipping tool to Zip + Password Protect this Folder. Transport the folder to a shared destination, like a temp site or email (email in DMs). The zipping + password should make the virus folder evade all email security.

&nbsp;

## Finding Scheduled Task Mechanism
Windows Key, search "Task Scheduler", hit "Run as Administrator"

(Left Menu) Click 'Task Scheduler Library'

Find Item2 Task, Right-Click and Stop it/Disable. 

Right-Click same task again, hit "Properties" -> Go into "Actions" tab.

Copy EVERYTHING (Ctrl + A) in that command window and either send to me in Discord or save to a text file. If you have time, having it in a text file would be great.  

Back in the Tasks window, we will *again* Right-Click that Task, and then hit "Export." Export the resulting XML file to C:\Temp\Infected. This is good evidence, and should be sent to me

&nbsp;

If above was unfruitful:

Windows Key, type "CMD" -> Hit "Run as Administrator"

Run the following commands in order:

- dir "C:\Winddows\System32\Tasks"
- copy C:\Windows\System32\Tasks\Item2 C:\Temp\Infected

This will copy the Item2 task to the Infected folder. This should be sent to me as well

&nbsp;

## Finding Registry Persistence Mechanism
Windows Key, search "regedit", hit "Run as Administrator"

Paste this in your top searchpath window to hop to the location:

- Computer\HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Windows NT\CurrentVersion\Schedule\TaskCache\Tasks
    - Searching in the menu for "{87C13C22-D9AA-4982-AC5A-247FA6EEF916}" 
- Computer\HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Windows NT\CurrentVersion\Schedule\TaskCache\Tree
    - Searching in the menu for "Item2"

Copy values of these keys to a text file. If you don't know what you're looking for, feel free to copy all of them or anything that looks interesting. 

Send the resulting text file to me
