# Redirecting Errors 
Like redirecting output, we can also redirect error channel of commands. File Descriptor number is a number is used to describe a communication channel in Linux. It is done by giving its number along with the `>`.
	In this challenge, I redirected the output of `/challenge/run` to *myflag* by using `>` and redirected its *errors* to *instructions* by using `2>`. After that, I read the myflag file which contains flag value.

```bash
giridhar@LAPTOP-EQ112OJM:~$ ssh -i ./key hacker@dojo.pwn.college
Connected!
hacker@piping~redirecting-errors:~$ /challenge/run > myflag 2> instructions
hacker@piping~redirecting-errors:~$ cat flag
cat: flag: No such file or directory
hacker@piping~redirecting-errors:/challenge$ /challenge/run
[INFO] WELCOME! This challenge makes the following asks of you:
[INFO] - the challenge will check that output is redirected to a specific file path : myflag
[INFO] - the challenge will check that error output is redirected to a specific file path : instructions
[INFO] - the challenge will output a reward file if all the tests pass : /flag

[HYPE] ONWARDS TO GREATNESS!

[INFO] This challenge will perform a bunch of checks.
[INFO] If you pass these checks, you will receive the /flag file.

[TEST] You should have redirected my stdout to a file called myflag. Checking...

[FAIL] You did not satisfy all the execution requirements.
[FAIL] Specifically, you must fix the following issue:
[FAIL]   You have not redirected anything for this process' stdout.
hacker@piping~redirecting-errors:/challenge$ cd /home/hacker
hacker@piping~redirecting-errors:~$ cat myflag

[FLAG] Here is your flag:
[FLAG] pwn.college{8oPxnlF0ycOKoQPzCAXZSw8P9Pe.ddjN1QDL2kTN0czW}
```

## References Used:
None
