# Grepping live output 
In previous challenge, I needed to first redirect the output of a program to a different file, then needed to search, but apparantely, it is not needed. The middlestep is avoided with the help of pipe`|`
operator. It means the output from left of pipe will be connected to input of command to right of pipe.
	In this challenge, I gave searching the flag line in the output by getting the output and doing it all in a single line.

```bash
Connected!
hacker@piping~grepping-live-output:~$ /challenge/run | grep pwn.college
[INFO] WELCOME! This challenge makes the following asks of you:
[INFO] - the challenge checks for a specific process at the other end of stdout : grep
[INFO] - the challenge will output a reward file if all the tests pass : /challenge/.data.txt

[HYPE] ONWARDS TO GREATNESS!

[INFO] This challenge will perform a bunch of checks.
[INFO] If you pass these checks, you will receive the /challenge/.data.txt file.

[TEST] You should have redirected my stdout to another process. Checking...
[TEST] Performing checks on that process!

[INFO] The process' executable is /nix/store/xpq4yhadyhazkcsggmqd7rsgvxb3kjy4-gnugrep-3.11/bin/grep.
[INFO] This might be different than expected because of symbolic links (for example, from /usr/bin/python to /usr/bin/python3 to /usr/bin/python3.8).
[INFO] To pass the checks, the executable must be grep.

[PASS] You have passed the checks on the process on the other end of my stdout!
[PASS] Success! You have satisfied all execution requirements.
pwn.college{gV8vAQJXtw1H0tJdwhKgmEoV1-N.dlTM4QDL2kTN0czW}
```

## References Used:
None
