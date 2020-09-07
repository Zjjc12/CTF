# Level 8

The password for the next level is stored in the file data.txt and is the only line of text that occurs only once

```console
bandit6@bandit:~$ ls
data.txt
```
Tried catting it, a lot of lines

Lets try sorting and then filtering using uniq:
```console
bandit8@bandit:~$ cat data.txt | sort | uniq -u
UsvVyFSfZZWbi6wgC7dAFyFuR6jQQUhR
```
Nice!
```console
zjjc123@kali:~$ ssh bandit9@bandit.labs.overthewire.org -p 2220
```