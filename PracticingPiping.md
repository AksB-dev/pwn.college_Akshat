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
##
## Appending Output
Redirecting input in append mode
### Solve
**Flag** `pwn.college{cMHFfmrIqXMMRDrza_vv9Lx2w68.QX3ATO0wSO2gjNzEzW}`
```bash
hacker@piping~appending-output:~$ /challenge/run >> the-flag
[INFO] WELCOME! This challenge makes the following asks of you:
[INFO] - the challenge will check that output is redirected to a specific file path : /home/hacker/the-flag

[HYPE] ONWARDS TO GREATNESS!

[INFO] This challenge will perform a bunch of checks.
[INFO] Good luck!

[TEST] You should have redirected my stdout to a file called /home/hacker/the-flag. Checking...

[HINT] File descriptors are inherited from the parent, unless the FD_CLOEXEC is set by the parent on the file descriptor.
[HINT] For security reasons, some programs, such as python, do this by default in certain cases. Be careful if you are
[HINT] creating and trying to pass in FDs in python.

[PASS] The file at the other end of my stdout looks okay!
[PASS] Success! You have satisfied all execution requirements.
I will write the flag in two parts to the file /home/hacker/the-flag! I'll do 
the first write directly to the file, and the second write, I'll do to stdout 
(if it's pointing at the file). If you redirect the output in append mode, the 
second write will append to (rather than overwrite) the first write, and you'll 
get the whole flag!
hacker@piping~appending-output:~$ cat the-flag 
 | 
\|/ This is the first half:
 v 
pwn.college{cMHFfmrIqXMMRDrza_vv9Lx2w68.QX3ATO0wSO2gjNzEzW}
                              ^
     that is the second half /|\
                              |

If you only see the second half above, you redirected in *truncate* mode (>) 
rather than *append* mode (>>), and so the write of the second half to stdout 
overwrote the initial write of the first half directly to the file. Try append 
mode!
```
### New Learnings
`>` will create a new output file every time, overwriting the first output
<br>
`>>` will append the new output to the previous output.

### References
None.
##
## Redirecting errors
Introduction to File Descriptors
<br>
Redirecting the errors of a command as well as its output to different files.
### Solve
**Flag** `pwn.college{MmOWlg2CPnHgf5JaUcNSQFg3rlW.QX3YTN0wSO2gjNzEzW}`
```bash
hacker@piping~redirecting-errors:~$ ls
 COLLEGE   not-the-flag   the-flag
 myflag    stdout        '~'
hacker@piping~redirecting-errors:~$ touch instructions
hacker@piping~redirecting-errors:~$ /challenge/run 2> instructions > myflag
hacker@piping~redirecting-errors:~$ cat instructions
[INFO] WELCOME! This challenge makes the following asks of you:
[INFO] - the challenge will check that output is redirected to a specific file path : myflag
[INFO] - the challenge will check that error output is redirected to a specific file path : instructions
[INFO] - the challenge will output a reward file if all the tests pass : /flag

[HYPE] ONWARDS TO GREATNESS!

[INFO] This challenge will perform a bunch of checks.
[INFO] If you pass these checks, you will receive the /flag file.

[TEST] You should have redirected my stdout to a file called myflag. Checking...

[PASS] The file at the other end of my stdout looks okay!

[TEST] You should have redirected my stderr to instructions. Checking...

[PASS] The file at the other end of my stderr looks okay!
[PASS] Success! You have satisfied all execution requirements.
hacker@piping~redirecting-errors:~$ cat myflag

[FLAG] Here is your flag:
[FLAG] pwn.college{MmOWlg2CPnHgf5JaUcNSQFg3rlW.QX3YTN0wSO2gjNzEzW}
```
### New Learnings
We can redirect the errors of a command to another file.
<br>
File Descriptors - Number that describes a communication channel in Linux<br>
FD 0: Standard Input<br>
FD 1: Standard Output<br>
FD 2: Standard Error<br>
We can redirect errors to a file using `2>`

### References
None.
##
## Redirecting input
Redirect input to programs
### Solve
**Flag** `pwn.college{IMRVax0YKJRojjWgzSIse6Amftj.QXwcTN0wSO2gjNzEzW}`
```bash
hacker@piping~redirecting-input:~$ touch PWN
hacker@piping~redirecting-input:~$ echo COLLEGE > PWN
hacker@piping~redirecting-input:~$ cat PWN
COLLEGE
hacker@piping~redirecting-input:~$ /challenge/run < PWN
Reading from standard input...
Correct! You have redirected the PWN file into my standard input, and I read 
the value 'COLLEGE' out of it!
Here is your flag:
pwn.college{IMRVax0YKJRojjWgzSIse6Amftj.QXwcTN0wSO2gjNzEzW}
```
### New Learnings
We can redirect input to programs using `<`
### References 
None
##
## Grepping stored results
### Solve
Created the `data.txt` file, then redirected the output of the command to it, then used the `grep` command to find the word `pwn`
**Flag** `pwn.college{wP1aBGGLgi1eDjv8zdLVDUj8I2C.QX4EDO0wSO2gjNzEzW}`
```bash
hacker@piping~grepping-stored-results:~$ ls
 COLLEGE   PWN   instructions   myflag   not-the-flag   stdout   the-flag  '~'
hacker@piping~grepping-stored-results:~$ cd tmp
bash: cd: tmp: No such file or directory
hacker@piping~grepping-stored-results:~$ cd /
hacker@piping~grepping-stored-results:/$ ls
bin   challenge  etc   home  lib32  libx32  mnt  opt   root  sbin  sys  usr
boot  dev        flag  lib   lib64  media   nix  proc  run   srv   tmp  var
hacker@piping~grepping-stored-results:/$ ls tmp
bin  hsperfdata_root  tmp.4mK6TfTSUV
hacker@piping~grepping-stored-results:/$ touch /tmp/data.txt
hacker@piping~grepping-stored-results:/$ ls tmp
bin  data.txt  hsperfdata_root  tmp.4mK6TfTSUV
hacker@piping~grepping-stored-results:/$ /challenge/run > /tmp/data.txt
[INFO] WELCOME! This challenge makes the following asks of you:
[INFO] - the challenge will check that output is redirected to a specific file path : /tmp/data.txt
[INFO] - the challenge will output a reward file if all the tests pass : /challenge/.data.txt

[HYPE] ONWARDS TO GREATNESS!

[INFO] This challenge will perform a bunch of checks.
[INFO] If you pass these checks, you will receive the /challenge/.data.txt file.

[TEST] You should have redirected my stdout to a file called /tmp/data.txt. Checking...

[HINT] File descriptors are inherited from the parent, unless the FD_CLOEXEC is set by the parent on the file descriptor.
[HINT] For security reasons, some programs, such as python, do this by default in certain cases. Be careful if you are
[HINT] creating and trying to pass in FDs in python.

[PASS] The file at the other end of my stdout looks okay!
[PASS] Success! You have satisfied all execution requirements.
hacker@piping~grepping-stored-results:/$ grep pwn /tmp/data.txt
pwn.college{wP1aBGGLgi1eDjv8zdLVDUj8I2C.QX4EDO0wSO2gjNzEzW}
pwn
pwned
pwns
pwning
```

### New Learnings
None.
### References
None.
##
## Grepping live output
### Solve

**Flag** `pwn.college{YuVFvscIDhatcqrjoN7CCpBQUrH.QX5EDO0wSO2gjNzEzW}`
```bash
hacker@piping~grepping-live-output:~$ /challenge/run | grep pwn
[INFO] WELCOME! This challenge makes the following asks of you:
[INFO] - the challenge checks for a specific process at the other end of stdout : grep
[INFO] - the challenge will output a reward file if all the tests pass : /challenge/.data.txt

[HYPE] ONWARDS TO GREATNESS!

[INFO] This challenge will perform a bunch of checks.
[INFO] If you pass these checks, you will receive the /challenge/.data.txt file.

[TEST] You should have redirected my stdout to another process. Checking...
[TEST] Performing checks on that process!

[INFO] The process' executable is /nix/store/8b4vn1iyn6kqiisjvlmv67d1c0p3j6wj-gnugrep-3.11/bin/grep.
[INFO] This might be different than expected because of symbolic links (for example, from /usr/bin/python to /usr/bin/python3 to /usr/bin/python3.8).
[INFO] To pass the checks, the executable must be grep.

[PASS] You have passed the checks on the process on the other end of my stdout!
[PASS] Success! You have satisfied all execution requirements.
pwn.college{YuVFvscIDhatcqrjoN7CCpBQUrH.QX5EDO0wSO2gjNzEzW}
pwn
pwned
pwns
pwning
```
### New Learnings
We don't need to store the output of a command in a file to look through it's output, we can use `|` (pipe) operator right after the command.
### References
None.
##
## Grepping errors
Grepping through errors
### Solve
**Flag** `pwn.college{wMJ3kBP9Ze5EKJY_qovQdf_Q3U8.QX1ATO0wSO2gjNzEzW}`
```bash
hacker@piping~grepping-errors:~$ /challenge/run 2>& 1
[INFO] WELCOME! This challenge makes the following asks of you:
[INFO] - the challenge checks for a specific process at the other end of stderr : grep
[INFO] - the challenge will output a reward file if all the tests pass : /challenge/.data.txt

[HYPE] ONWARDS TO GREATNESS!

[INFO] This challenge will perform a bunch of checks.
[INFO] If you pass these checks, you will receive the /challenge/.data.txt file.

[TEST] You should have redirected my stderr to another process. Checking...

[FAIL] You did not satisfy all the execution requirements.
[FAIL] Specifically, you must fix the following issue:
[FAIL]   stderr of this process does not appear to be a pipe!
hacker@piping~grepping-errors:~$ /challenge/run 2>& 1 | grep pwn
[INFO] WELCOME! This challenge makes the following asks of you:
[INFO] - the challenge checks for a specific process at the other end of stderr : grep
[INFO] - the challenge will output a reward file if all the tests pass : /challenge/.data.txt

[HYPE] ONWARDS TO GREATNESS!

[INFO] This challenge will perform a bunch of checks.
[INFO] If you pass these checks, you will receive the /challenge/.data.txt file.

[TEST] You should have redirected my stderr to another process. Checking...
[TEST] Performing checks on that process!

[INFO] The process' executable is /nix/store/8b4vn1iyn6kqiisjvlmv67d1c0p3j6wj-gnugrep-3.11/bin/grep.
[INFO] This might be different than expected because of symbolic links (for example, from /usr/bin/python to /usr/bin/python3 to /usr/bin/python3.8).
[INFO] To pass the checks, the executable must be grep.

[PASS] You have passed the checks on the process on the other end of my stderr!
[PASS] Success! You have satisfied all execution requirements.
pwns
pwning
pwn.college{wMJ3kBP9Ze5EKJY_qovQdf_Q3U8.QX1ATO0wSO2gjNzEzW}
pwned
pwn
```
### New Learnings
The `|` operator only redirects standard output to another program.<br>
We can use `>&` operator to redirect a file descriptor to another file descriptor.

### References
None.
##
## Filtering with grep -v
Introduction to `grep -v` command
**Flag** `pwn.college{Ih_1fzxGDtdN8aSJgROITmVyJCs.0FOxEzNxwSO2gjNzEzW}`
### Solve
``` bash 
hacker@piping~filtering-with-grep-v:~$ /challenge/run | grep -v DECOY
pwn.college{Ih_1fzxGDtdN8aSJgROITmVyJCs.0FOxEzNxwSO2gjNzEzW}
```
### New Learnings
We can use `grep -v` command to filter out a string
### References
None.
##
## Duplicating piped dated with tee


