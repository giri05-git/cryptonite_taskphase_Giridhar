# Cracking Passwords
Each user access is locked with a password. All the passwords were stored in a file called
`/etc/passwd`, but this file is globally readable, and that is a threat to all the user accounts. Hence, these passwords were moved to a file `/etc/shadow`. When a password is input, it one-way encrypts(hashes) and is compared against the stored value. As the backups for the password stored file is unencrypted and insufficiently protected, data disclosures occur. This cracking of the password file is done via the *John the Ripper*.
	In this challenge, I used *John the Ripper* to crack the password file */etc/shadow* which is stored here in */challenge/shadow-leak*. Then, I got the password for the zardus user and switched user and invoked the program `/challenge/run` to get the flag.

```bash
Connected!
hacker@users~cracking-passwords:~$ john ./etc/shadow
Created directory: /home/hacker/.john
hacker@users~cracking-passwords:~$ john /etc/shadow-leak
stat: /etc/shadow-leak: No such file or directory
hacker@users~cracking-passwords:~$ john /challenge/shadow-leak
Loaded 1 password hash (crypt, generic crypt(3) [?/64])
Press 'q' or Ctrl-C to abort, almost any other key for status
0g 0:00:00:10 0% 2/3 0g/s 301.7p/s 301.7c/s 301.7C/s piglet..knight
aardvark         (zardus)
1g 0:00:00:18 100% 2/3 0.05361g/s 312.2p/s 312.2c/s 312.2C/s Johnson..buzz
Use the "--show" option to display all of the cracked passwords reliably
Session completed
hacker@users~cracking-passwords:~$ su zardus
Password:
zardus@users~cracking-passwords:/home/hacker$ /challenge/run
Congratulations, you have become Zardus! Here is your flag:
pwn.college{gfQs7ITDztrtMFC0vTHmsOnzxoA.ddTN0UDL2kTN0czW}
```

## References Used:
None 
	

