# Interrupting Processes
Sometimes we might not need to kill a program, but just need to exit from it. If we don't do so, it messes up with the memory of terminal. So we basically use the hotkey `Ctrl-C` which basically interrupt a process by exiting from it.
	In this challenge, I was asked to get the flag from the process `/challenge/run` but it will not be provided until that program is interrupted. So, I interrupted the program and the terminal provided me the flag.

```bash
Connected!
c/chhacker@processes~interrupting-processes:~$ /challenge/run
I could give you the flag... but I won't, until this process exits. Remember,
you can force me to exit with Ctrl-C. Try it now!
^C
Good job! You have used Ctrl-C to interrupt this process! Here is your flag:
pwn.college{si72N7l9cdqcbgUg9oF0uqRU1p_.dNDN4QDL2kTN0czW}
```
## References Used:
None
