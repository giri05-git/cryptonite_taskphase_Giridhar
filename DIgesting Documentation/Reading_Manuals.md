# Reading Manuals
We are introduced to `man` command. *man* is the short for *manual*, and as the name suggests, it will give us the whole info(manual) on the command we are passing as argument. All the manpages are stored in
a database which lives in the `usr/share/man` directory but no commands require its actual path to be entered in its terminal to get its manpage. Moreover, giving the actual path can result in some random stuff being displayed.
	In this challenge, I was asked to get the flag from `/challenge/challenge` but the argument to be given to it was a surprise, so I went to the manpage for `challenge` to get an idea on what to give as argument. There, I saw an argument `--lwkzxn NUM` which would give the flag if the NUM is 751.
So from there, I realised that *--lwkzxn* was the argument and 751 was the argument to this argument. Doing this earned me the flag.

```bash
giridhar@LAPTOP-EQ112OJM:~$ ssh -i ./key hacker@dojo.pwn.college
Connected!
man hacker@man~reading-manuals:~$ man challenge

CHALLENGE(1)                                      Challenge Commands                                     CHALLENGE(1)

NAME
       /challenge/challenge - print the flag!

SYNOPSIS
       challenge OPTION

DESCRIPTION
       Output the flag when called with the right arguments.

       --fortune
              read a fortune

       --version
              output version information and exit

       --lwkzxn NUM
              print the flag if NUM is 751

AUTHOR
       Written by Zardus.

REPORTING BUGS
       The repository for this dojo: <https://github.com/pwncollege/linux-luminarium/>

SEE ALSO
       man(1) bash-builtins(7)
hacker@man~reading-manuals:~$ /challenge/challenge -lwkzxn 751
Incorrect usage! Please read the challenge man page!
hacker@man~reading-manuals:~$ /challenge/challenge --lwkzxn 751
Correct usage! Your flag: pwn.college{ARAlwXkOPzCx_7n5iI1bDOidH1_.dRTM4QDL2kTN0czW}
```

## References Used:
None
