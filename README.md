> I want to share my knowledge and hacks with world.

​	All scripts are tested on clean debian installations.

​	**All scripts must be run as root. SUDO can be incorrect.** 

###### License

All listed here free to use, edit and share. Please, link source - i want share my solutions to all.


# webmaster

​	*Writed in middle of 2017. We must keep up with the times.* 

Get script:

```shell
wget https://raw.githubusercontent.com/egeneralov/webmaster/master/install
wget https://raw.githubusercontent.com/egeneralov/webmaster/master/add-domain
wget https://raw.githubusercontent.com/egeneralov/webmaster/master/add-user
chmod +x install add-domain add-user
./webmaster
```

### Script ask 6 questions:

###### Domain

​	Enter your main domain *(like github.com)*. www alias without redirect will be added automaticaly.

###### MySQL root password

​	LEMP stack must include database (i think). **Do not keep empty.**

###### user name

​	New user will be added. Please, enter short name *(like eduard)*.

###### user full name

​	Your full name. Use for send mail from cli with your name.

###### Password for new user

​	Password for your user. It is shown to you in an open mode. **Do not keep empty!**

###### Your mail

​	Your current mailbox. Using for tesing.

### Provide automatic installation for 1 domain:

1. MTA (pam auth)
 1. Postfix
    1. 587 SSL
 2. Dovecot
    1. 25 STARTTLS
    2. 143 STARTTLS
    3. 993 SSL
2. LEMP
 1. nginx
 2. php 7
3. FTP server
   1. explict over TLS
4. MySQL
   1. clean installation

### Authorisation:

All users in system can use with his own password in system:

1.  home folder via ftp
2.  email via IMAP with SSL like user@domain.com

### Details:

​	Not all mail clients can use TLS with this stack. Sorry, i didn`t know how to support all mail clients. Tested on OS X Mail, iOS Mail, Linux Evolution.

**User home:** /sites/username

**First domain will be placed in:** /sites/firtsuser/example.com

**First user will be aliased in email for:**

​	*(if server recive mail for abuse@domain.com - message will be delivered to firstuser@domain.com)*

1. root
2. mailer-daemon
3. postmaster
4. nobody
5. hostmaster
6. usenet
7. news
8. webmaster
9. www
10. ftp
11. abuse


