# UbuntuUpdates
## Issue update commands with a single command

This script is useful if you are tired of typing:

```bash
apt -y update
apt -y upgrade
apt -y dist-upgrade
apt autoremove
apt autoclean
```

Download the script "updates".\
Copy it from your home folder to the primary directory of executable commands on the system, and make it executable:

```bash
sudo cp -p ~/updates /usr/bin/
sudo chmod +x /usr/bin/updates
````

Or, copy it directly from github, and make it executable:

```bash
sudo wget -O /usr/bin/updates https://raw.githubusercontent.com/JeffZwolle/UbuntuUpdates/master/updates
sudo chmod +x /usr/bin/updates
````

Command line parameters:

> force = Ignore the message about running this command with screen command.
> direct = Ignore pausing at different stage. If distribution upgrade is needed, then it will choose to do so.
> reboot = Automatically reboot the system if the system thinks that a reboot is needed.

Example, which I often use (as root):

```bash
updates force direct
````

This script must be run with with administrative privileges.

Script logs are saved to: /var/log/updates.log

## Zabbix Template

There is a Zabbix template available which is optional.\
It will show in Zabbix that the updates script is running, which can be handy to understand certain alerts.\
The script will extract the settings from the Zabbix Agent config file.\
Zabbix is optional. If Zabbix Agent is not installed, then the script will just ignore that part of the script.
