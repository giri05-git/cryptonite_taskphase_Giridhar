# Matching with []
Square brackets are, limited form of ?, in which instead of matching any character,[] is a wildcard for some subset of potential characters, specified within the brackets.
	In this challenge, we need to change our working directory `/challenge/files` and then we
need to run `/challenge/run` but the argument with just one glob should help us get the file_b,file_a,
file_s, and file_h.

```bash
giridhar@LAPTOP-EQ112OJM:~$ ssh -i ./key hacker@dojo.pwn.college
Connected!
hacker@globbing~matching-with-:~$ cd /challenge/files
hacker@globbing~matching-with-:/challenge/files$ ls
file_a  file_c  file_e  file_g  file_i  file_k  file_m  file_o  file_q  file_s  file_u  file_w  file_y
file_b  file_d  file_f  file_h  file_j  file_l  file_n  file_p  file_r  file_t  file_v  file_x  file_z
hacker@globbing~matching-with-:/challenge/files$ file_[absh]
ssh-entrypoint: file_a: command not found
hacker@globbing~matching-with-:/challenge/files$ /challenge/run file_[absh]
You got it! Here is your flag!
pwn.college{4m04bxnkrzdUSdsNGk8SWKbU4rb.dNjM4QDL2kTN0czW}
```

## References Used:
None
