# Your First Shell Script
We know that we use the terminal to run programs, and for almost everything. So when we have a lot of commands which are set up to do a specific thing, doing it all in the main terminal is gonna get the length of the terminal very big. So, such commands can be together in a file called shell script, which can be run when u want to do that specific operation. It is run by passing it as an argument to new instance of the shell(bash). So when done like this, it takes the commands from the file rather than the user.
	In this challenge, I created a file called `x.sh` using the command `nano x.sh`. Then I wrote 
				`#!/bin/bash
				 /challenge/pwn
				 /challenge/college`
in the shell file and then made it executable for the user. then I did *bash x.sh* to run it and get the flag.

```bash
Connected!
hacker@chaining~your-first-shell-script:~$ ls
COLLEGE  PWN  college  f  flag  grep  instructions  instructions.txt  myflag  not-the-flag  profile  the-flag  x.sh
hacker@chaining~your-first-shell-script:~$ gedit x.sh
Unable to init server: Could not connect: Connection refused

(gedit:93): Gtk-WARNING **: 10:54:44.007: cannot open display:
hacker@chaining~your-first-shell-script:~$ echo $0
/run/dojo/bin/ssh-entrypoint
hacker@chaining~your-first-shell-script:~$ nano x.sh
hacker@chaining~your-first-shell-script:~$ chmod u+x x.sh
hacker@chaining~your-first-shell-script:~$ bash x.sh
Great job, you've written your first shell script! Here is the flag:
pwn.college{crnpRHhRbR9X_IZnwokXJxdCFsg.dFzN4QDL2kTN0czW}
```
