# Matching with *
We are learning about `*` glob. When it encounters a * character in any argument, the shell treat it as a wildcard and try to replace the argument with any files that match the pattern. Basically * fills up for a set of characters that matches with any file.
	In this challenge, I needed to first go to `challenge` directory, but the catch is, we are not allowed to use more than 4 characters in arguments, so we need to use * glob to access that directory.
After that, I just invoked the program run.

```bash
giridhar@LAPTOP-EQ112OJM:~$ ssh -i ./key hacker@dojo.pwn.college
Connected!
This challenge resets your working directory to /home/hacker unless you change
directory properly...
hacker@globbing~matching-with-:~$ cd /c*
hacker@globbing~matching-with-:/challenge$ /run
ssh-entrypoint: /run: Is a directory
hacker@globbing~matching-with-:/challenge$ cd /ru*
hacker@globbing~matching-with-:/run$ cd *
ssh-entrypoint: cd: too many arguments
hacker@globbing~matching-with-:/run$ cd /*/*
ssh-entrypoint: cd: too many arguments
hacker@globbing~matching-with-:/run$ cd ~
hacker@globbing~matching-with-:~$ cd /c*
hacker@globbing~matching-with-:/challenge$ /run
ssh-entrypoint: /run: Is a directory
hacker@globbing~matching-with-:/challenge$ ./run
You ran me with the working directory of /challenge! Here is your flag:
pwn.college{Y7Bl-XhiOXtO1Yx6sMTMKIS6jHE.dFjM4QDL2kTN0czW}
```
## References Used:
None
