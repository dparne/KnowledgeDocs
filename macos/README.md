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
sudo mdutil -a -i on
```

For reindexing things (Preferrably done overnight)

```bash
sudo rm -rf /.Spotlight-V100/*
```


# List Users

For listing all users (I mean all), run this command:

`sh dscl . list /users`

It will output something like this

```bash
Macintosh:Git dineshparne$ dscl . list /users
_amavisd
_analyticsd
_appleevents
_applepay
_appowner
_appserver
_appstore
_ard
_assetcache
_astris
_atsserver
_avbdeviced
_calendar
_captiveagent
_ces
_clamav
_cmiodalassistants
_coreaudiod
_coremediaiod
_ctkd
_cvmsroot
_cvs
_cyrus
_datadetectors
_devdocs
_devicemgr
_displaypolicyd
_distnote
_dovecot
_dovenull
_dpaudio
_eppc
_findmydevice
_fpsd
_ftp
_gamecontrollerd
_geod
_hidd
_iconservices
_installassistant
_installer
_jabber
_kadmin_admin
_kadmin_changepw
_krb_anonymous
_krb_changepw
_krb_kadmin
_krb_kerberos
_krb_krbtgt
_krbfast
_krbtgt
_launchservicesd
_lda
_locationd
_lp
_mailman
_mbsetupuser
_mcxalr
_mdnsresponder
_mobileasset
_mysql
_netbios
_netstatistics
_networkd
_nsurlsessiond
_nsurlstoraged
_ondemand
_postfix
_postgres
_qtss
_sandbox
_screensaver
_scsd
_securityagent
_serialnumberd
_softwareupdate
_spotlight
_sshd
_svn
_taskgated
_teamsserver
_timed
_timezone
_tokend
_trustevaluationagent
_unknown
_update_sharing
_usbmuxd
_uucp
_warmd
_webauthserver
_windowserver
_www
_wwwproxy
_xserverdocs
daemon
-_-youself-_-
macports
nobody
rabbitmq
root
```

# Notification Center

To stop notifications run these commands

```bash
killall NotificationCenter
launchctl unload -w /System/Library/LaunchAgents/com.apple.notificationcenterui.plist
```

# Max Processes for User

To check the maximum number of processes that we can run for user, run

```bash
ulimit -u
```
