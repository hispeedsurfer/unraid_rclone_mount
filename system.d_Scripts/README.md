# rclone Mount & Upload Scripts for Plex Users/Others using Unraid and System.d 

### The following configuration has been tested on Debian 11 running swizzing. 

### Important info:

This will auto mount the rclone VFS mount and mergerFS folder to `$UserHomeFolder/cloud/`.
`~/cloud/cache` is your local folder structure and where pending uploads are stashed.
`~/cloud/%RcloneRemoteMount` is your rclone VFS mount location
`~/cloud/MergerFS` is where your merged folder is located. It is HIGHLY recommended you read and write from this path.

### Requirements:

- MergerFS
- rclone (latest is recommended)

### Steps:

1. Copy service files to `/etc/systemd/system/`
2. Modify `%RcloneRemoteMount` with you desired remote rclone location. (e.g. googledrive:/optionalfolder/)
3. Run `systemctl daemon-reload` 
4. Enable the systemd service using `sudo systemctl enable --now mergerfs@yourusernamehere`
5. ?????
6. Profit?