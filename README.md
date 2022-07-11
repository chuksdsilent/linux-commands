# Linux Commands

To list all files and folders

```
ls -al /tmp

```

- ls = command
- -l = option
- -a = display hidden files
- /temp - argument

To create a directory

```
mkdir directory_name

```

To remove a File

```
rm file_name

```

To delete a directory

```
rm -r directory_name

```

-r - recursive

To remove empty directory

```
rmdir directory_name

```

To Enter a directory

```
cd directory_name

```

To know who loggedin into you system in the past

```
last

```

To know your username

```
whoami

```

Prompt

[student@localhost ~]$ <br />

- student = username
- localhost = computer name
- ~ = location
- $ = loggedin user is a non root user

* \# = loggedin user is root

To know who is looged in into the server

```
who

```

To know what the user is doing

```
w

```

To know the name of your server

```
hostname

```

To know the kernel version of your system

```
username -r

```

-r - revision number

To know the date/time in the serve

```
date

```

To know the ip address of your server

```
ip a

```

To check internet connectivity

```
ping google.com

```

To see all the command you typed

```
history

```

To display present working directory

```
pwd

```

To move to root directory

```
cd / or cd ~

```

To switch user

```
su ${username}

```

To switch to root user

```
su - root // This is not a good practice

```

To switch to root

```
sudo su - root

su means switch user

```

To logout

```
ctrl+d or logout or exit

```

To add a new user

```
sudo useradd ${username}

```

Non-root users have limited priviledges - run limited command

To add a user

```
sudo useradd ${username}

```

when using sudo everything is logged.

To give a user password

```
sudo passwd ${username}

```

To remove everything inside a directory

```
rm -rf \* directory_name

```

To find a word in a file

```
grep ${search_word} ${file_path}

```

To get the line number where the word appeared

```
grep -n {search_word} ${file_path}

```

- -i = ignore the case
- -n = show the line number
- -o = only occurance
- -v = ignore the word

To copy file from one location to another

```
cp ${source} ${destination}

```

To copy all the items of a directory to another location

```
cp -rv ${source} to ${destination}

```

- -r = recursive
- -v = variable

To copy all the items of a directory to another location with the folder

```
mv ${source} ${destination}

```

To create nested directory

```
mkdir -p directory/directory

```

- -p = create parent directory

To create alias

```
alias ld='ls -al'

```

To see all alias commands

```
alias

```

VI Editor <br />
VI - Visual Instrument <br />
VIM - visual instrument improved <br />

```
- insert mode = to make changes (a, i insert) <br />
- command mode = to save the file, close the file, show line number etc.
  To exist insert mode
  esc key
  To Save file
  :w
  To quit
  :q
  To save and quit
  :wq
  To undo
  press u
  To delete a line
  press d twice
  To display the line number
  :se nu
  To exit without saving
  :q!
```

To know the name of your operating system

`cat /etc/os-release`

To find the current version

`uname -r`

- -r = revision

To see the user

`id ${username}`

```
User pasword and groups are stored in etc folder
user
-> passwd (/etc/)
-> group (/etc/)
```

To check user details

```
grep ${username} /etc/passwd

```

Output

- student:x:1000:1000:tudent:/home/student:/bin/bash

- 1st -username
- 2nd - passwd
- 3rd - uid
- 4th - gid
- 5th - command
- 6th - location of home directory
- 7th - name of the shell assigned to the user

To Know the user group

```
grep user2 /etc/group

```

Output

`wheel::10:student`

- 1st - name of the group
- 2nd - password
- 3rd - group id
- 4th - users that are part of the group

To Know the user group

```
grep user2 /etc/shadow

```

Output

chuks:$8EuYko8Y9dWhj0:1906:1:99999:7:::

- 1 - username
- 2 - password hash (99999 - never expire)
- 3 - last pass change date details
- 4 - min days between password change
- 5 - pass expiration in days
- 6 - warning days
- 7 - password inactive date
- 8 - account inactive date

### How to change the detail above

list all details

```
chage -l ${username}

```

How to change the detail above

```
chage ${username} and follow the prompt

```

To change the password of the root user

```
sudo su - root

```

ldap - lightweight Directory Access Protocol

To see your type of user

```
which useradd

```

To add a user

```
sudo su - root
useradd ${username}

```

To set user password

```
sudo passwd ${username}

```

To add a user to a group

```
usermod -G group1,group1 -u 2500 -c "comment" -s /usr/bin/sh ${username}

```

- -c = modify comments
- -g = modify primary group
- -G = modify secondary group
- -a = retain all secondary group
- -u = uid
- -s = shell
- -d = /${username}

How to create a group

```
groupadd ${groupname}

```

To verify

```
grep ${groupname} /etc/group

```

How to delete a group

```
groupdel ${groupname}

```

To Delete a user

```
userdel -r ${username}

```

To open sudo file

```
visudo

```

Why Linux is secure

1. file level security - permission(basic, ACL, Special) <br />
2. SElinux - what is happening inside OS <br />
3. firewall - filters network traffic <br />

Things attached to a file

- who is the owner
- who is the group owner
- what are the permission on the file

Permissions in linux

- read - r = 4
- write - w = 2
- execute - x = 1
- read-write - rw = 6
- read-execute - rx = 5
- read-write-execute - rwx = 7
- no permission - 0

- owner - u
- group - g
- others - o
- all - a

To change user permission

- owner - oshabz - rw -rw
- group - oshabz - rw - r
- others - r - r

To display information about a file

```
stat ${filename}

```

To change the user's permission

```
sudo chmode 660 ${filename}

```

To change the group owner of a file

```
chown ${owner_name}:${group_name} ${file_name};

```

### Chaning and Piping command

use semicolon to chain commands

```
cd new_folder; npm run start; code .
```

Piping
This takes output from left and use it as input on the right

```
ls -l | grep rpc

grep bash /etc/passwd | wc -l

```

how to get number of character and words

```
wc /etc/passwd

```

To print out data in a file

```
ls -l abc >out.txt 2> error.log

```

single greater than(>) means replace the previous text

```
grep bash /etc/passwd | wc -l > out.txt

```

Double greater than(>) means append

```
grep bash /etc/passwd | wc -l >> out.txt

```

To save the error in error log

```
grep bash /etc/passwd | wc -l >> out.txt 2>> error.log

```

To Check the CPU

```
lscpu

```

To check RAM

```
free -h

```

To check your computer serial number

```
dmidecode -t1

```

To know the disk status

```
df -h

```

To check the hard disk and ram in your system

```
lsblk

```

To mount a device

```
sudo su - root

```

To mount drive

```
mount ${source} ${destination}

```

Ignore all lines that contains tmpfs

```
df -h | grep -v tmpfs

```

To check disc usage

```
du -sh \

```

To check disk in human readable form

```
df -h

```

Type of users

Root(Admin) <br />
Non-root <br />
system/application <br />

- System user cn not login (because they dont have login shell. They are created for support of application)

To check the number of users that can login

```
grep bash /etc/passwd | wc -l

```

To check the users who cant login

```
grep nologin /etc/passwd | wc -l

```

Find is used to find and perform actions while locate can only output the search

To find and perform an action

```
find ${start_search_from} ${options} ${what_to_find} ${what_action_to_take}

```

To search for a file/diectory

```
find / -name type  -d $(file_name.ext)
```

To search a file with permission

```
find /home type f -perm 644
```

To change the permission of a file with the file command

```
find / -type f -print -perm 666 -exec chmod 644 {} \;

```

To locate a file

First update database by using the following command

```
updatedb
```

To locate a file

```
locate ${file_name}
```

To get date and time details

```
timedatectl
```

To create multiple files

```
touch filename{1..10}
```

Inodes are used to store file meta data like filename, file size etc

To get inode folders

```
df -hi
```

Link is the same thing as shortcut

Wildcard

To delete file starting with a text

```
rm -f ${filename_starting_with}*

```

To copy files that start with a text

```
cp ${filename_starting_with}* ${location}
```

To delete all files in a folder

```
rm -f *
```

To display a file with a single character in filename

```
ls -l ?
```

To display filename starting with a range of character

```
ls -l [ax]*
```

This mean list all file name that start with a and also file name that start with x

To create a range of files

```
touch filename{1..10}
```
