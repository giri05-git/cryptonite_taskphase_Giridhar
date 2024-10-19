# Executable Shell Scripts
Everytime we can't use bash to get the output since it is difficult, so in order to avoid so, all you need to do is, make it executable and like we used to do it in the previous *pondering path* module, we can give the absolute path of the shell file to get the output.
	In this challenge, I made the shell script `x.sh`. And I wrote the lines
				`#!/bin/bash
				 /challenge/solve`
in it, made sure user was given executable permissions and I gave its path as a command invoking the shell.

```bash
giridhar@LAPTOP-EQ112OJM:~$ ssh -i ./key hacker@dojo.pwn.college
Connected!
hacker@chaining~executable-shell-scripts:~$ nano x.sh
hacker@chaining~executable-shell-scripts:~$ ls -l
total 40
-rw-r--r-- 1 hacker hacker    4 Oct  8 20:37 COLLEGE
-rw-r--r-- 1 hacker hacker   45 Oct 14 20:12 PWN
-rw-r--r-- 1 hacker hacker    0 Oct  5 20:59 college
-rw-r--r-- 1 root   hacker   58 Oct 15 11:39 f
lrwxrwxrwx 1 hacker hacker   15 Oct  5 21:17 flag -> /challenge/flag
-rw-r--r-- 1 hacker hacker   27 Oct  9 14:20 grep
-rw-r--r-- 1 hacker hacker  829 Oct  9 14:04 instructions
-rw-r--r-- 1 root   hacker   77 Oct  9 14:49 instructions.txt
-rw-r--r-- 1 hacker hacker   93 Oct  9 14:04 myflag
lrwxrwxrwx 1 hacker hacker    5 Oct  7 18:48 not-the-flag -> /flag
drwxr-xr-x 2 hacker hacker 4096 Oct  5 21:08 profile
-rw-r--r-- 1 hacker hacker  435 Oct  8 20:52 the-flag
-rwxr-xr-x 1 hacker hacker   29 Oct 19 11:25 x.sh
hacker@chaining~executable-shell-scripts:~$ ~/x.sh
You must make a shellscript in your home directory that will launch
/challenge/solve, make it executable, and invoke it without explicitly
specifying 'bash'!
hacker@chaining~executable-shell-scripts:~$ cd /home/hacker
hacker@chaining~executable-shell-scripts:~$ ls
COLLEGE  PWN  college  f  flag  grep  instructions  instructions.txt  myflag  not-the-flag  profile  the-flag  x.sh
hacker@chaining~executable-shell-scripts:~$ ./x.sh
Congratulations on your shell script execution! Your flag:
pwn.college{oFsKR1QT-wYfGp8mNHMu-IxE-Nv.dRzNyUDL2kTN0czW}
```

## References Used:
None
