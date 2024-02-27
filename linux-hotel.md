# Sources:
* https://wiki.lab.linuxhotel.de/
* https://lab.linuxhotel.de/customers
* https://www.tuxcademy.org/product/grd1/

# Special characters

* `~` - the home directory


# Standard commands

* `cd`- change directory
* `pwd`- print working directory
* `ls`- list files and directories
* `man` - show manual pages
* `history` - print shell history
* `echo` - print arguments
* `cat` - print contents of file
* `grep` - search for patterns in lines
* `sort` - sort lines in various ways
* `uniq` - remove duplicate, neighbouring lines
* `cut` - cut out fields from lines
* `wc` - count words, characters, lines
* `head` - first lines
* `tail` - last lines
* `tac` - reverse output (last line first)

## Practice

1. List all files in the current directory ordered by their creation time
2. List all files in the current directory ordered by size

# Shortcuts

* `Ctrl-D` - end of input
* `TAB` - complete files and directories
* `Ctrl-R` - search through history

# Shelltux

* `shelltux status --all` - show all exercises
* `shelltux start 8` - start exercise nr. 8
* `shelltux solve` - verify solution

Exercises: 19, 27

# The pager `less`

* `q` - quit
* `/` - searching
* `n` - next result

# Filters

## Exercises

### Uniq with stable sort

Remove duplicates from os.txt, without breaking ordering

Hints: nl, cut, sort -k, uniq -f

### Analyse a log file

1. Which IPv4 addresses tried to login with wrong passowrds?
2. How often did each IP address try to log in?
3. Make a ranking of the most blunt IP addresses

Hints: grep -E -o ... what does an IP address look like ;)?

```shell
grep "Failed password" auth.log | grep -E -o '[0-9]{1,3}\.[0-9]{1,3}\.[0-9]{1,3}\.[0-9]{1,3}' | sort | uniq
grep "Failed password" auth.log | grep -E -o '[0-9]{1,3}\.[0-9]{1,3}\.[0-9]{1,3}\.[0-9]{1,3}' | sort | uniq -c | sort -nr | head
```


## Regular expressions

Always use `grep -E`

* `.` - any single character
* `{3}` - 3 occurrences of the preceding character
* `{1,3}` - between 1 and 3 occurrences of the preceding character
* `[a-z]` - one character in te range from a to z`

# Mountpoints

* `umount /media/something` - remove mountpoint at `/media/something`
* `mount /dev/sdb /mnt/usbstick` - make fielsystem on `/dev/sdb` available in `/mnt/usbstick`

## Exercise

1. Create two directories `/mnt/usbstick1` and `/mnt/usbstick2`
2. Mount the USB drive in `/mnt/usbstick1`. Create a file on it using `touch`.
3. Unmount the USB drive, inspect the direcotry?
4. Mount the USB drive in `/mnt/usbstick2`.
5. Inspect the directory
6. Unmount the drive again.
7. Create two files in `/mnt/usbstick1` and `/mnt/usbstick2` **without the drive being mounted**.
8. Mount the drive in `/mnt/usbstick1`. Inspect the directory, unmount the drive, inspect again.
9. Mount the drive twice on `/mnt/usbstick1` **and** on `/mnt/usbstick2`. Create a file in one of the directories, inspect both directories.

# Package system

Tool: apt (Advanced Package Tool)

1. How can we use `apt` to finde the name of the Chromium package?
2. How can we display information about the Chromium package?
    * What version is available?
    * What other software packages does it need?
    * How much disk space will it use?
3. How can we install the Chromium package?
    * What happens when we do?
    * Where does apt get Firefox from?
4. How can we remove the Chromium package again?

# Finding files

## By size/space

Tools: df, du

1. How much space is available below `/var`?
2. How big is each direct subdirectory of `/usr`
3. What are 5 biggest directories below `/var`?

## By any criteria

Tool: find

1. All files below `/usr` that are bigger than 1 MiB
2. All PNG files below `/usr` that are bigger than 512 KiB
3. All executable programs below `/usr`
4. All files in `/home` that were changed today
5. All PNG **and** JPG files in `/usr` bigger than 512 KiB

# Processes

* `ps aux` - list processes with all information
* `kill 1234` - send TERM signal to process 1234
* `kill -9 1234` - send KILL signal to process 1234

## Services

Tool: systemctl

1. How to stop the nginx webserver?
2. How to start the nginx webserver?
3. How to prevent nginx from being started at system boot?
4. How to make it start at system boot again?
5. How to find information on the webserver service while it is running?
6. How to find log output of the nginx service?
7. How to find all log messages of the SSH server generated today?


# Archives

Pack your home directory into an archive, and extract it to `/tmp/restore`, but **without** creating an archive file.

Hint: It's really quite easy ;)


Pack your home directory into an archive, and extract it to `/tmp/restore2` on the laptop of your partner, without creating an archive file.


# Linux distributions

*    Linux operating systems
*    Distributions and whz there are differences
*    Free software and open source

# Introduction to the Usage of Shell Bash

*     usage hints
*     important special characters and their usage
*     abbreviations and configurations
*     Configuring user locale
*     processing data streams with pipes and redirections
*     regular expressions

# Working with Files

*     common commands ( cp, mv, ... )
*     editing text files with vim
*     Linux directory structure ( /usr, /var, /home, ... )
*     Mounting file systems
*     finding files and solving disk space issues ( find, du, df, ... )
*     basic file permissions ( chmod, ... )
*     backup and restore data ( tar, rsync, ... )

# Configuring the Linux Environment

*     jobs and processes
*     find and install software packages
*     start and stop services
*     automating repeating tasks

# Accessing Resources on the Network

*     efficient usage of ssh
*     useful tools for accessing the network ( wget, ... )
# Special characters

* `~` - the home directory


# Standard commands

* `cd`- change directory
* `pwd`- print working directory
* `ls`- list files and directories
* `man` - show manual pages
* `history` - print shell history
* `echo` - print arguments
* `cat` - print contents of file
* `grep` - search for patterns in lines
* `sort` - sort lines in various ways
* `uniq` - remove duplicate, neighbouring lines
* `cut` - cut out fields from lines
* `wc` - count words, characters, lines
* `head` - first lines
* `tail` - last lines
* `tac` - reverse output (last line first)

## Practice

1. List all files in the current directory ordered by their creation time
2. List all files in the current directory ordered by size

# Shortcuts

* `Ctrl-D` - end of input
* `TAB` - complete files and directories
* `Ctrl-R` - search through history

# Shelltux

* `shelltux status --all` - show all exercises
* `shelltux start 8` - start exercise nr. 8
* `shelltux solve` - verify solution

Exercises: 19, 27

# The pager `less`

* `q` - quit
* `/` - searching
* `n` - next result

# Filters

## Exercises

### Uniq with stable sort

Remove duplicates from os.txt, without breaking ordering

Hints: nl, cut, sort -k, uniq -f

### Analyse a log file

1. Which IPv4 addresses tried to login with wrong passowrds?
2. How often did each IP address try to log in?
3. Make a ranking of the most blunt IP addresses

Hints: grep -E -o ... what does an IP address look like ;)?

```shell
grep "Failed password" auth.log | grep -E -o '[0-9]{1,3}\.[0-9]{1,3}\.[0-9]{1,3}\.[0-9]{1,3}' | sort | uniq
grep "Failed password" auth.log | grep -E -o '[0-9]{1,3}\.[0-9]{1,3}\.[0-9]{1,3}\.[0-9]{1,3}' | sort | uniq -c | sort -nr | head
```


## Regular expressions

Always use `grep -E`

* `.` - any single character
* `{3}` - 3 occurrences of the preceding character
* `{1,3}` - between 1 and 3 occurrences of the preceding character
* `[a-z]` - one character in te range from a to z`

# Mountpoints

* `umount /media/something` - remove mountpoint at `/media/something`
* `mount /dev/sdb /mnt/usbstick` - make fielsystem on `/dev/sdb` available in `/mnt/usbstick`

## Exercise

1. Create two directories `/mnt/usbstick1` and `/mnt/usbstick2`
2. Mount the USB drive in `/mnt/usbstick1`. Create a file on it using `touch`.
3. Unmount the USB drive, inspect the direcotry?
4. Mount the USB drive in `/mnt/usbstick2`.
5. Inspect the directory
6. Unmount the drive again.
7. Create two files in `/mnt/usbstick1` and `/mnt/usbstick2` **without the drive being mounted**.
8. Mount the drive in `/mnt/usbstick1`. Inspect the directory, unmount the drive, inspect again.
9. Mount the drive twice on `/mnt/usbstick1` **and** on `/mnt/usbstick2`. Create a file in one of the directories, inspect both directories.

# Package system

Tool: apt (Advanced Package Tool)

1. How can we use `apt` to finde the name of the Chromium package?
2. How can we display information about the Chromium package?
    * What version is available?
    * What other software packages does it need?
    * How much disk space will it use?
3. How can we install the Chromium package?
    * What happens when we do?
    * Where does apt get Firefox from?
4. How can we remove the Chromium package again?

# Finding files

## By size/space

Tools: df, du

1. How much space is available below `/var`?
2. How big is each direct subdirectory of `/usr`
3. What are 5 biggest directories below `/var`?

## By any criteria

Tool: find

1. All files below `/usr` that are bigger than 1 MiB
2. All PNG files below `/usr` that are bigger than 512 KiB
3. All executable programs below `/usr`
4. All files in `/home` that were changed today
5. All PNG **and** JPG files in `/usr` bigger than 512 KiB

# Processes

* `ps aux` - list processes with all information
* `kill 1234` - send TERM signal to process 1234
* `kill -9 1234` - send KILL signal to process 1234

## Services

Tool: systemctl

1. How to stop the nginx webserver?
2. How to start the nginx webserver?
3. How to prevent nginx from being started at system boot?
4. How to make it start at system boot again?
5. How to find information on the webserver service while it is running?
6. How to find log output of the nginx service?
7. How to find all log messages of the SSH server generated today?


# Archives

Pack your home directory into an archive, and extract it to `/tmp/restore`, but **without** creating an archive file.

Hint: It's really quite easy ;)


Pack your home directory into an archive, and extract it to `/tmp/restore2` on the laptop of your partner, without creating an archive file.


# Linux distributions

*    Linux operating systems
*    Distributions and whz there are differences
*    Free software and open source

# Introduction to the Usage of Shell Bash

*     usage hints
*     important special characters and their usage
*     abbreviations and configurations
*     Configuring user locale
*     processing data streams with pipes and redirections
*     regular expressions

# Working with Files

*     common commands ( cp, mv, ... )
*     editing text files with vim
*     Linux directory structure ( /usr, /var, /home, ... )
*     Mounting file systems
*     finding files and solving disk space issues ( find, du, df, ... )
*     basic file permissions ( chmod, ... )
*     backup and restore data ( tar, rsync, ... )

# Configuring the Linux Environment

*     jobs and processes
*     find and install software packages
*     start and stop services
*     automating repeating tasks

# Accessing Resources on the Network

*     efficient usage of ssh
*     useful tools for accessing the network ( wget, ... )

# Linux Directory Structure 
https://linuxhandbook.com/linux-directory-structure/
![image](https://github.com/ikhsanhabibi/linux-ubuntu/assets/33756873/f57ec4fb-c8af-4db8-a112-4800a6992b6f)


E-Mail: nik@velocitux.com


# Special characters

* `~` - the home directory


# Standard commands

* `cd`- change directory
* `pwd`- print working directory
* `ls`- list files and directories
* `man` - show manual pages
* `history` - print shell history
* `echo` - print arguments
* `cat` - print contents of file
* `grep` - search for patterns in lines
* `sort` - sort lines in various ways
* `uniq` - remove duplicate, neighbouring lines
* `cut` - cut out fields from lines
* `wc` - count words, characters, lines
* `head` - first lines
* `tail` - last lines
* `tac` - reverse output (last line first)

## Practice

1. List all files in the current directory ordered by their creation time
2. List all files in the current directory ordered by size

# Shortcuts

* `Ctrl-D` - end of input
* `TAB` - complete files and directories
* `Ctrl-R` - search through history

# Shelltux

* `shelltux status --all` - show all exercises
* `shelltux start 8` - start exercise nr. 8
* `shelltux solve` - verify solution

Exercises: 19, 27

# The pager `less`

* `q` - quit
* `/` - searching
* `n` - next result

# Filters

## Exercises

### Uniq with stable sort

Remove duplicates from os.txt, without breaking ordering

Hints: nl, cut, sort -k, uniq -f

### Analyse a log file

1. Which IPv4 addresses tried to login with wrong passowrds?
2. How often did each IP address try to log in?
3. Make a ranking of the most blunt IP addresses

Hints: grep -E -o ... what does an IP address look like ;)?

```shell
grep "Failed password" auth.log | grep -E -o '[0-9]{1,3}\.[0-9]{1,3}\.[0-9]{1,3}\.[0-9]{1,3}' | sort | uniq
grep "Failed password" auth.log | grep -E -o '[0-9]{1,3}\.[0-9]{1,3}\.[0-9]{1,3}\.[0-9]{1,3}' | sort | uniq -c | sort -nr | head
```


## Regular expressions

Always use `grep -E`

* `.` - any single character
* `{3}` - 3 occurrences of the preceding character
* `{1,3}` - between 1 and 3 occurrences of the preceding character
* `[a-z]` - one character in te range from a to z`

# Mountpoints

* `umount /media/something` - remove mountpoint at `/media/something`
* `mount /dev/sdb /mnt/usbstick` - make fielsystem on `/dev/sdb` available in `/mnt/usbstick`

## Exercise

1. Create two directories `/mnt/usbstick1` and `/mnt/usbstick2`
2. Mount the USB drive in `/mnt/usbstick1`. Create a file on it using `touch`.
3. Unmount the USB drive, inspect the direcotry?
4. Mount the USB drive in `/mnt/usbstick2`.
5. Inspect the directory
6. Unmount the drive again.
7. Create two files in `/mnt/usbstick1` and `/mnt/usbstick2` **without the drive being mounted**.
8. Mount the drive in `/mnt/usbstick1`. Inspect the directory, unmount the drive, inspect again.
9. Mount the drive twice on `/mnt/usbstick1` **and** on `/mnt/usbstick2`. Create a file in one of the directories, inspect both directories.

# Package system

Tool: apt (Advanced Package Tool)

1. How can we use `apt` to finde the name of the Chromium package?
2. How can we display information about the Chromium package?
    * What version is available?
    * What other software packages does it need?
    * How much disk space will it use?
3. How can we install the Chromium package?
    * What happens when we do?
    * Where does apt get Firefox from?
4. How can we remove the Chromium package again?

# Finding files

## By size/space

Tools: df, du

1. How much space is available below `/var`?
2. How big is each direct subdirectory of `/usr`
3. What are 5 biggest directories below `/var`?

## By any criteria

Tool: find

1. All files below `/usr` that are bigger than 1 MiB
2. All PNG files below `/usr` that are bigger than 512 KiB
3. All executable programs below `/usr`
4. All files in `/home` that were changed today
5. All PNG **and** JPG files in `/usr` bigger than 512 KiB

# Processes

* `ps aux` - list processes with all information
* `kill 1234` - send TERM signal to process 1234
* `kill -9 1234` - send KILL signal to process 1234

## Services

Tool: systemctl

1. How to stop the nginx webserver?
2. How to start the nginx webserver?
3. How to prevent nginx from being started at system boot?
4. How to make it start at system boot again?
5. How to find information on the webserver service while it is running?
6. How to find log output of the nginx service?
7. How to find all log messages of the SSH server generated today?


# Archives

Pack your home directory into an archive, and extract it to `/tmp/restore`, but **without** creating an archive file.

Hint: It's really quite easy ;)


Pack your home directory into an archive, and extract it to `/tmp/restore2` on the laptop of your partner, without creating an archive file.


# Linux distributions

*    Linux operating systems
*    Distributions and whz there are differences
*    Free software and open source

# Introduction to the Usage of Shell Bash

*     usage hints
*     important special characters and their usage
*     abbreviations and configurations
*     Configuring user locale
*     processing data streams with pipes and redirections
*     regular expressions

# Working with Files

*     common commands ( cp, mv, ... )
*     editing text files with vim
*     Linux directory structure ( /usr, /var, /home, ... )
*     Mounting file systems
*     finding files and solving disk space issues ( find, du, df, ... )
*     basic file permissions ( chmod, ... )
*     backup and restore data ( tar, rsync, ... )

# Configuring the Linux Environment

*     jobs and processes
*     find and install software packages
*     start and stop services
*     automating repeating tasks

# Accessing Resources on the Network

*     efficient usage of ssh
*     useful tools for accessing the network ( wget, ... )




Montag 26.03.2024

Linux
OS
Distribution
Flavour or distros https://de.wikipedia.org/wiki/Liste_von_Linux-Distributionen
Kernel
die Hauptkomponente eines Linux-Betriebssystems und die zentrale Schnittstelle zwischen der Hardware eines Computers und seinen Prozessen
Shell
benutzername@hostname das ist bash shell
other shells: zsh, bash,etc
https://phoenixnap.com/kb/linux-shells 
Unix

Linux from scratch
https://www.linuxfromscratch.org/
Open Source
Offene Quelle
https://opensource.org/
Free Software
https://fsfe.org/freesoftware/freesoftware.de.html
Use, distribute, understand, improve
Sicherheit

Stabilität

Kostenlos



Debian
The universal operating system
Ubuntu
Enterprise, for company
RedHathttps://framagit.org/feinstaub/shelltux
Enterprise, cloud



Shell beenden
exit
ctrl + d


Shelltux
https://framagit.org/feinstaub/shelltux
Übungen: 9, 12, 13, 14, 16, 19, 21, 27, 28, 29
Bonus: 15, 20, 31, 34

Pipe
stdout: standard output



head
tail
wc
uniq
sort

coreutils:
dpkg -L coreutils | grep /bin


regex


log
var/log


Aufgaben:
    1. Finde alle IPv4-Adressen, von denen fehlgeschlagene Anmeldeversuche kamen 
    2. Erstelle ein Rangliste der Top-10-Angreifer. 

grep "Failed password" auth.log | grep -E -o '[0-9]{1,3}\.[0-9]{1,3}\.[0-9]{1,3}\.[0-9]{1,3}' | sort | uniq -c | sort -n | tail -n10

grep "Failed password" auth.log | grep -E -o '[0-9]{1,3}\.[0-9]{1,3}\.[0-9]{1,3}\.[0-9]{1,3}' | sort | uniq -c | sort -nr | head 

create a file from stdoutput
stdout > test.tx


Übung

 Mount Point        Use                                                 
------------------------------------------------------------------------
 /etc               device files                                        
 /usr/bin           user directories                                    
 /usr/sbin dynamic  loadable libraries                                  
 /usr/local/bin     rebootable temporary files                          
 /usr/local/sbin    temporary mount points for file systems             
 /usr/lib/modules   default directories for data from services          
 /sys               additional software packages                        
 /usr/lib           kernel modules                                      
 /opt               log files                                           
 /var               files of the bootloader                             
 /var/log           system-wide configuration files                     
 /var/tmp           temporary files                                     
 /srv               kernel and system information files                 
 /tmp               system commands added manually by the administrator 
 /home              basic commands (for all users)                      
 /root              data provided by services                           
 /media             runtime data provided by services                   
 /mnt               system commands                                     
 /proc              mount points for removable media                    
 /dev               kernel and process information                      
 /run               user directory for user root                        
 /boot              commands added manually by the system administrator


 Mount Point        Use                                                 
------------------------------------------------------------------------
 /etc               system-wide configuration files                                    
 /usr/bin           system commands                 
 /usr/sbin dynamic  system commands added manually by the administrator                          
 /usr/local/bin     basic commands (for all users)                          
 /usr/local/sbin    commands added manually by the system administrator      
 /usr/lib/modules   kernel modules     
 /sys               system-wide configuration files                    
 /usr/lib           loadable libraries                               
 /opt               additional software packages                                         
 /var               system-wide configuration files                       
 /var/log           log files                     
 /var/tmp           temporary files                                  
 /srv               data provided by services              
 /tmp               temporary mount points for file systems
 /home              user directories                  
 /root              user directory for user root                     
 /media             mount points for removable media                
 /mnt               default directories for data from services                     
 /proc              kernel and process information                 
 /dev               device files               
 /run               runtime data provided by services                    
 /boot              files of the bootloader


GRUB is also a boot manager. The boot loader is the part of GRUB that loads the kernel of the operating system into memory. 


Paket management

apt-cache search packagename
apt search packagename

apt install packagename

apt show packagename

apt remove packagename

l10n: localization → 10 words in the middle
l18n: internationalization → 18 words in the middle


Cryptography
Public vs private key

Language
locale
LC_ALL = "en_US.UTF-8"
LC_ALL=C

dpkg: low layer of apt, apt uses dpkg

list all package 
dpkg -l

check all the residual, removed package but config files exist, rc removed but configured
dpkg -l | grep ^rc


ssh
ssh root@116.203.185.116
password: tah7aeL7Ai

check debian version
lsb_release -a

apt list –upgradeable


# update to newest debian version

/etc/apt/sources.list and files under /etc/apt/sources.list.d/) to add sources for bookworm and typically to remove sources for bullseye. 

apt update

apt full-upgrade


deb http://deb.debian.org/debian bookworm main contrib non-free
# deb-src http://deb.debian.org/debian bullseye main contrib non-free

deb http://deb.debian.org/debian bookworm-updates main contrib non-free
# deb-src http://deb.debian.org/debian bullseye-updates main contrib non-free

# deb http://deb.debian.org/debian bullseye-backports main contrib non-free
# deb-src http://deb.debian.org/debian bullseye-backports main contrib non-free

deb http://security.debian.org/debian-security bookworm-security main contrib non-free
# deb-src http://security.debian.org/debian-security bullseye-security main contrib non-free



Storage

local: floppy disk or floppy diskette /dev/fd0
HDD, SSD /nvm/sda
NVM /dev/nvme
USB

Network storage: File sharing, SMB, AFP, NFS

list all the storages
ls /dev/sd*

details about the storage (only as a root)
fdisk -l

swapoff
free -m
swapoff /dev/sda4

partition
fdisk -l

list partition
p

delete
d

new partition
n

write
w

check block devices
lsblk

mount disk
mount /dev/sda4 /mnt/a
mount /dev/sda4 /mnt/b

unmount
umount /dev/sda4 /mnt/a
umount /dev/sda4 /mnt/b

convert and copy file
dd

mount image
mount img.disk /mnt

if both folders (a b) are monted, the files will be override


Logical Volume Manager (LVM)

vgs — Display information about volume groups
lvs — Display information about logical volumes

## LVM

### Physical Volume als Partition

Partitionstyp auf LVM setzen:

```plain
Command (m for help): t
Partition number (1-5, default 5): 5
Partition type or alias (type L to list all): 43

Changed type of partition 'Linux filesystem' to 'Linux LVM'.
```

### VG mit erstem LV erstellen

```plain
pvcreate /dev/sda5
vgcreate vg-data /dev/sda5
lvcreate -n movies -L 4g vg-data
```

format
```
mkfs.ext4 /dev/vg-data/movies
```

### LV vergrößern

Aufgabe: Vergrößert das LV movies so, dass es die gesamte VG einnimmt.

Tipp: lv-TAB

Ziel: `dd if=/dev/zero of="Toy Story.mp4" bs=1M count=4700` soll funktionieren

```plain
lvresize -l +100%FREE /dev/vg-data/movies
resize2fs /dev/vg-data/movies
```

Oder: Dateisystem direkt mit resizen

```plain
lvresize -l +100%FREE -r /dev/vg-data/movies
```

### VG erweitern mit weiterer Partition

Aufgabe: Fügt der VG ein weiteres PV hinzu und vergrößert dann das LV auf 15g.

Tipp: fdisk, pvcreate, vgextend, lvextend

