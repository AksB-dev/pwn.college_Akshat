# Comprehending Commands
## cat: not the pet, but the command!
Introduction to the `cat` command

### Solve
Provided the file name `flag` as the argument to the `cat` command.

**Flag** `pwn.college{sEKA2mOl57huq61hZZWNMV7VXog.QXxcTN0wSO2gjNzEzW}`

```bash
hacker@commands~cat-not-the-pet-but-the-command:~$ cat flag
pwn.college{sEKA2mOl57huq61hZZWNMV7VXog.QXxcTN0wSO2gjNzEzW}
```

### New Learnings
`cat` is used to read out files.
<br> Even if it gets more than one argumnent it will concacatenate the contents of the files.
### References
None
##
## catting absolute paths
Using absolute paths as arguments to the command `cat`

### Solve
Wrote the absolute path as the argument.

**Flag** `pwn.college{QKc9UjIdwoS04_yYUCT5dZUHr9u.QX5ETO0wSO2gjNzEzW}`

```bash
hacker@commands~catting-absolute-paths:~$ cat /flag
pwn.college{QKc9UjIdwoS04_yYUCT5dZUHr9u.QX5ETO0wSO2gjNzEzW}
```
 ### New Learnings
 Absolute paths can used as arguments to the `cat` command.
 
 ### References
 None
 ##
 ## More catting practice
 ### Solve
 
 **Flag** `pwn.college{AlzU3pB5k2-yJo-VBOTtnvFdnXp.QXwITO0wSO2gjNzEzW}`
 
```bash
You cannot use the 'cd' command in this level, and must retrieve the flag by 
absolute path. Plus, I hid the flag in a different directory! You can find it 
in the file /usr/share/apache2/flag. Go cat it out **without** cding into that 
directory!
hacker@commands~more-catting-practice:~$ cd /usr
You used 'cd'! In this level, I don't allow you to change the working directory 
--- you MUST chase pass 'cat' the absolute path of where I put it on the 
filesystem (which is /usr/share/apache2/flag).
hacker@commands~more-catting-practice:~$ cat /usr/share/apache2/flag
pwn.college{AlzU3pB5k2-yJo-VBOTtnvFdnXp.QXwITO0wSO2gjNzEzW}
```
### New Learnings
None.
### References
None.
##
## grepping for a needle in haystack
Introduction to `grep` command
### Solve
Flag always starts from `pwn.college` so I searched it up using the `grep` in the mentioned file.
 **Flag** `pwn.college{0euhHktX5B2dP7OYyX6LyRj-JpG.QX3EDO0wSO2gjNzEzW}`

```bash
hacker@commands~grepping-for-a-needle-in-a-haystack:~$ grep pwn.college /challenge/data.txt
pwn.college{0euhHktX5B2dP7OYyX6LyRj-JpG.QX3EDO0wSO2gjNzEzW}
```
### New Learnings
`grep` command searches the file for the lines containing the string specified by the user, and it will print it in the console.

### References
None.

##
## comparing files
Introduction to `diff` command
### Solve
Changed to the `challenge` directory.
Compared the two files using the `diff` command
 
**Flag** `pwn.college{w8_lBTOCt8k9REdQE4VFFBiAo9k.01MwMDOxwSO2gjNzEzW}`

```bash
hacker@commands~comparing-files:~$ cd /challenge
hacker@commands~comparing-files:/challenge$ diff decoys_only.txt decoys_and_real.txt 
88a89
> pwn.college{w8_lBTOCt8k9REdQE4VFFBiAo9k.01MwMDOxwSO2gjNzEzW}
```
### New Learnings
`diff` command compares two files, and shows what is different between them.<br>
```xcx``` - Line `x` changed<br>
`<` - Used to denote the first file<br>
`>` - Used to denote the second file<br>
`88a89` - after the 88th line of the first file, the second file has an additional line.

### References
None.
##
## listing files
Introduction to `ls` command.
### Solve
Found the program by listing the files in the `challenges` directory.

**Flag** `pwn.college{cIpMn8Kv3eW2roKnY9TgtMUaAsg.QX4IDO0wSO2gjNzEzW}`
```bash
hacker@commands~listing-files:~$ ls /challenge
15795-renamed-run-26917  DESCRIPTION.md
hacker@commands~listing-files:~$ /challenge/15795-renamed-run-26917 
Yahaha, you found me! Here is your flag:
pwn.college{cIpMn8Kv3eW2roKnY9TgtMUaAsg.QX4IDO0wSO2gjNzEzW}
```

### New Learnings
`ls` command will list all the files in the directories mentioned.
<br> It will list the files in the current directory if no argument is there

### Reference
None.
##
## touching files
Introduction to `touch` command.
### Solve
Created the two files mentioned.

**Flag** `pwn.college{8eu36sPCPq8ziO0yM3zdkautLgJ.QXwMDO0wSO2gjNzEzW}`

```bash
hacker@commands~touching-files:~$ touch /tmp/pwn
hacker@commands~touching-files:~$ touch /tmp/college
hacker@commands~touching-files:~$ /challenge/run
Success! Here is your flag:
pwn.college{8eu36sPCPq8ziO0yM3zdkautLgJ.QXwMDO0wSO2gjNzEzW}
```
### New Learnings
`touch` command creates a file.

### References
##
## removing files
Introduction to `rm` command.
### Solve
Deleted the file mentioned.

**Flag** `pwn.college{U6SDyBOJRhYbBJg9PQ3iIYEq3qZ.QX2kDM1wSO2gjNzEzW}`

```bash
hacker@commands~removing-files:~$ ls
 delete_me  '~'
hacker@commands~removing-files:~$ rm delete_me 
hacker@commands~removing-files:~$ ls
'~'
hacker@commands~removing-files:~$ /challenge/check
Excellent removal. Here is your reward:
pwn.college{U6SDyBOJRhYbBJg9PQ3iIYEq3qZ.QX2kDM1wSO2gjNzEzW}
```
### New Learnings
`rm` command removes a file.

### References
None.
##
## moving files
Introduction to `mv` command.
### Solve
Moved the file to the directory mentioned.

**Flag** `pwn.college{8SFsr-mB-UsooXCIV_CBcw-vQm6.0VOxEzNxwSO2gjNzEzW}`

```bash
hacker@commands~moving-files:~$ mv /flag /tmp/hack-the-planet
Correct! Performing 'mv /flag /tmp/hack-the-planet'.
hacker@commands~moving-files:~$ /challenge/check
Congrats! You successfully moved the flag to /tmp/hack-the-planet! Here it is:
pwn.college{8SFsr-mB-UsooXCIV_CBcw-vQm6.0VOxEzNxwSO2gjNzEzW}
```
### New Learnings
`mv` command moves a file, the directory (to which the file should be moved to ) should be written after the file name.

### References
None.
##
## hidden files
Introduction to `ls -a` command to find hidden files.
### Solve
Found the hidden file by using `ls -a` command.

**Flag** `pwn.college{ADDbZlG2VGmXe2rsq9JkJMMZXpy.QXwUDO0wSO2gjNzEzW}`
```bash
hacker@commands~hidden-files:~$ ls /
bin  boot  challenge  dev  etc  home  lib  lib32  lib64  libx32  media  mnt  nix  opt  proc  root  run  sbin  srv  sys  tmp  usr  var
hacker@commands~hidden-files:~$ ls -a /
.  ..  .dockerenv  .flag-208661975928676  bin  boot  challenge  dev  etc  home  lib  lib32  lib64  libx32  media  mnt  nix  opt  proc  root  run  sbin  srv  sys  tmp  usr  var
hacker@commands~hidden-files:~$ /.flag-208661975928676
bash: /.flag-208661975928676: Permission denied
hacker@commands~hidden-files:~$ cat flag-208661975928676
cat: flag-208661975928676: No such file or directory
hacker@commands~hidden-files:~$ cat /flag-208661975928676
cat: /flag-208661975928676: No such file or directory
hacker@commands~hidden-files:~$ cat .flag-208661975928676
cat: .flag-208661975928676: No such file or directory
hacker@commands~hidden-files:~$ cat /.flag-208661975928676
pwn.college{ADDbZlG2VGmXe2rsq9JkJMMZXpy.QXwUDO0wSO2gjNzEzW}
```

### New Learnings
`ls -a` command will list hidden files along with the other files.
<br> Files that start with `.` don't get listed when `ls` command is run. 

### Reference
None.
##
## An Epic FileSystem Quest
Finding the hidden flag using the hints given.
### Solve
Used commands to go to the next step.
<br> Used absolute paths for `ls` and `cat` commands, to not change directories.

**Flag** `pwn.college{84-aiPAOjNlWhSq5amuyCStrDE8.QX5IDO0wSO2gjNzEzW}`

```bash
hacker@commands~an-epic-filesystem-quest:~$ cd /
hacker@commands~an-epic-filesystem-quest:/$ ls
TRACE  bin  boot  challenge  dev  etc  flag  home  lib  lib32  lib64  libx32  media  mnt  nix  opt  proc  root  run  sbin  srv  sys  tmp  usr  var
hacker@commands~an-epic-filesystem-quest:/$ cat TRACE 
Congratulations, you found the clue!
The next clue is in: /opt/linux/linux-5.4/arch/sh/include/uapi/asm

The next clue is **hidden** --- its filename starts with a '.' character. You'll need to look for it using special options to 'ls'.
hacker@commands~an-epic-filesystem-quest:/$ cd /opt/linux/linux-5.4/arch/sh/include/uapi/asm
hacker@commands~an-epic-filesystem-quest:/opt/linux/linux-5.4/arch/sh/include/uapi/asm$ ls
Kbuild    byteorder.h  cpu-features.h   ioctls.h       posix_types_32.h  ptrace.h     ptrace_64.h  sigcontext.h  sockios.h  swab.h   unistd.h
auxvec.h  cachectl.h   hw_breakpoint.h  posix_types.h  posix_types_64.h  ptrace_32.h  setup.h      signal.h      stat.h     types.h  unistd_64.h
hacker@commands~an-epic-filesystem-quest:/opt/linux/linux-5.4/arch/sh/include/uapi/asm$ ls -a
.   .TIP    auxvec.h     cachectl.h      hw_breakpoint.h  posix_types.h     posix_types_64.h  ptrace_32.h  setup.h       signal.h   stat.h  types.h   unistd_64.h
..  Kbuild  byteorder.h  cpu-features.h  ioctls.h         posix_types_32.h  ptrace.h          ptrace_64.h  sigcontext.h  sockios.h  swab.h  unistd.h
hacker@commands~an-epic-filesystem-quest:/opt/linux/linux-5.4/arch/sh/include/uapi/asm$ cat .TIP
Great sleuthing!
The next clue is in: /opt/linux/linux-5.4/drivers/gpu/drm/nouveau/nvkm/subdev/top

Watch out! The next clue is **trapped**. You'll need to read it out without 'cd'ing into the directory; otherwise, the clue will self destruct!
hacker@commands~an-epic-filesystem-quest:/opt/linux/linux-5.4/arch/sh/include/uapi/asm$ ls /opt/linux/linux-5.4/drivers/gpu/drm/nouveau/nvkm/subdev/top
BLUEPRINT-TRAPPED  Kbuild  base.c  gk104.c  priv.h
hacker@commands~an-epic-filesystem-quest:/opt/linux/linux-5.4/arch/sh/include/uapi/asm$ cat /opt/linux/linux-5.4/drivers/gpu/drm/nouveau/nvkm/subdev/top
cat: /opt/linux/linux-5.4/drivers/gpu/drm/nouveau/nvkm/subdev/top: Is a directory
hacker@commands~an-epic-filesystem-quest:/opt/linux/linux-5.4/arch/sh/include/uapi/asm$ cat /opt/linux/linux-5.4/drivers/gpu/drm/nouveau/nvkm/subdev/top/BLUEPRINT-TRAPPED 
Yahaha, you found me!
The next clue is in: /usr/share/javascript/mathjax/unpacked/jax/output/HTML-CSS/fonts/Gyre-Termes/DoubleStruck

Watch out! The next clue is **trapped**. You'll need to read it out without 'cd'ing into the directory; otherwise, the clue will self destruct!
hacker@commands~an-epic-filesystem-quest:/opt/linux/linux-5.4/arch/sh/include/uapi/asm$ ls /usr/share/javascript/mathjax/unpacked/jax/output/HTML-CSS/fonts/Gyre-Termes/DoubleStruck
BRIEF-TRAPPED  Regular
hacker@commands~an-epic-filesystem-quest:/opt/linux/linux-5.4/arch/sh/include/uapi/asm$ cat /usr/share/javascript/mathjax/unpacked/jax/output/HTML-CSS/fonts/Gyre-Termes/DoubleStruck/BRIEF-TRAPPED 
Tubular find!
The next clue is in: /opt/linux/linux-5.4/include/config/arch/use/cmpxchg

The next clue is **delayed** --- it will not become readable until you enter the directory with 'cd'.
hacker@commands~an-epic-filesystem-quest:/opt/linux/linux-5.4/arch/sh/include/uapi/asm$ cd /opt/linux/linux-5.4/include/config/arch/use/cmpxchg
hacker@commands~an-epic-filesystem-quest:/opt/linux/linux-5.4/include/config/arch/use/cmpxchg$ ls
CLUE  lockref.h
hacker@commands~an-epic-filesystem-quest:/opt/linux/linux-5.4/include/config/arch/use/cmpxchg$ cat CLUE
Yahaha, you found me!
The next clue is in: /usr/lib/terminfo/h

Watch out! The next clue is **trapped**. You'll need to read it out without 'cd'ing into the directory; otherwise, the clue will self destruct!
hacker@commands~an-epic-filesystem-quest:/opt/linux/linux-5.4/include/config/arch/use/cmpxchg$ ls /usr/lib/terminfo/h
NOTE-TRAPPED  hurd
hacker@commands~an-epic-filesystem-quest:/opt/linux/linux-5.4/include/config/arch/use/cmpxchg$ cat /usr/lib/terminfo/h/NOTE-TRAPPED 
Lucky listing!
The next clue is in: /usr/share/emacs/26.3/lisp/textmodes
hacker@commands~an-epic-filesystem-quest:/opt/linux/linux-5.4/include/config/arch/use/cmpxchg$ ls /usr/share/emacs/26.3/lisp/textmodes
HINT              bibtex.elc     enriched.elc  less-css-mode.elc  page-ext.elc    po.elc      reftex-auc.elc     reftex-index.elc    reftex-sel.elc   remember.elc   tex-mode.elc    text-mode.elc
artist.elc        conf-mode.elc  fill.elc      makeinfo.elc       page.elc        refbib.elc  reftex-cite.elc    reftex-loaddefs.el  reftex-toc.elc   rst.elc        texinfmt.elc    tildify.elc
bib-mode.elc      css-mode.elc   flyspell.elc  mhtml-mode.elc     paragraphs.elc  refer.elc   reftex-dcr.elc     reftex-parse.elc    reftex-vars.elc  sgml-mode.elc  texinfo.elc     two-column.elc
bibtex-style.elc  dns-mode.elc   ispell.elc    nroff-mode.elc     picture.elc     refill.elc  reftex-global.elc  reftex-ref.elc      reftex.elc       table.elc      texnfo-upd.elc  underline.elc
hacker@commands~an-epic-filesystem-quest:/opt/linux/linux-5.4/include/config/arch/use/cmpxchg$ cat /usr/share/emacs/26.3/lisp/textmodes/HINT
Lucky listing!
The next clue is in: /usr/lib/python3/dist-packages/sphinx/ext/autodoc/__pycache__

Watch out! The next clue is **trapped**. You'll need to read it out without 'cd'ing into the directory; otherwise, the clue will self destruct!
hacker@commands~an-epic-filesystem-quest:/opt/linux/linux-5.4/include/config/arch/use/cmpxchg$ ls /usr/lib/python3/dist-packages/sphinx/ext/autodoc/__pycache__
NUGGET-TRAPPED  __init__.cpython-38.pyc  directive.cpython-38.pyc  importer.cpython-38.pyc  inspector.cpython-38.pyc
hacker@commands~an-epic-filesystem-quest:/opt/linux/linux-5.4/include/config/arch/use/cmpxchg$ cat /usr/lib/python3/dist-packages/sphinx/ext/autodoc/__pycache__/NUGGET-TRAPPED 
Tubular find!
The next clue is in: /usr/share/man/cs/man8

Watch out! The next clue is **trapped**. You'll need to read it out without 'cd'ing into the directory; otherwise, the clue will self destruct!
hacker@commands~an-epic-filesystem-quest:/opt/linux/linux-5.4/include/config/arch/use/cmpxchg$ ls /usr/share/man/cs/man8
README-TRAPPED  faillog.8.gz  groupadd.8.gz  groupdel.8.gz  groupmod.8.gz  grpck.8.gz  lastlog.8.gz  nologin.8.gz  vipw.8.gz
hacker@commands~an-epic-filesystem-quest:/opt/linux/linux-5.4/include/config/arch/use/cmpxchg$ cat /usr/share/man/cs/man8/README-TRAPPED 
CONGRATULATIONS! Your perserverence has paid off, and you have found the flag!
It is: pwn.college{84-aiPAOjNlWhSq5amuyCStrDE8.QX5IDO0wSO2gjNzEzW}
```

### New Learnings
None
### References
None
##
## making directories
Introduction to `mkdir` command
### Solve
Used `mkdir` to make a new directory, and then `touch` command to make the new file.

**Flag** `pwn.college{AlZTYaEHFpYr1PWKuVqIMlNSeFI.QXxMDO0wSO2gjNzEzW}`
```bash
hacker@commands~making-directories:~$ mkdir /tmp/pwn
hacker@commands~making-directories:~$ cd /tmp/pwn
hacker@commands~making-directories:/tmp/pwn$ touch college
hacker@commands~making-directories:/tmp/pwn$ /challenge/run
Success! Here is your flag:
pwn.college{AlZTYaEHFpYr1PWKuVqIMlNSeFI.QXxMDO0wSO2gjNzEzW}
```

### New Learnings
`mkdir` command makes a new directory.

### References
None.
##
## finding files
Introduction to `find` command
### Solve
Used `find` command to look a for the specified file

**Flag** `pwn.college{A_qADoLCWKRj9ZnsRtGeJ296VKb.QXyMDO0wSO2gjNzEzW}`

```bash
hacker@commands~finding-files:~$ find / -name flag
find: ‘/root’: Permission denied
find: ‘/etc/ssl/private’: Permission denied
find: ‘/tmp/tmp.TpSOPGOVKK’: Permission denied
/usr/local/lib/python3.8/dist-packages/pwnlib/flag
/usr/lib/python3/dist-packages/docutils/writers/flag
find: ‘/var/cache/apt/archives/partial’: Permission denied
find: ‘/var/cache/ldconfig’: Permission denied
find: ‘/var/cache/private’: Permission denied
find: ‘/var/log/private’: Permission denied
find: ‘/var/log/apache2’: Permission denied
find: ‘/var/log/mysql’: Permission denied
find: ‘/var/lib/apt/lists/partial’: Permission denied
find: ‘/var/lib/mysql-keyring’: Permission denied
find: ‘/var/lib/php/sessions’: Permission denied
find: ‘/var/lib/private’: Permission denied
find: ‘/var/lib/mysql-files’: Permission denied
find: ‘/var/lib/mysql’: Permission denied
find: ‘/run/mysqld’: Permission denied
find: ‘/run/sudo’: Permission denied
find: ‘/proc/tty/driver’: Permission denied
find: ‘/proc/1/task/1/fd’: Permission denied
find: ‘/proc/1/task/1/fdinfo’: Permission denied
find: ‘/proc/1/task/1/ns’: Permission denied
find: ‘/proc/1/fd’: Permission denied
find: ‘/proc/1/map_files’: Permission denied
find: ‘/proc/1/fdinfo’: Permission denied
find: ‘/proc/1/ns’: Permission denied
find: ‘/proc/7/task/7/fd’: Permission denied
find: ‘/proc/7/task/7/fdinfo’: Permission denied
find: ‘/proc/7/task/7/ns’: Permission denied
find: ‘/proc/7/fd’: Permission denied
find: ‘/proc/7/map_files’: Permission denied
find: ‘/proc/7/fdinfo’: Permission denied
find: ‘/proc/7/ns’: Permission denied
/opt/pwndbg/.venv/lib/python3.8/site-packages/pwnlib/flag
/nix/store/7ns27apnvn4qj4q5c82x0z1lzixrz47p-radare2-5.9.8/share/radare2/5.9.8/flag
/nix/store/5z3sjp9r463i3siif58hq5wj5jmy5m98-python3.12-pwntools-4.13.1/lib/python3.12/site-packages/pwnlib/flag
/nix/store/5n5lp1m8gilgrsriv1f2z0jdjk50ypcn-rizin-0.7.3/share/rizin/flag
/nix/store/h88mxp2mbgyj06vypwmqpy05idhwimnp-python3.13-pwntools-4.14.1/lib/python3.13/site-packages/pwnlib/flag
/nix/store/s8b49lb0pqwvw0c6kgjbxdwxcv2bp0x4-radare2-5.9.8/share/radare2/5.9.8/flag
/nix/store/bnlabj2vsbljhp597ir29l51nrqhm89w-rizin-0.7.4/share/rizin/flag
/nix/store/1hyxipvwpdpcxw90l5pq1nvd6s6jdi5m-python3.12-pwntools-4.14.1/lib/python3.12/site-packages/pwnlib/flag
/nix/store/5qz6hgb1qzpvjrsw20wyiylx5zw8b9bk-pwntools-4.14.0/lib/python3.13/site-packages/pwnlib/flag
hacker@commands~finding-files:~$ cat /nix/store/7ns27apnvn4qj4q5c82x0z1lzixrz47p-radare2-5.9.8/share/radare2/5.9.8/flag
cat: /nix/store/7ns27apnvn4qj4q5c82x0z1lzixrz47p-radare2-5.9.8/share/radare2/5.9.8/flag: Is a directory
hacker@commands~finding-files:~$ cat /nix/store/5z3sjp9r463i3siif58hq5wj5jmy5m98-python3.12-pwntools-4.13.1/lib/python3.12/site-packages/pwnlib/flag
cat: /nix/store/5z3sjp9r463i3siif58hq5wj5jmy5m98-python3.12-pwntools-4.13.1/lib/python3.12/site-packages/pwnlib/flag: Is a directory
hacker@commands~finding-files:~$ cat /nix/store/5n5lp1m8gilgrsriv1f2z0jdjk50ypcn-rizin-0.7.3/share/rizin/flag
cat: /nix/store/5n5lp1m8gilgrsriv1f2z0jdjk50ypcn-rizin-0.7.3/share/rizin/flag: Is a directory
hacker@commands~finding-files:~$ cat /nix/store/h88mxp2mbgyj06vypwmqpy05idhwimnp-python3.13-pwntools-4.14.1/lib/python3.13/site-packages/pwnlib/flag
cat: /nix/store/h88mxp2mbgyj06vypwmqpy05idhwimnp-python3.13-pwntools-4.14.1/lib/python3.13/site-packages/pwnlib/flag: Is a directory
hacker@commands~finding-files:~$ cat /nix/store/s8b49lb0pqwvw0c6kgjbxdwxcv2bp0x4-radare2-5.9.8/share/radare2/5.9.8/flag
cat: /nix/store/s8b49lb0pqwvw0c6kgjbxdwxcv2bp0x4-radare2-5.9.8/share/radare2/5.9.8/flag: Is a directory
hacker@commands~finding-files:~$ cat /nix/store/bnlabj2vsbljhp597ir29l51nrqhm89w-rizin-0.7.4/share/rizin/flag
cat: /nix/store/bnlabj2vsbljhp597ir29l51nrqhm89w-rizin-0.7.4/share/rizin/flag: Is a directory
hacker@commands~finding-files:~$ cat /nix/store/1hyxipvwpdpcxw90l5pq1nvd6s6jdi5m-python3.12-pwntools-4.14.1/lib/python3.12/site-packages/pwnlib/flag
cat: /nix/store/1hyxipvwpdpcxw90l5pq1nvd6s6jdi5m-python3.12-pwntools-4.14.1/lib/python3.12/site-packages/pwnlib/flag: Is a directory
hacker@commands~finding-files:~$ cat /nix/store/5qz6hgb1qzpvjrsw20wyiylx5zw8b9bk-pwntools-4.14.0/lib/python3.13/site-packages/pwnlib/flag
cat: /nix/store/5qz6hgb1qzpvjrsw20wyiylx5zw8b9bk-pwntools-4.14.0/lib/python3.13/site-packages/pwnlib/flag: Is a directory
hacker@commands~finding-files:~$ cat /usr/local/lib/python3.8/dist-packages/pwnlib/flag
cat: /usr/local/lib/python3.8/dist-packages/pwnlib/flag: Is a directory
hacker@commands~finding-files:~$ cd /usr/local/lib/python3.8/dist-packages/pwnlib/flag
hacker@commands~finding-files:/usr/local/lib/python3.8/dist-packages/pwnlib/flag$ flag
bash: flag: command not found
hacker@commands~finding-files:/usr/local/lib/python3.8/dist-packages/pwnlib/flag$ cat flag
cat: flag: No such file or directory
hacker@commands~finding-files:/usr/local/lib/python3.8/dist-packages/pwnlib/flag$ cd /
hacker@commands~finding-files:/$ cat /usr/lib/python3/dist-packages/docutils/writers/flag
pwn.college{A_qADoLCWKRj9ZnsRtGeJ296VKb.QXyMDO0wSO2gjNzEzW}
```

### New Learnings
`find` command is used to find files in a specific directory
<br>We can filter by name using `-name` 

### References
None.
##
## linking files
Introduction to linking files
### Solve
The file was already existing so I deleted it to create a symbolic link to the `/flag` file.

**Flag** `pwn.college{Msm1AmkloKur_xPzPPeyBBG6VNa.QX5ETN1wSO2gjNzEzW}`
```bash
hacker@commands~linking-files:~$ ln -s /flag ~/not-the-flag 
ln: failed to create symbolic link '/home/hacker/not-the-flag': File exists
hacker@commands~linking-files:~$ rm ~/not-the-flag 
hacker@commands~linking-files:~$ ln -s /flag ~/not-the-flag 
hacker@commands~linking-files:~$ challenge/catflag 
bash: challenge/catflag: No such file or directory
hacker@commands~linking-files:~$ /challenge/catflag 
About to read out the /home/hacker/not-the-flag file!
pwn.college{Msm1AmkloKur_xPzPPeyBBG6VNa.QX5ETN1wSO2gjNzEzW}
hacker@commands~linking-files:~$ file /flag
/flag: regular file, no read permission
hacker@commands~linking-files:~$ file ~/not-the-flag 
/home/hacker/not-the-flag: symbolic link to /flag
```
### New Learnings
A file is basically an address of the contents of the file.
A hard link is another address that indexes that address(accesses the hard link and the file are identical).
<br>
A symbolic link (also called soft link) contains the original file name, on accessing the symbolic link, the terminal will get the original file name and it will access the data of the orignal file.

### References
https://youtu.be/m55AtwjBXpE?list=PL-ymxv0nOtqqRAz1x90vxNbhmSkeYxHVC

https://docs.google.com/presentation/d/17OWCQsGTRsuCrB50njXbTXaEourHgdzVrN0cUshfDXI/edit?slide=id.g88f71ddc4c_0_0#slide=id.g88f71ddc4c_0_0


