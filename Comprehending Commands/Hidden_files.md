# Hidden files
We know *ls* command is used to see all the files available in the directory. But all the files that start with *.* doesn't show up when ls command is used. So in order to see such hidden files, we use
`ls -a` command.
	In this challenge, I used the *ls -a* command to find the flag that is hidden in a file named with *.* in the start. In the file, use grep to find the line with the flag.

```bash
giridhar@LAPTOP-EQ112OJM:~$ ssh -i ./key hacker@dojo.pwn.college
Connected!
hacker@commands~hidden-files:~$ cd /
hacker@commands~hidden-files:/$ ls -a
.   .dockerenv            bin   challenge  etc   lib    lib64   media  nix  proc  run   srv  tmp  var
..  .flag-87202779230605  boot  dev        home  lib32  libx32  mnt    opt  root  sbin  sys  usr
hacker@commands~hidden-files:/$ grep pwn.college .flag-87202779230605
pwn.college{sJV7NU5Dv27uyUU1Snde6xWYOPy.dBTN4QDL2kTN0czW}
```

## References Used:
None
