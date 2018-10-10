# Windows
## Fixing Crashes

- If Jenkins instance crashes one way to fix it is to run the following commands in the command prompt

```bat
net stop jenkins

net start jenkins
```

- Jenkins should be setup to run as a windows service for this to work. You should do that to run it automatically on boot in a windows server OS

# Slack Integration
- Install the Jenkins CI app from your slack account's apps page
- Configure it. Please make a note of the **token** as you will need it to configure slack plugin for Jenkins
- Then simply follow the instructions from the slack plugin page [here](https://github.com/jenkinsci/slack-plugin/tree/slack-2.3) (**NOTE** this link is for slack 2.3 plugin. In the future the versions may be higher so make sure you are checking the right version)
