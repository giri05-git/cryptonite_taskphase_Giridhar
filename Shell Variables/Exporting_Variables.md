# Exporting Variables
All the values we set to a variable are set locally to that shell process. So, running any other commands won't inherit these values when used there. So in order to get a value defined in a shell process to another one, we use *export* .
	In this challenge, we need to invoke the program `/challenge/run` but should only be invoked after the setting the value *COLLEGE* to the variable *PWN* and this variable should be exported and similary, another variable *COLLEGE* should be set with the value *PWN*. So in the former case, I used
export along with the assignment and in the latter, I didn't.

```bash
 Connected!
hacker@variables~exporting-variables:~$ export PWN=COLLEGE
You've set the PWN variable to the proper value!
hacker@variables~exporting-variables:~$ COLLEGE=PWN
You've set the PWN variable to the proper value!
You've set the COLLEGE variable to the proper value!
hacker@variables~exporting-variables:~$ /challenge/run
CORRECT!
You have exported PWN=COLLEGE and set, but not exported, COLLEGE=PWN. Great
job! Here is your flag:
pwn.college{EhicECbXX6GcHlgG8tU7-ZE3EyB.dJjN1QDL2kTN0czW}
You've set the PWN variable to the proper value!
You've set the COLLEGE variable to the proper value!
```
## References Used:
None
