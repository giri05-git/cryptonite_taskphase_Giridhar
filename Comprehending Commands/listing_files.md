# listing files
We have seen how we can access files. But a directory can have lot of files, so it is not possible to directly access them without knowing their name. Then, the `ls` command comes to play. We can use ls command to list all files in the directories provide to it as arguments and if no directory is mentioned, it lists all the files and directories in the home directory.
	In the challenge, we need to go inside challenge directory to find the run program which is stored in some random name. So for that, we use `ls`command  in the challenge directory. We see a file
named as `12193-renamed-run-6561`. We run it and get our flag.

```bash 
giridhar@LAPTOP-EQ112OJM:~$ ssh -i ./key hacker@dojo.pwn.college
Connected!
hacker@commands~listing-files:~$ ls /challenge
12193-renamed-run-6561  DESCRIPTION.md
hacker@commands~listing-files:~$ cd /challenge
hacker@commands~listing-files:/challenge$ ./12193-renamed-run-6561
Yahaha, you found me! Here is your flag:
pwn.college{Y_nNIAJqtlBBMe2msA9Tv3GDvCr.dhjM4QDL2kTN0czW}
```
## References Used:
None
