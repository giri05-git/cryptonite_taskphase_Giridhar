# Changing File Ownership
All files in Linux is owned by a user on the system. There might be different user accounts, and all files in their own home directories. We can change ownerships of files by using `chown` command by giving multiarguments i.e, the username and filename. 
	In this challenge, I was asked to change the ownership of the `/flag` file to the *hacker* user. I did that using `*chown* command and then I catted the file to get the flag.

```bash
Connected!
hacker@permissions~changing-file-ownership:~$ ls
COLLEGE  PWN  college  f  flag  grep  instructions  instructions.txt  myflag  not-the-flag  profile  the-flag
hacker@permissions~changing-file-ownership:~$ chown hacker /flag
hacker@permissions~changing-file-ownership:~$ cat /flag
pwn.college{k6U7YnZr_5o0Dq_NvT7zY2pJhtI.dFTM2QDL2kTN0czW}
```

## References Used:
None
