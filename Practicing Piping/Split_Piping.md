# Split-piping stderr and stdout
In this challenge, we need to take the program `/challenge/hack` which has data on stdout and stderr. Then, I needed to redirect its output data to `/challenge/planet' and its error data to `challenge/the`.
But if we give this plain, it leads to errors. So we give the argument as `>()`.

```bash
Connected!
/chacker@piping~split-piping-stderr-and-stdout:~$ /challenge/hack > /challenge/planet
ssh-entrypoint: /challenge/planet: Permission denied
hacker@piping~split-piping-stderr-and-stdout:~$ /challenge/hack > >(/challenge/planet) 2> >(/challenge/the)
Congratulations, you have learned a redirection technique that even experts
struggle with! Here is your flag:
pwn.college{AUQfu-MFNs3KyO7G8tGD1jNsbX2.dFDNwYDL2kTN0czW}
```

## References Used:
None
