# Digesting Documentation
## Learning from Documentation
Introduction to arguments of programs
### Solve
Passed the given argument to the specified command

**Flag** `pwn.college{ECcAgi1H8KIXEXtjSZu_Wb0fxVZ.QX0ITO0wSO2gjNzEzW}`
```bash
hacker@man~learning-from-documentation:~$ /challenge/challenge --giveflag
Correct argument! Here is your flag:
pwn.college{ECcAgi1H8KIXEXtjSZu_Wb0fxVZ.QX0ITO0wSO2gjNzEzW}
```
### New Learnings
We sometimes have to pass arguments to programs to use them as per our needs.

### References
None.

## Learning Complex Usage
Complex usage of arguments, arguments having arguments of their own.
### Solve
Passed the argument of the argument of the `/challenge/challenge` command

**Flag** `pwn.college{kIw4w6W4HAr6hbGDPlvGwNzYL9r.QX1ITO0wSO2gjNzEzW}`
```bash
hacker@man~learning-complex-usage:~$ /challenge/challenge --printfile /flag
Correct argument! Here is the /flag file:
pwn.college{kIw4w6W4HAr6hbGDPlvGwNzYL9r.QX1ITO0wSO2gjNzEzW}
```
### New Learnings
Arguments of a program can take arguments.
### References 
None.
##
## Reading Manuals
Introduction to `man` command
### Solve
Displayed manual of the `challenge` command, and then the passed the argument given to get the flag using `/challenge/challenge`

**Flag** `pwn.college{EeZji8EvcHrCb7OUUuAJuHTBe9I.QX0EDO0wSO2gjNzEzW}`
```bash
hacker@man~reading-manuals:~$ man /challenge/challenge
It looks like you're trying to run 'man' with an absolute path to the command. 
That isn't how man works! Instead, man references a centralized database of 
manpages, and fetches one based on a name, not a file path. So to pull up the 
man page for the program '/bin/ls', you would run 'man ls', not 'man /bin/ls'.
hacker@man~reading-manuals:~$ man challenge
hacker@man~reading-manuals:~$ challenge --ejivcr 871
bash: challenge: command not found
hacker@man~reading-manuals:~$ man challenge
hacker@man~reading-manuals:~$ challenge --ejivcr 879
bash: challenge: command not found
hacker@man~reading-manuals:~$ /challenge/challenge --ejivcr 879
Correct usage! Your flag: pwn.college{EeZji8EvcHrCb7OUUuAJuHTBe9I.QX0EDO0wSO2gjNzEzW}
hacker@man~reading-manuals:~$ man challenge
```
### New Learnings
`man` does not take the absolute path to a command, it gets command using its name not its file path.
### References 
None.

## Searching Manuals
Searching a man page to get the correct command.
### Solve
Searched the man page of the `challenge` command to find the argument that would give me the flag

**Flag** `pwn.college{8KN4r8KyAjYXbzb_83L2wDT52Ae.QX1EDO0wSO2gjNzEzW}`
```bash
hacker@man~searching-manuals:~$ man challenge
hacker@man~searching-manuals:~$ /challenge/challenge --jqrrh
Initializing...
Correct usage! Your flag: pwn.college{8KN4r8KyAjYXbzb_83L2wDT52Ae.QX1EDO0wSO2gjNzEzW}
```
### New Learnings
We can search man pages using `/` and `?` (to search backwards). 
<br>Press `n` to go the next result and `N` to go the previous.

### References
None.

## Searching for Manuals
Searching the manpage of the `man` command to find out the correct command

### Solve
Searched the manpage of `man` to know how to find commands, then used the `regex` argument to find the manpage of the `challenge` command.
<br>Then read the manpage of the `challenge` command and captured the flag

**Flag** `pwn.college{AnT8wQOT7l1lJQKprd2J-OKwSFW.QX2EDO0wSO2gjNzEzW}`
```bash
hacker@man~searching-for-manuals:~$ man man
hacker@man~searching-for-manuals:~$ man --regex
What manual page do you want?
For example, try 'man man'.
hacker@man~searching-for-manuals:~$ man --regex challenge
hacker@man~searching-for-manuals:~$ /challenge/challenge nwllPR 871
Incorrect usage! Please read the hidden challenge man page!
hacker@man~searching-for-manuals:~$ /challenge/challenge --nwllPR 871
Incorrect usage! Please read the hidden challenge man page!
hacker@man~searching-for-manuals:~$ man --regex challenge
hacker@man~searching-for-manuals:~$ challenge --nwllpr NUM
bash: challenge: command not found
hacker@man~searching-for-manuals:~$ /challenge/challenge --nwllpr 871
Correct usage! Your flag: pwn.college{AnT8wQOT7l1lJQKprd2J-OKwSFW.QX2EDO0wSO2gjNzEzW}
```
### New Learnings
We can pass `--regex` argument in `man` command to show the pages with any part of their name matching with the argument given.

### References
None.
##
## Helpful Programs
Passing `--help` argument which tells us how to use the command.
### Solve
Passed the `-h` argument to `/challenge/challenge` to learn to how to get the flag.
**Flag** `pwn.college{MwqYRivAxAF-rRwRLsLr1bsVvba.QX3IDO0wSO2gjNzEzW}`
```bash
hacker@man~helpful-programs:~$ challenge -h
bash: challenge: command not found
hacker@man~helpful-programs:~$ /challenge/challenge -h
usage: a challenge to make you ask for help [-h] [--fortune] [-v] [-g GIVE_THE_FLAG] [-p]

optional arguments:
  -h, --help            show this help message and exit
  --fortune             read your fortune
  -v, --version         get the version number
  -g GIVE_THE_FLAG, --give-the-flag GIVE_THE_FLAG
                        get the flag, if given the correct value
  -p, --print-value     print the value that will cause the -g option to give you the flag
hacker@man~helpful-programs:~$ /challenge/challenge -p
The secret value is: 130
hacker@man~helpful-programs:~$ /challenge/challenge -p 130
usage: a challenge to make you ask for help [-h] [--fortune] [-v] [-g GIVE_THE_FLAG] [-p]
a challenge to make you ask for help: error: unrecognized arguments: 130
hacker@man~helpful-programs:~$ /challenge/challenge -g 130
Correct usage! Your flag: pwn.college{MwqYRivAxAF-rRwRLsLr1bsVvba.QX3IDO0wSO2gjNzEzW}
```
### New Learnings
A few commands may not have a manpage so we can learn how to use those commands by passing the `--help` or `-h` argument.

### References
None.
##
## Help for Builtins
Introduction to builtins.
### Solve

**Flag** `pwn.college{YTs-MHLgBTgfJbhgAszxjGgezHt.QX0ETO0wSO2gjNzEzW}`

```bash
hacker@man~help-for-builtins:~$ help challenge
challenge: challenge [--fortune] [--version] [--secret SECRET]
    This builtin command will read you the flag, given the right arguments!
    
    Options:
      --fortune		display a fortune
      --version		display the version
      --secret VALUE	prints the flag, if VALUE is correct

    You must be sure to provide the right value to --secret. That value
    is "YTs-MHLg".
hacker@man~help-for-builtins:~$ challenge --secret YTs-MHLg
Correct! Here is your flag!
pwn.college{YTs-MHLgBTgfJbhgAszxjGgezHt.QX0ETO0wSO2gjNzEzW}
```

### New Learnings
Some commands are built into the shell itself, the shell doesn't launch any programs it handles them internally.

### References
None.