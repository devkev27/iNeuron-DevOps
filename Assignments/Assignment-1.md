### Basic Linux Commands Assignment

1. #### Connect and disconnect with login access
	* What happens when you login a non-existent user
```bash
$ su john
su: user john does not exist
```
The terminal lets you know that user does not exist. You can only login with a user account that has been created.

2. ##### Password changing
	* login into your account and then change the password
		- change your password into ``IneuR0n#42`` and hit enter
		- Try changing the password again to ``1234``
		- Try again without changing the password but just hitting enter
``
``passwd: all authentication tokens updated successfully``
password has succesfully changed
``
``BAD PASSWORD: The password is shorter than 8 characters``
The password 1234 will not be accepted as the characters are not long enough

``BAD PASSWORD: No password supplied
The terminal lets you know that you did not enter any password

3. #### Working with Directories
	* Enter the command ``cd / ``and then enter ``ls``
		* Explain the output
	* Now enter the command ``cd /home``
		* Enter ls and explain what ``/home`` directory is used for
	* Enter ``cd ..``
		* Explain what happened
	* Now enter ``cd /var/www/html`` and then enter ``cd``
		* Explain what has happened
	* Now enter ``cd /root``
		* Enter ``ls`` and check what output we have on the screen

```bash
$ cd /
$ ls
bin dev home lib64 mnt proc run srv tmp var
boot etc lib media opt root sbin sys usr 
```
cd / takes us to the root directory of the current drive, ls shows us all the directories visible

```bash
$ cd /home
$ ls
kev
``` 

/home directory is the file system directory where all the files for users of the operating system are stored

``cd ..`` takes use back to the previous directory

``$ cd /var/www/html: No such file or directory``
I realised a web server was required such as Apache, therefore I installed PHP which installed Apache server itself

```bash
$ cd /var/www/html
$ ls
index.html
$ cd
~
```

After installation and changing directory into ``/var/www/html`` we can see inside there is an index.html file. Entering cd from here takes us back to our system home directory

```bash
$ sudo su
$ cd /root
$ ls
anaconda-ks.cfg initial-setup-ks.cfg
```

Root access is required to access the root directory, so I entered sudo su first. ls shows the kickstarter files in the home directory of the root users

4. #### Working with File Listing
	* Go to ``cd /etc`` and enter ``ls``
		* Explain the difference in output compared to the previous command
	* Enter ``ls -al``
		* Now see what different output it shows
	* Enter ls --help and see all the other options for ``ls`` commands

```bash
$ cd /etc
$ ls
afpovertcp.cfg			        localtime			        racoon
aliases					locate.rc				rc.common
aliases.db				mail.rc					rc.netboot
apache2					man.conf				resolv.conf
asl					manpaths				rmtab
asl.conf				manpaths.d				rpc
auto_home				master.passwd			        rtadvd.conf
auto_master				networks				security
autofs.conf				newsyslog.conf			        services
bashrc					newsyslog.d				shells
bashrc_Apple_Terminal	                nfs.conf				snmp
com.apple.launchd		        notify.conf				ssh
csh.cshrc				ntp.conf				ssl
csh.login				ntp_opendirectory.conf	                sudo_lecture
csh.logout				openldap				sudoers
cups					pam.d					sudoers.d
defaults				passwd					symantec
emond.d					paths					syslog.conf
find.codes				paths.d					ttys
ftpusers				periodic				uucp
gettytab				pf.anchors				wfs
group					pf.conf					xtab
hosts					pf.os					zprofile
hosts.equiv				postfix					zshrc
irbrc					ppp					zshrc_Apple_Terminal
kern_loader.conf		        profile
krb5.keytab				protocols
```

The etc folder contains all of our system configuration files in it. etc is short for etcetera which means and so on. The /etc directory now means a central location for all configuration files are located. This is like the nerve centre of your Linux/Unix machine

```bash
$ ls -al
-rw-r--r--   1 root  wheel     515 24 Aug 09:59 afpovertcp.cfg
lrwxr-xr-x   1 root  wheel      15 24 Aug 09:59 aliases -> postfix/aliases
-rw-r-----   1 root  wheel   16384 24 Aug 09:59 aliases.db
drwxr-xr-x   9 root  wheel     288 24 Aug 09:59 apache2
```
``ls -al`` gives us extra information about all the files in the directory such as permissions, owner, group, size in bites, modification time as well as the file name at the end

```bash
$ ls -i
34903729 aliases				34903647 openldap
34903384 aliases.db				34903461 pam.d
34903506 apache2				34903764 passwd
34903404 asl					34903444 paths
34903592 asl.conf				34903403 paths.d
```

``ls -i`` shows us all the files along with their inode number. Inode is the index node that indetifies a specific file

``ls --help`` gives us a list information about all the other ways ls can be used which we can play around with

5. #### Know where you are and where you are working
Here we use **pwd, cd** and **ls** to understand where you are working on the terminal how you can switch from one directory to another one.

* Open terminal after restarting Linux
	* Check which location you are working, enter ``pwd``
* Now enter ``cd /var``
	* check ``ls`` and see what outcome we get
* Explore other help options of each command to learn what else we can do with these commands

```bash
$ pwd
/home/kev
```

This shows our present working directory, upon the start of the terminal I am inside the directory of my user files

```bash
$ cd /var
backups
cache
lib
local
lock -> /run/lock
log
mail
opt
run -> /run
spool
tmp
www
```

``/var`` directory contains files to which the system writes data during the course of its operation



