# Becoming root with su
We know that we won't be able to do some programs unless we are the root user. Usually, there won't be any programs that let you become the *root* user. For this we use two facilities: `su` and `sudo`.When we use su, running as the root user, root shell is initialized. But when su is used, we are asked to enter the password to confirm the user.
	In this challenge, we are asked to use the older one *su(switch user)*. When we give the command, password is asked which is provided to us in the question, i.e, *hack-the-planet*. Once doing this, we become the root user, and then we should cat the flag file to get the flag value.

```bash
giridhar@LAPTOP-EQ112OJM:~$ ssh -i ./key hacker@dojo.pwn.college
Connected!
suhacker@users~becoming-root-with-su:~$ su
Password:
su: Authentication failure
hacker@users~becoming-root-with-su:~$ su
Password:
root@users~becoming-root-with-su:/home/hacker# cat /flag
pwn.college{UvFEZuR4SiD3_M44oX1fL_I1oob.dVTN0UDL2kTN0czW}
```
