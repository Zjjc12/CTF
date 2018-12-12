# Level 1

The level goal said that "The password for the next level is stored in a file called - located in the home directory"

I looked for files in teh home directory and found:

```console
bandit0@bandit:~$ ls
readme
```

And it showed a file called readme

So then I read it using cat:

```console
bandit0@bandit:~$ cat readme
boJ9jbbUNNfktd78OOpsqOltutMc3MY1
```

Found the password for the next level
```
boJ9jbbUNNfktd78OOpsqOltutMc3MY1
```