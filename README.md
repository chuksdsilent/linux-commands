## Linux Commands

In Linux extions are not mandatory when creating a file in terminal

list all files and folders <br /> 
ls -l /tmp
ls - command
-l - option
/temp - argument

To create a directory
mkdir directory_name

To remove a File
rm file_name

To delete a directory
rm -r directory_name
-r - recursive

To remove empty directory
rmdir directory_name

To Enter a directory
cd directory_name

To know who loggedin into you system in the past
last

To know your username
whoami

prompt
[student@localhost ~]$
student - username
localhost - computer name
~ - location
$ - loggedin user is a non root user
# - loggedin user is root

To know who is looged in into the server
who

To know what the user is doing
w

To know the name of your server
hostname

To know the kernel version of your system
username -r
-r - revision number

To know the date/time in the serve
date

To know the ip address of your server
ip a

To check connectivity
ping google.com

To see all the command you typed
history

To display present working directory
pwd

To move to root directory
cd / or cd ~

To switch user
su ${username}
su - root // This is not a good practice

To switch to root
sudo su - root

su means switch user
- means load the environment
root means arg

To logout
ctrl+d or logout or exit

To add a new user
sudo useradd ${username}

Non-root users have limited priviledges
	- run limited command
	
To add a user
sudo useradd ${username}

when using sudo everything is logged.


To give a user password
sudo passwd ${username}
Enter the password

To remove everything inside a directory 
rm -rf * directory_name

To find a word in  a file
grep ${search_word} ${file_path}

To get the line number where the word appeared
grep -n {search_word} ${file_path}