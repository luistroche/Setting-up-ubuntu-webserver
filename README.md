# Setting-up-ubuntu-webserver
Basic Steps to setup Ubuntu LEMP Webserver. 

<!-- //setting strong root password -->

#passwd root

<!-- add superstrongpassword. -->


<!-- update upgrade server -->

#apt-get update && apt-get upgrade

<!-- set hostname: -->


#echo "example-hostname" > /etc/hostname
#hostname -F /etc/hostname

<!-- //Edit /etc/hosts to add hostnames -->

#nano /etc/hosts

<!-- check timezone -->

#timedatectl

<!-- check time -->

#date

<!-- Set TimeZone -->

#dpkg-reconfigure tzdata

<!-- add new user -->

#adduser NewUsername
add superstrongpassword


<!-- add user to sudoers -->

adduser NewUsername sudo

<!-- add sshkey to webserver -->

ssh-copy-id example_user@203.0.113.10

<!-- disable root login -->

#sudo nano /etc/sshd_config

<!-- PermitRootLogin no  -->
<!-- PasswordAuthentication no  -->
<!-- AddressFamily inet allows only ipv4 -->


<!-- restart sshd -->

<!-- Setting up firewall -->

$ sudo ufw default allow outgoing
Default outgoing policy changed to 'allow'
(be sure to update your rules accordingly)

$ sudo ufw default deny incoming
Default incoming policy changed to 'deny'
(be sure to update your rules accordingly)

$ sudo ufw allow ssh
Rules updated
Rules updated (v6)

sudo ufw allow 80/tcp
Rules updated
Rules updated (v6)

sudo ufw allow 443/tcp
Rules updated
Rules updated (v6)

$ sudo ufw enable
Command may disrupt existing ssh connections. Proceed with operation (y|n)? y
Firewall is active and enabled on system startup

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

<!-- *****settup login******* -->

<!-- *****setup fail2ban***** -->
