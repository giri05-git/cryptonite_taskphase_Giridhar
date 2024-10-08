# Matching with ?
? character in argument is treated a single-character wildcard by the shell. That is similar logic to 
* but unlike *, single character.
	In this challenge, I was asked to invoke the program run first after moving to directory
*challenge*. But this challenge doesn't allow us to use *c* and *l* in the argument, instead we have to use ? there.

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
