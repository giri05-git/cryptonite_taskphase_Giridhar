# Using Sudo
In this challenge, I was given sudo access. So I used it to read the flag file to get the flag value.

```bash
Connected!
suhacker@users~using-sudo:~$ sudo -1
sudo: invalid option -- '1'
usage: sudo -h | -K | -k | -V
usage: sudo -v [-AknS] [-g group] [-h host] [-p prompt] [-u user]
usage: sudo -l [-AknS] [-g group] [-h host] [-p prompt] [-U user] [-u user] [command]
usage: sudo [-AbEHknPS] [-r role] [-t type] [-C num] [-g group] [-h host] [-p prompt] [-T timeout] [-u user]
            [VAR=value] [-i|-s] [<command>]
usage: sudo -e [-AknS] [-r role] [-t type] [-C num] [-g group] [-h host] [-p prompt] [-T timeout] [-u user] file ...
hacker@users~using-sudo:~$ sudo cat /flag
pwn.college{Ucn9ZXOhF5qbsso2jTger__obpq.dhTN0UDL2kTN0czW}
```

## References Used:
None
