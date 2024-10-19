
# Killing Processes
We know how to invoke processes, similarly, we can terminate an already running process by using the `kill` command.
     In this challenge, I was asked to run a program `challenge/run` but this will only run if the process `challenge/don’t_run` is not running.
So in order to run the program, I first killed the already running program by getting it’s *PID* using *ps-ef* command, then I invoked the other program to get the flag.

```bash
Connected!

hacker@processes~killing-processes:~$ ps -e

    PID TTY          TIME CMD

      1 ?        00:00:00 docker-init

      7 ?        00:00:00 /run/dojo/bin/s

     71 ?        00:00:00 su

     73 ?        00:00:00 bash

     74 ?        00:00:00 sleep

     75 pts/0    00:00:00 ssh-entrypoint

     92 pts/0    00:00:00 ps

hacker@processes~killing-processes:~$ cd /challenge

hacker@processes~killing-processes:/challenge$ ps -ef

UID          PID    PPID  C STIME TTY          TIME CMD

Root           1       0  0 17:37 ?        00:00:00 /sbin/docker-init -- /nix/var/nix/profiles/default/bin/dojo-init /ru

Root           7       1  0 17:37 ?        00:00:00 /run/dojo/bin/sleep 6h

Root          71       1  0 17:37 ?        00:00:00 su -c /challenge/.launcher hacker

Hacker        73      71  0 17:37 ?        00:00:00 /challenge/don’t_run

Hacker        74      73  0 17:37 ?        00:00:00 sleep 6h

Hacker        75       0  0 17:37 pts/0    00:00:00 /run/dojo/bin/ssh-entrypoint

Hacker        93      75  0 17:37 pts/0    00:00:00 ps -ef

hacker@processes~killing-processes:/challenge$ kill 73

hacker@processes~killing-processes:/challenge$ ./run

Great job! Here is your payment:

Pwn.college{gNXxJlwSOHczePXtZ_Ky8CIAdVW.dJDN4QDL2kTN0czW}
```
## References Used:
None
