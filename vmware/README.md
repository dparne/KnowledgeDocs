## Creating a headless VM using VMWare Fusion

- Create a file at LaunchDaemons `com.dparne.headlessvm.plist`

```xml
<?xml version="1.0" encoding="UTF-8"?>
<!DOCTYPE plist PUBLIC "-//Apple//DTD PLIST 1.0//EN" "http://www.apple.com/DTDs/PropertyList-1.0.dtd">
<plist version="1.0">
<dict>
    <key>Disabled</key>
    <false/>
    <key>KeepAlive</key>
    <false/>
    <key>Label</key>
    <string>com.dparne.headlessvm</string>
    <key>ProgramArguments</key>
    <array>
        <string>/Applications/VMware Fusion.app/Contents/Library/vmrun</string>
        <string>-T</string>
        <string>fusion</string>
        <string>start</string>
        <string>/Users/dineshparne/Documents/Virtual Machines.localized/CentOS 64-bit.vmwarevm/CentOS 64-bit.vmx</string>
        <string>nogui</string>
    </array>
    <key>RunAtLoad</key>
    <true/>
    <key>UserName</key>
    <string>root</string>
</dict>
</plist>
```
