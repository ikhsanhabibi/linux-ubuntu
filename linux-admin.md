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

Every possible UNIX/Linux file permission: https://www.unixmantra.com/2013/04/unix-linux-file-permissions.html


### Process
htop, pcp-htop - interactive process viewer

```
PID     Process ID
USER
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
