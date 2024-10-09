# Redirecting more output
	In this challenge, we get the flag after running `/challenge/run` but only if we redirect
its output to the file `myflag`. So after redirecting, our flag is sent to the myflag file.
But when I ran the program, we see that it print to our terminal. Over the standard error, it prints 
us all the instructions for the command. After that, to get the flag, I read the file `myfile` 
using the `cat` command.

```bash
giridhar@LAPTOP-EQ112OJM:~$ ssh -i ./key hacker@dojo.pwn.college
Connected!
hacker@piping~redirecting-more-output:~$ /challenge/run > myflag
[INFO] WELCOME! This challenge makes the following asks of you:
[INFO] - the challenge will check that output is redirected to a specific file path : myflag
[INFO] - the challenge will output a reward file if all the tests pass : /flag

[HYPE] ONWARDS TO GREATNESS!

[INFO] This challenge will perform a bunch of checks.
[INFO] If you pass these checks, you will receive the /flag file.

[TEST] You should have redirected my stdout to a file called myflag. Checking...

[PASS] The file at the other end of my stdout looks okay!
[PASS] Success! You have satisfied all execution requirements.
hacker@piping~redirecting-more-output:~$ cat myflag

[FLAG] Here is your flag:
[FLAG] pwn.college{kt4iVA03DJVWxTp0O8hwbNpLBrS.dVjN1QDL2kTN0czW}
```

## References Used:
None
