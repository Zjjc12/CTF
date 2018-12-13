# Level 7

The password is stored in data.txt next to the word millionth

```console
bandit6@bandit:~$ ls
data.txt
```
Tried catting it, would not recommend.
```console
bandit7@bandit:~$ stat data.txt
  File: data.txt
  Size: 4184396
  .....
```
Lets try grep:
```console
bandit7@bandit:~$ strings data.txt | grep millionth
millionth	cvX2JJa4CFALtqS87jk27qwqGhBM9plV
```
Easy W
```console
zjjc123@kali:~$ ssh bandit8@bandit.labs.overthewire.org -p 2220
```