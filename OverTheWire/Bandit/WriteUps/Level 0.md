# Level 0

The level goal said that "The password for the next level is stored in a file called "readme"

I looked for files in the home directory and found:

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