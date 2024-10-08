# More catting practice
We can give either absolute or relative paths as argument to *cat* command.
	In this challenge, we are supposed to get the directory of file but we can't move to it using
`cd`, but we can give absolute path to cat. So first give `cat flag` to which the terminal denies output but gives us file location. Then give that absolute path as argument, then we will get the flag.

```bash
giridhar@LAPTOP-EQ112OJM:~$ ssh -i ./key hacker@dojo.pwn.college
Connected!
You cannot use the 'cd' command in this level, and must retrieve the flag by
absolute path. Plus, I hid the flag in a different directory! You can find it
in the file /lib/firefox/distribution/flag. Go cat it out **without** cding
into that directory!
hacker@commands~more-catting-practice:~$ cat /lib/firefox/distribution/flag
pwn.college{kLQUidKM4oWl3k8QNQkoUGdhlDb.dBjM5QDL2kTN0czW}

```

## References Used:
None
