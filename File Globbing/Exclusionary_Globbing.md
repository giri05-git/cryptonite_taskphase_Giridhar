# Exclusionary Globbing
We can filter out files in a glob. This is done with the help of bracket glob. If the first character 
in the brackets is a `!` or `^`, and that bracket instance matches characters that aren't listed.
	In this challenge, I first moved shell directory to `/challenge/files`. Then I ran the program
`/challenge/run` and as I needed to run all the files that don't start with p, w, or n, I gave the argument a bracket glob, that started with !, as `[!pwn]*`. Hence the correct usage atlast gave me the 
correct flag.

```bash
hacker@globbing~exclusionary-globbing:/challenge/files$ /challenge/run *[!pwn]
Your expansion did not expand to the requested files (amazing beautiful
challenging delightful educational fantastic great happy incredible jovial kind
laughing magical optimistic queenly radiant splendid thrilling uplifting
victorious xenial youthful zesty).
Instead, it expanded to:
amazing beautiful challenging delightful educational fantastic great happy incredible jovial kind laughing magical nice optimistic pwning queenly radiant splendid thrilling uplifting victorious wonderful xenial youthful zesty
hacker@globbing~exclusionary-globbing:/challenge/files$ /challenge/run [!pwn]*
You got it! Here is your flag!
pwn.college{4jl0k_GJfwCAhbyE5bxSnCPvWiV.dZjM4QDL2kTN0czW}
```

## References Used:
None
