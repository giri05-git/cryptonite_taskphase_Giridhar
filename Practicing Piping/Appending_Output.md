# Appending Output
 We use output redirection to save command results for later usages. Sometimes, we want to save different command results to a file. But, if we try to do output redirection each time, the file gets overwritten again and again, so in order to keep all command results in a single file, we use the 
append argument `>>`.
	In this  challenge, we needed to do an append mode redirect of `/challenge/run` to the file
`/home/hacker/the-flag`. When we do this, the first half of the flag is written to the file, and second
half is written to stdout only is stdout is redirected to the file. If you use append mode, second half
joins with the first half itself. But once when I tried with truncation(`>`), second half overwrote the first half and I only got half the flag.

```bash
giridhar@LAPTOP-EQ112OJM:~$ ssh -i ./key hacker@dojo.pwn.college
Connected!
hacker@piping~appending-output:~$ /challenge/run >> home/hacker/the-flag
ssh-entrypoint: home/hacker/the-flag: No such file or directory
hacker@piping~appending-output:~$ /challenge/run >> /home/hacker/the-flag
[INFO] WELCOME! This challenge makes the following asks of you:
[INFO] - the challenge will check that output is redirected to a specific file path : /home/hacker/the-flag

[HYPE] ONWARDS TO GREATNESS!

[INFO] This challenge will perform a bunch of checks.
[INFO] Good luck!

[TEST] You should have redirected my stdout to a file called /home/hacker/the-flag. Checking...

[HINT] File descriptors are inherited from the parent, unless the FD_CLOEXEC is set by the parent on the file descriptor.
[HINT] For security reasons, some programs, such as python, do this by default in certain cases. Be careful if you are
[HINT] creating and trying to pass in FDs in python.

[PASS] The file at the other end of my stdout looks okay!
[PASS] Success! You have satisfied all execution requirements.
I will write the flag in two parts to the file /home/hacker/the-flag! I'll do
the first write directly to the file, and the second write, I'll do to stdout
(if it's pointing at the file). If you redirect the output in append mode, the
second write will append to (rather than overwrite) the first write, and you'll
get the whole flag!
hacker@piping~appending-output:~$ cat /home/hacker/the-flag
 |
\|/ This is the first half:
 v
pwn.college{Ad98wM6D3BQN1DHmRi12wx5UZlB.ddDM5QDL2kTN0czW}
                              ^
     that is the second half /|\
                              |

If you only see the second half above, you redirected in *truncate* mode (>)
rather than *append* mode (>>), and so the write of the second half to stdout
```

## References Used:
None
