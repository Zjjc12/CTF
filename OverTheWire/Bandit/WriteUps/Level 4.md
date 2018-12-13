# Level 4

The level goal is to find password in a human-readable file in inhere directory.

Lets try:
```console
bandit3@bandit:~$ ls
inhere
```
Ok, then:
```console
bandit3@bandit:~$ cd inhere
```
Then:
```console
bandit4@bandit:~/inhere$ ls
-file00  -file02  -file04  -file06  -file08
-file01  -file03  -file05  -file07  -file09
```
Lets try one:
```console
bandit4@bandit:~/inhere$ cat -file00
cat: invalid option -- 'f'
Try 'cat --help' for more information.
```
wait forgot..
```console
bandit4@bandit:~/inhere$ cat ./-file00
����������~%	C[�걱>��| �
```
Hmmmmm...
```console
bandit4@bandit:~/inhere$ file ./-file00
./-file00: data
```
Seems like random garbage. Cat -vt doesn't seem right.

Lets try:
```console
bandit4@bandit:~/inhere$ ls -h
-file00  -file02  -file04  -file06  -file08
-file01  -file03  -file05  -file07  -file09
```
Nope
```console
bandit4@bandit:~/inhere$ file *
file: Cannot open `ile00' (No such file or directory).
file: Cannot open `ile01' (No such file or directory).
file: Cannot open `ile02' (No such file or directory).
file: Cannot open `ile03' (No such file or directory).
file: Cannot open `ile04' (No such file or directory).
file: Cannot open `ile05' (No such file or directory).
file: Cannot open `ile06' (No such file or directory).
file: Cannot open `ile07' (No such file or directory).
file: Cannot open `ile08' (No such file or directory).
file: Cannot open `ile09' (No such file or directory).
```
Ahh the filename

How about:
```console
bandit4@bandit:~/inhere$ cat ./*
����������~%	C[�걱>��| ����U"7�w���H��ê�Q��(���#����T�v��(�ִ�����A*�
2J�Ş؇_�y7�.A��u��#���w$N?c�-��Db3��=���=<�W�����ht�Z��!��{�U�+��pm���;��:D��^��@�gl�Q��@�%@���ZP*E��1�V���̫*����koReBOKuIDDepwhWk7jZC0RTdopnAYKh
FPn
    '�U���M��/u
               XS
�mu�z���хN�{��Y�d4�����]3�����9(�
```
There it is:
```
koReBOKuIDDepwhWk7jZC0RTdopnAYKh
```


