
ssh ikhsan@notebook36


how process can communicate? signale, pipes, ipc, shared memory

## Wednesday, 28.02.2024 


- print out the password file ```cat passwd | column -s: -t```

- Understanding /etc/passwd File Format: https://www.cyberciti.biz/faq/understanding-etcpasswd-file-format/

```
username    pass    User ID (UID)   group ID      extra info        home dir            shell
nutzer31    x       1000            1000          nutzer31,,,       /home/nutzer31     /bin/bash
```

- print out the group file ```cat group | column -t -s:```

- print out the shadow file (password) ```cat shadow | column -t -s:```

- Understanding /etc/shadow file format on Linux: https://www.cyberciti.biz/faq/understanding-etcshadow-file/

- How to create user: https://www.geeksforgeeks.org/useradd-command-in-linux-with-examples/

```useradd -c "Dominik George"-d /home/nik -m -s /bin/bash -U nik/```

- Delete user ``` userdel -r nik ```
- Change user  ```  usermod -s /bin/zsh nik ```

Tools: ```/usr/sbin/group*```
```
groupadd groupdel groupmod
```

```
nik                  x  1001   1002   Dominik George                      /home/nik                  /bin/bash
ikhsan               x  1002   1008   Ikhsan Habibi                       /home/ikhsan               /bin/bash
irvin                x  1003   1009   Irvin Lopez                         /home/irvin                /bin/bash
martin               x  1004   1010   Martin Schlierf                     /home/martin               /bin/bash
florian              x  1005   1011   Florian Hönig                       /home/florian              /bin/bash
frank                x  1006   1012   Frank Pioch                         /home/frank                /bin/bash

nik                  x  1002   
finance              x  1003   ikhsan
it                   x  1004   irvin,frank,nik
gf                   x  1005   martin,florian
betriebsbar          x  1006   martin,nik
hr                   x  1007   frank
ikhsan               x  1008   
irvin                x  1009   
martin               x  1010   
florian              x  1011   
frank                x  1012 

```

Every possible UNIX/Linux file permission: https://www.unixmantra.com/2013/04/unix-linux-file-permissions.html


### Process
htop, pcp-htop - interactive process viewer

```
PID     Process ID
USER    Owner of the process
PRI     Priority
N       Niceness
S       Status
```

```
Running or Runnable (R)
Uninterruptible Sleep (D)
Interruptable Sleep (S)
Stopped (T)
Zombie (Z)
```
```
CPU     Percetage of CPU
VIRT    Virtual Memory
RES     Residual Memory
SHR     Shared Memory
```

ps - report a snapshot of the current processes.


jobs
ctrl + z

bg - background

gzip < /dev/zero > /dev/zero

gzip < /dev/zero > /dev/zero &


built in command: help command, help fg, help bg

type

zstd more cpu capacity

kill -l
sigterrm
sigkill
sigstop - ctrl + z
sigint - interrupt - ctrl + c
sigcont - continue

daemon


killall

pkill -x exact command

pgrep -l process_name

pgrep, pkill, pidwait - look up, signal, or wait for processes based on name and other attributes

pstree  - display a tree of processes

threads

lsof - list open file

File types: https://www.bogotobogo.com/Linux/linux_File_Types.php
```
- file
d directory
c character device file
b block
l systemlink
p normal pipe
s socket

```

find - search for files in a directory hierarchy

find / /run/ -xdev -type p -ls 2>/dev/null
find / /run/ -xdev -type s -ls 2>/dev/null

how process can communicate? signale, pipes, ipc, shared memory

https://wiki.lab.linuxhotel.de/doku.php/admin_grundlagen:bootloader

uefi - shim - bootloader - kernel -init - dienst

hostnamectl
timedatectl
systemctl

daemon
services
process

https://help.interfaceware.com/v6/differences-between-processes-daemons-and-services

## Thursday, 29.02.2024 


linus distro
debian 5 years LTS
red hat 10 years LTS

dpkg -s debian_package - description
dpkg -s udisks2

dpkg -L udisks2 | grep /man - documentation
dpkg -L udisks2 | grep /doc - documentation
dpkg -L udisks2 | grep /bin
dpkg -L udisks2 | grep /etc - configuration


usr is static
/usr/bin - there are programms
find / -xdev -type d -writable -prune -ls 2> /dev/null
service: /var, /home, /usr

fhs: https://de.wikipedia.org/wiki/Filesystem_Hierarchy_Standard

administer /etc/group and /etc/gshadow
gpasswd -a nutzer gruppe 

less /etc/passwd
less /etc/shadow
less /etc/group

SUID - Set user id
-rwsr-xr-x 1 root root 68248 Mar 23  2023 /usr/bin/passwd

print suid file - everyone can read and execute
find / -xdev -type f -user root -perm /u+s -ls

if it is not necessary, the remove the suid right

man dpkg-statoverride  - the suid file will be override even after updates

cockpit - Cockpit is a web accessible interactive admin interface for Linux machines. 
apt show cockpit
apt install cockpit

check whether it is installed
dpkg -s cockpit

systemctl status cockpit
systemctl cat cockpit
systemctl list-dependencies

systemd: https://wiki.lab.linuxhotel.de/doku.php/admin_grundlagen:systemd

fstrim - discard unused blocks on a mounted filesystem
fstrim -av


Hardware

lsusb - list USB devices
lspci - list all PCI devices

modinfo - Show information about a Linux Kernel module
modinfo bluetooth

lsmod - Show the status of modules in the Linux Kernel
modinfo - Show information about a Linux Kernel module
dmseg - print or control the kernel ring buffer
modprobe - Add and remove modules from the Linux Kernel

put the usb stick
udevadm monitor

diff lsmod.vorher lsmod.nachher


linux news: https://lwn.net/


network: https://wiki.lab.linuxhotel.de/doku.php/admin_grundlagen:udev
apt install ethtool

ethtool -i network_id


udev - udev supplies the system software with device events, manages permissions of device nodes and may create additional symlinks in the /dev/ directory, or renames network interfaces.

udevadm - udevadm expects a command and command specific options. It controls the runtime behavior of systemd-udevd, requests kernel events, manages the event queue, and provides simple debugging mechanisms.

ip link - show / manipulate routing, network devices, interfaces and tunnels



1. Betriebsystem
device
dirver
network card

ip link
lsmod
ethtool

2. Ethernet,Wifi, PPP -> host to host
paket
switch
mac addresse

3. IP -> host to host
ip address
subnetz
router

4. TC, UDP -> process to process
port

lsof nPi
nc


5. dns,http, ssh

submask
192.168.y.x/24
172.16-31.x.x/16
10.x.x.x/8


ip address del 192.168.1.231/24 dev enp1s0f1
ip address add 192.168.73.31/24 dev enp1s0f1


watch -d ip neigbour

wireshark

lsof -nPi - TCP UDP

network: https://wiki.lab.linuxhotel.de/doku.php/admin_grundlagen:netzwerk#dokuwiki__top


nmcli c
ip address show dev enp1s0f1
nmcli c up 0b4208d4-f0b9-430d-8778-87f48e5ec03e
nmcli c down 0b4208d4-f0b9-430d-8778-87f48e5ec03e

nmcli c edit 0b4208d4-f0b9-430d-8778-87f48e5ec03e
set 802-3-ethernet.mtu 1480
save persistent
activate


interface
nmtui

nano /etc/NetworkManager/system-connections/linuxhotel.nmconnection

journalctl -e
journalctl -f
journalctl -eu ssh.service


apt-cache show package_name
apt-cache list package_name

journalctl --list-boots
https://wiki.lab.linuxhotel.de/doku.php/admin_grundlagen:journald

## Friday, 01.03.2024 

sudo -i

webserver apache2: https://wiki.lab.linuxhotel.de/doku.php/lpi2:apache

docker
https://wiki.lab.linuxhotel.de/doku.php/admin_grundlagen:docker

enter into docker container
docker exec -it container_id /bin/bash

docker run -it container_name bash

docker- anwendungcontainer
systemd-nspawn - betriebstystem container
lxc - betriebstystem container

flatpak
https://wiki.lab.linuxhotel.de/doku.php/admin_grundlagen:flatpak

ssh
ssh-keygen -t ed25519
ssh-copy-id user@hostename

ssh ikhsan@notebook36


agent not in root - ssh pub should be copied, and set a pasword
passwd username
ssh -A ikhsan@notebook36 - to Ingo
shh ikhsan@notebook32 - to Irvin


Jump
ssh -J ikhsan@notebook36 ikhsan@notebook32


package search
apt search packagename
apt-cache search packagename
apt show packagename

dpkg -S packagename

sshfs
sshfs ikhsan@notebook32: meine-datei/ - mount to other server

tar
instead the whole path to zip:
sudo tar -c /usr/share/ > share.tar

use this, to changeto /usr, the zip it:
sudo tar cC /usr share > share.tar

compress 
sudo tar -cC /usr/ share | gzip > share.tar

compres gz
sudo tar -cC /usr share | gzip > shre.tar.gz

compress zstd
sudo tar -cC /usr share | zstd > share.tar.zstd

du - different file size
du -sh share.tar /usr/share/

time sh -c 'sudo tar -cC /usr share | gzip share.tar.gz'
du -sh sh* /usr/share/

grant user as admin
gpasswd -a irvin admin

compress 'share folder' to server
ssh ikhsan@notebook32 'sudo tar -cC /usr share | zstd '> share.tar.zstd


extract the compressed file from local on the other server
option1 - easy
cat share.tar.zstd | ssh ikhsan@notebook32 'zstdcat | tar -x'

option2 - hard
ssh ikhsan@notebook32 'zstdcat | tar -x' < share.tar.zstd

send backup to other server
local compres -sending - decompress

sudo tar -cC /usr share | zstd | ssh ikhsan@notebook32 'cat > share.tar.zstd'

extract into other server
ssh ikhsan@notebook32 'cat share.tar.zstd | zstdcat | tar -x'

rsync
