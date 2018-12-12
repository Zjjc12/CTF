# Level 1

The level goal is to find a file called "-"

I tried:
```console
bandit0@bandit:~$ find
.
./readme
./.bash_logout
./.profile
./.bashrc
```

After looking through the files I found nothing interesting.

I realized that I was still on level 0 made me very sad :(

I logged into level 2 using the level 1 password:

```console
zjjc123@kali:~$ ssh bandit1@bandit.labs.overthewire.org -p 2220
```

Success

Next I listed the files in the home directory:

```console
bandit1@bandit:~$ ls
-
```

It showed the file.

So I tried:

```console
bandit1@bandit:~$ cat -
```

Unresponsive... Weird...

Maybe

```console
bandit1@bandit:~$ cat "-"
```

Nope....

Oh... I searched up "-" filename and realized that it refers to STDIN/STDOUT
so to open it:

```console
bandit1@bandit:~$ cat ./-
CV1DtqXWVFXTvM2F0k09SHz0YwRINYA9
```

Got it :)

Now I just need to remember to ssh into the next level:

```console
zjjc123@kali:~$ ssh bandit2@bandit.labs.overthewire.org -p 2220
```

Done!



