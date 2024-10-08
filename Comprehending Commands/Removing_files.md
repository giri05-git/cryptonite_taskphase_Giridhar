# Removing Files
`rm` command exists in Linux filesystem to remove files. These command comes to help when there is so many files that we need to remove some useless files for convenience
	In this challenge, I created a file named `delete_me` in the home directory using touch command.
After creating it, I deleted the file. Then, I invoked the program `check` in challenge directory,
which confirms that the file has been deleted and returns the flag.

```bash
giridhar@LAPTOP-EQ112OJM:~$ ssh -i ./key hacker@dojo.pwn.college
Connected!
hacker@commands~removing-files:~$ touch delete_me
hacker@commands~removing-files:~$ rm delete_me
hacker@commands~removing-files:~$ /challenge/check
Excellent removal. Here is your reward:
pwn.college{sZ_cPMUXwRPUaexLo_AcIBwe-ZZ.dZTOwUDL2kTN0czW}
```

## References Used
None
