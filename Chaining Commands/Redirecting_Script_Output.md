# Redirecting Script Output
	In this challenge, I was asked to bring back piping. So, first I started by making the shell file using then `nano x.sh`. Then in that, I wrote
				`#!/bin/bash
				 /challenge/pwn
				 /challenge/college`
in the the file, and bashed it to get the output, and using the piping operator *|*, I gave the output as an input to the program `/challenge/solve` to get the flag.
```bash
hacker@chaining~redirecting-script-output:~$ nano x.sh
hacker@chaining~redirecting-script-output:~$ chmod u+x x.sh
hacker@chaining~redirecting-script-output:~$ bash x.sh | /challenge/solve
Correct! Here is your flag:
pwn.college{kVhOY0P5eng8UR3M2bxzcNRlgcS.dhTM5QDL2kTN0czW}
```

## References Used:
None
