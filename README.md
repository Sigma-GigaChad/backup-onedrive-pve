# backup-onedrive-pve
How to backup PVE on onedrive using rclone and a script that will execute after each backup

This is based on this script: https://github.com/TheRealAlexV/proxmox-vzbackup-rclone
Which I recommand following but I have had some problems and to be honest I don't remember which but this script is working for me at least. Note that it does not work with LXC containers for now.

I think it is because I wanted to backup to my NAS localy and then make a second backup on the Cloud.

We should also implement backups encryptions like the other script does. Feel free to do it and make a pull request.

## Requirements
- rclone
- onedrive account

## How to do it ?
- Clone this repo on your PVE server
- Configure rclone with your onedrive account
- Place the config file here: /root/.config/rclone/rclone.conf
- Edit /etc/vzdump.conf and change the script path to the path of the script
- Make a backup and check if it works (LXC containers are not supported for now)

## How to restore ?
For now you have to download it manually and restore it with the right command.
Later I will also implement the "rehydrate" like the other script does.