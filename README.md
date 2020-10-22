Setting-up-ubuntu-webserver
Basic Steps to setup Ubuntu LEMP Webserver. 

#setting strong root password 

```bash
passwd root
```

# add superstrongpassword. 


# update upgrade server 
```bash
apt-get update && apt-get upgrade
```


# set hostname: 

```bash
$ echo "example-hostname" > /etc/hostname
$ hostname -F /etc/hostname
```


# //Edit /etc/hosts to add hostnames 
```bash
$ nano /etc/hosts
```


# check timezone 

```bash
$ timedatectl
```


# check time 

```bash
 $ date
```


# Set TimeZone 

```bash
$ dpkg-reconfigure tzdata
```



# add new user 

```bash
$ adduser NewUsername
```

# add superstrongpassword 


# add user to sudoers 

```bash
$ adduser NewUsername sudo
```

# add sshkey to webserver 


```bash
$ ssh-copy-id example_user@203.0.113.10

```


# disable root login 

```bash

$ sudo nano /etc/sshd_config
--> PermitRootLogin no  
--> PasswordAuthentication no  
--> AddressFamily inet allows only ipv4 
```





# restart sshd 

# Setting up firewall 

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

# *****settup login******* 

# *****setup fail2ban***** 
