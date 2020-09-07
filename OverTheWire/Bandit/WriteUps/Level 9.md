# Level 9

The password for the next level is stored in the file data.txt in one of the few human-readable strings, preceded by several ‘=’ characters.

Lets try using strings first
```console
bandit9@bandit:~$ strings data.txt
Z/,_
WW"&8
...
...
```
The key is already available but there has to be a way to filter the '='

Let's try piping strings to grep

```console
bandit9@bandit:~$ strings data.txt | grep ===
========== the*2i"4
========== password
Z)========== is
&========== truKLdjsbJ5g7yyJ2X2R0o3a5HQJFuLk
```
Let's GOOO!
