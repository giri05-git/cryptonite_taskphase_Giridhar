# Starting Backgrounded Processes
We can start running processes in background by using `bg` command. But, we can only do this by first suspending processes to move them to the background. Instead of doing this, we can directly move them to the background and start running there by appending `&` to the command.
	In this challenge, we are asked to launch `/challenge/run` in background to get the flag. So I used *&* along with the command to get the flag.

```bash
Connected!
hacker@processes~starting-backgrounded-processes:~$ /challenge/run
You've started me in the foreground! You must start me in the background (by
appending '&' to the command) to get the flag!
hacker@processes~starting-backgrounded-processes:~$ /challenge/run &
[1] 85
hacker@processes~starting-backgrounded-processes:~$


Yay, you started me in the background! Because of that, this text will probably
overlap weirdly with the shell prompt, but you're used to that by now...

Anyways! Here is your flag!
pwn.college{MCkOdmUEED-gknMLlpvFYSuMm6k.dlDN4QDL2kTN0czW}
```
## References Used:
None
