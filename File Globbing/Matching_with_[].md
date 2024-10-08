# Matching with []
Square brackets are, limited form of ?, in which instead of matching any character,[] is a wildcard for some subset of potential characters, specified within the brackets.
	In this challenge, we need to change our working directory `/challenge/files` and then we
need to run `/challenge/run` but the argument with just one glob should help us get the file_b,file_a,
file_s, and file_h.

```bash
giridhar@LAPTOP-EQ112OJM:~$ ssh -i ./key hacker@dojo.pwn.college
Connected!
This challenge resets your working directory to /home/hacker unless you change
directory properly...
hacker@globbing~matching-with-:~$ cd /?ch
You used either the 'c', 'l', or '*' characters. Disallowed!
This challenge resets your working directory to /home/hacker unless you change
directory properly...
hacker@globbing~matching-with-:~$ cd /?ha??enge
hacker@globbing~matching-with-:/challenge$ ./run
You ran me with the working directory of /challenge! Here is your flag:
pwn.college{cRf2hOOWihtguOuTD1LjagVhtLy.dJjM4QDL2kTN0czW}
```

## References Used:
None
