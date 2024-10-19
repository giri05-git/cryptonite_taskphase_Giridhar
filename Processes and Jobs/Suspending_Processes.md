# Suspending Processes
Sometimes a process might be going on, but we might need to move them to the background without actually closing it, this is what it is called suspending the process. It is done using `Ctrl-Z`hotkey.
	In this challenge, I was asked to run a copy of a program while a copy of it is suspended in the background. For this, I launched the program, then I suspended, then I invoked the program again, which gave me the flag.

```bash
Connected!
hacker@processes~suspending-processes:~$ /challenge/run
I'll only give you the flag if there's already another copy of me running in
this terminal... Let's check!

UID          PID    PPID  C STIME TTY          TIME CMD
root          83      66  0 18:17 pts/0    00:00:00 bash /challenge/run
root          85      83  0 18:17 pts/0    00:00:00 ps -f

I don't see a second me!

To pass this level, you need to suspend me and launch me again! You can
background me with Ctrl-Z or, if you're not ready to do that for whatever
reason, just hit Enter and I'll exit!
^Z
[1]+  Stopped                 /challenge/run
hacker@processes~suspending-processes:~$ /challenge/run
I'll only give you the flag if there's already another copy of me running in
this terminal... Let's check!

UID          PID    PPID  C STIME TTY          TIME CMD
root          83      66  0 18:17 pts/0    00:00:00 bash /challenge/run
root          90      66  0 18:17 pts/0    00:00:00 bash /challenge/run
root          92      90  0 18:17 pts/0    00:00:00 ps -f

Yay, I found another version of me! Here is the flag:
pwn.college{cPKjHxgFjqzwMl7L8I3aqZ7LQpK.dVDN4QDL2kTN0czW}
```

## References Used:
None
