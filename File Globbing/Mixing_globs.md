# Mixing globs
In this challenge, I've put whatever I learnt at previous challenges to use. I was asked to go into a directory `/challenge/files` and then run `/challenge/run` with a glob argument that got us the files *challenging* , *educational* and *pwning*. So, inorder to do that, I gave glob argument `[cep]*` and I got the flag.

```bash
giridhar@LAPTOP-EQ112OJM:~$ ssh -i ./key hacker@dojo.pwn.college
Connected!
hacker@globbing~mixing-globs:~$ cd /challenge/files
hacker@globbing~mixing-globs:/challenge/files$ /challenge/run [cep]*
You got it! Here is your flag!
pwn.college{c1kixlijMf_QJq7yal4sf05xilz.dVjM4QDL2kTN0czW}
```

## References Used:
None
