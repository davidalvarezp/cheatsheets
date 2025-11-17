<link rel="stylesheet" href="style.css">

# Linux Commands Cheatsheet

- [Keyboard Shortcuts](#keyboard-shortcuts)
- [Users and Groups](#users-and-groups)
- [Searching](#shearching)
- [SSH Login & Remote Access](#ssh-login--remote-access)
- [Directory Navigation](directory-navigation)
- [Files](#files)
  - Listing
  - File Operations
  - File Viewing / Editing
  - File Permissions
- Packages
  - Debian/Ubuntu
  - Universal
- Processes
- Network
- Hardware Information
- Disk Usage
- File Compression
- File Transfer
- Shell Commands & Variables

---

## Keyboard Shortcuts

| Shortcut | Description |
|---------|-------------|
| **Ctrl + C** | Kill the process running in the terminal. |
| **Ctrl + Z** | Stop the current process (resume with `fg` or `bg`). |
| **Ctrl + W** | Cut one word before the cursor. |
| **Ctrl + U** | Cut the part of the line before the cursor. |
| **Ctrl + K** | Cut the part of the line after the cursor. |
| **Ctrl + Y** | Paste from clipboard. |
| **Ctrl + R** | Recall last command that matches provided characters. |
| **Ctrl + O** | Run the previously recalled command. |
| **Ctrl + G** | Exit command history without executing. |
| **clear** | Clear the terminal screen. |
| **!!** | Run the last command again. |
| **exit** | Log out of the current session. |

---

## Users and Groups

| Command | Description |
|---------|-------------|
| `who` | Display who is currently logged in. |
| `w` | Show logged-in users and their activity. |
| `finger [user]` | Show user information. |
| `sudo useradd [user]` | Create a new user. |
| `sudo adduser [user]` | Create a new user (guided interface). |
| `sudo userdel [user]` | Delete a user. |
| `sudo usermod -aG [group] [user]` | Add user to group. |
| `passwd` | Change own password. |
| `sudo passwd [user]` | Change another user's password. |
| `sudo groupadd [group]` | Create a new group. |
| `sudo groupdel [group]` | Delete a group. |
| `sudo groupmod -n [new] [old]` | Rename a group. |
| `sudo [command]` | Temporarily elevate privileges. |

---

## Searching

| Command | Description |
|---------|-------------|
| `find [path] -name [pattern]` | Find files matching a pattern. |
| `find [path] -size +100M` | Find files bigger than specified size. |
| `grep [pattern] [file]` | Search pattern in file. |
| `grep -r [pattern] [dir]` | Recursive search. |
| `locate [name]` | Locate all files related to a name. |
| `whereis [command]` | Find source, binary, and man page for a command. |
| `which [command]` | Search command path in `$PATH`. |
| `awk '[pattern] {print $0}' [file]` | Print lines matching pattern. |
| `sed 's/[old]/[new]/' [file]` | Replace text. |
| `chgrp [group] [file/dir]` | Change group ownership. |

---

## SSH Login & Remote Access

| Command | Description |
|---------|-------------|
| `ssh [user]@[host]` | Connect to remote host. |
| `ssh -p [port] [user]@[host]` | Connect via specified port. |
| `ssh-keygen` | Generate SSH key pair. |
| `sudo service sshd start` | Start SSH daemon. |
| `scp [file] [user]@[host]:[path]` | Secure file copy. |
| `sftp [user]@[host]` | Interactive file transfer via SFTP. |
| `telnet [host]` | Connect via Telnet (port 23). |

---

## Directory Navigation

| Command | Description |
|---------|-------------|
| `pwd` | Show current directory. |
| `cd` | Go to home directory. |
| `cd ~` | Go to home directory. |
| `cd ..` | Move up one level. |
| `cd -` | Return to previous directory. |
| `cd [path]` | Change to specified directory. |
| `dirs` | Show directory stack. |

---

## Files

### Listing

| Command | Description |
|---------|-------------|
| `ls` | List files and directories. |
| `ls -a` | List including hidden files. |
| `ls -l` | Long listing format. |

### File Operations

| Command | Description |
|---------|-------------|
| `mkdir [dir]` | Create directory. |
| `rm [file]` | Remove file. |
| `rm -r [dir]` | Remove directory recursively. |
| `rm -rf [dir]` | Remove without confirmation. |
| `cp [src] [dest]` | Copy file. |
| `cp -r [src] [dest]` | Copy directory recursively. |
| `mv [src] [dest]` | Move or rename. |
| `ln -s [path]/[file] [link]` | Create symbolic link. |
| `touch [file]` | Create empty file. |

### File Viewing / Editing

| Command | Description |
|---------|-------------|
| `cat [file]` | Show file contents. |
| `cat [src] >> [dest]` | Append contents to file. |
| `head [file]` | Show first 10 lines. |
| `tail [file]` | Show last 10 lines. |
| `more [file]` | Paginated viewing. |
| `less [file]` | Advanced paginated viewing. |
| `nano [file]` | Edit with nano. |
| `vi [file]` / `vim [file]` | Edit with Vi/Vim. |
| `gpg -c [file]` | Encrypt file. |
| `gpg [file].gpg` | Decrypt `.gpg` file. |
| `wc -w [file]` | Count words, lines, bytes. |
| `ls | xargs wc` | Count lines/words in directory files. |

---

## File Permissions

| Command | Description |
|---------|-------------|
| `chmod 777 [file]` | Full permissions (rwxrwxrwx). |
| `chmod 755 [file]` | rwxr-xr-x. |
| `chmod 766 [file]` | rwxrw-rw-. |
| `chown [user] [file]` | Change owner. |
| `chown [user]:[group] [file]` | Change owner and group. |

---

## Packages (Debian/Ubuntu)

| Command | Description |
|---------|-------------|
| `sudo apt-get install [pkg]` | Install package via apt-get. |
| `sudo apt install [pkg]` | Install package (new APT). |
| `apt search [keyword]` | Search APT repository. |
| `apt list` | List installed APT packages. |
| `apt show [pkg]` | Show package information. |
| `sudo dpkg -i [file.deb]` | Install `.deb` package. |
| `sudo dpkg -l` | List dpkg installed packages. |

---

## Packages (Red Hat, CentOS, Fedora)

| Command | Description |
|---------|-------------|
| `sudo yum install [pkg]` | Install package via YUM. |
| `yum search [keyword]` | Search YUM repository. |
| `yum list installed` | List installed YUM packages. |
| `sudo dnf install [pkg]` | Install via DNF. |
| `sudo rpm -i [file.rpm]` | Install `.rpm` file. |

---

## Packages (Universal)

| Command | Description |
|---------|-------------|
| `tar zxvf [file.tar.gz]` | Extract tar.gz file. |
| `cd [extracted_dir]` | Change to extracted directory. |
| `./configure && make && make install` | Build and install from source. |
| `sudo snap install [pkg]` | Install snap package. |
| `sudo snap find [keyword]` | Search snap store. |
| `sudo snap list` | List snap packages. |
| `flatpak install [pkg]` | Install Flatpak package. |
| `flatpak search [keyword]` | Search Flatpak packages. |
| `flatpak list` | List installed Flatpaks. |

---

## Processes

| Command | Description |
|---------|-------------|
| `top` | View running processes. |
| `htop` | Interactive process viewer. |
| `hostname` | Show system hostname. |
| `hostname -i` | Show system IP address. |
| `last` | Show last logins. |
| `last reboot` | Show reboot history. |
| `date` | Current date and time. |
| `timedatectl` | Query/change system clock. |
| `cal` | Show calendar. |
| `prgrep [keyword]` | List processes by keyword. |
| `w` | Show logged-in users. |
| `pidof [process]` | Show PID of process. |
| `whoami` | Show current user. |
| `bg` | Resume job in background. |
| `fg` | Bring job to foreground. |
| `kill [pid]` | Kill process by ID. |
| `pkill [name]` | Kill process by name. |
| `killall [name]` | Kill all matching processes. |
| `lsof` | List open files. |
| `modprobe [module]` | Add kernel module. |
| `dmesg` | Show boot messages. |
| `trap "[commands]" [signal]` | Catch shell signals. |
| `wait` | Wait for process to finish. |
| `nohup [command] &` | Run process in background. |

---

## Network

| Command | Description |
|---------|-------------|
| `ip addr show` | Show IPs and interfaces. |
| `ip address add [IP]` | Assign IP to interface. |
| `ifconfig` | Show IP addresses. |
| `netstat -tuln` | Show TCP/UDP ports. |
| `netstat -pnltu` | Show ports with programs. |
| `whois [domain]` | Query domain info. |
| `dig [domain]` | DNS lookup. |
| `dig -x [IP]` | Reverse DNS lookup. |
| `host [domain]` | IP lookup for domain. |
| `nslookup [domain]` | Domain lookup. |

---

## Hardware Information

| Command | Description |
|---------|-------------|
| `lscpu` | CPU information. |
| `lsblk` | Block devices. |
| `lsusb -tv` | USB tree. |
| `lshw` | Hardware configuration. |
| `cat /proc/cpuinfo` | CPU details. |
| `cat /proc/meminfo` | Memory info. |
| `cat /proc/mounts` | Mounted filesystems. |
| `sudo dmidecode` | BIOS hardware info. |
| `hdparm -i /dev/[dev]` | Disk information. |
| `hdparm -tT /dev/[dev]` | Disk speed test. |
| `badblocks -s /dev/[dev]` | Test unreadable blocks. |
| `pmap` | Memory usage map. |
| `lspci -tv` | PCI devices. |

---

## Disk Usage

| Command | Description |
|---------|-------------|
| `du -ah` | Disk usage (all files). |
| `du -sh` | Disk usage summary. |
| `df -h` | Free/used disk space. |
| `df -i` | Free inodes. |
| `findmnt` | Show mount points. |
| `fdisk -l` | Disk partitions. |
| `mount [device] [mount]` | Mount device. |

---

## File Compression

| Command | Description |
|---------|-------------|
| `tar cf [archive.tar] [dir]` | Create tar archive. |
| `tar xf [archive.tar]` | Extract tar archive. |
| `tar czf [archive.tar.gz]` | Create tar.gz archive. |
| `gzip [file]` | Compress file. |
| `gunzip [file.gz]` | Decompress gzip. |
| `bzip2 [file]` | Compress file (.bz2). |
| `bunzip2 [file.bz2]` | Decompress .bz2. |
| `shred -u [file]` | Overwrite then delete file. |

---

## File Transfer

| Command | Description |
|---------|-------------|
| `scp [src] [user]@[host]:[dest]` | Secure copy to remote. |
| `rsync -a [src] [user]@[host]:[dest]` | Sync directories. |
| `wget [url]` | Download file. |
| `curl -O [url]` | Download with curl. |
| `ftp [host]` | FTP transfer. |
| `sftp [user]@[host]` | Secure file transfer. |

---

## Shell Commands & Variables

| Command | Description |
|---------|-------------|
| `alias name='command'` | Create alias. |
| `watch -n [sec] [cmd]` | Run command at intervals. |
| `sleep [time] && [cmd]` | Delay command execution. |
| `at [hh:mm]` | Schedule job. |
| `man [cmd]` | Manual page. |
| `history` | Command history. |
| `let x=value` | Assign integer variable. |
| `export VAR` | Export variable. |
| `declare VAR=value` | Declare variable. |
| `set` | List all shell variables. |
| `unset VAR` | Remove variable. |
| `echo $VAR` | Print variable value. |

