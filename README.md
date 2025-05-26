# Debian-Discord-Updater<br/>
<br/>
This is a simple tool to automate the update process of Discord on Debian-based systems. Discord Inc. unfortunately refuses to provide a repository, which is why Discord cannot be kept up to date centrally using the package management (e.g. apt). As soon as the latest version of Discord is not installed, Discord can no longer be used.<br/>
<br/>
This script can be started with the following options:<br/>
<br/>
**Without arguments        ->**  The script installs the latest version of Discord. If Discord was not previously installed, Discord will be installed. If the latest version of Discord is already installed, nothing will happen.<br/>
**--disable                ->**  The script removes the cronjob that checks for a new version of Discord after every system start. However, the script remains under /usr/sbin/discord-updater.sh and can still be executed as sudoer or root with all options.<br/>
**--remove                 ->**  The script removes the cronjob that checks for a new version of Discord after every system start. The script is also removed from the /usr/sbin/discord-updater.sh directory. It can no longer be executed in the future and must first be downloaded again.<br/>
**--enable                 ->**  The script does the same things as if it were executed without arguments. In addition, however, the script copies itself into the sbin directory and creates a cronjob. This enables the script to check for updates for Discord after every reboot and to install them if necessary. The search for updates starts about 10 seconds after the boot process.<br/>
<br/>
<br/>
<br/>
The following packages are required to run this script: wget, curl.<br/>
If the packages are not installed, they will be installed by this script. If the script is removed using by “--remove”, wget, curl and discord will not be uninstalled. If you no longer need these packages, you can remove them using by “apt remove” or “apt purge”.<br/>
