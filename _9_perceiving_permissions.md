## Changing File Ownership

### Lesson:
Learnt how to change ownership of a file using ```chown``` command. <br>
The syntax is ```chown [username] [filename]```

<br>

### Code

```bash
hacker@permissions~changing-file-ownership:~$ ls -l /flag
-r-------- 1 hacker root 58 Oct 18 06:08 /flag
hacker@permissions~changing-file-ownership:~$ chown hacker /flag
hacker@permissions~changing-file-ownership:~$ cat /flag
pwn.college{4yxrRJSY5Rv2jFVL3OhBcM_57fU.dFTM2QDL1ADO0czW}
```
<br>

### Flag: pwn.college{4yxrRJSY5Rv2jFVL3OhBcM_57fU.dFTM2QDL1ADO0czW}

<br>

## Groups and Files

### Lesson: 
Learned how to change group ownership of a file using ```chgrp``` 

<br>

### Code

```bash
hacker@permissions~groups-and-files:~$ ls -l /flag
-r--r----- 1 root root 58 Oct 18 09:55 /flag
hacker@permissions~groups-and-files:~$ chgrp hacker /flag
hacker@permissions~groups-and-files:~$ cat /flag
pwn.college{YEKF-FUwY_eP08F3-qgG1g5ai1n.dFzNyUDL1ADO0czW}
```
<br>

### Flag: pwn.college{YEKF-FUwY_eP08F3-qgG1g5ai1n.dFzNyUDL1ADO0czW}

<br>

## Fun with Group Names

### Lesson: 
Learned how to figure out the groups user is in by using the ```id``` command, then changing group access to the flag using ```chgrp```.
<br>

### Code

```bash
hacker@permissions~fun-with-groups-names:~$ id
uid=1000(hacker) gid=1000(grp5619) groups=1000(grp5619)
hacker@permissions~fun-with-groups-names:~$ ls -l /flag
-r--r----- 1 root root 58 Oct 18 10:01 /flag
hacker@permissions~fun-with-groups-names:~$ chgrp grp5619 /flag
hacker@permissions~fun-with-groups-names:~$ cat /flag
pwn.college{wVijtUs0wHRTMR1hpamWvk-kzlE.dJzNyUDL1ADO0czW}
```
<br>

### Flag: pwn.college{wVijtUs0wHRTMR1hpamWvk-kzlE.dJzNyUDL1ADO0czW}

<br>

## Changing Permissions

### Lesson: 
Learned how to change permissions of a file using ```chmod```.<br>
The **first character** when you do ```ls -l``` is the file type. The next **3 characters** are the file permissions for the owning user, the **next 3** are for the owning group, and the **last 3** are for all other access (users and groups).
```
r - user/group/other can read the file (or list the directory)
w - user/group/other can modify the files (or create/delete files in the directory)
x - user/group/other can execute the file as a program (or can enter the directory, e.g., using `cd`)
- - nothing 
```

The ```chmod``` command can be used like : ```chmod [OPTIONS] MODE FILE```

eg. 
```
u+r adds read access to the user's permissions
g+wx adds write and execute access to the group's permissions
o-w removes write access for other users
a-rwx removes all permissions for the user, group, and world****
```


<br>

### Code

```bash
hacker@permissions~changing-permissions:~$ ls -l /flag
-r-------- 1 root root 58 Oct 18 10:15 /flag
hacker@permissions~changing-permissions:~$ chmod ugo+rwx /flag
hacker@permissions~changing-permissions:~$ ls -l /flag
-rwxrwxrwx 1 root root 58 Oct 18 10:15 /flag
hacker@permissions~changing-permissions:~$ cat /flag
pwn.college{0Uy3qWrMYEvY1CPnJfYUnAo29md.dNzNyUDL1ADO0czW}
```
<br>

### Flag: pwn.college{0Uy3qWrMYEvY1CPnJfYUnAo29md.dNzNyUDL1ADO0czW}

<br>

## Executable Files

### Lesson: 
Just applied my knowledge of ```chmod``` from the previous questions using ```u+rwx``` for the ```/challenge/run``` file.

<br>

### Code

```bash
hacker@permissions~executable-files:~$ ls -l /challenge/run
-r--r--r-- 1 hacker hacker 32 Jul  4 06:37 /challenge/run
hacker@permissions~executable-files:~$ chmod u+rwx /challenge/run
hacker@permissions~executable-files:~$ /challenge/run
Successful execution! Here is your flag:
pwn.college{M2rvBKLz1JKqJ50jYqThmyMdCNC.dJTM2QDL1ADO0czW}
```
<br>

### Flag: pwn.college{M2rvBKLz1JKqJ50jYqThmyMdCNC.dJTM2QDL1ADO0czW}

<br>

## Permission Tweaking Practice

### Lesson: 
Learned how to set multiple permissions at the same time and this module also added the element of fear of restarting from round 1 again if we messed it up. But it was pretty fun in my opinion. 
<br>

### Code

```bash
hacker@permissions~permission-tweaking-practice:~$ chmod ugo+rwx /challenge/pwn
NEEDED, BUT UNMET permissions of "/challenge/pwn": r--r--r--
* the user does have read permissions
- the user doesn't have write permissions
- the user doesn't have execute permissions
* the group does have read permissions
- the group doesn't have write permissions
- the group doesn't have execute permissions
* the world does have read permissions
- the world doesn't have write permissions
- the world doesn't have execute permissions

CURRENT, INCORRECT permissions of "/challenge/pwn": rwxrwxrwx
* the user does have read permissions
* the user does have write permissions
* the user does have execute permissions
* the group does have read permissions
* the group does have write permissions
* the group does have execute permissions
* the world does have read permissions
* the world does have write permissions
* the world does have execute permissions

You set the permissions incorrectly! Restarting the game!
hacker@permissions~permission-tweaking-practice:~$ chmod ugo-wx /challenge/pwn
You set the correct permissions!
Round 1 (of 8)!

Current permissions of "/challenge/pwn": r--r--r--
* the user does have read permissions
- the user doesn't have write permissions
- the user doesn't have execute permissions
* the group does have read permissions
- the group doesn't have write permissions
- the group doesn't have execute permissions
* the world does have read permissions
- the world doesn't have write permissions
- the world doesn't have execute permissions

Needed permissions of "/challenge/pwn": ------r--
- the user doesn't have read permissions
- the user doesn't have write permissions
- the user doesn't have execute permissions
- the group doesn't have read permissions
- the group doesn't have write permissions
- the group doesn't have execute permissions
* the world does have read permissions
- the world doesn't have write permissions
- the world doesn't have execute permissions
hacker@permissions~permission-tweaking-practice:~$ chmod u-rwx,g-rwx,o=r /challenge/pwn
You set the correct permissions!
Round 2 (of 8)!

Current permissions of "/challenge/pwn": ------r--
- the user doesn't have read permissions
- the user doesn't have write permissions
- the user doesn't have execute permissions
- the group doesn't have read permissions
- the group doesn't have write permissions
- the group doesn't have execute permissions
* the world does have read permissions
- the world doesn't have write permissions
- the world doesn't have execute permissions

Needed permissions of "/challenge/pwn": ------r-x
- the user doesn't have read permissions
- the user doesn't have write permissions
- the user doesn't have execute permissions
- the group doesn't have read permissions
- the group doesn't have write permissions
- the group doesn't have execute permissions
* the world does have read permissions
- the world doesn't have write permissions
* the world does have execute permissions
hacker@permissions~permission-tweaking-practice:~$ chmod u-rwx,g-rwx,o-rwx,o=rx /challenge/pwn
You set the correct permissions!
Round 3 (of 8)!

Current permissions of "/challenge/pwn": ------r-x
- the user doesn't have read permissions
- the user doesn't have write permissions
- the user doesn't have execute permissions
- the group doesn't have read permissions
- the group doesn't have write permissions
- the group doesn't have execute permissions
* the world does have read permissions
- the world doesn't have write permissions
* the world does have execute permissions

Needed permissions of "/challenge/pwn": ---rwxr-x
- the user doesn't have read permissions
- the user doesn't have write permissions
- the user doesn't have execute permissions
* the group does have read permissions
* the group does have write permissions
* the group does have execute permissions
* the world does have read permissions
- the world doesn't have write permissions
* the world does have execute permissions
hacker@permissions~permission-tweaking-practice:~$ chmod u-rwx,g+rwx,o-rwx,o=rx /challenge/pwn
You set the correct permissions!
Round 4 (of 8)!

Current permissions of "/challenge/pwn": ---rwxr-x
- the user doesn't have read permissions
- the user doesn't have write permissions
- the user doesn't have execute permissions
* the group does have read permissions
* the group does have write permissions
* the group does have execute permissions
* the world does have read permissions
- the world doesn't have write permissions
* the world does have execute permissions

Needed permissions of "/challenge/pwn": ------r-x
- the user doesn't have read permissions
- the user doesn't have write permissions
- the user doesn't have execute permissions
- the group doesn't have read permissions
- the group doesn't have write permissions
- the group doesn't have execute permissions
* the world does have read permissions
- the world doesn't have write permissions
* the world does have execute permissions
hacker@permissions~permission-tweaking-practice:~$ chmod u-rwx,g-rwx,o-rwx,o=rx /challenge/pwn
You set the correct permissions!
Round 5 (of 8)!

Current permissions of "/challenge/pwn": ------r-x
- the user doesn't have read permissions
- the user doesn't have write permissions
- the user doesn't have execute permissions
- the group doesn't have read permissions
- the group doesn't have write permissions
- the group doesn't have execute permissions
* the world does have read permissions
- the world doesn't have write permissions
* the world does have execute permissions

Needed permissions of "/challenge/pwn": r-xr-xr-x
* the user does have read permissions
- the user doesn't have write permissions
* the user does have execute permissions
* the group does have read permissions
- the group doesn't have write permissions
* the group does have execute permissions
* the world does have read permissions
- the world doesn't have write permissions
* the world does have execute permissions
hacker@permissions~permission-tweaking-practice:~$ chmod u=rx,g=rx /challenge/pwn
You set the correct permissions!
Round 6 (of 8)!

Current permissions of "/challenge/pwn": r-xr-xr-x
* the user does have read permissions
- the user doesn't have write permissions
* the user does have execute permissions
* the group does have read permissions
- the group doesn't have write permissions
* the group does have execute permissions
* the world does have read permissions
- the world doesn't have write permissions
* the world does have execute permissions

Needed permissions of "/challenge/pwn": r-xrwxr-x
* the user does have read permissions
- the user doesn't have write permissions
* the user does have execute permissions
* the group does have read permissions
* the group does have write permissions
* the group does have execute permissions
* the world does have read permissions
- the world doesn't have write permissions
* the world does have execute permissions
hacker@permissions~permission-tweaking-practice:~$ chmod g+w /challenge/pwn
You set the correct permissions!
Round 7 (of 8)!

Current permissions of "/challenge/pwn": r-xrwxr-x
* the user does have read permissions
- the user doesn't have write permissions
* the user does have execute permissions
* the group does have read permissions
* the group does have write permissions
* the group does have execute permissions
* the world does have read permissions
- the world doesn't have write permissions
* the world does have execute permissions

Needed permissions of "/challenge/pwn": --x--xr-x
- the user doesn't have read permissions
- the user doesn't have write permissions
* the user does have execute permissions
- the group doesn't have read permissions
- the group doesn't have write permissions
* the group does have execute permissions
* the world does have read permissions
- the world doesn't have write permissions
* the world does have execute permissions
hacker@permissions~permission-tweaking-practice:~$ chmod u-r,g-rw /challenge/pwn
You set the correct permissions!
You've solved all 8 rounds! I have changed the ownership
of the /flag file so that you can 'chmod' it. You won't be able to read
it until you make it readable with chmod!

Current permissions of "/flag": ---------
- the user doesn't have read permissions
- the user doesn't have write permissions
- the user doesn't have execute permissions
- the group doesn't have read permissions
- the group doesn't have write permissions
- the group doesn't have execute permissions
- the world doesn't have read permissions
- the world doesn't have write permissions
- the world doesn't have execute permissions
hacker@permissions~permission-tweaking-practice:~$ chmod ugo+rwx /flag
hacker@permissions~permission-tweaking-practice:~$ cat /flag
pwn.college{w8dLq8CQYF1mem6t8MLA2k2e09r.dBTM2QDL1ADO0czW}
```
<br>

### Flag: pwn.college{w8dLq8CQYF1mem6t8MLA2k2e09r.dBTM2QDL1ADO0czW}

<br>

## Permissions Setting Practice

### Lesson: 
Just practiced using ```chmod```.
<br>

### Code

```bash
hacker@permissions~permissions-setting-practice:~$ chmod u=r,g=r,o=x /challenge/pwn
NEEDED, BUT UNMET permissions of "/challenge/pwn": rw-r--rwx
* the user does have read permissions
* the user does have write permissions
- the user doesn't have execute permissions
* the group does have read permissions
- the group doesn't have write permissions
- the group doesn't have execute permissions
* the world does have read permissions
* the world does have write permissions
* the world does have execute permissions

CURRENT, INCORRECT permissions of "/challenge/pwn": r--r----x
* the user does have read permissions
- the user doesn't have write permissions
- the user doesn't have execute permissions
* the group does have read permissions
- the group doesn't have write permissions
- the group doesn't have execute permissions
- the world doesn't have read permissions
- the world doesn't have write permissions
* the world does have execute permissions

You set the permissions incorrectly! Restarting the game!
hacker@permissions~permissions-setting-practice:~$ chmod u=rw,g=r,o=rwx /challenge/pwn
You set the correct permissions!
Round 1 (of 8)!

Current permissions of "/challenge/pwn": rw-r--rwx
* the user does have read permissions
* the user does have write permissions
- the user doesn't have execute permissions
* the group does have read permissions
- the group doesn't have write permissions
- the group doesn't have execute permissions
* the world does have read permissions
* the world does have write permissions
* the world does have execute permissions

Needed permissions of "/challenge/pwn": rw--wxr--
* the user does have read permissions
* the user does have write permissions
- the user doesn't have execute permissions
- the group doesn't have read permissions
* the group does have write permissions
* the group does have execute permissions
* the world does have read permissions
- the world doesn't have write permissions
- the world doesn't have execute permissions
hacker@permissions~permissions-setting-practice:~$ chmod u=rw,g=wx,o=r /challenge/pwn
You set the correct permissions!
Round 2 (of 8)!

Current permissions of "/challenge/pwn": rw--wxr--
* the user does have read permissions
* the user does have write permissions
- the user doesn't have execute permissions
- the group doesn't have read permissions
* the group does have write permissions
* the group does have execute permissions
* the world does have read permissions
- the world doesn't have write permissions
- the world doesn't have execute permissions

Needed permissions of "/challenge/pwn": rwx----wx
* the user does have read permissions
* the user does have write permissions
* the user does have execute permissions
- the group doesn't have read permissions
- the group doesn't have write permissions
- the group doesn't have execute permissions
- the world doesn't have read permissions
* the world does have write permissions
* the world does have execute permissions
hacker@permissions~permissions-setting-practice:~$ chmod u=rwx,g=-,o=wx /challenge/pwn
You set the correct permissions!
Round 3 (of 8)!

Current permissions of "/challenge/pwn": rwx----wx
* the user does have read permissions
* the user does have write permissions
* the user does have execute permissions
- the group doesn't have read permissions
- the group doesn't have write permissions
- the group doesn't have execute permissions
- the world doesn't have read permissions
* the world does have write permissions
* the world does have execute permissions

Needed permissions of "/challenge/pwn": r--r----x
* the user does have read permissions
- the user doesn't have write permissions
- the user doesn't have execute permissions
* the group does have read permissions
- the group doesn't have write permissions
- the group doesn't have execute permissions
- the world doesn't have read permissions
- the world doesn't have write permissions
* the world does have execute permissions
hacker@permissions~permissions-setting-practice:~$ chmod u=r,g=r,o=x /challenge/pwn
You set the correct permissions!
Round 4 (of 8)!

Current permissions of "/challenge/pwn": r--r----x
* the user does have read permissions
- the user doesn't have write permissions
- the user doesn't have execute permissions
* the group does have read permissions
- the group doesn't have write permissions
- the group doesn't have execute permissions
- the world doesn't have read permissions
- the world doesn't have write permissions
* the world does have execute permissions

Needed permissions of "/challenge/pwn": --xr--r-x
- the user doesn't have read permissions
- the user doesn't have write permissions
* the user does have execute permissions
* the group does have read permissions
- the group doesn't have write permissions
- the group doesn't have execute permissions
* the world does have read permissions
- the world doesn't have write permissions
* the world does have execute permissions
hacker@permissions~permissions-setting-practice:~$ chmod u=x,g=r,o=rx /challenge/pwn
You set the correct permissions!
Round 5 (of 8)!

Current permissions of "/challenge/pwn": --xr--r-x
- the user doesn't have read permissions
- the user doesn't have write permissions
* the user does have execute permissions
* the group does have read permissions
- the group doesn't have write permissions
- the group doesn't have execute permissions
* the world does have read permissions
- the world doesn't have write permissions
* the world does have execute permissions

Needed permissions of "/challenge/pwn": rwxr-xr--
* the user does have read permissions
* the user does have write permissions
* the user does have execute permissions
* the group does have read permissions
- the group doesn't have write permissions
* the group does have execute permissions
* the world does have read permissions
- the world doesn't have write permissions
- the world doesn't have execute permissions
hacker@permissions~permissions-setting-practice:~$ chmod u=rwx,g=rx,o=r /challenge/pwn
You set the correct permissions!
Round 6 (of 8)!

Current permissions of "/challenge/pwn": rwxr-xr--
* the user does have read permissions
* the user does have write permissions
* the user does have execute permissions
* the group does have read permissions
- the group doesn't have write permissions
* the group does have execute permissions
* the world does have read permissions
- the world doesn't have write permissions
- the world doesn't have execute permissions

Needed permissions of "/challenge/pwn": ------rwx
- the user doesn't have read permissions
- the user doesn't have write permissions
- the user doesn't have execute permissions
- the group doesn't have read permissions
- the group doesn't have write permissions
- the group doesn't have execute permissions
* the world does have read permissions
* the world does have write permissions
* the world does have execute permissions
hacker@permissions~permissions-setting-practice:~$ chmod u=-,g=-,o=rwx /challenge/pwn
You set the correct permissions!
Round 7 (of 8)!

Current permissions of "/challenge/pwn": ------rwx
- the user doesn't have read permissions
- the user doesn't have write permissions
- the user doesn't have execute permissions
- the group doesn't have read permissions
- the group doesn't have write permissions
- the group doesn't have execute permissions
* the world does have read permissions
* the world does have write permissions
* the world does have execute permissions

Needed permissions of "/challenge/pwn": rw--wx---
* the user does have read permissions
* the user does have write permissions
- the user doesn't have execute permissions
- the group doesn't have read permissions
* the group does have write permissions
* the group does have execute permissions
- the world doesn't have read permissions
- the world doesn't have write permissions
- the world doesn't have execute permissions
hacker@permissions~permissions-setting-practice:~$ chmod u=rw,g=wx,o=- /challenge/pwn
You set the correct permissions!
You've solved all 8 rounds! I have changed the ownership
of the /flag file so that you can 'chmod' it. You won't be able to read
it until you make it readable with chmod!

Current permissions of "/flag": ---------
- the user doesn't have read permissions
- the user doesn't have write permissions
- the user doesn't have execute permissions
- the group doesn't have read permissions
- the group doesn't have write permissions
- the group doesn't have execute permissions
- the world doesn't have read permissions
- the world doesn't have write permissions
- the world doesn't have execute permissions
hacker@permissions~permissions-setting-practice:~$ chmod ugo+rwx /flag
hacker@permissions~permissions-setting-practice:~$ cat /flag
pwn.college{YVR88Ieb1rSiKpUcCBmBxE03so4.dNTM5QDL1ADO0czW}
```
<br>

### Flag: pwn.college{YVR88Ieb1rSiKpUcCBmBxE03so4.dNTM5QDL1ADO0czW}

<br>

## The SUID Bit

### Lesson: 
There are cases where non-root users need administrative aceess to do certain tasks. The SUID (Set User ID) permissions allow them to to run a program as the owner of that program's file. For eg. ```sudo```, ```su```.

Giving the SUID bit to an executable bit is simple.
```chmod u+s [program]```
<br>

### Code

```bash
hacker@permissions~the-suid-bit:~$ chmod u+s /challenge/getroot
hacker@permissions~the-suid-bit:~$ /challenge/getroot
SUCCESS! You have set the suid bit on this program, and it is running as root!
Here is your shell...
root@permissions~the-suid-bit:~# cat /flag
pwn.college{cbLnQ0OETL5VkbMWxMUkpcgKX5j.dNTM2QDL1ADO0czW}
```
<br>

### Flag: pwn.college{cbLnQ0OETL5VkbMWxMUkpcgKX5j.dNTM2QDL1ADO0czW}

<br>
