# Resuming Processes
We saw that we can suspend a process to background. This process can be resumed using `fg` command. This
command brings the suspended process in background back to the foreground.
	In this challenge, we just need to suspend the *run* program. So, first launch it, then suspend it using the *fg* command and then you'll get the flag.

```bash
Connected!
hacker@processes~resuming-processes:~$ /challenge/run
Let's practice resuming processes! Suspend me with Ctrl-Z, then resume me with
the 'fg' command! Or just press Enter to quit me!
^Z
[1]+  Stopped                 /challenge/run
hacker@processes~resuming-processes:~$ fg
/challenge/run
I'm back! Here's your flag:
pwn.college{A7RixCqUIGXj5SHrXRuAsmryAqA.dZDN4QDL2kTN0czW}
```

## References Used:
None
