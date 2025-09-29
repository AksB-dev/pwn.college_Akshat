# Practicing Piping
## Redirecting Output
Redirecting output to files
### Solve
**Flag** `pwn.college{Ug88NRDjFUmdICk3ra76eBvV1ix.QX0YTN0wSO2gjNzEzW}`
```bash
hacker@piping~redirecting-output:~$ touch COLLEGE
You have created the COLLEGE file, but you didn't write the correct value to 
it. Make sure to write PWN to the COLLEGE file.
hacker@piping~redirecting-output:~$ echo PWN > COLLEGE
Correct! You successfully redirected 'PWN' to the file 'COLLEGE'! Here is your 
flag:
pwn.college{Ug88NRDjFUmdICk3ra76eBvV1ix.QX0YTN0wSO2gjNzEzW}
```
### New Learnings
We can redirect an output to a file using `echo` command.
<br>
Format of the command: `echo OUTPUT > FILENAME`
### References
None.
##
## Redirecting more output
Redirecting output of any command to a file
### Solve
**Flag** `pwn.college{ArhHumvdpaWL9GYjA6mjMHkLLrK.QX1YTN0wSO2gjNzEzW}`
```bash
hacker@piping~redirecting-more-output:~$ /challenge/run > myflag
[INFO] WELCOME! This challenge makes the following asks of you:
[INFO] - the challenge will check that output is redirected to a specific file path : myflag
[INFO] - the challenge will output a reward file if all the tests pass : /flag

[HYPE] ONWARDS TO GREATNESS!

[INFO] This challenge will perform a bunch of checks.
[INFO] If you pass these checks, you will receive the /flag file.

[TEST] You should have redirected my stdout to a file called myflag. Checking...

[PASS] The file at the other end of my stdout looks okay!
[PASS] Success! You have satisfied all execution requirements.
hacker@piping~redirecting-more-output:~$ cat myflag

[FLAG] Here is your flag:
[FLAG] pwn.college{ArhHumvdpaWL9GYjA6mjMHkLLrK.QX1YTN0wSO2gjNzEzW}
```
### New Learnings
The output of a command can be redirected to a file
using `>`.

### References
None.