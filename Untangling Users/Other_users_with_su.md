# Other users with su
We know when we just use the su command, we are asked password to gain access as the root user. But, it is not just root user, we can switch access to any user using their username. We just need to provide the username as an argument for su.
	In this challenge, we need to invoke the program `/challenge/run`, but this can be only done if we are the user with the username *zardus*. So first, I switched user by doing *su zardus*, then gave the password *dont-hack-me* given in the question. Then, I got the flag after running the program there.

```bash
Connected!
hacker@users~other-users-with-su:~$ su zardus
Password:
zardus@users~other-users-with-su:/home/hacker$ /challenge/run
Congratulations, you have become Zardus! Here is your flag:
pwn.college{k7mjFcWUy7SHRzkg6XlJKR75T-q.dZTN0UDL2kTN0czW}
```

## References Used:
None
