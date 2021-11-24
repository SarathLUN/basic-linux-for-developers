# Basic Linux for Developers
Date: 1 full-day on 2021-11-27 09:00 AM ;  Location: EZECOM HQ

## Objectives:

- To share some basic command lines those are needed for daily development operation
- Almost every server are linux
- We may full stack from infrastructure upto coding
- IaaC (Infrastructure as a Code) start from this too

## 1. user and login

- create user

```shell
useradd -m $username # Ex: useradd -m tony.stark, this will create user along with home directory
```

- set password

```shell
passwd $username # Ex: passwd tony.stark, then enter the password and confirm password
```

- add group member

```shell
usermod -G sudo $username # add user to group sudo
```

- login

```shell
ssh $username@$IP_address # not recommended to use IP, instead should use hostname
ssh $username@$hostname # default port ssh = 22
ssh -p $port_number $username@$hostname # custom port ssh
```

- switch user

```shell
sudo -i # switch to user root
```

## 2. exploration

- current directory

```shell
pwd # show the path of current working directory
```

In path, `.` is referred to current directory, while `..` is refer to parent directory (1 level up).

- change directory

Linux file system will start with root `/`, check more detail on directory structure [here](https://www.howtogeek.com/117435/htg-explains-the-linux-directory-structure-explained/)

```shell
cd /home/tony.stark # this will change directory to the home directory of user 'tony.stark'
cd . # change directory to current directory, mean no going anywhere
cd .. # change directory to parent directory in 1 level up
cd ../.. # change directory to parent directory in 2 levels up
```

- hidden

In linux, hidden file will be indicated by `.` prefix of the name of file or directory `.file_name`, `.directory_name`

```shell
drwxr-xr-x   13 sarath  staff   416B Nov 23 16:55 .git # this is a hidden directory
-rw-r--r--    1 sarath  staff   620B Nov  6 22:11 .gitignore # this is a hidden file
```

- list

```shell
ls # list out in column base layout of files & sub-directories in current directory 
ls -l # list out in detail base layout of files & sub-directories in current directory
ls -la # list out in detail base layout of files & sub-directories (including hidden) in current directory
```

- tree view

```shell
tree . # tree view of current directory
```

Some linux may not install `tree` by default, however we still can install via its package manager

```shell
yum install tree # for RedHat family
apt install tree # for Debian family
```

also check more detail about default package manager [here](https://www.makeuseof.com/tag/power-choice-power-package-management/).

## 3. operation file and folder

- create file
- update file
- remove file
- create directory
- remove directory
- copy
- move

## 4. permission
## 5. service and process
## 6. connection check
