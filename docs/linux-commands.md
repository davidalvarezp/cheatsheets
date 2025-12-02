<link rel="stylesheet" href="_style.css">

# Linux Commands Cheatsheet

## Index
- [Keyboard Shortcuts](#keyboard-shortcuts)
- [Users and Groups](#users-and-groups)
- [Searching](#searching)
- [SSH Login & Remote Access](#ssh-login--remote-access)
- [Directory Navigation](#directory-navigation)
- [Files](#files)
  - [Listing](#listing)
  - [File Operations](#file-operations)
  - [File Viewing / Editing](#file-viewing--editing)
  - [File Permissions](#file-permissions)
  - [File Compression](#file-compression)
  - [File Transfer](#file-transfer)
- [Packages](#packages)
  - [Debian / Ubuntu](#debian--ubuntu)
  - [RedHat / CentOS / Fedora](#redhat--centos--fedora)
  - [Universal](#universal)
- [Processes](#processes)
- [Network](#network)
- [Hardware Information](#hardware-information)
- [Disk Usage](#disk-usage)
- [Shell Commands & Variables](#shell-commands--variables)

---

## Keyboard Shortcuts

| Shortcut | Description |
|----------|-------------|
| **Ctrl + C** | Terminate running process. |
| **Ctrl + Z** | Suspend process (resume: `fg`, `bg`). |
| **Ctrl + W** | Delete previous word. |
| **Ctrl + U** | Delete from cursor to start of line. |
| **Ctrl + K** | Delete from cursor to end of line. |
| **Ctrl + Y** | Paste last removed text. |
| **Ctrl + R** | Search command history. |
| **Ctrl + O** | Execute displayed history command. |
| **Ctrl + G** | Cancel history search. |
| **!!** | Repeat last command. |
| **clear** | Clear terminal output. |
| **exit** | Exit current session. |

---

## Users and Groups

| Command | Description |
|---------|-------------|
| `who`, `w` | Show logged-in users. |
| `finger [user]` | Show user details. |
| `sudo adduser [user]` | Create user (interactive). |
| `sudo useradd [user]` | Create user (manual). |
| `sudo userdel [user]` | Delete user. |
| `sudo usermod -aG [group] [user]` | Add user to group. |
| `passwd`, `sudo passwd [user]` | Change password. |
| `sudo groupadd [group]` | Create group. |
| `sudo groupdel [group]` | Delete group. |
| `sudo groupmod -n [new] [old]` | Rename group. |
| `sudo [command]` | Run with elevated privileges. |

---

## Searching

| Command | Description |
|---------|-------------|
| `find [path] -name [pattern]` | Search files by name. |
| `find [path] -size +100M` | Search files by size. |
| `grep [pattern] [file]` | Search inside file. |
| `grep -r [pattern] [dir]` | Recursive search. |
| `locate [name]` | Search by filename index. |
| `whereis [command]` | Show binary, source and manpath. |
| `which [command]` | Show executable path. |
| `awk '/pattern/ {print}' [file]` | Print matching lines. |
| `sed 's/old/new/' [file]` | Replace text. |
| `chgrp [group] [file]` | Change group owner. |

---

## SSH Login & Remote Access

| Command | Description |
|---------|-------------|
| `ssh [user]@[host]` | SSH login. |
| `ssh -p [port] [user]@[host]` | SSH via custom port. |
| `ssh-keygen` | Generate SSH key pair. |
| `sudo systemctl start sshd` | Start SSH service. |
| `scp [file] [user]@[host]:[dest]` | Secure file copy. |
| `sftp [user]@[host]` | SFTP session. |
| `telnet [host]` | Telnet connection. |

---

## Directory Navigation

| Command | Description |
|---------|-------------|
| `pwd` | Show current directory. |
| `cd`, `cd ~` | Go to home directory. |
| `cd ..` | Up one directory. |
| `cd -` | Previous directory. |
| `cd [path]` | Change directory. |
| `dirs` | Directory stack. |

---

## Files

### Listing

| Command | Description |
|---------|-------------|
| `ls` | List files. |
| `ls -a` | Include hidden files. |
| `ls -l` | Long format listing. |

### File Operations

| Command | Description |
|---------|-------------|
| `mkdir [dir]` | Create directory. |
| `touch [file]` | Create empty file. |
| `rm [file]` | Delete file. |
| `rm -r [dir]` | Recursive delete. |
| `rm -rf [dir]` | Force delete. |
| `cp [src] [dest]` | Copy file. |
| `cp -r [src] [dest]` | Copy directory. |
| `mv [src] [dest]` | Move/rename. |
| `ln -s [path] [link]` | Create symbolic link. |

### File Viewing / Editing

| Command | Description |
|---------|-------------|
| `cat [file]` | Print file. |
| `head [file]` | First lines. |
| `tail [file]` | Last lines. |
| `less` / `more` | Paginated view. |
| `nano`, `vim` | CLI editors. |
| `gpg -c [file]` | Encrypt. |
| `gpg [file].gpg` | Decrypt. |
| `wc [file]` | Count words/lines/bytes. |

### File Permissions

| Command | Description |
|---------|-------------|
| `chmod [mode] [file]` | Change permissions. |
| `chown [user] [file]` | Change owner. |
| `chown [user]:[group] [file]` | Change owner/group. |

---

## File Compression

| Command | Description |
|---------|-------------|
| `tar cf [archive.tar] [dir]` | Create .tar. |
| `tar xf [archive.tar]` | Extract .tar. |
| `tar czf [archive.tar.gz] [dir]` | Create .tar.gz. |
| `gzip`, `gunzip` | Compress/decompress gzip. |
| `bzip2`, `bunzip2` | Compress/decompress bzip2. |
| `shred -u [file]` | Secure delete. |

---

## File Transfer

| Command | Description |
|---------|-------------|
| `scp [src] [user]@[host]:[dest]` | Secure copy. |
| `rsync -a [src] [host:dest]` | Sync directories. |
| `wget [url]` | Download via HTTP/FTP. |
| `curl -O [url]` | Download with curl. |
| `ftp [host]` | FTP client. |
| `sftp [user]@[host]` | Secure FTP. |

---

## Packages

### Debian / Ubuntu

| Command | Description |
|---------|-------------|
| `sudo apt install [pkg]` | Install package. |
| `apt search [term]` | Search package. |
| `apt list` | List packages. |
| `apt show [pkg]` | Package info. |
| `sudo dpkg -i [file.deb]` | Install .deb. |
| `dpkg -l` | List dpkg packages. |

### RedHat / CentOS / Fedora

| Command | Description |
|---------|-------------|
| `sudo yum install [pkg]` | Install via YUM. |
| `yum search [term]` | Search YUM repo. |
| `yum list installed` | Installed packages. |
| `sudo dnf install [pkg]` | Install via DNF. |
| `sudo rpm -i [file.rpm]` | Install .rpm file. |

### Universal

| Command | Description |
|---------|-------------|
| `tar zxvf [file.tar.gz]` | Extract compressed source. |
| `./configure && make && make install` | Compile and install. |
| `snap install [pkg]` | Install Snap. |
| `flatpak install [pkg]` | Install Flatpak. |

---

## Processes

| Command | Description |
|---------|-------------|
| `top`, `htop` | Process monitor. |
| `pidof [name]` | Show PID. |
| `kill [pid]`, `pkill [name]` | Kill process. |
| `killall [name]` | Kill multiple processes. |
| `bg`, `fg` | Manage jobs. |
| `lsof` | List open files. |
| `dmesg` | Kernel/boot messages. |
| `whoami` | Current user. |
| `last`, `last reboot` | Login and reboot logs. |
| `hostname`, `hostname -i` | Hostname and IP. |
| `nohup [cmd] &` | Run detached. |

---

## Network

| Command | Description |
|---------|-------------|
| `ip addr show` | Show IP interfaces. |
| `ip address add [IP]` | Assign IP. |
| `ifconfig` | Show IP config. |
| `netstat -tuln` | Listening ports. |
| `netstat -pnltu` | Ports with processes. |
| `whois [domain]` | Domain info. |
| `dig [domain]`, `dig -x [IP]` | DNS lookup / reverse. |
| `host [domain]` | Host lookup. |
| `nslookup [domain]` | DNS query. |

---

## Hardware Information

| Command | Description |
|---------|-------------|
| `lscpu` | CPU info. |
| `lsblk` | Block devices. |
| `lsusb -tv` | USB tree. |
| `lshw` | Hardware details. |
| `/proc/cpuinfo`, `/proc/meminfo` | System hardware files. |
| `sudo dmidecode` | BIOS/firmware info. |
| `hdparm -i /dev/[disk]` | Disk info. |
| `hdparm -tT /dev/[disk]` | Disk performance test. |
| `badblocks -s /dev/[disk]` | Detect bad blocks. |
| `lspci -tv` | PCI devices. |

---

## Disk Usage

| Command | Description |
|---------|-------------|
| `du -ah` | Disk usage (all files). |
| `du -sh` | Summary of directory. |
| `df -h` | Disk space usage. |
| `df -i` | Inode usage. |
| `findmnt` | Mounted filesystems. |
| `fdisk -l` | Partition list. |
| `mount [device] [path]` | Mount partition. |

---

## Shell Commands & Variables

| Command | Description |
|---------|-------------|
| `alias name='cmd'` | Create alias. |
| `watch -n [sec] [cmd]` | Repeat command. |
| `sleep [time] && cmd` | Delay execution. |
| `at [hh:mm]` | Schedule a task. |
| `man [cmd]` | Manual pages. |
| `history` | Command history. |
| `export VAR=value` | Export environment variable. |
| `unset VAR` | Remove variable. |
| `echo $VAR` | Print variable. |
| `set`, `declare` | Manage variables. |

