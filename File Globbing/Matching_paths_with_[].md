# Matching paths with []
Globbing happens on path basis, so we can expand entire paths with your globbed arguments.
	In this challenge, we need to bracket-globs into the absolute paths to the file_b,
file_a, file_s and file_h files by giving it as a single argument to the program /challenge/run.
So, first I needed to move to the directory which contains this files, i.e, `/challenge/files`
Then I ran the program `/challenge/run` with giving its argument the absolute path of the required files i.e, as `/challenge/files/file_[absh]`.

```bash
Connected!
hacker@globbing~matching-paths-with-:~$ cd /challenge/files
hacker@globbing~matching-paths-with-:/challenge/files$ /challenge/run /challenge/files/file_[absh]
Error: please run with a working directory of /home/hacker!
hacker@globbing~matching-paths-with-:/challenge/files$ /challenge/run ~/challenge/files/file_[absh]
Error: please run with a working directory of /home/hacker!
hacker@globbing~matching-paths-with-:/challenge/files$ cd /home/hacker
hacker@globbing~matching-paths-with-:~$ /challenge/run /challenge/files/file_[absh]
You got it! Here is your flag!
pwn.college{g_-cF6tExwasv5aDU3h2XlnMOc8.dRjM4QDL2kTN0czW}
```

## References Used:
None
