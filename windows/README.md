# Process Watch/Kill
```batch
C:\>tasklist
 
 Image Name                     PID Session Name        Mem Usage
 ========================= ======== ================ ============
 firefox.exe                  26356 Console             139,352 K
 regedit.exe                  24244 Console               9,768 K
 cmd.exe                      18664 Console               2,380 K
 conhost.exe                   2528 Console               7,852 K
 notepad.exe                  17364 Console               7,892 K
 notepad.exe                  24696 Console              22,028 K
 notepad.exe                  25304 Console               5,852 K
 explorer.exe                  2864 Console              72,232 K

C:\>Taskkill /IM firefox.exe /F
 or

C:\>Taskkill /PID 26356 /F
```

Also to find out which process is locking a file in windows download this

https://docs.microsoft.com/en-us/sysinternals/downloads/process-explorer and follow instructions provided.

For finding out process listening on ports 

- Start>>All Programs>>Accessories>>System Tools>>Resource Monitor
- Click on Listening Ports section

- Run cmd as different user `runas /user:{domain}\{username} cmd.exe`

# Jenkins on Windows

- When running Jenkins on a windows server. The pipeline scripts are run as different user than the one that runs Jenkins. And the scripts inside are run as `nt authority\system`. So to access it through scripts we had to mount it as the `nt authority\system` 
- To do that, Download Windows tools for psexec: http://technet.microsoft.com/en-us/sysinternals/bb842062.aspx.  Extract folder. There should be a PsExec.exe file in there 
- Open a `cmd.exe`, Run `./PsExec -i -s cmd.exe` from the location of folder.
- In new shell type `whoami`. Should see: `nt authority\system`
- mount the drive with net use.  Command `net use Z: ${location}` 
- Command `net use Z: /delete` to unmount 
- List all drives -> `fsutil fsinfo drives`
