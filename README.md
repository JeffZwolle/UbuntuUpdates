# UbuntuUpdates
Issue update commands with a single command.

This script is useful if you are tired of typing:

apt -y update
apt -y upgrade
apt -y dist-upgrade
apt autoremove
apt autoclean

Copy this script to the primary directory of executable commands on the system, and make it executable:

sudo cp -p ~/updates /usr/bin/
sudo chmod +x /usr/bin/updates

Command line parameter:

force = Ignore the message about running this command with screen command.
direct = Ignore pausing at different stage. If distribution upgrade is needed, then it will choose to do so.
reboot = Automatically reboot the system if the system thinks that a reboot is needed.

Script logs are saved to: /var/log/updates.log

There is a Zabbix template available which is optional.
It will show in Zabbix that the updates script is running, which can be handy to understand certain alerts.
