# Touching Files
Since there exists command to read a file or display the available files, we also have a command to create a file, i.e, `touch` command.
	In this challenge, we create two files pwn and college in tmp directory using absolute path, then invoke run program in challenge directory to get flag.

```bash
giridhar@LAPTOP-EQ112OJM:~$ ssh -i ./key hacker@dojo.pwn.college
Connected!
hacker@commands~touching-files:~$ cd /tmp
hacker@commands~touching-files:/tmp$ ls
bin  hsperfdata_root  tmp.MiOQGWw5Zc
hacker@commands~touching-files:/tmp$ touch pwn
hacker@commands~touching-files:/tmp$ touch college
hacker@commands~touching-files:/tmp$ ls
bin  college  hsperfdata_root  pwn  tmp.MiOQGWw5Zc
hacker@commands~touching-files:/tmp$ cd ~
hacker@commands~touching-files:~$ /challenge/run
Success! Here is your flag:
pwn.college{0TyICJ9gNV1uvWwrYJs6b8XxGfh.dBzM4QDL2kTN0czW}
```

## References Used:
None
