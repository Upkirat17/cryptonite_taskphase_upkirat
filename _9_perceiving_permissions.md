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

## 

### Lesson: 

<br>

### Code

```bash

```
<br>

### Flag: 

<br>

## 

### Lesson: 

<br>

### Code

```bash

```
<br>

### Flag: 

<br>

## 

### Lesson: 

<br>

### Code

```bash

```
<br>

### Flag: 

<br>

## 

### Lesson: 

<br>

### Code

```bash

```
<br>

### Flag: 

<br>

## 

### Lesson: 

<br>

### Code

```bash

```
<br>

### Flag: 

<br>

## 

### Lesson: 

<br>

### Code

```bash

```
<br>

### Flag: 

<br>

