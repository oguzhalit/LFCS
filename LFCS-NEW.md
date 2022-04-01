# Linux Fundamentals:
- [Module 1: Essential Commands](#module-1-essential-commands)
    - [Lesson 1: Installing Linux](#lesson-1-installing-linux)
    - [Lesson 2: Using Essential Tools](#lesson-2-using-essential-tools)
    - [Lesson 3: Using Essential File Management Tools](#lesson-3-using-essential-file-management-tools)
    - [Lesson 4: Working With Text Files](#lesson-4-working-with-text-files)
    - [Lesson 5: Connecting to a Server](#lesson-5-connecting-to-a-server)
    - [Lesson 6: Working with the Bash Shell](#lesson-6-working-with-the-bash-shell)
- [Module 2: User and Group Management and Permissions](#module-2-user-and-group-management-and-permissions)
    - [Lesson 7: User and Group Management](#lesson-7-managing-users-and-groups)
    - [Lesson 8: Permissions Management](#lesson-8-managing-linux-permissions-and-quota)
    - [Lesson 9: Storage Management Essentials](#lesson-9-storage-management-essetials)
- [Module 3:  Operating Running Systems](#module-3-operating-running-systems)
    - [Lesson 10: Managing Networking](#lesson-10-managing-users-and-groups)
    - [Lesson 11: Managing Time](#lesson-11-managing-linux-permissions-and-quota)
    - [Lesson 12: Working with Systemd](#lesson-12-storage-management-essetials)
    - [Lesson 13: Process Management](#lesson-13-managing-users-and-groups)
    - [Lesson 14: Managing Software](#lesson-14-managing-linux-permissions-and-quota)
    - [Lesson 15: Scheduling Tasks](#lesson-15-storage-management-essetials)
    - [Lesson 16: Reading Log Files](#lesson-16-managing-linux-permissions-and-quota)

# LFCS - New
Preparation for Linux Foundation Certified System Administrator

- [Module 1-1: Advanced System Administration](#module-1-1-advanced-system-administration)
    - [Lesson 1: An Introduction to Bash Shell Scripting](#lesson-1-managing-users-and-groups)
    - [Lesson 2: Managing Local Security](#lesson-2-managing-linux-permissions-and-quota)
    - [Lesson 3: Configuring Networking](#lesson-3-storage-management-essetials)
    - [Lesson 4: Managing Advanced Systemd Features](#lesson-4-managing-users-and-groups)
    - [Lesson 5: Configuring Logging](#lesson-5-managing-linux-permissions-and-quota)
    - [Lesson 6: Basic Kernel Management](#lesson-6-storage-management-essetials)
    - [Lesson 7: Managing the Boot Procedure](#lesson-7-managing-users-and-groups)
- [Module 2-2: Managing Security Features](#module-2-2-managing-security-features)
    - [Lesson 8: Configuring a Firewall](#lesson-8-managing-users-and-groups)
    - [Lesson 9: Managing SELinux and AppArmor](#lesson-9-managing-linux-permissions-and-quota)
- [Module 3-3: Storage Management](#module-3-3-storage-management)
    - [Lesson 10: Managing Partitions](#lesson-10-managing-users-and-groups)
    - [Lesson 11: Managing File Systems and Mounts](#lesson-11-managing-linux-permissions-and-quota)
    - [Lesson 12: Managing LVM](#lesson-12-storage-management-essetials)
    - [Lesson 13: Managing Software RAID](#lesson-13-managing-linux-permissions-and-quota)
    - [Lesson 14: Managing User Quota](#lesson-14-storage-management-essetials)
- [Module 4-4: Service Configuration](#module-4-4-managing-ssh-services)
    - [Lesson 15: Managing SSH Services](#lesson-15-managing-users-and-groups)
    - [Lesson 16: Managing Web Services](#lesson-16-managing-linux-permissions-and-quota)
    - [Lesson 17: Configuring FTP Services](#lesson-17-storage-management-essetials)
    - [Lesson 18: Configuring a Basic DNS Server](#lesson-18-managing-linux-permissions-and-quota)
    - [Lesson 19: Providing NFS and CIFS File Shares](#lesson-19-storage-management-essetials)
    - [Lesson 20: Configuring a Database Server](#lesson-20-managing-linux-permissions-and-quota)
    - [Lesson 21: Configuring Basic Email Handling](#lesson-21-storage-management-essetials)
    - [Lesson 22: Configuring a Web Proxy](#lesson-22-storage-management-essetials)
- [Module 5-5: Managing Virtualization](#module-5-5-managing-virtualization)
    - [Lesson 23: Working with Virtual Machines](#lesson-23-managing-users-and-groups)
    - [Lesson 24: Working with Containers](#lesson-24-managing-linux-permissions-and-quota)
    - [Lesson 25: Sample Exam](#lesson-25-storage-management-essetials)


## Module 1: Essential Commands

### Lesson 1: Installing Linux
We will use several distributions:
* CentOs
* Ubuntu
* SUSE - OpenSUSE

###### Linux Boot Seq

* Linux boot process

BIOS POST -> Boot Loader(GRUB2) -> Kernel İnitilazition -> INIT Process(system)

BIOS POST = POST stands for power-on
BOOT LOADER = /BOOT file system upload
KERNEL INIT = kernel loaded
INIT Process = systemd loaded

* Runlevels - Systemd Targets

``` runlevel ``` show current runlevel
``` systemctl get-default ``` get default runlevel
``` systemctl set-default multi-user.target ``` change default runlevel

- 5 Boots into a GUI ``` graphical.target ```
- 3 Boots into a CLI ``` multiuser.target ```

```
runlevel 0 -> poweroff.target

runlevel 1 -> rescue.target

runlevel 2 -> multi-user.target

runlevel 3 -> multi-user.target

runlevel 4 -> multi-user.target

runlevel 5 -> graphical.target

runlevel 6 -> reboot.target
```

### Lesson 2: Using Essential Tools

###### Common linux commands 

* ``` logout ``` or ``` exit ``` - to log off from your current session. 
* ``` whoami ``` - name of logged in user
* ``` hostname ``` - full hostname
* ``` date ``` - current date and time
* ``` uname ``` - information about system
* ``` passwd ``` - change your password 
* ``` touch ``` - creating an empty file 
* ``` last ``` - shows logged users to the system

- Working with ``` man ``` command. 
By using ``` man ``` we will work with following sections:
1. User commands (1)
4. Devices (4)
5. Configuration files (5)
8. Sysadmin commands (8)

Examples:
- ``` man man ``` - show information man
- ``` man 8 useradd ``` - show information about command from section 8 
- ``` man -a passwd ``` - show information about command from all sections
- ``` man -k ``` - using manual with keyword, when you don't know which command to use 
- ``` appropos user ``` - same results as for ``` man -k ``` command 
- ``` man -k | grep 8 ``` - search for section 8
- ``` man -k user | grep 8 | grep create ``` - search for section 8 and find create use commands
- ``` sudo mandb ``` - create or update the manual page index caches
- ``` info coreutils ``` informantion 
- ``` pinfo coreutils ``` information commands
- ``` su - ``` - switch for root user
- ``` whatis ls ``` - information ls

###### Common bash features

- stdin or '<' redirect standard input
- stdout - your console, or redirect output to a file use '>' or '>>' to append
- stderr or 2> - for redirect error
- piping
    * ``` ls | less ``` input of ``` ls ``` filtered by ``` less ```
    * ``` ps aux | grep httpd ```
- ``` find /proc -name "cpu*" 2> /dev/null ``` - find cpu in /proc directory and send error output to the null device
- ``` history ``` - command line history, to use command from history simple write commands number from history ``` !28 ```
    * history stored in *.bash_history*, you can find this file by typing ``` ls -a ``` - where *-a* means to show hidden files. 

###### Using bash shell scripts
* ``` echo who > myscript ``` - create and add line to the file
* ``` echo ls >> myscript ``` - append to the file
* ``` chmod +x myscript ``` - make your script executable
* ``` ./myscript ``` - run your script 

###### Lesson 2 Command Review

* ``` whoami ```
* ``` hostname ```
* ``` date ```
* ``` uname ```
* ``` passwd ```
* ``` touch ```
* ``` last ```
* ``` man ```
* ``` whatis ```
* ``` apropos ```
* ``` mandb ```
* ``` pinfo ```

###### Lab questions 
![img](https://github.com/oguzhalit/LFCS-2/blob/master/images/LFCS-1.png)

###### Lab answers 
* Q1: ```  man -k kernel | grep info ```
* Q2: ```  man -k hostname ```
* Q3: ```  lvcreate --help ```

* ``` uname -r ``` - get kernel version
* ``` hostnamectl set-hostname ``` - change hostname 
* ``` nmtui-hostname ``` - change hostname from gui on CentOS
* ``` lvcreate --help ``` - all options in [] brackets are optional, all options in {} brackets are mandatory, must be used 

### Lesson 3: Using Essential File Management Tools
###### 3.1 Understanding the Linux File System Hierarchy

Hierarchy:
* / - root directory
    * /boot - files need to start your computer's OS
    * /home - loc of user home directories
    * /usr  - operating system files 
    * /var  - diverse information (log, cache)
    * /bin  - regular binaries
    * /sbin - system binaries
    * /dev  - stand devices, all device files
    * /etc  - configuration files
    * /opt  - application files
    * /proc - interface to linux kernel
    * /run  - new temp dir, processis that temporarily need to write files
    * /srv  - store document for services, like FTP,Web Servers
    * /sys  - hardware information
    * /tmp  - old temp dir, automatic clean reboot
    * /var  - dynamically can be created by the operating system

* mount - connection between directory and device
    * ``` /dev/sdb1 ``` - 
        * /dev is device directory, 
        * sd - scsi disk
        * b - second scsi disk 
        * 1 - number of partition.

By using command ``` mount ``` we can mount different disks to the different directories.
Directories in linux defined by *FHS* - Filesystem Hierarchy Standards 

![img](https://github.com/Bes0n/LFCS/blob/master/images/img1.JPG)

###### 3.2 Listing files with ls command
- ``` ls -l ``` - long list of items
- ``` ls -a ``` - shows hidden items
- ``` ls -il ``` - shows inode number too
- ``` ls -lrt ``` - list items by last time modified
- ``` ls -l /etc ``` - get content of /etc directory
- ``` ls -R ``` - list entire directory structure (recursive)
- ``` ls -ld /etc ``` - get information of /etc directory directly

###### 3.3 Using Shell Wildcards
Three types of globbing:
- '*' - ``` ls a* ``` - will list all files starting with 'a' character. With any length
- ? - ``` ls ca? ``` - will list files which have 'ca' in the beginning and with last character, for instance 'cat' or 'car'
- [a-b] - ``` ls ca[bt] ``` or ``` ls ca[b-t] ``` - first will list with 'ca' and 'b' or 't', second will list 'ca' and starting from 'b' to 't'
Example: ``` ls [a-d]??* ``` - list word starting with 'a' to 'd', have '??' at least two characters and '*' any amount of characters in the end

###### 3.4 Copying files with cp
- ``` cp /etc/hosts . ``` - copy hosts files in home directory
- ``` cp -R /tmp . ``` - copy entire subdirectory structure in home directory
- ``` cp /etc/hosts ~/data/ ``` - copy hosts file in home/data directory. Don't forget to put slash behind the directory

###### 3.5 Working with Directories
- ``` cd /tmp ``` - change directory
- ``` pwd ``` - print working directory
- ``` mkdir data ``` - create subdirectory data
- ``` mkdir -p files/pete ``` - create directory files with pete directory entire using '-p' - path option
- ``` rmdir videos/ ``` - remove empty directory
- ``` rm -rf ``` - remove directory forcely. Even if directory has a files in it. 

###### 3.5 Working with Hardware

- ``` dmesg ``` - get informations hardware
- ``` udevadm info --query=path --name=/dev/sda5 ``` - device information 
- ``` udevamd monitor ``` - watch hardware attach
- ``` lspci ``` - display information all devices (video cart, wireless adapter etc)
- ``` lsblk ``` - list physical disk
- ``` lscpu ``` - display information cpu
- ``` lsmem --summary ``` - display information memory
- ``` free -mh ``` - get memory informaion
- ``` lshw ``` - detailed information hardware conf 

###### 3.6 Using Absolute and Relative Paths
Absolute path can be:
- ``` /tmp/data/files/pete ```
Relative path can be:
- ``` /files/photos/2017 ``` - no need to change directory from 'tmp' 
- ``` cd .. ``` - go to previous directory
- ``` cd ``` - move to your home directory
- ``` cd ../.. ``` - go to two levels down on directory

We can copy items by using relative path: 
![img](https://github.com/Bes0n/LFCS/blob/master/images/img2.JPG)

- ``` tree /tmp/data ``` - get structure of the directory
- ``` cp hosts /tmp/data/photos/2016/ ``` - copy hosts to '2016' directory using **absolute** path
- ``` cp hosts ../../photos/2017/newfiles ``` - copy hosts to '2017' directory using **relative** path

###### 3.7 Moving Files with mv
``` mv /tmp/testfile ~ ``` - move file 'testfile' to your home directory
``` mv testfile anotherfile ``` - rename file 

###### 3.8 Removing Files with rm
``` rm anotherfile ``` - remove anotherfile
``` rm -r ``` - recursive removal 
``` rm -rf etc ``` - remove directory without prompt 
``` rm -rf / ``` - remove everything on your system (dangerous command)
``` rm -- -myfile ``` - remove files with dashes on the beginning

###### 3.9 Understanging Hard and Symbolic Links (soft links)
* Links
    * hard
    * symbolic

Hard Links:
- You can have several names to refer on one inode
- Must be stored on the same device
- Can't be linked to the directories

Symbolic Links:
- Refers to the name
- Become invalid if the name removed
- More flexible than hard link
- Can exist on different devices

![img](https://github.com/Bes0n/LFCS/blob/master/images/img3.JPG)

###### 3.10 Managing Hard and Symbolic Links
- ``` ln /etc/hosts myhosts ``` - create hard link
- ``` ls -l /etc/hosts myhosts ``` - directories will be in the same size
- ``` ls -il /etc/hosts myhosts ``` - list with inodes number
- ``` ls -s myhosts symhosts ``` - create symbolic link from hard link

symhosts symbolic link refers to the myhosts hard link:
![img](https://github.com/Bes0n/LFCS/blob/master/images/img4.JPG)

- ``` ln -s etc /etc ``` - create symbolic link to directory '/etc'

###### 3.11 Finding Files with find
- ``` find /etc -name hosts ``` - start searching in '/etc' directory and look for file with name 'hosts'
- ``` find /etc -name "*hosts*" ``` - look for file which contain 'hosts' name in it. But use double quotes
- ``` find / -user "student" ``` - find files which belong to 'student' user 

###### 3.12 Using Advanced find options
- ``` find /etc -name "*hosts*" -exec cp {} find/names \;``` - find all files in '/etc' with name *hosts* and cp all output from find to the directory 'find/names'. '\;' - must be used to exit from exec interpretor. Where **{}** means output of **find** command
- ``` find /etc -size +100k -exec cp {} find/size \; ``` - look for files more than 100 kilobytes and copy them into the directory 'find/size'
- ``` grep student /etc/* 2>/dev/null ``` - grep will look for files, which contains 'student' word inside
- ``` find /etc -exec grep -l student {} \; 2>dev/null ``` - find files through grep which contains 'student' word inside 
- ``` find /etc -exec grep -l student {} \; -exec cp {} find/contents/ \; 2>/dev/null ``` - cp all found files in 'find/contents/' directory and avoid any error messages. 
- ``` find * -name '*' -type f  | xargs grep "student"``` - find file in student

###### 3.13 Archiving Files with tar
- ``` tar -cvf my_archive.tar /home ``` -  create tar my_archive.tar, content /home
- ``` tar -xvf my_archive -C my_dir``` - extract to file my_dir
- ``` tar -tvf ``` - show contents of an archive

###### Lesson 3 Command Review

* ```ls```
* ```cp```
* ```mkdir```
* ```rmdir```
* ```mv```
* ```rm```
* ```ln```
* ```find```
* ```tar```
* ```gzip```
* ```bzip2```
* ```zip```
* ```file```

###### Lab questions 
![img](https://github.com/oguzhalit/LFCS-2/blob/master/images/LFCS-2.png)


###### Lab answers 

* Q1: ``` mkdir -p /tmp/files/pictures /tmp/files/photos /tmp/files/videos ```
* Q2: ``` cp /etc/[a-c]* /tmp/files ```
* Q3: ``` mv /tmp/files/[a,b]* /tmp/files/photos/ ``` - ``` mv /tmp/files/[c]* /tmp/files/videos/ ```
* Q4: ``` find /etc -type -f -size -1000c -exec cp {} /tmp/files/pictures/ \; ```
* Q5: ``` ln -s /var /tmp/files ```
* Q6: ``` tar cvfz my_archive.tgz /home ```
* Q7: ``` mkdir /tmp/archive && tar xvf my_archive.tgz /tmp/archive ```

### Lesson 4: Working With Text Files
###### 4.1 Understanding How to work with vim

**vi** works on two modes:
* command mode
* input mode

We can switch from **command mode** to **input mode** by using:
- ``` i ``` 
- ``` o ``` - opening new line
- ``` O ``` - opening new line above the current position 
- ``` [Ins] ``` - same as ``` i ```
- ``` a ``` - append to the current cursor position 

We can switch from **input mode** to **command mode** by using:
- ``` ESC ```
- ``` ZZ ```
- ``` :wq ```

Copy and paste:
* ``` v :visual ```
* ``` d :delete ```
* ``` y :yank ```
* ``` p :paste ```

Undo: 
* ``` u :undo ```
* ``` Ctrl + R ``` - redo 

- ``` g ``` - top of the document
- ``` G ``` - bottom of the document 
- ``` /text ``` - search for text
- ``` :noh ``` - disable highlight for current search
- ``` n, N ``` - switch for next inside of search 
- ``` :300 ``` - go to line 300 
- ``` dd, x ``` - delete line 

###### 4.2 Creating text files with vim
- ``` :%s/one/ONE/g ``` - substitute *one* with *ONE*, **g** - means global. For all occurences. 


###### 4.3 Browsing text files with less
- ``` less /var/log/messages ``` - less based on the vim 
- ``` /root ``` - search for *root* word in less mode
- ``` n, N ``` - for next item
- ``` g, G ``` - for top and bottom of the document

###### 4.4 Displaying Text File Contents with cat and tac
- ``` cat myfile ``` - content of the file from first line last
- ``` tac myfile ``` - content of the file from last line first

###### 4.5 Using head and tail to see File Start and End 
- ``` head -n 10 /etc/passwd ``` - get first 10 lines of the files
- ``` tail -n 10 /etc/passwd ``` - get last 10 lines of the files
- ``` head -n 4 /etc/passwd | tail -n 1 ``` - get line 4 by using pipeline 
- ``` tail -f /var/log/messages ``` - *-f* automatically shows information once it's written

###### 4.6 Working with grep (generic regular expression parser)
- ``` grep -ilR student /etc 2>/dev/null ``` - find files which contain *student* word, **-i** insensitive, **-l** means show file name, **-R** means recursive, **2>/dev/null** - avoid any error messages.  
- ``` ps aux | grep cron ``` - search inside of processes for process name *cron*
- ``` ps aux | grep cron | grep -v grep ``` - inside of search don't show me *grep* output 

###### 4.7 Understanding Regular Expressions 
* Regular expressions are text patterns that are used by tools like grep and others
* Don't confuse regular expressions with globbing
* ``` grep 'a*' ``` - put your regular expressions in single quotes
* grep, vim, awk, sed - tools which use regular expressions

![img](https://github.com/Bes0n/LFCS/blob/master/images/img5.JPG)

###### 4.8 Using Regular Expressions with grep
- ``` grep '^abc' grepfile1 ``` - get words starting with 'abc'
- ``` grep 'abc$' grepfile1 ``` - get words end with 'abc'
- ``` grep 'a.c' grepfile1 ```  - matching 'abc', 'a2c', 'aac', 'abc123'
- ``` man -k user | egrep '1|8' ``` - get extended grep for user manual with pattern 1 or 8
- ``` egrep 'ab{2}c' grepfile1 ``` - output will be 'abbc', 2 preceeding characters
- ``` grep 'a[bB]c' grepfile1 ``` - we can get 'abc' or 'aBc' or '123abc'
- ``` egrep '(123{3})' grepfile1 ``` - get group of items three times, output - '123123123' 
- ``` grep 'ab*c' grepfile1 ``` - no or more items between 'ab' and 'c', output can be - 'ac', 'abc', 'abbc', 'abbbbbc'
- ``` egrep 'ab+c' grepfile1 ``` - more items between 'ab' and 'c', output can be - 'abc', 'abbc', 'abbbbbc'
- ``` egrep 'ab?c' grepfile1 ``` - null or one preceeding character, can be - 'aac', 'ac', 'abc'

###### 4.9 Using Common Text Processing Utilities

* ```cut```: filter output from a text file
* ```sort```: sort files, often used in pipes
* ```tr```: translates uppercase to lowercase
* ```awk```: search for specific patterns
* ```sed```: powerful stream editor to batch-modify text files

- ``` cut -d : -f 3 /etc/passwd | sort -n ``` - filter out text from */etc/passwd* by using delimeter *:*, *-f 3* - is a third field. Sort by numbers use '-n'
- ``` cut -d : -f 1 /etc/passwd | sort ``` - filter out text from */etc/passwd* by using delimeter *:*, *-f 1* - is a first field. Sort by characters'
- ``` cut -d : -f 1 /etc/passwd | sort | tr [:lower:] [:upper:] ``` - translate output from lower to uppercase
- ``` echo hello | tr [a-z] [A-Z]``` - translate output from lower to uppercase
- ``` awk -F : '{print $1}' /etc/passwd ``` - same as *cut* but more powerful 
- ``` sed -i -e  '10d' grepfile1 ``` - streamline editor, *-i* interactor, *-e* edit. We removed line 10 from grepfile1
- 
###### Lesson 4 Command Review

* ```vim```
* ```more```
* ```less``
* ```head```
* ```tail```
* ```cat```
* ```tac```
* ```grep```
* ```awk```
* ```sed```
* ```tr```
* ```cut```
* ```sort```

###### Lab Questions

![img](https://github.com/oguzhalit/LFCS-2/blob/master/images/LFCS-3.png)

###### Lab Solutions
- Q1: ``` head -n 5 /etc/passwd | tail -n 1 ```
- Q2: ``` sed -n '5p' /etc/passwd ``` 
- Q3: ``` ps aux | awk '{print $1}' ```
- Q4: ``` grep '^root' /etc/* 2>/dev/null ```
- Q5: ``` grep '^...$' /etc/* 2>/dev/null ``` 
- Q6: ``` grep '\<alex\>' * ```  

### Lesson 5: Connecting to a Server

###### 5.1 Working as Root or a Local User
- ``` su - ``` - log on as root
- ``` sudo su - ``` or ``` sudo -i ``` - log on as root on ubuntu

###### 5.2 Using su to Perform Administration Tasks
- ``` su - username ``` - perform log on as regular user 'username'

###### 5.3 Using sudo to Perform Administration Task
- ``` sudo -i ``` - will get error that user is not in the sudoers file
- ``` id student ``` - get id of the user. uid, gid and groups
- ``` usermod -aG wheel student ``` - add 'student' user in 'wheel' group to perform sudo tests
- ``` visudo ``` - open configuration of sudo file 
- *Note: after adding your user in sudoers, you have to log off and log on, so your changes can be applied*

###### 5.4 Creating a simple sudo configuration
Access for specific users managed by **visudo** command. 
- ``` sudo passwd linda ``` - set up password for user
- ``` su - linda ``` - open linda shell 
- ``` linda ALL=/sbin/useradd ``` - provide access to linda user on ALL hosts to execute command *useradd* in visudo file

###### 5.5 Working on Linux from Graphical or Command Line Mode
- ``` w ``` - get information about active terminals
- ``` chvt ``` - switch to virtual terminal
- ``` chvt 7 ``` - switch back to terminal number 7. Depends of distribution where graphical interface located. 
- ``` pts/0 ``` - information about user logged through ssh session

###### 5.6 Connecting Remotely to Linux
- ``` sshd ``` - secure shell daemon
- ``` telnetd ``` - insecure and should not be used anymore
- ``` PuTTy ``` - remote ssh client for windows, nowadays powershell can be used
- ```  VNC ``` - remote desktop client for Linux 
- ``` ssh student@192.168.4.240 ``` - connect to linux remote machine with student user

###### 5.7 Understanding the Use of etc securetty
- ``` vim /etc/securetty ``` - list of secure TTY's. Here you can include or exclude list of terminals. 

###### Lesson 5 Command Review

* ```su```
* ```sudo```
* ```chvt``
* ```ssh```
* ```ssh-keygen```
* ```ssh-copy-id```
* ```scp```


###### Lab Questions

![img](https://github.com/oguzhalit/LFCS-2/blob/master/images/LFCS-4.png)

### Lesson 6: Working with the bash shell

###### 6.2 Using I/O Redirection And Piping

- Standard İnput (0): <
  * ``` sort < /etc/services ```
- Standard Output (1): >
  * ``` ls > ~/myfile ```
  * ``` who >> ~/myfile ```
- Standard Error (2): 2>
  * ``` grep -R root /proc 2>/dev/null ```
  * ``` grep -R root /etc &> ~/myfile ```

- Piping
  A pipe is used to send the output of one command to be used as input for a second command
  * ``` ps aux | grep http ```
  * ``` ps aux | tee psfile | grep ssh ```

###### 6.3 Working with history

- Commands a user types are written to ~/.bash_history
- ``` history -c ``` to clear the current history
- ``` history -w ``` to write the current history
- ``` !nn ``` to repeat a specific line from history
- ``` !ec ``` to repeat a echo ""

###### 6.5 Using Variables

- A variable is a label to which a dynamic value can be assigned
- ``` varname=value ``` define var
- ``` echo $varname ``` read var
- ``` env ``` print env

###### 6.7 Bash Startup files

- /etc/environment contains a list of variables and is the first file
  that is processed while starting bash
- /etc/profile is executed while users login
  * ~/.bash_profile can be used as a user-specific version
  * ~/.bash_logout is processed when a user logs out
- /etc/bashrc is processed every time a subshell is started
  * A user-specific ~/.bashrc file may be used

###### Lesson 6 Command Review

* ```sort```
* ```tee```
* ```history```
* ```alias```
* ```export```

###### Lab Questions

![img](https://github.com/oguzhalit/LFCS-2/blob/master/images/LFCS-5.png)

###### Lab Solutions

- Q1: ``` alias ipconfig='ip addr show' ```
- Q2: ``` export COLOR=red ```
- Q3: ``` alias ```

## Module 2: User and Group Management and Permissions
### Lesson 7: Managing Users and Groups
###### 7.2 Understanding File Ownership
Users as groups can have access to resources, files, directories e.t.c
- ``` id ``` - get information about users
- ``` id linda ``` - information about linda user 
- ``` gid=1000(student) ``` - means that primary group for student user is **student** group

###### 7.3 Creating Users with useradd and adduser
- ``` useradd -D ``` - create user by using default options
- ``` useradd -c 'the boss' -G wheel -s /bin/passwd bob ```
- ``` useradd -s /bin/zsh -c "my user" -m anna ``` - create user on CentOs
- ``` adduser kate ``` - you will be promted for all requrired information on Ubuntu 
- ``` chsh ``` - change default shell

###### 7.4 Creating Groups with groupadd
- ``` groupadd sales ``` - create group **sales**
- ``` usermod -aG sales anna ``` - add user to the group **sales**, where **-a** means append to the group

###### 7.5 Managing User and Group Properties
- ``` w ```  show currenly login user
- ``` who ``` who like w 
- ``` getent passwd user ``` specific user information
- ``` usermod -L anna  ``` - lock the user
- ``` useromd -U annd ``` - unlock the user
- ``` usermod -aG wheel amy ``` - add wheel group amy
- ``` userdel -r ``` - remove user, it's home directory and mail spool
- ``` groupdel ``` - remove group
- ``` groupmod ``` - modify properties of the existing group 

###### 7.6 Configuring Defaults for Creating Users
We have */etc/default* directory, where *useradd* file can be modified. That one refers to the *useradd -D* option. Default user properties. 

- ``` /etc/login.defs ``` - mail spool location, password expire days, length, age. UID and GID information. 
- ``` /etc/skel/ ``` - items inside of skel directory will be copied to the home directory of newle created user
- ``` /etc/default/useradd ``` - change default useradd properties
- ``` /etc/shadow ``` - information password 

###### 7.7 Managing Password Properties
- ``` passwd --help ``` - settings for passwd command
- ``` echo password | passwd --stdin brenda ``` - update password for brenda user. Can be scripted. 
- ``` chage brenda ``` - change age of the password for brenda user

###### 7.8 Understanding User Configuration Files
- ``` /etc/passwd ``` and ``` /etc/shadow ``` - information stored about users in these folders
- ``` vipw ``` - vi for passwd, modify contents of /etc/passwd directly
- ``` /etc/group ``` - group configuration files. Primary groups don't have members because they declared already in */etc/passwd* as primary group. We can manage members here of secondary groups. 

###### 7.9 Understanding Session Management

- ```who``` and ```w``` show is currently logged in
- ```loginctl``` allows for current session management
  * ``` loginctl list-sessions ```
  * ``` loginctl show-sessions <id> ```
  * ``` loginctl show-user <username> ``` 
  * ``` loginctl terminate-session <session-id> ```

###### 7.10 Understanding Login on External Authentication Sources
Setting up remote authentication can be difficult. Can be done on **Active Directory** or **LDAP** 

###### 7.11 Configuring Login on External Authentication Sources
First of all we need to install proper software

- ``` yum groups install "Directory Client" ``` - software required for external authentication 
- ``` authconfig ``` or ``` authconfig-gtk ``` - gtk is graphic utility. To run gui verion *authconfig-gtk*

![img](https://github.com/Bes0n/LFCS/blob/master/images/img6.JPG)

###### 7.12 Configuring Resource Access Restrictions
- ``` cd /etc/security ``` then ``` vim limits.conf ``` - here we can configure limits of resources provided to the users.

![img](https://github.com/Bes0n/LFCS/blob/master/images/img7.JPG)

As you can see from image here we can configure number of maximum processes, maxlogins, cores usage and so on.

###### Lesson 7 Command Review

* ```useradd```
* ```usermod```
* ```userdel```
* ```groupadd```
* ```groupmod```
* ```groupdel```
* ```id```
* ```getent```
* ```passwd```
* ```chage```
* ```w```
* ```who```
* ```vipw```
* ```vigr```
* ```loginctl```
* ``` chsh ```

###### Lab Questions

![img](https://github.com/oguzhalit/LFCS-2/blob/master/images/LFCS-7.png)

###### Lab Solutions

- Q1: ``` useradd username ```
- Q2: ``` vim /etc/login.defs ``` change pass_max_days to 60
- Q3: ``` groupadd sales ``` - ``` useradd -G sales linda ```
- Q4: ``` groupadd account ``` - ``` useradd -G account anna ```
- Q5: ``` groupadd users ``` - ``` useradd -G users lisa```
- Q6: ``` echo password | passwd --stdin linda ```
- Q7: ``` vim /etc/default/useradd ``` change to HOME=/home 


### Lesson 8: Managing Linux Permissions and Quota
###### 8.1 Understanding Basic Linux Permissions
- Basic Permissions (file or directory):
    * Read **(4)** - you can read file or list items in that directory
    * Write **(2)** - modify contents of the file, create or delete files inside of directory
    * Execute **(1)**  - you can run the file. You need read permission to execute the script. To access directory to use *cd* we need execute permission. 

- Ownership:
    * Users
    * Group
    * Others

- ``` chmod 760 file ``` - where **7** - permission for user, **6** - permission for group, **0** - permission for others.

As we understand number **7** is a sum of **4**(read) + **2**(write)+ **1**(execute). So **7** is a full permission. So user will have full access permission. 

**6** means that group will have **4**(read) and **2**(write) permissions

**0** means that others will don't have any permissions for that file 

###### 8.2 Managing Basic Linux Permissions
- ``` chgrp  sales mydirectory ``` - make group **sales** as an owner of **mydirectory** directory
- ``` chown anna mydirectory ``` - make user **anna** as an owner of **mydirectory** directory
- ``` chown linda:sales mydirectory ``` or ```chown linda.sales mydirectory```  - make **linda** user and **sales** group as an owner of **mydirectory** directory in one command 
- ``` chmod g+w account ``` - add write group permission to account directory
- ``` chmod o-rx account ``` - remove read and execute permissions from account directory for others

###### 8.3 Understanding Advanced Linux Permissions
Advanced permissions:
- **suid** (4) - set user id. Run file as owner. Dangerous permission.
- **sgid** (2) - set group id. Run as group owner. Also dangerous permission. Inherit directory group owner. 
- **sticky** (1) - sticky bit. Has no meaning on files. Delete if only owner for directory. 


###### 8.4 Managing Advanced Linux Permissions
- ``` chmod u+s playme ``` - set permissions as represantive to file. 
- ``` /bin/passwd ``` - using same permissions set by **suid**

- ``` chmod g+s * ``` - set group id for directory to use shared directory. Group ownership will be set from parent directory. 
- ``` chmod +t * ``` - add sticky bit to the files. File can't be removed by other users if sticky bit applied inside of shared directory. 

###### 8.4.1 Managing umask

- Default permissions are set by the umask

* umask is a shell setting that define a mask that will be subtracted from the default perm
* Default perm on dir are 777
* Default perm on file are 666
* umask 022 wil set default perm on files to 644
* umask 027 wil set default perm on dir to 750

- ``` umask ``` current umask
- ``` /etc/profile && ~/. bash_profile ``` change umask permanent
- umask - 

###### 8.5 Understanding Access Control Lists
Two types of ACL:
* normal - take care of files that already exists 
* default - take care of files that will be created

- ```setfacl -R -m g:sales:rx file``` - set **-m** modify access list **-R** recursively to **file** for group **sales** with **rx** read-execute permissions
- ```setfacl -R -m d:g:sales:rx file``` - **d** column added for default ACL

To use ACL we need filesystem acl. Without this option we couldn't use ACL

###### 8.6 Managing Access Control Lists
- ```setfacl -R -m g:sales:rx account``` - group **sales** need read and execute for **account** directory
- ```getfacl account/``` - get information about access list

```
# file: mydirectory/
# owner: root
# group: sales
user::rwx
group::rwx
group:sales:r-x
mask::rwx
other::---
```

- ```setfacl -m d:g:sales:rx account``` - default actions, which will be applied to any items created in **mydirectory**

```
# file: mydirectory/
# owner: root
# group: sales
user::rwx
group::rwx
group:sales:r-x
mask::rwx
other::---
default:user::rwx
default:group::rwx
default:group:sales:r-x
default:mask::rwx
default:other::---
```


###### 8.7 Understanding Extended Attributes
Extended Attributes - properties of files only. 
Commands: 
* chattr
* lsattr 

###### 8.8 Managing Extended Attributes
- ```chattr +i file1``` - add immutable attribute to the **file1**
- ```lsattr file1``` - get information about attribute. 
```
[root@centos mydirectory]# lsattr file1 
----i----------- file1
```

We can't do anything to the immutable file. 
```
[root@centos mydirectory]# echo hello >> file1
-bash: file1: Permission denied
[root@centos mydirectory]# rm -f file1 
rm: cannot remove ‘file1’: Operation not permitted
```

Except: 
- ``` chattr -i file1 ``` - remove immutable attribute from the **file1**

###### 8.9 Understanding Linux File System Quota
Put limitation to the user for using disk space. 

###### 8.10 Managing Quota on Ext File Systems
- ```yum install -y quota``` - install required software
- ```vim /etc/fstab``` - mounting systems quota automatically
- ```chmod -R 777 /quota``` - full access for /quota directory
- ``` mount -o remount quota ``` - to be sure that file system mounted with the right option. 
- ``` quotacheck -mavug ``` - running quotacheck. 
- ```quota -vu lisa``` - checking what is user **lisa** using 
- ``` repquota -aug ``` - get information about quota limits for users

###### 8.11 Managing Quota on XFS File Systems
- ``` xfs_quota --help ``` or ```man xfs_quota```

###### 8.12 Finding Files with Specific Permissions
- ```man find``` - look for **perm**
- ```find . -perm 0600 -exec ls -l {} \; ``` - find files in /etc with special permissions and list items. 
- ``` find . -perm /4000 -exec ls -l {} \; ``` - items which have set user id permission mode. 

###### Lesson 8 Command Review

* ``` chown ```
* ``` chgrp ```
* ``` umask ```
* ``` chmod ```

###### Lab Questions

![img](https://github.com/oguzhalit/LFCS-2/blob/master/images/LFCS-8.png)

###### Lab Solutions

- Q1: ``` umask 077 ```
- Q2: ``` mkdir -p /data/sales /data/account ```
- Q3: ``` chgrp sales /data/sales && chmod g+rw /data/sales ```
- Q4: ``` chmod +t /data/sales ```
- Q5: ``` chown anna /data/sales ```


### Lesson 9: Storage Management Essentials

###### 9.2 Creating MBR Partitions

- ``` lsblk ``` list block devices 
- ``` fdisk /dev/sdb ``` create partition
  * ``` m ``` for help
  * ``` p ``` print
  * ``` n ``` create new partition
  * ``` p ``` primary partition
  * ``` 1 ``` partition number
  * ``` 2048 ``` first sector
  * ``` 10485 ``` last sector
  * ``` p ``` print view new part
  * ``` w ``` write new part
- ``` cat /proc/partitions ``` have partitions
- ``` partprobe ``` after adding partititons 
- ``` cat /proc/partitions ``` then view new part

###### 9.3 Creating GPT Partitions

- ``` gdisk /dev/sdb ``` create part
  * ``` ? ``` for help
  * ``` p ``` print
  * ``` n ``` create new part
  * ``` 1 ``` part number
  * ``` 2048 ``` first sector
  * ``` +2G ``` last sector
  * ``` 8300 ``` lfs
  * ``` p ``` view creating part
  * ``` w ``` write part

###### 9.4 Creating filesystems

``` mkfs [TAB-TAB]``` view filesystem format command
``` mkfs.xfs /dev/sdb1 ``` foarmatted partitions xfs
``` mkfs.ext4 /dev/sdb1 ``` formatted partition ext4

###### 9.5 Creating filesystems

``` mount /dev/sdb1 /mnt ``` mount /dev/sdb1 and mnt
``` lsof /mnt ``` list open files in mnt
``` mount ``` view all mount
``` mount | grep '^dev' ``` view mount only device
``` findmnt ``` view mount
``` umount /mnt ``` disconnect device mount

###### Lesson 9 Command Review

- ``` lsblk ```
- ``` fdisk ```
- ``` partprobe ```
- ``` gdisk ```
- ``` mkfs ```
- ``` mount ```
- ``` findmnt ```
- ``` umount ```
- ``` lsof ```

###### Lab Questions 

![img](https://github.com/oguzhalit/LFCS-2/blob/master/images/LFCS-8.png)

###### Lab Solutions 

- Q1: ``` gdisk /dev/sdb ```
      * ``` p - n - 2 - enter - enter - +1G - enter - w - Y ```
- Q2: ``` mkfs.ext4 /dev/sdb2 ```
- Q3: ``` mount /dev/sdb2 /mnt ```

## Module 3: Networking
### Lesson 10: Configuring Networking
###### 10.1 Summarizing IPv4 Basics
![img](https://github.com/Bes0n/LFCS/blob/master/images/img8.JPG)

###### 10.2 Summarizing IPv6 Basics
![img](https://github.com/Bes0n/LFCS/blob/master/images/img9.JPG)

- Predefined IPv6 Addresses
![img](https://github.com/Bes0n/LFCS/blob/master/images/img10.JPG)

- Obtaining an IPv6 Address 
![img](https://github.com/Bes0n/LFCS/blob/master/images/img11.JPG)

###### 10.3 Applying Run time Network Configuration
- ``` ip ```- monitor your network in run time. 
- ```ip link show``` - information about network interfaces
- ```ip address show``` - get all ip addresses
- ```ip address add dev ens33 10.0.0.10/24``` - add secondary IP address for devices named **ens33**. After reboot this IP will gone. You need persistent IP address. 
- ```ifconfig | help``` - shouldn't be used anymore
- ```ip route show``` - get information about routes
- ```cat /etc/resolv.conf ``` - dns nameserver (ping to resolve this nameserver) (if not contain ns error Name or service not known)
- ``` ip route del default via 192.168.4.2 ``` - route delete (if deleted network is unreacheable)
- ``` ip route add default via 192.168.4.2 ``` - route add 
- ``` ip addr del dev ens33 192.168.4.249/24 ``` - name or service not know
- ``` dhclient ``` - dhcp client re-obtain ip-v4 address
- ``` ip addr add dev ens33 10.0.0.10/24 ``` set manually ip address, secondry ip addr
- ``` ifconfig ``` get network information

###### 10.4 Understanding Network Device Naming
- **biosdevname** - uses device names that reveal information about physical location. 
![img](https://github.com/Bes0n/LFCS/blob/master/images/img12.JPG)

###### 10.5 Managing Host Names

- ``` hostname ``` - return fqdn
- ``` hostname -I ``` all ip addr returns
- ``` cat /etc/hostname ``` get hostname
- ``` hostnamectl ``` control the hostname
- ``` hostnamectl status ``` details hostname
- ``` uname -a ``` details hostname 
- ``` hostnamectl set-hostname newhostname ``` set hostname (exit & login)

###### 10.6 Managing Host Name Resolution

- ``` /etc/hosts ``` add fake host
- ``` /etc/nsswitch.conf ``` # dns taramalarının sırası belirtilir.

###### 10.7 Using Common Network Tools

- ``` ping -f -s 4096 google.com ``` ping boomm
- ``` netstat -tulpen ``` get listening port
- ``` ss -tuna ``` socket stats informations
- ``` nmap ip_addr ```  scan open ports ip_addr
- ``` dig nu.nl ``` dns information


###### 10.5 Applying Persistent Network Configuration in CentOS
- ```cat /etc/redhat-release``` - check your release version
- ```nmtui``` - network manager user interface
- ```nmcli``` - network manager command line
- ```man nmcli-examples``` - you can look for different examples
- ```rpm -qa | grep bash-completion``` - need for tabulation. To complete written commands
- ```nmcli connection modify ens33 ipv4.addresses 192.168.4.240/24 ipv4.gateway 192.168.4.2 ipv4.dns 8.8.8.8``` - set static ip address, gateway and DNS. 
- ```nmcli connection up ens33``` - enable network interface
- ```cd /etc/sysconfig/network-scripts``` - network configuration stored in this directory. 

###### 10.6 Applying Persistent Network Configuration in SUSE
- ```yast``` - generic SUSE configuration tool. From this configuration tool we can manage system settings. 

###### 10.7 Applying Persistent Network Configuration in Ubuntu
- ```cd /etc/network/``` - network interfaces directory

![img](https://github.com/Bes0n/LFCS/blob/master/images/img13.JPG)

- ``` ifdown ens33 ``` and then ```ifup ens33``` - reload network interface to apply changes to the network interface. 

###### 10.8 Managing Host Names
- ``` /etc/hostname ``` - where hostname information stored
- ``` uname -a ``` - get information about machine 
- ``` cd /proc/sys/kernel ``` - information about hostname also written here.  
- ``` vim /etc/hosts ```- configuration of hostname resolving
- ``` /etc/services ``` 

###### 10.9 Managing Host Name Resolution
- ```vim /etc/resolv.conf``` - configuration file of dns. 

```
# Generated by NetworkManager
search mydns.example.com example.com
nameserver 100.253.0.10
nameserver 110.225.100.10
```
*Note: if you can see that dns configured by NetworkManager better don't touch it directly.*

- ```vim /etc/nsswitch.conf``` - this file defines which file will be read first. **hostname**, **resolv.conf** or **myhostname**

```
#hosts:     db files nisplus nis dns
hosts:      files dns myhostname
```
*As we can see hostname comes first, dns second and myhostname is last*

###### 10.10 Using Common Network Tools
- ```ping``` - test response of other hosts

Let's ping google.com

```
64 bytes from bud02s27-in-f14.1e100.net (172.217.19.110): icmp_seq=1 ttl=52 time=21.7 ms
64 bytes from bud02s27-in-f14.1e100.net (172.217.19.110): icmp_seq=2 ttl=52 time=21.6 ms
64 bytes from bud02s27-in-f14.1e100.net (172.217.19.110): icmp_seq=3 ttl=52 time=21.4 ms
64 bytes from bud02s27-in-f14.1e100.net (172.217.19.110): icmp_seq=4 ttl=52 time=21.8 ms
```

- ```dig``` - verify dns related issues. If command not found install **bind-utils**
- ```dig google.com``` - let's check for google.com dns name 
```
; <<>> DiG 9.9.4-RedHat-9.9.4-74.el7_6.2 <<>> google.com
;; global options: +cmd
;; Got answer:
;; ->>HEADER<<- opcode: QUERY, status: NOERROR, id: 481
;; flags: qr rd ra; QUERY: 1, ANSWER: 1, AUTHORITY: 0, ADDITIONAL: 1

;; OPT PSEUDOSECTION:
; EDNS: version: 0, flags:; udp: 4000
;; QUESTION SECTION:
;google.com.                    IN      A

;; ANSWER SECTION:
google.com.             135     IN      A       172.217.19.110

;; Query time: 19 msec
;; SERVER: 120.253.20.10#53(120.253.20.10)
;; WHEN: Mon Aug 05 14:30:24 CEST 2019
;; MSG SIZE  rcvd: 55
```
*Where IN means an Internet, A means an Answer.* 

- ``` dig nosuchdomainindig.com ``` - search for non-existing domain

``` 
; <<>> DiG 9.9.4-RedHat-9.9.4-74.el7_6.2 <<>> nosuchdomainindig.com
;; global options: +cmd
;; Got answer:
;; ->>HEADER<<- opcode: QUERY, status: NXDOMAIN, id: 47450
;; flags: qr rd ra; QUERY: 1, ANSWER: 0, AUTHORITY: 1, ADDITIONAL: 1

;; OPT PSEUDOSECTION:
; EDNS: version: 0, flags:; udp: 4000
;; QUESTION SECTION:
;nosuchdomainindig.com.         IN      A

;; AUTHORITY SECTION:
com.                    827     IN      SOA     a.gtld-servers.net. nstld.verisign-grs.com. 1565008545 1800 900 604800 86400

;; Query time: 19 msec
;; SERVER: 150.253.20.10#53(150.253.20.10)
;; WHEN: Mon Aug 05 14:37:01 CEST 2019
;; MSG SIZE  rcvd: 123
```

*Note: from **status: NXDOMAIN** we can see that such domain does not exist*

- ``` yum install nmap ``` - install nmap - provides information about ports.
- ``` nmap 10.0.2.15 ``` - get information about open ports. 
```
Starting Nmap 6.40 ( http://nmap.org ) at 2019-08-05 14:41 CEST
Nmap scan report for centos.example.com (10.0.2.15)
Host is up (0.000010s latency).
Not shown: 999 closed ports
PORT   STATE SERVICE
22/tcp open  ssh
```

###### Lesson 10 Command Review

- ``` ip a ```
- ``` ip a dev eth0 1.2.3.4/8 ```
- ``` ip route show ```
- ``` cat /etc/resolv.conf ```
- ``` ping ```
- ```dhclient ```
- ```netstat ```
- ``` ss ```
- ``` dig ```
- ``` nmap ```
- ``` hostname ```
- ``` hostnamectl ```
- ``` uname ```

###### Lab Questions

![img](https://github.com/oguzhalit/LFCS-2/blob/master/images/LFCS-10.png)

### Lesson 11: Managing Time
- ``` hardware time -> system time -> NTP ``` 

###### 11.2 Managing Linux Time

- ``` date ``` - show current time, system time
- ``` date -s 14:53 ``` - set time
- ``` hwclock ``` - hardware time
- ``` timedatectl ``` - time control utilization
- ``` timedatectl list-timezones ``` - list timezone
- ``` timedatectl set-timezone Europe/Istanbul ```- set timezone

###### 11.3 Understanding the NTP Protocol


- https://orolia.com/manuals/SS/Content/_Global/Topics/NTP/NTP_Stratums.htm
- iburst


###### 11.4 Configuring Time Synchronization

- ``` timedatectl status ``` ntp(Network time protocol) sync
- ``` chronyc sources``` information time source
- ``` ntpdate pool.ntp.org ```  fetch time pool.ntp.org, time problem fix it

###### Lesson 11 Command Review

- ``` date ```
- ``` hwclock ```
- ``` timedatectl ```
- ``` ntpdate ```
- ``` ntpq ```
- ``` chronyc ```

###### Lesson 11 Lab

![img](https://github.com/oguzhalit/LFCS-2/blob/master/images/LFCS-11.png)

### Lesson 12: Working with Systemd
###### 12.1 Understanding Systemd

- ``` /usr/lib/systemd/system ``` - default units
- ``` /etc/systemd ```  - custom units

###### 12.2 Understanding Systemd

- ``` systemctl -t help ``` - show unit types
- ``` systemctl list-unit-files ``` - list all installed units
- ``` systemctl list-units ``` - list active units
- ``` systemctl enable name.service ``` - enable but doesn't start a service
- ``` systemctl start name.service ``` - starts a service
- ``` systemctl disable name.service ``` - disable but doesn't stop a service
- ``` systemctl stop name.service ``` - stops a service
- ``` systemctl status name.service ``` gives information about the service


- ``` vendor preset: disabled ``` - after installing, it doesnt get enabled automatically
- ``` name.service; disabled ``` automatically be started after restart(enable)
- ``` Active: inactive (dead) ``` - not currently ruunning 

###### 12.3 Modifying Service Configuration

- ``` systemctl cat name.service ``` reads current unit configuration
- ``` systemctl show ``` shows all available configuration parameters
- ``` systemctl edit name.service ``` allows you to edit service configuration
- ``` systemctl daemon-reload ``` modifying service configuration
- ``` systemctl restart name.service ``` restart the service



###### 12.4 Understanding Targets

- A target is group of services
- Some targets are isolatable 
  * emergency.target
  * rescue.target
  * multi-user.target
  * graphical.target

- ``` systemctl list-dependencies name.target ``` - see the contents and dependencies of a systemd target

###### 12.5 Managing Targets

- ``` systemctl start name.target ```
- ``` systemctl isolate name.target ```
- ``` systemctl list-dependencies name.target ```
- ``` systemctl get-default ```
- ``` systemctl set-default name.target ```

###### Lesson 12 Command Review

- ``` systemctl start ```
- ``` systemctl status ```
- ``` systemctl stop ```
- ``` systemctl enable ```
- ``` systemctl disable ```
- ``` systemctl list-units ```
- ``` systemctl set-default ```
- ``` systemctl get-default ```
- ``` systemctl cat ```
- ``` systemctl show ```
- ``` systemctl edit ```
- ``` systemctl deamon-reload ```
- ``` systemctl isolate ```
- ``` systemctl list-dependencies ```

###### Lesson 12 Lab

![img](https://github.com/oguzhalit/LFCS-2/blob/master/images/LFCS-12.png)

### Lesson 13: Process Management
###### 13.1 Understanding Linux Processes and Jobs

init = systemd
----------|> http
----------|> sshd
--------------|> bash
-----------------|> echo
----------|> job

###### 13.2 Managing Interactive Shell Jobs

``` dd if=/dev/zero of=/dev/null & ``` run job background
``` bg ```
``` jobs ``` view jobs
``` fg ``` 

###### 13.3 Monitoring Processes with top

``` top ``` active proc view
``` htop ```

###### 13.4 Changing top Display Properties

``` top -u user ``` specific user proc view
``` top + f ``` edit field, select [:space:]
``` top + 1 ```
``` top + 2 ```
``` top + z ``` change color
``` cd ~/.toprc ``` current display settings 

###### 13.5 Monitoring Process Properties with ps

``` ps aux | less ``` - view running process
``` ps aux | grep proc ```
``` ps -ef ``` same information, diffrent way
``` ps fax ``` graphical display showing, parent process
``` ps aux --sort pmem | less ``` sort mem uses
``` free -mh ``` information memory and swap
 
###### 13.6 Changing Process Priority

``` renice ``` change priority
``` renice -n 5 pid ``` set renice
``` nice ``` similear renice
``` nice -n 20 command ``` run priority nice command

###### 13.7 Managing Processes with kill

``` man 7 signal ``` for signal item
``` ps aux | grep command ``` find process
``` kill -9 command_pid ``` 
``` killall ``` 

###### 13.8 Lesson 13 Command Review

``` top ```
``` ps ```
``` jobs ```
``` fg ```
``` bg ```
``` nice ```
``` renice ```
``` kill ```
``` killall ```

###### Lesson 13 Lab: Managing Processes

![img](https://github.com/oguzhalit/LFCS-2/blob/master/images/LFCS-13.png)

### Lesson 14: Managing Software

``` ldd /usr/bin/passwd ``` passwd command required libarry
``` dpkp -i package_name ```
``` /etc/apt/sources.list ``` apt repo
``` apt search nmap ```
``` apt install nmap ```
``` autoremove ```


###### 14.8 Lesson 14 Command Review

``` rpm ```
``` yum ```
``` dnf ```
``` yumdownloader ```
``` apt ```

###### Lesson 14 Lab: Managing Software

![img](https://github.com/oguzhalit/LFCS-2/blob/master/images/LFCS-14.png)

### Lesson 15: Scheduling Tasks
###### 15.1 Understanding Linux Task Scheduling

- cron: the classical solution, allows you to schedule re-occuring tasks
  * uses the crond daemon
  * use crontab -e to edit tasks
- at: for tasks that need to run once only
  * uses the atd daemon
  * uses at to schedule the tasks
- systemd timers: the newer  alternative to cron jobs
  * create a .timer unit and run it using systemctl

###### 15.2 Scheduling Tasks with cron

- ``` systemctl status crond ``` 
- ``` vim /etc/crontab ```
- ``` crontab -e ```
- ``` cd /etc/cron.d ```
- ``` vim sysstat ``` 
- ``` less /var/log/messages ```

###### 15.3 Using systemd Timers

- ``` cd /usr/lib/systemd/system && ls *timer ```
- ``` systemctl status example.timer ```
- ``` man -k systemd | grep timer ```
- ``` man systemd.timer ```
- ``` systemd status atd ```
- ``` at 12:12 - poweroff - logger hello - <EOT> ```
- ``` atq ``` 
- ``` atrm ```

###### 15.5 Lesson 15 Command Review

- ``` at ```
- ``` atq ```
- ``` atrm ```
- ``` crontab -e ```
- ``` systemctl ```

###### Lesson 15 Lab: Scheduling Tasks

![img](https://github.com/oguzhalit/LFCS-2/blob/master/images/LFCS-15.png)

### Lesson 16: Reading Log Files
###### 16.1 Understanding Linux Logging

- Syslog is the legacy service that takes care of logging
- Syslog on modern Linux is implemented through rsyslogd
- systemd-journald is a systemd-integrated log service

###### 16.2 Working with journalctl

- ``` journalctl ``` show the complete journal
- ``` journalctl -u <unit> ``` shows informations about specific unit
- ``` journalctl --dmesg ``` shows kernel messages
- ``` journal -u crond --since yesterday --until 9:00 -p info ```

###### 16.3 Understanding Rsyslog

- The ```rsyslogd``` service works with facility, priority and destination
- The facility is what ```rsyslogd``` should be logging for
- The priority indicates the severity of a log event
- ``` ls /etc/rsyslog.* ```
- ``` vim /etc/rsyslog.conf ```
- ``` logger hello && tail /var/log/messages ```


###### 16.4 Lesson 16 Command Review

- ``` journalctl ```
- ``` tail ```
- ``` less ```
- ``` logger ```

###### Lesson 16 Lab: Working with Logging

![img](https://github.com/oguzhalit/LFCS-2/blob/master/images/LFCS-16.png)

## Module 1: Advanced System Administration

### Lesson 1: An Introduction to Bash Shell Scripting

- A shell script can be as simple as a number of commands that is seq executed

###### 1.2 Essential Shell Script Components
```
#!/bin/bash
#
# some explanation

echo what dir do you wat to go to ?

read DIR

cd $DIR
pwd
ls

exit 0
```

###### 1.3 Using Loops in Shell Scripts

* if ... theb ... fi
* while ... do ... done
* until ... do ... done
* case ... in ... esac
* for ... in ... do ... done 

```
#!/bin/bash

if [ -z $1 ]
then
	echo you have to provide an argument
        exit 6
fi

echo the arument is $1
```
* while example
```
#!/bin/bash

COUNTER=$1
COUNTER=$(( COUNTER * 60 ))

minusone(){
	COUNTER=$(( COUNTER - 1 ))
	sleep 1
}

while [ $COUNTER -gt 0 ]
do
	echo you still have $COUNTER seconds left
        minusone
done

[ $COUNTER = 0 ] && echo time is up && minusone
[ $COUNTER = "-1" ] && echo you now are one second late && minusone

while true
do
	echo you now are ${COUNTER#-} seconds late
	minusone
done

```
###### Lesson 1 Lab: Writing Shell Scripts

![img](https://github.com/oguzhalit/LFCS-2/blob/master/images/LFCS-17-1.png)

###### Lesson 1 Lab Solution: Writing Shell Scripts
```
cat ldapusers
cn=lisa,dc=example,dc=com
cn=amy,dc=example,dc=com
```
```
#!/bin/bash
# extract the user names
for i in $(cat ldapusers)
do
    USER=${i%%,*}
    USER=${USER#+=}
    echo $USER >> users
done

# show user creation
for j in $(cat users)
do
    echo useradd $j
done
```
### Lesson 2: Managing Local Security

###### 2.2 Configuring PAM

``` /etc/pam.d/ ``` pam configuration files
``` /lib64/security ``` all pam libraries
``` man -k pam ``` doc pam lib

###### 2.3 Working with /etc/security 

``` /etc/securetty ``` configure pam login
``` /etc/pam.d/login ``` real life example

###### 2.4 Managing Secure Mount Options

* Mount options
  - nodev - disable acces devices
  - nosuid - disable any binary that has SUID or SGID perm set
  - noexec - restricts execution of any binaries
  - ro - read-only
* Remount Reload Security Options
  - mount -o remount

``` /etc/fstab ``` change default acces to noexec
``` mount -o remount,rw /mydata/ ``` reload
``` ./mydata/runme ``` perm deny

###### Lesson 2 Lab: Managing Security


![img](https://github.com/oguzhalit/LFCS-2/blob/master/images/LFCS-18-2.png)

### Lesson 3: Configuring Networking


###### Lesson 3.2 Applying Persistent Networking

``` /etc/network/interfaces ``` managing network
``` /etc/netplan/50* ``` managing network
``` sudo netplan apply ``` apply configuration
 

###### Lesson 3.3 Using systemd-networkd

* All recent distributions can deal with systemd-networkd

* systemctl disable NetworkManager

* systemctl enable systemd-networkd

* systemctl enable systemd-resolved

* rm /etc/resolv.conf

* ln -s /run/systemd/resolve/resolv.conf /etc/resolv.conf

* mkdir /etc/systemd/network

* /etc/systemd/network/20-dhcp.network

* /etc/systemd/network/10-static-enp3s0.network

###### Lesson 3 Command Review

- ``` nmtui ```
- ``` nmcli ```
- ``` netplan ```


###### Lesson 3 Lab Managing Networking

![img](https://github.com/oguzhalit/LFCS-2/blob/master/images/LFCS-19-3.png)


### Lesson 4: Managing Advanced Systemd Features

##### Lesson 4.1 Modifying Systemd Units

* ``` systemctl show unit.type ``` - show possible unit parameters
* ``` systemctl edit unit.type ``` - change settings
* ``` systemctl daemon-reload ``` - update systemd
* ``` systemctl restart unit.type ``` restratt new settings


##### Lesson 4.2 Managing Systemd Sockets

* ``` systemctl list-unit-files | grep socket ``` list sockets

* ``` systemctl cat sshd.socket ``` view file



##### Lesson 4.3 Managing Systemd Timers

* ``` systemctl list-unit-files | grep timer ``` view timers


##### Lesson 4.4 Understanding Systemd Cgroups

* Control Groups place resources in controllers that represent the type of resource

* Some common default controllers are cpu, memory and blkio

* Systemd divides cpu, cpuacct, blkio and memory into slices
    - system for system processes and daemons
    - machine for virtual machines
    - user for user sessions


##### Lesson 4.5 Managing Systemd Unit Dependencies

* before: this unit starts before the specified unit
* after: this unit starts when the specified unit is started
* requires: when this unit starts, the unit listed here is also started
* wanted: when this units starts, the unit listed here is also started


##### Lesson 4.6 Configuring Systemd Self-Healing

``` systemctl edit unit.type```
```
|-------------------------------|
[Service] 
Restart=always 
RestartSec=3 
|-------------------------------|
```
##### Lesson 4 Lab Managing Systemd


![img](https://github.com/oguzhalit/LFCS-2/blob/master/images/LFCS-20-4.png)

### Lesson 5 Configuring Logging

##### Lesson 5.1 Configuring rsyslogd

* Settings are stored in /etc/rsyslog/rsyslog.conf
* Snap-in files can be placed in /etc/rsyslog.d
* Functionality can be extended by using modules
* Log Actions are defined using facility.priority destination
* Rsyslog supports remote logging
* Uses 514 Port Default

##### Lesson 5.2 Managing Log Rotation

* Log rotation ensures that log files are rotated when they meet certain criteria
* Upon rotation, the old files is closed and a new file is opened
* Log rotation runs as a daily cron job
* Configuration is in /etc/logrotate.conf and drop files /etc/logrotate.d

* ```logger```
* ```logrotate ```
* ```logrotate.status```

##### Lesson 5.3 Making systemd-journald Logs Persistent

* Edit /etc/systemd/journald.conf to contain the line Storage=persistent
* Create the directory /var/log/journal
* systemctl force-reload systemd-journald to reload the journal

- Managing Journal Rotation
    * SystemMaxFileSize = specifies max file size
    * SystemMaxFiles = specifies max number of files
    * MaxFileSec = specifies max time that entries will be stored in a single journal
    * SystemKeepFree = can bu used to specify a maximum amount of disk space that sholud be kept free

##### Lesson 5 Lab: Configuring Logging

![img](https://github.com/oguzhalit/LFCS-2/blob/master/images/LFCS-21-5.png)

### Lesson 6 