# Spotlight

- Wanna disable spotlight to stop the indexing troubles? Run this

```bash
sudo launchctl unload -w /System/Library/LaunchDaemons/com.apple.metadata.mds.plist
```
or
```bash
sudo mdutil -a -i off
```

- Can't live without spotlight and you desperately want it back? Run this

```bash
sudo launchctl load -w /System/Library/LaunchDaemons/com.apple.metadata.mds.plist
```
or 
```bash
sudo mdutil -a -i off
```
