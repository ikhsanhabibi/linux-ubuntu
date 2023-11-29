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
