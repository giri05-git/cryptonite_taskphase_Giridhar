# Listing Processes
So we can get info on all running processes in a terminal.
This is done using the `ps` command. But if we just enter that command, we are only gonna get the running Processes in the terminal which is not that useful.
So in order to get processes running in all terminals, we can use `ps -e` and in order to get all the formats i.e Infosys about a process, we use `ps-f`. Similarly, in the *BSD* syntax, we can use `ps-a` for Listing Processes to all users, `ps-x` for Listing processes not running currently and `ps-u` for user readable output.
      
So in this challenge, I was asked to get the flag from the program */challenge/run* and whose name has been randomized and also is not able to be spotted by using ls command. But since this program is launched in the terminal, I did `ps-ef` to get the whole info on the program from where I can use the actual filename to run the program and get the flag.

```bash
giridhar@LAPTOP-EQ112OJM:~$ ssh -I ./key hacker@dojo.pwn.college
Connected!
hacker@processes~listing-processes:~$ cd /challenge
hacker@processes~listing-processes:/challenge$ ps -ef
UID          PID    PPID  C STIME TTY          TIME CM
Root           1       0  0 17:19 ?        00:00:00 /sbin/docker-init -- /nix/var/nix/profiles/default/bin/dojo-init /ru
Root           7       1  0 17:19 ?        00:00:00 /run/dojo/bin/sleep 6h
Root          68       1  0 17:19 ?        00:00:00 /challenge/28401-run-20114

Root          72      68  0 17:19 ?        00:00:00 sleep 6h

Hacker        73       0  0 17:19 pts/0    00:00:00 /run/dojo/bin/ssh-entrypoint

Hacker        90      73  0 17:19 pts/0    00:00:00 ps -ef
hacker@processes~listing-processes:/challenge$ ./28401-run-20114
Yahaha, you found me! Here is your flag:
Pwn.college{8AhmHf4-csE-XfE94cdq4aJqiOq.dhzM4QDL2kTN0czW}
Now I will sleep for a while (so that you could find me with ‘ps’).
```
## References Used:
None



