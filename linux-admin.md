# linux admin

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

Tools: ```/usr/sbin/user*```


## Berechtigungen

## Traditionelle UNIX-Dateirechte

Wiki: https://wiki.lab.linuxhotel.de/doku.php/linux_grundlagen:dateirechte

## Beispiel: Arbeitsgruppenverzeichnisse

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
martin               x  1004   1010   Martin                              /home/martin               /bin/bash
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

```
for g in finance it gf hr betriebsbar; do groupadd $g; done
for g in finance it gf hr betriebsbar; do mkdir /srv/tux/$g; done
cat users | while read u g; do echo useradd -d /home/$u -m -s /bin/bash -U -G $g $u; done
for g in finance it gf hr betriebsbar; do chown nobody:$g /srv/tux/$g; done
chmod 2070 /srv/tux/*
```

Erste Aufgaben:

Tools: /usr/sbin/user*

1. Wie lege ich User an?
   Beispiel: User nik, soll sich einloggen können, mit der Shell bash, und einem Home-Verzeichnis /home/nik, und dem vollen Namen "Dominik George"

`useradd -c "Dominik George" -d /home/nik -m -s /bin/bash -U nik`
    (-d /home/nik und -U sind Defaults)

2. Wie lösche ich einen User, was muss/kann ich dabei beachten?

`userdel -r nik` (ggf. Dateien außerhalb des Homes finden)

3. Wie kann ich nachträglich die Shell eines Users ändern?

`usermod -s /bin/zsh nik`


1. Legt die einzelnen Teams als Gruppe an (kleingeschrieben, wie am Flipchart)
2. Legt für jedes Team ein Arbeitsverzeichnis an unter /srv/tux/gruppenname.
3. Legt die User an wie am Flipchart. Die User sollen jeweils in ihren Team-Gruppen sein.
4. Setzt die Rechte für die Arbeitsgruppenverzeichnisse:
    * Alle Mitglieder der entsprechenden Gruppe dürfen alles
    * Alle anderen dürfen nichts


### Erweiterung mit ACLs

5. Die Gruppe gf soll in allen Verzeichnissen lesen können

Tools: getfacl, setfacl

`setfacl -m group:gf:rx /srv/tux/*`

- ACL
setfacl - set file (access control lists)

Default-ACL wird an neue Dateien im Verzeichnis vererbt:

`setfacl -d -m user::rw,group::rw,other::-,group:gf:r *`

```plain
root@notebook36:/srv/tux# getfacl betriebsbar
# file: betriebsbar
# owner: nobody
# group: betriebsbar
# flags: -s-
user::---
group::rwx
group:gf:r-x
mask::rwx
other::---
default:user::rw-
default:group::rw-
default:group:gf:r--
default:mask::rw-
default:other::---
```

- change attribute ```chattr```

## Andere Benutzerquellen

Woher kommen Benutzer/Gruppen? -> /etc/nsswitch.conf

Alle Benutzer und Gruppen auflisten, auch aus LDAP, usw.: `getent passwd`, `getent group`
