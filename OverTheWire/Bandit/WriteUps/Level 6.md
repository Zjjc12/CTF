# Level 6

The password is stored somewhere on the server

```console
bandit6@bandit:~$ ls
```
nothing.

```console
bandit6@bandit:~$ cd ..
bandit6@bandit:/home$ ls
bandit0   bandit16  bandit23      bandit29      bandit33
bandit1   bandit17  bandit24      bandit29-git  bandit4
bandit10  bandit18  bandit25      bandit3       bandit5
bandit11  bandit19  bandit26      bandit30      bandit6
bandit12  bandit2   bandit27      bandit30-git  bandit7
bandit13  bandit20  bandit27-git  bandit31      bandit8
bandit14  bandit21  bandit28      bandit31-git  bandit9
bandit15  bandit22  bandit28-git  bandit32
```
Ah wrong directory.

Let's try:
```console
bandit6@bandit:/home$ find * -size 33c
bandit0/readme
bandit1/-
bandit15/.bandit14.password
bandit16/.bandit15.password
bandit17/.bandit16.password
bandit18/readme
bandit2/spaces in this filename
bandit21/.prevpass
bandit25/.bandit24.password
find: ‘bandit27-git’: Permission denied
find: ‘bandit28-git’: Permission denied
find: ‘bandit29-git’: Permission denied
bandit3/inhere/.hidden
.......
```
That's not going to work..
```console
bandit6@bandit:/home$ find -group bandit6
find: ‘./bandit28-git’: Permission denied
find: ‘./bandit30-git’: Permission denied
find: ‘./bandit31-git’: Permission denied
find: ‘./bandit5/inhere’: Permission denied
find: ‘./bandit27-git’: Permission denied
find: ‘./bandit29-git’: Permission denied
bandit6@bandit:/home$ find -user bandit7
find: ‘./bandit28-git’: Permission denied
find: ‘./bandit30-git’: Permission denied
find: ‘./bandit31-git’: Permission denied
find: ‘./bandit5/inhere’: Permission denied
find: ‘./bandit27-git’: Permission denied
find: ‘./bandit29-git’: Permission denied
```
Why is permission denied?

It could be at the root directory...

```console
bandit6@bandit:/$ find . -size 33c -group bandit6 -user bandit7 | grep bandit7 | grep password
find: ‘./run/lvm’: Permission denied
find: ‘./run/screen/S-bandit23’: Permission denied
find: ‘./run/screen/S-bandit19’: Permission denied
find: ‘./run/screen/S-bandit16’: Permission denied
find: ‘./run/screen/S-bandit20’: Permission denied
find: ‘./run/screen/S-bandit24’: Permission denied
find: ‘./run/shm’: Permission denied
find: ‘./run/lock/lvm’: Permission denied
find: ‘./var/spool/rsyslog’: Permission denied
find: ‘./var/spool/cron/crontabs’: Permission denied
find: ‘./var/log’: Permission denied
find: ‘./var/tmp’: Permission denied
find: ‘./var/cache/ldconfig’: Permission denied
find: ‘./var/cache/apt/archives/partial’: Permission denied
find: ‘./var/lib/apt/lists/partial’: Permission denied
find: ‘./var/lib/polkit-1’: Permission denied
find: ‘./cgroup2/csessions’: Permission denied
find: ‘./home/bandit28-git’: Permission denied
find: ‘./home/bandit30-git’: Permission denied
find: ‘./home/bandit31-git’: Permission denied
find: ‘./home/bandit5/inhere’: Permission denied
find: ‘./home/bandit27-git’: Permission denied
find: ‘./home/bandit29-git’: Permission denied
find: ‘./tmp’: Permission denied
find: ‘./lost+found’: Permission denied
find: ‘./root’: Permission denied
find: ‘./etc/ssl/private’: Permission denied
find: ‘./etc/lvm/backup’: Permission denied
find: ‘./etc/lvm/archive’: Permission denied
find: ‘./etc/polkit-1/localauthority’: Permission denied
find: ‘./sys/fs/pstore’: Permission denied
find: ‘./proc/tty/driver’: Permission denied
find: ‘./proc/7525/task/7525/fd/6’: No such file or directory
find: ‘./proc/7525/task/7525/fdinfo/6’: No such file or directory
find: ‘./proc/7525/fd/5’: No such file or directory
find: ‘./proc/7525/fdinfo/5’: No such file or directory
find: ‘./boot/lost+found’: Permission denied
./var/lib/dpkg/info/bandit7.password
```
At the bottom...
```console
bandit6@bandit:/$ cat ./var/lib/dpkg/info/bandit7.password
HKBPTKQnIay4Fw76bEy8PVxKEDQRKTzs
```
Got it.


