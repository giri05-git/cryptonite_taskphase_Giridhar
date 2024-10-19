# Groups and Files
Files are not only owned by a single owner but it can be group too. Just like *chown* is used to changer user access, `chgrp` is used to change the group ownership of a file.
	In this challenge, I changed the group ownership of the flag file to the hacker user using 
*chgrp hacker /flag* and the I catted the flag file to get the flag value.

```bash
Connected!
hacker@permissions~groups-and-files:~$ chgrp hacker /flag
hacker@permissions~groups-and-files:~$ cat /flag
pwn.college{MamNHBAGif6QksKcs3qpjVOtei_.dFzNyUDL2kTN0czW}
```

## References Used:
None
