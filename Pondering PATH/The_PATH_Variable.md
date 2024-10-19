# The PATH Variable
We know that we'll be able to find the location of a program knowing it's path, but in case of some commands like ls and all, we don't know anything abt its path. In this case, we use a special shell variable called *PATH*, which stores a bunch of directory paths in which shell will search of programs corresponding to commands. 
	In this challenge, I was asked to run the program `challenge/run` after which the flag file will be deleted if there is the rm command is present. So in order to remove it, we need to set the path variable to empty string, so rm command will not be found, and we will get the flag when the program is run.

```bash
Connected!
hacker@path~the-path-variable:~$ PATH="" /challenge/run
Trying to remove /flag...
/challenge/run: line 4: rm: No such file or directory
The flag is still there! I might as well give it to you!
pwn.college{4_kDlt6xnyXEbl9n1n_ACPdBrp0.dZzNwUDL2kTN0czW}
```
## References Used:
None
