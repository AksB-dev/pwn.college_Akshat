# Shell Variables
## Printing Variables
### Solve
**Flag** `pwn.college{8voW0GJ0aZ6W0eUdGJcQTSNw1vP.QX3UTN0wSO2gjNzEzW}`
```bash
hacker@variables~printing-variables:~$ echo $PWD
/home/hacker
hacker@variables~printing-variables:~$ echo $FLAG
pwn.college{8voW0GJ0aZ6W0eUdGJcQTSNw1vP.QX3UTN0wSO2gjNzEzW}
```
### New Learnings
We can use `echo` to print out the contents of the variable by prefixing `$` in front of the variable name
### References
None.
## Setting Variables
### Solve
**Flag** `pwn.college{0ORlrgK-cChkSX263GlJPQ5rlFS.QX5UTN0wSO2gjNzEzW}`
```bash
hacker@variables~setting-variables:~$ PWN=COLLEGE
You've set the PWN variable properly! As promised, here is the flag:
pwn.college{0ORlrgK-cChkSX263GlJPQ5rlFS.QX5UTN0wSO2gjNzEzW}
```
### New Learnings
We can assign values to variables using `=` (no space  required)
<br> Variable names are case sensitive<br>
`$` is only used to access variables
### References
None.
## Multi-word Variables
### Solve
**Flag** `pwn.college{k8eIXawerKoj4O53x__b0NaLa5l.QXwYTN0wSO2gjNzEzW}`
```bash
hacker@variables~multi-word-variables:~$ PWN="COLLEGE YEAH"
You've set the PWN variable properly! As promised, here is the flag:
pwn.college{k8eIXawerKoj4O53x__b0NaLa5l.QXwYTN0wSO2gjNzEzW}
```
### New Learnings
If we want to assign multiple words to a variable then we need to use double-quotes to enclose the string.
### References
None.
##
## Exporting Variables
### Solve
**Flag** `pwn.college{UjBvcrEMRbl8vCvsoE7nL6XW87o.QXyYTN0wSO2gjNzEzW}`
```bash
hacker@variables~exporting-variables:~$ export PWN=COLLEGE
You've set the PWN variable to the proper value!
hacker@variables~exporting-variables:~$ sh
sh-5.2$ 
sh-5.2$ exit
exit
You've set the PWN variable to the proper value!
hacker@variables~exporting-variables:~$ COLLEGE=PWN
You've set the PWN variable to the proper value!
You've set the COLLEGE variable to the proper value!
hacker@variables~exporting-variables:~$ /challenge/run
CORRECT!
You have exported PWN=COLLEGE and set, but not exported, COLLEGE=PWN. Great 
job! Here is your flag:
pwn.college{UjBvcrEMRbl8vCvsoE7nL6XW87o.QXyYTN0wSO2gjNzEzW}
You've set the PWN variable to the proper value!
You've set the COLLEGE variable to the proper value!
```
### New Learnings
Variables we set in a session are local to that shell process by default. Other programs won't get the variable.
<br>For other programs to get the variables we can export them using the `export` command.
### References
None.
##
## Printing Exported Variables
### Solve
**Flag** `pwn.college{4YsE24--BCZ1bvElVQBNRkaba9u.QX4UTN0wSO2gjNzEzW}`
```bash
hacker@variables~printing-exported-variables:~$ env
SHELL=/run/dojo/bin/bash
HOSTNAME=variables~printing-exported-variables
PWD=/home/hacker
MANPATH=/run/dojo/share/man:
DOJO_AUTH_TOKEN=fffebee8edd045cf7d269edbd9ff1678a06a5f0a25bb508a9b5e716ee59b98d9
HOME=/home/hacker
LANG=C.UTF-8
FLAG=pwn.college{4YsE24--BCZ1bvElVQBNRkaba9u.QX4UTN0wSO2gjNzEzW}
TERMINFO=/run/dojo/share/terminfo
TERM=xterm-256color
SHLVL=2
LC_CTYPE=C.UTF-8
SSL_CERT_FILE=/run/dojo/etc/ssl/certs/ca-bundle.crt
PATH=/run/challenge/bin:/run/dojo/bin:/root/.cargo/bin:/usr/local/sbin:/usr/local/bin:/usr/sbin:/usr/bin:/sbin:/bin
DEBIAN_FRONTEND=noninteractive
_=/run/dojo/bin/env
```
### New Learnings
`env` command prints out every exported variable set in the shell.
### References 
None.
##
## Storing Command Output
**Flag** `pwn.college{84o6mEfScCOwgUd-Wd-kc_uzIzC.QX1cDN1wSO2gjNzEzW}`
### Solve
```bash
hacker@variables~storing-command-output:~$ PWN=$(/challenge/run)
Congratulations! You have read the flag into the PWN variable. Now print it out 
and submit it!
hacker@variables~storing-command-output:~$ echo $PWN
pwn.college{84o6mEfScCOwgUd-Wd-kc_uzIzC.QX1cDN1wSO2gjNzEzW}
```
### New Learnings
We can use `$()` to store the output of a command into a variable.
<br> We can also use backticks ` `` ` but that cannot be used for nesting.
### References
None.
##
## Reading Input
### Solve
**Flag** `pwn.college{YCoT-YRtgkLYU8NTjOVu6onmr_Y.QX4cTN0wSO2gjNzEzW}`
```hacker@variables~reading-input:~$ read PWN
COLLEGE
You've set the PWN variable properly! As promised, here is the flag:
pwn.college{YCoT-YRtgkLYU8NTjOVu6onmr_Y.QX4cTN0wSO2gjNzEzW}
hacker@variables~reading-input:~$ read -p "Enter: " PWN
Enter: COLLEGE
You've set the PWN variable properly! As promised, here is the flag:
pwn.college{YCoT-YRtgkLYU8NTjOVu6onmr_Y.QX4cTN0wSO2gjNzEzW}
```

### New Learnings
`read` takes input from the user, kinda like `scanf` in C.
<br> We can specify a prompt by using the `-p` argument.
### References
None.
##
## Reading files
### Solve
**Flag** `pwn.college{AauZ9nPWFJv5zf8RTFNqqYiuFiF.QXwIDO0wSO2gjNzEzW}`
```bash
hacker@variables~reading-files:~$ read PWN < /challenge/read_me 
You've set the PWN variable properly! As promised, here is the flag:
pwn.college{AauZ9nPWFJv5zf8RTFNqqYiuFiF.QXwIDO0wSO2gjNzEzW}
```
### New Learnings
We can redirect a file into the standard output of read, when read will read from a file when it reads into the variable.
### References 
None.