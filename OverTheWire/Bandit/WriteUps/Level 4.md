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
Searched around for a bit found cat -vt
```console
bandit4@bandit:~/inhere$ cat -vt ./-file00
pCM-5M-D^MM-hM-wM-,M-^BM-(M-0M-^^M-^@^SM-tM-&~%^I^SC[M-'M-jM-1M-1>M-zM-P^D| M-^T
```
Seems legit
```console
bandit4@bandit:~/inhere$ cat -vt ./-file01
M-;M-^XM-XU"7M-"w^YM-bM-ZM-^HM-^AM-+M-CM-*M-PQM-^PM-tM-^MM-^B(M-^Q^DM-lM-D#M-&M--M-R^@bandit4@bandit:~/inhere$ cat -vt ./-file02
M-i^^T^_M-^^vM-^ZM-^M(M-qM-VM-4M-2M-^BM-^[M-^CM-lA*M-^U
2^UJM-^IM-EM-^^M-XM-^G_M-5y7bandit4@bandit:~/inhere$ cat -vt ./-file03
M-iM-^V.AM-^HM-iuM-^^M-|#M-gM-U^\M-Ew$N?cM-^C-M-^]M-;Db3^TM-^KM-`=M-v^BM-xbandit4@bandit:~/inhere$ cat -vt ./-file04
M-^N=<M-B^HM-^KWM-^^GM-uM-V^P^@M-^GM-#htM-^D^GZM-^SM-^S!^X^PM-^UM-[{^YM-^VU^KM-xbandit4@bandit:~/inhere$ cat -vt ./-file05
+^T^CM-,M-;p^C^Pm^^^AM-^?M-8M-^G;^QM-]M-l:DM-^XM-x^M-^ZM-:@^@M-bglM-]QM-kbandit4@bandit:~/inhere$ cat -vt ./-file06
M-^\^EM-)@M-9%@M-dM-ZM-M^XZP*E^B^BM-&M-s1M-CVM-^CM-^YM-^WM-LM-+*M-&M-.M-^I^YM-[
```
```console
bandit4@bandit:~/inhere$ cat -vt ./-file07
koReBOKuIDDepwhWk7jZC0RTdopnAYKh
```
Try it:

```console
zjjc123@kali:~$ ssh bandit5@bandit.labs.overthewire.org -p 2220
```
Works

