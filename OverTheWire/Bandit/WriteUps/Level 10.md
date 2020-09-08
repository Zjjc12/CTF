# Level 10

The password for the next level is stored in the file data.txt, which contains base64 encoded data

Seems relatively simple. There's a base64 function provided in linux. The -d argument decodes  a base 64 file.

```console
bandit10@bandit:~$ base64 -d data.txt
The password is IFukwKGsFW8MOq3IRFqrxE1hxTNEbUPR
```