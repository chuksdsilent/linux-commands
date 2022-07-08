## Linux Commands

In Linux extions are not mandatory when creating a file in terminal

list all files and folders <br /> 
ls -l /tmp
ls - command
-l - option
-a = display hidden files
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
options
-i = ignore the case
-n = show the line number
-o = only occurance
-v = ignore the word

To copy from one location to another
cp ${source} ${destination}

To copy all the items of a directory to another location
cp -rv /usr/bin/ to ${destination}
-r = recursive
-v = variable


To copy all the items of a directory to another location with the folder
mv ${source} ${destination}

To create nexted directory
mkdir -p directory/directory
options
-p = create parent directory

To create alias
alias ld='ls -al'

To see all alias commands
alias

VI Editor
VI - Visual Instrument
VIM - visual instrument improved

- insert mode = to make changes (a, i  insert)
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

To know the name of your operating system
cat /etc/os-release

To find the current version
uname -r
option
-r = revision