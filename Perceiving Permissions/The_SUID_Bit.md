# The SUID Bit
We know that system admin decides all the permissions goes to who. But some tasks, we can make any user do as the owner of the file. But the user should be made sure to be the one assigned by the root user. So for this, SUID's are set up which any person permissions as same as the owner only when the user is confirmed to be the one given access with a password. This is done by giving a `s` part in the giving permissions part.
	In this challenge, I added the SUID bit to the program `/challenge/getroot` which helped us create a root shell which we used to the cat the flag from it without being the root owner yourself.

```bash
Connected!
hacker@permissions~the-suid-bit:~$ chmod u+s /challenge/getroot
hacker@permissions~the-suid-bit:~$ cat /flag
cat: /flag: Permission denied
hacker@permissions~the-suid-bit:~$ /challenge/getroot
SUCCESS! You have set the suid bit on this program, and it is running as root!
Here is your shell...
root@permissions~the-suid-bit:~# cat /flag
pwn.college{E2zkov4mI1mQnhuwQNSztWZ-O2O.dNTM2QDL2kTN0czW}
```

## References Used:
None
