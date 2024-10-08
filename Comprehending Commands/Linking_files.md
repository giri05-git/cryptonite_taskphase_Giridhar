# Linking Files
A file is an address at which the contents of the file live. So we create links,ex like soft/symbolic links. In such links, we link the original file with a secondary link, so when we access the secondary link, Linux realises it is a symbolic link, read the original file name, and then automatically access that file. Similarly, another link exist called hard link, which is an alternate address that index the data - accesses to the original file are completely identical, in that, they immediately yield necessary data.
	In this challenge, the flag is in `/flag`, but we can't do `challenge/catflag` directly because
that program is already symlinked to `/home/hacker/not-the-flag`, so what we need to do is to create a symlink between */flag* and *~/not-the-flag*, so that when we access *challenge/catflag*, it goes to 
*~/not-the-flag* which is actually */flag* linked in it. But I tried so so many times to create the link
for *~/not-the-flag* but it showed link already exists. So, first I googled how to overwrite link and found out`-f` can be used. So I overwrote the link, then run `/challenge/catflag` so I got the flag at last

```bash
giridhar@LAPTOP-EQ112OJM:~$ ssh -i ./key hacker@dojo.pwn.college
Connected!
hacker@commands~linking-files:~$ ln -s challenge/flag ~/not-the-flag
ln: failed to create symbolic link '/home/hacker/not-the-flag': File exists
hacker@commands~linking-files:~$ ln -s /flag ~/not-the-flag
ln: failed to create symbolic link '/home/hacker/not-the-flag': File exists
hacker@commands~linking-files:~$ ln -sf /flag ~/not-the-flag
hacker@commands~linking-files:~$ /challenge/catflag
About to read out the /home/hacker/not-the-flag file!
pwn.college{k-rJprkFQLhaaKeIyFMEcufR6e2.dlTM1UDL2kTN0czW}
```
## References Used:
None
