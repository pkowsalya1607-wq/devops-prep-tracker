# Comprehensive Linux Commands for DevOps

## File & Directory
- **`ls`**: List directory contents.
  - Example: `ls -l` to show detailed listings.

- **`cd`**: Change directory.
  - Example: `cd /path/to/directory`.

- **`mkdir`**: Create a new directory.
  - Example: `mkdir new_directory`.

- **`rmdir`**: Remove an empty directory.
  - Example: `rmdir old_directory`.

## File Operations
- **`touch`**: Create an empty file.
  - Example: `touch filename.txt`.

- **`cp`**: Copy files or directories.
  - Example: `cp source.txt destination.txt`.

- **`mv`**: Move or rename files or directories.
  - Example: `mv oldname.txt newname.txt`.

- **`rm`**: Remove files or directories.
  - Example: `rm file.txt`.

## Users & Permissions
- **`chmod`**: Change file permissions.
  - Example: `chmod 755 script.sh`.

- **`chown`**: Change file owner.
  - Example: `chown user:group file.txt`.

- **`useradd`**: Create a new user.
  - Example: `useradd newuser`.

- **`passwd`**: Change user password.
  - Example: `passwd username`.

## Process Management
- **`ps`**: Report a snapshot of current processes.
  - Example: `ps aux` for all processes.

- **`top`**: Display dynamic real-time view of running processes.

- **`kill`**: Terminate processes by ID.
  - Example: `kill 1234`.

- **`bg`**: Continue a suspended job in the background.

## Networking
- **`ping`**: Send ICMP ECHO_REQUEST to network hosts.
  - Example: `ping google.com`.

- **`curl`**: Transfer data from or to a server.
  - Example: `curl -O file.txt` to download.

- **`ifconfig`**: Configure a network interface.

- **`ssh`**: Secure shell access to remote machines.
  - Example: `ssh user@host`.

## Disk & Storage
- **`df`**: Report file system disk space usage.
  - Example: `df -h` for human-readable output.

- **`du`**: Estimate file space usage.
  - Example: `du -sh directory/` for summary.

- **`mount`**: Mount a filesystem.

- **`umount`**: Unmount a filesystem.

## System Monitoring
- **`free`**: Display amount of free and used memory in the system.
  - Example: `free -m` for MB.

- **`uptime`**: Tell how long the system has been running.

- **`vmstat`**: Report virtual memory statistics.

## Logs
- **`tail`**: Output the last part of files.
  - Example: `tail -f /var/log/syslog` to follow log updates.

- **`grep`**: Search for patterns in files.
  - Example: `grep "error" /var/log/syslog` to find errors.

## Scheduling
- **`cron`**: Schedule commands to run at intervals.
  - Example: `crontab -e` to edit crontab.

- **`at`**: Schedule a one-time command.
  - Example: `at 09:00 tomorrow` to run a command at 9 AM next day.