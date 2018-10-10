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
