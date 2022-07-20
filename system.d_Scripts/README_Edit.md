# Instructions are currently not reflective of the mounting script that's on the repo. Please consult the instructions inside the file for the meantime while I get around to fixing it here. Only revelant part is Unraid User Requirements section.

# rclone Mount & Upload Scripts for Plex Users/Others using Unraid and System.d 

Collection of scripts to create rclone google mounts to allow fast launch times with Plex (or Emby).
Or just for having a way to automate a backup for folders.   

The main thread for more support: https://forums.unraid.net/topic/75436-guide-how-to-use-rclone-to-mount-cloud-drives-and-play-files/.

## Unraid Users Requirements:

- Unraid Rclone Plugin
    - 1.5.1 or higher needed [https://forums.unraid.net/topic/51633-plugin-rclone/](Details)
    - Installs rclone and allows the creation of remotes and mounts
- Optional: Unraid CA User Scripts Plugin
    - Best way to run scripts [https://forums.unraid.net/topic/48286-plugin-ca-user-scripts/](Details)
    - Optional: Create Service Accounts. [https://github.com/xyou365/AutoRclone](Follow step 1-4. Highly recommend using groups if you have a gsuite)

## For non-Unraid Users

### The following configuration has been tested on Debian 11 running swizzing. 

### Important info:

This will auto mount the rclone VFS mount and mergerFS folder to `$UserHomeFolder/cloud/`
`~/cloud/cache` is your local folder structure and where pending uploads are stashed
`~/cloud/gdrive` is your rclone VFS mount location

### Requirements:

- MergerFS
- rclone (latest is recommended)

### Steps:

1. Copy service files to `/etc/systemd/system/`
2. Modify `%RcloneRemoteMount` with you desired remote rclone location. (e.g. googledrive:/optionalfolder/)
3. Run `systemctl daemon-reload` 