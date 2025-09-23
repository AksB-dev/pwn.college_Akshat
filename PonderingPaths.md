# Pondering Paths

## The Root
Invoking pwn program using its absolute path

### Solve
**Flag** `pwn.college{wqnQrkGXeJwZAXWMEyTAVejJxGj.QX4cTO0wSO2gjNzEzW}`



```bash
hacker@paths~the-root:~$ cd pwn
bash: cd: pwn: No such file or directory
hacker@paths~the-root:~$ /pwn
BOOM!!!
Here is your flag:
pwn.college{wqnQrkGXeJwZAXWMEyTAVejJxGj.QX4cTO0wSO2gjNzEzW}
```

### New Learnings
Filesystem starts from '/'.
To invoke a program, we can write its path.

### References
None.
##

## Program and absolute paths
More complicated path

### Solve
**Flag** `pwn.college{QoBHQ8ruk-93Cceo0Db9HVFpGml.QX1QTN0wSO2gjNzEzW}`

```bash
hacker@paths~program-and-absolute-paths:~$ /challenge/run
Correct!!!
/challenge/run is an absolute path! Here is your flag:
pwn.college{QoBHQ8ruk-93Cceo0Db9HVFpGml.QX1QTN0wSO2gjNzEzW}
hacker@paths~program-and-absolute-paths:~$ 
```

### New Learnings
We can invoke programs that are in other directories also, they need not be in the root directory.

### References
None.
##

## Position thy self
Navigating between directories

**Flag** `pwn.college{0659nd1fB5KEb--WCGS6jfi62JC.QX2QTN0wSO2gjNzEzW}`

First, I tried to directly invoke the `/challenge/run` program without going to the right directory. I then changed the directory, and then invoked the program.

```bash
hacker@paths~position-thy-self:~$ cd /challenge/run
bash: cd: /challenge/run: Not a directory
hacker@paths~position-thy-self:~$ cd /challenge
hacker@paths~position-thy-self:/challenge$ /challenge/run
Incorrect...
You are not currently in the /usr/share/zoneinfo/posix/Asia directory.
Please use the `cd` utility to change directory appropriately.
hacker@paths~position-thy-self:/challenge$ cd /usr/share/zoneinfo/posix/Asia
hacker@paths~position-thy-self:/usr/share/zoneinfo/posix/Asia$ /challenge/run
Correct!!!
/challenge/run is an absolute path, invoked from the right directory!
Here is your flag:
pwn.college{0659nd1fB5KEb--WCGS6jfi62JC.QX2QTN0wSO2gjNzEzW}
hacker@paths~position-thy-self:/usr/share/zoneinfo/posix/Asia$ 
hacker@paths~position-thy-self:/usr/share/zoneinfo/posix/Asia$ ~
bash: /home/hacker: Is a directory
hacker@paths~position-thy-self:/usr/share/zoneinfo/posix/Asia$ cd ~
```

### New Learnings
A Program can only be invoked from its specific path.,<br>
`~` shows the current path.

### References.
None.
##

## Position elsewhere
Navigating Directories
### Solve
**Flag** `pwn.college{8VNksZKS_ksaxyircyAKC3FKIJF.QX3QTN0wSO2gjNzEzW}`

```bash
hacker@paths~position-elsewhere:~$ cd ~
hacker@paths~position-elsewhere:~$ ~
bash: /home/hacker: Is a directory
hacker@paths~position-elsewhere:~$ cd
hacker@paths~position-elsewhere:~$ /challenge/run
Incorrect...
You are not currently in the /etc/apt/sources.list.d directory.
Please use the `cd` utility to change directory appropriately.
hacker@paths~position-elsewhere:~$ cd /etc/apt/sources.list.d
hacker@paths~position-elsewhere:/etc/apt/sources.list.d$ /challenge/run
Correct!!!
/challenge/run is an absolute path, invoked from the right directory!
Here is your flag:
pwn.college{8VNksZKS_ksaxyircyAKC3FKIJF.QX3QTN0wSO2gjNzEzW}
```
### New Learnings
None.
### References
None.
##
## Position yet elsewhere
Navigating directories.
### Solve
**Flag** `pwn.college{sIAl23VnRgyo12K3VSTo_7cLcmi.QX4QTN0wSO2gjNzEzW}`

```bash
hacker@paths~position-yet-elsewhere:~$ /challenge/run
Incorrect...
You are not currently in the /etc directory.
Please use the `cd` utility to change directory appropriately.
hacker@paths~position-yet-elsewhere:~$ cd /etc
hacker@paths~position-yet-elsewhere:/etc$ /challenge/run
Correct!!!
/challenge/run is an absolute path, invoked from the right directory!
Here is your flag:
pwn.college{sIAl23VnRgyo12K3VSTo_7cLcmi.QX4QTN0wSO2gjNzEzW}
```
### New Learnings
None.
### References
None.

##
## implicit relative paths, from /
Invoke the program using a relative path

### Solve
First, I had to change the current working directory to `/`, and then invoke the program.

**Flag** `pwn.college{YD76cCAwwsCUyud4HjdvF1jiu9h.QX5QTN0wSO2gjNzEzW}`

```bash
hacker@paths~implicit-relative-paths-from-:~$ ../challenge/run
bash: ../challenge/run: No such file or directory
hacker@paths~implicit-relative-paths-from-:~$ cd /
hacker@paths~implicit-relative-paths-from-:/$ challenge/run
Correct!!!
challenge/run is a relative path, invoked from the right directory!
Here is your flag:
pwn.college{YD76cCAwwsCUyud4HjdvF1jiu9h.QX5QTN0wSO2gjNzEzW}
```

### New Learnings
Relative path does not start with root `/`
<br>Relative path is interpreted relative to the current working directory.<br>
`..` refers to parent directory

### References
None.
##
## explicit relative paths, from /






