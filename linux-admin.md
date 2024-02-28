# linux admin

### Wednesday, 28.02.2024 

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

- How to create user: https://www.geeksforgeeks.org/useradd-command-in-linux-with-examples/

```useradd -c "Dominik George"-d /home/nik -m -s /bin/bash -U nik/```

- Delete user ``` userdel -r nik ```
- Change user  ```  usermod -s /bin/zsh nik ```

Tools: ```/usr/sbin/group*```
```
groupadd
groupdel
groupmod
```
