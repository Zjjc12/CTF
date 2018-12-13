# Level 5

The level goal is to find password under "inhere" with special properties

Lets try:
```console
bandit5@bandit:~$ ls
inhere
bandit5@bandit:~$ cd inhere
bandit5@bandit:~/inhere$ ls
maybehere00  maybehere04  maybehere08  maybehere12  maybehere16
maybehere01  maybehere05  maybehere09  maybehere13  maybehere17
maybehere02  maybehere06  maybehere10  maybehere14  maybehere18
maybehere03  maybehere07  maybehere11  maybehere15  maybehere19

bandit5@bandit:~/inhere$ cd maybehere00
bandit5@bandit:~/inhere/maybehere00$ ls
-file1  -file2  -file3  spaces file1  spaces file2  spaces file3
```
I'm not looking through individual files:
```console
bandit5@bandit:~/inhere$ file ./maybehere**/*
./maybehere00/-file1:       ASCII text, with very long lines
./maybehere00/-file2:       ASCII text, with very long lines
./maybehere00/-file3:       PGP\011Secret Key -
./maybehere00/spaces file1: ASCII text, with very long lines
./maybehere00/spaces file2: ASCII text, with very long lines
./maybehere00/spaces file3: data
./maybehere01/-file1:       ASCII text, with very long lines
./maybehere01/-file2:       ASCII text
./maybehere01/-file3:       data
./maybehere01/spaces file1: ASCII text, with very long lines
./maybehere01/spaces file2: ASCII text, with very long lines
./maybehere01/spaces file3: data
./maybehere02/-file1:       ASCII text, with very long lines
./maybehere02/-file2:       X1 archive data
./maybehere02/-file3:       data
./maybehere02/spaces file1: ASCII text, with very long lines
./maybehere02/spaces file2: ASCII text, with very long lines
./maybehere02/spaces file3: data
./maybehere03/-file1:       ASCII text, with very long lines
./maybehere03/-file2:       ASCII text, with very long lines
./maybehere03/-file3:       data
./maybehere03/spaces file1: ASCII text, with very long lines
./maybehere03/spaces file2: ASCII text, with very long lines
./maybehere03/spaces file3: data
./maybehere04/-file1:       ASCII text, with very long lines
./maybehere04/-file2:       ASCII text, with very long lines
./maybehere04/-file3:       data
.......
```
./maybehere00/-file3 and ./maybehere02/-file2 seems interesting
```console
bandit5@bandit:~/inhere$ cat ./maybehere00/-file3
```
nothing interesting...

Try finding any file file with byte size 1033 by passing du to grep:
```console
du -b ./maybehere**/* | grep -e 1033
```
The file size seems important...

Google search time:
```console
bandit5@bandit:~/inhere$ find * -size 1033
```
Need c for bytes
```console
bandit5@bandit:~/inhere$ find * -size 1033c
maybehere07/.file2
```
```console
bandit5@bandit:~/inhere$ cat maybehere07/.file2
DXjZPULLxYr17uwoI01bNLQbtFemEgo7
```
Finally
```console
zjjc123@kali:~$ ssh bandit6@bandit.labs.overthewire.org -p 2220
```
