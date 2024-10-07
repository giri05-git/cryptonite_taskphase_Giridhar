# cryptonite_taskphase_Giridhar
#The Root
We are able to invoke a program by providing its path on the command line.A file system starts 
at `/`. This contains other dictionaries, configuration files, programs and flags in it.
In our challenge, we are asked to invoke one such program called `pwn`. Therefore, we are
invoking the program using its absolute path. So just use `/pwn`. This finishes the challenge 
and flag is earned.
```bash
giridhar@LAPTOP-EQ112OJM:~$ ssh -i ./key hacker@dojo.pwn.college
Connected!
hacker@paths~the-root:~$ /pwn
BOOM!!!
Here is your flag:
pwn.college{MBk9S5H4Z63Lg9MNpNzcps_meWK.dhzN5QDL2kTN0czW}\
```
## References Used:
None
