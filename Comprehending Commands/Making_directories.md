# Making Directories
Directories can be made used `mkdir` command like a file being made used `touch` command.
	In this challenge, we created a dictionary `/tmp/pwn` using mkdir and made a file *college*
in it using *touch* command. Then atlast, I invoked the program `/challenge/run` to cross check the solution and get the flag.

```bash
giridhar@LAPTOP-EQ112OJM:~$ ssh -i ./key hacker@dojo.pwn.college
Connected!
hacker@commands~making-directories:~$ mkdir /tmp/pwn
hacker@commands~making-directories:~$ cd /tmp/pwn
hacker@commands~making-directories:/tmp/pwn$ touch college
hacker@commands~making-directories:/tmp/pwn$ /challenge/run
Success! Here is your flag:
pwn.college{ch0zTbjy0OXaBMf310EOb2na_OC.dFzM4QDL2kTN0czW}
```

## References Used:
None
