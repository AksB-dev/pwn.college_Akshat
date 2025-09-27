# File Globbing
## Matching with *
### Solve
**Flag** `pwn.college{gm6HIwbBCtq4_bA9b-3j8s77lKz.QXxIDO0wSO2gjNzEzW}`
```bash
hacker@globbing~matching-with-:~$ cd /ch*
hacker@globbing~matching-with-:/challenge$ /challenge/run 
You ran me with the working directory of /challenge! Here is your flag:
pwn.college{gm6HIwbBCtq4_bA9b-3j8s77lKz.QXxIDO0wSO2gjNzEzW}
```
### New Learnings
`*` is a glob
<br> terminal will replace `*` with any argument is matches the pattern.
`*` does not match `/` or a leading `.`

### References
None.

## Matching with ?
### Solve
**Flag** 
`pwn.college{AG-a0pO63CaHOGSwcO87YFr6Mv-.QXyIDO0wSO2gjNzEzW}`
```bash
hacker@globbing~matching-with-:~$ cd /?ha??enge
hacker@globbing~matching-with-:/challenge$ /challenge/run 
You ran me with the working directory of /challenge! Here is your flag:
pwn.college{AG-a0pO63CaHOGSwcO87YFr6Mv-.QXyIDO0wSO2gjNzEzW}
```
### New Learnings
`?` is like `*` but only for a single character.
### References 
None.
##
### Matching with []
**Flag** `pwn.college{4In-_Mcu8QbRb9kail24lS6R3q8.QXzIDO0wSO2gjNzEzW}`
```bash
hacker@globbing~matching-with-:~$ cd /challenge/files
hacker@globbing~matching-with-:/challenge/files$ /challenge/run
Error: you did not use a square bracket glob...
hacker@globbing~matching-with-:/challenge/files$ /challenge/run file_[bash]
You got it! Here is your flag!
pwn.college{4In-_Mcu8QbRb9kail24lS6R3q8.QXzIDO0wSO2gjNzEzW}
```
### New Learnings
`[]` is kinda like `?`, but it is a subset of potential characters, it will match with anyone of the characters inside the brackets.

### References
None.
##
## Matching paths with []
### Solve
**Flag** `pwn.college{gYuEnd6fb5yZgSsUUb9vgkX0HDV.QX0IDO0wSO2gjNzEzW}`

```bash
hacker@globbing~matching-paths-with-:~$ /challenge/run ~/challenge/files/file_[bash]
Your expansion did not expand to the requested files (/challenge/files/file_b, 
/challenge/files/file_a, /challenge/files/file_s, and /challenge/files/file_h). 
Instead, it expanded to:
/home/hacker/challenge/files/file_[bash]
hacker@globbing~matching-paths-with-:~$ /challenge/run home/hacker/challenge/files/file_[bash]
Your expansion did not expand to the requested files (/challenge/files/file_b, 
/challenge/files/file_a, /challenge/files/file_s, and /challenge/files/file_h). 
Instead, it expanded to:
home/hacker/challenge/files/file_[bash]
hacker@globbing~matching-paths-with-:~$ /challenge/run home/hacker/challenge/file_[bash]
Error: you will need to specify the path to the files as part of your glob 
argument, since they are in a different directory than your current working 
directory!
HINT: You are trying to specify files in the home/hacker/challenge directory, 
but the files are actually in the /challenge/files directory.
hacker@globbing~matching-paths-with-:~$ /challenge/run home/hacker/challenge/files/file_[bash]
Your expansion did not expand to the requested files (/challenge/files/file_b, 
/challenge/files/file_a, /challenge/files/file_s, and /challenge/files/file_h). 
Instead, it expanded to:
home/hacker/challenge/files/file_[bash]
hacker@globbing~matching-paths-with-:~$ /challenge/run /challenge/files/file_[bash]
You got it! Here is your flag!
pwn.college{gYuEnd6fb5yZgSsUUb9vgkX0HDV.QX0IDO0wSO2gjNzEzW}
```
### New Learnings
We can expand the paths of the program using the globbed arguments

### References
None.

##
## Multiple globs
### Solve
**Flag** `pwn.college{QB9rGBTg6GC4GArcMgVc1gkCr1p.0lM3kjNxwSO2gjNzEzW}`
```bash
hacker@globbing~multiple-globs:~$ cd /challenge/files
hacker@globbing~multiple-globs:/challenge/files$ /challenge/run /*p*
Error: your argument is too long! It must be 3 characters or less.
hacker@globbing~multiple-globs:/challenge/files$ /challenge/run/*p*
bash: /challenge/run/*p*: Not a directory
hacker@globbing~multiple-globs:/challenge/files$ /challenge/run *p*
You got it! Here is your flag!
pwn.college{QB9rGBTg6GC4GArcMgVc1gkCr1p.0lM3kjNxwSO2gjNzEzW}
```

### New Learnings
Multiple globs in a single word, 
<br>
`*p*` will cover anything that comes before `p` and everything that comes after `p`

### References
None.
##
## Mixing Globs
### Solve
I saw that `challenging`, `educational` and `pwning` were the only words starting from either `c`, `e` or `p`. The words had something after, which is why I used `*` after the `[]`

**Flag** `pwn.college{U-WUDeqLFn8zrk_SL7rGaX5jDqC.QX1IDO0wSO2gjNzEzW}`
```bash
hacker@globbing~mixing-globs:~$ cd /challenge/files
hacker@globbing~mixing-globs:/challenge/files$ ls 
amazing    challenging  educational  great  incredible  kind      magical  optimistic  queenly  splendid   uplifting   wonderful  youthful
beautiful  delightful   fantastic    happy  jovial      laughing  nice     pwning      radiant  thrilling  victorious  xenial     zesty
hacker@globbing~mixing-globs:/challenge/files$ /challenge/run i?n
Error: you did not use a square bracket glob...
hacker@globbing~mixing-globs:/challenge/files$ /challenge/run [i?n]
Your expansion did not expand to the requested files (challenging, educational, 
pwning). Instead, it expanded to:
[i?n]
hacker@globbing~mixing-globs:/challenge/files$ /challenge/run *[i*n]*
Error: your argument is too long! It must be 6 characters or less.
hacker@globbing~mixing-globs:/challenge/files$ /challenge/run *[i*n]*
Error: your argument is too long! It must be 6 characters or less.
hacker@globbing~mixing-globs:/challenge/files$ /challenge/run *[i*n]
Your expansion did not expand to the requested files (challenging, educational, 
pwning). Instead, it expanded to:
*[i*n]
hacker@globbing~mixing-globs:/challenge/files$ /challenge/run *[in]
Your expansion did not expand to the requested files (challenging, educational, 
pwning). Instead, it expanded to:
*[in]
hacker@globbing~mixing-globs:/challenge/files$ /challenge/run *[in]*
Your expansion did not expand to the requested files (challenging, educational, 
pwning). Instead, it expanded to:
amazing beautiful challenging delightful educational fantastic incredible jovial kind laughing magical nice optimistic pwning queenly radiant splendid thrilling uplifting victorious wonderful xenial
hacker@globbing~mixing-globs:/challenge/files$ /challenge/run [pec]*
You got it! Here is your flag!
pwn.college{U-WUDeqLFn8zrk_SL7rGaX5jDqC.QX1IDO0wSO2gjNzEzW}
```
### New Learnings
None.
### References
None.
##
## Exclusionary globbing
**Flag** `pwn.college{sRLEgXjwd7GtfgzfTXXiypQoRzX.QX2IDO0wSO2gjNzEzW}`
```bash
hacker@globbing~exclusionary-globbing:~$ cd /challenge/files
hacker@globbing~exclusionary-globbing:/challenge/files$ /challenge/run [^pwn]
Your expansion did not expand to the requested files (amazing beautiful 
challenging delightful educational fantastic great happy incredible jovial kind 
laughing magical optimistic queenly radiant splendid thrilling uplifting 
victorious xenial youthful zesty).
Instead, it expanded to:
[^pwn]
hacker@globbing~exclusionary-globbing:/challenge/files$ /challenge/run [^pwn]*
You got it! Here is your flag!
pwn.college{sRLEgXjwd7GtfgzfTXXiypQoRzX.QX2IDO0wSO2gjNzEzW}
```
### New Learnings
We can filter out characters we don't want by typing `!` or `^` before the characters in the square bracket.

### References.
None.
##
### Tab Completion
### Solve
**Flag** `pwn.college{sKnAd_ha9RfPwD_VBwX_V5gRLZU.0FN0EzNxwSO2gjNzEzW}`
```bash
hacker@globbing~tab-completion:~$ cat /challenge/pwncollege
cat: /challenge/pwncollege: No such file or directory
hacker@globbing~tab-completion:~$ cat /challenge/pwncollege​ 
pwn.college{sKnAd_ha9RfPwD_VBwX_V5gRLZU.0FN0EzNxwSO2gjNzEzW}
```
### New Learnings
When we press tab in the keyboard, the terminal autocompletes the file or directory name.

### References
None.
##
## Multiple options for Tab Completion
### Solve
Kept pressing the `Tab` key, until I found the flag file.
**Flag** `pwn.college{U37itucNEJG6fUqmbof0uHtq_lK.0lN0EzNxwSO2gjNzEzW}`
```bash
hacker@globbing~multiple-options-for-tab-completion:~$ cat /challenge/files/pwn
pwn                    pwn-college            pwn-the-planet         pwncollege-family      pwncollege-flag        pwncollege-flamingo    pwncollege-flyswatter  pwncollege-hacking     
hacker@globbing~multiple-options-for-tab-completion:~$ cat /challenge/files/pwncollege-
pwncollege-family      pwncollege-flag        pwncollege-flamingo    pwncollege-flyswatter  pwncollege-hacking     
hacker@globbing~multiple-options-for-tab-completion:~$ cat /challenge/files/pwncollege-fl
pwncollege-flag        pwncollege-flamingo    pwncollege-flyswatter  
hacker@globbing~multiple-options-for-tab-completion:~$ cat /challenge/files/pwncollege-fla
pwncollege-flag      pwncollege-flamingo  
hacker@globbing~multiple-options-for-tab-completion:~$ cat /challenge/files/pwncollege-flag
pwn.college{U37itucNEJG6fUqmbof0uHtq_lK.0lN0EzNxwSO2gjNzEzW}
```
### New Learnings
When we press `Tab` key, the terminal will auto-complete until the point in which there are multiple options.
<br>If we press `Tab` one more time, it will display all the options possible.
<br>Some other shells cycle through the options if the `Tab` key is pressed multiple times.

### References
None.
##
## Tab Completion on commands
### Solve
**Flag** `pwn.college{YGWbDG45r2BEbbEuQ7EdK8dTskW.0VN0EzNxwSO2gjNzEzW}`
```bash
hacker@globbing~tab-completion-on-commands:~$ pwncollege-3659 
.bash_history  .config/       .lesshst       not-the-flag   ~/             
hacker@globbing~tab-completion-on-commands:~$ pwncollege-3659 not-the-flag
Correct! Here is your flag:
pwn.college{YGWbDG45r2BEbbEuQ7EdK8dTskW.0VN0EzNxwSO2gjNzEzW}
```
### New Learnings
Pressing the `Tab` key can also auto-complete commands.
### References 
None.

