# Level 0

I was met with a welcome screen of with the gaol of the game to log using ssh. An IP address, an user name, a password, and a port was given. First I figured that I had to ssh to the host.

I tried :

```
ssh bandit0@bandit.labs.overthewire.org
```

And I was met with:

```
bandit0@bandit.labs.overthewire.org: Permission denied (publicly, password).
```

After a bit of time I realized that my default port was probably 22 so then I ran:

```
ssh bandit0@bandit.labs.overthewire.org -p 2220
```

After entering the password I was greeted with the welcome screen.
