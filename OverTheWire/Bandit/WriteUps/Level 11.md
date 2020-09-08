# Level 11

The password for the next level is stored in the file data.txt, where all lowercase (a-z) and uppercase (A-Z) letters have been rotated by 13 positions

Here's a more difficult one. So in rot13, the characters get rotated by 13 letters, halfway through the alphabet, in both uppercase and lowercase.
Linux has this one handled too. You can map one set of characters to another set of characters, and linux will automatically translate it for you.

Now, we want to map letters n-z + a-m to A-Z, and map letters  N-Z + A-M to A-Z. We could type these all out into two sets going like so:

```console
bandit11@bandit:~$ cat data.txt|tr 'npqrstuvwxyzabcde...KLM' 'ABCDEFGHI...XYZ'
```

But that seems like a lot of work. Linus allows you to use dashes to specify ascii character ranges to translate. 
Since the entire uppercase and lowercase alphabet is right next eachother, that makes things considerably simpler.

```console
bandit11@bandit:~$ cat data.txt|tr 'n-za-mN-ZA-M' 'a-zA-Z'
The password is 5Te8Y4drgCRfCx8ugdwuEX8KFC6k2EUu
```