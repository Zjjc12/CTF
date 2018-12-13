# Level 3

The level goal is to find a hidden file in the inhere directory.

I first tried:
```console
bandit3@bandit:~$ ls
inhere
```
Ok, then:
```console
bandit3@bandit:~$ cd inhere
```
The file is hidden so:
```console
bandit3@bandit:~/inhere$ ls -a
.  ..  .hidden
```
Ha gottem:
```console
bandit3@bandit:~/inhere$ cat .hidden
pIwrPrtPN36QITSp3EQaw936yaFoFgAB
```
```console
zjjc123@kali:~$ ssh bandit4@bandit.labs.overthewire.org -p 2220
```


