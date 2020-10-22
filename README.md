Setting-up-ubuntu-webserver
Basic Steps to setup Ubuntu LEMP Webserver. 

- - [X]  setting strong root password 

```bash
passwd root
```

- [X]  add superstrongpassword. 


- [X] update upgrade server 
```bash
apt-get update && apt-get upgrade
```


- [X] set hostname: 

```bash
$ echo "example-hostname" > /etc/hostname
$ hostname -F /etc/hostname
```


- [X] //Edit /etc/hosts to add hostnames 
```bash
$ nano /etc/hosts
```


- [X] check timezone 

```bash
$ timedatectl
```


- [X] check time 

```bash
 $ date
```


- [X] Set TimeZone 

```bash
$ dpkg-reconfigure tzdata
```



- [X] add new user 

```bash
$ adduser NewUsername
```

- [X] add superstrongpassword 


- [X] add user to sudoers 

```bash
$ adduser NewUsername sudo
```

- [X] add sshkey to webserver 


```bash
$ ssh-copy-id example_user@203.0.113.10

```


- [X] disable root login 

```bash

$ sudo nano /etc/sshd_config
--> PermitRootLogin no  
--> PasswordAuthentication no  
--> AddressFamily inet allows only ipv4 
```





- [X] restart sshd 

- [X] Setting up firewall 

```bash
$ sudo ufw default allow outgoing
Default outgoing policy changed to 'allow'
(be sure to update your rules accordingly)
```


```bash
$ sudo ufw default deny incoming
Default incoming policy changed to 'deny'
(be sure to update your rules accordingly)
```

```bash
$ sudo ufw allow ssh
Rules updated
Rules updated (v6)

$ sudo ufw allow 80/tcp
Rules updated
Rules updated (v6)

$ sudo ufw allow 443/tcp
Rules updated
Rules updated (v6)

$ sudo ufw enable
Command may disrupt existing ssh connections. Proceed with operation (y|n)? y
Firewall is active and enabled on system startup

```


```bash
$ sudo ufw status
Status: active

To                         Action      From
--                         ------      ----
22/tcp                     ALLOW       Anywhere                  
80/tcp                     ALLOW       Anywhere                  
443/tcp                    ALLOW       Anywhere                  
22/tcp (v6)                ALLOW       Anywhere (v6)             
80/tcp (v6)                ALLOW       Anywhere (v6)             
443/tcp (v6)               ALLOW       Anywhere (v6)   


```

- [X] *****settup login******* 

- [X] *****setup fail2ban***** 
