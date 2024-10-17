## Listing Processes

### Lesson:  
Learned how to use the ```ps``` funcion along with it's arguemtents like ```ef``` and ```aux```.

```ps``` - Lists the processes running
Standard Syntax:
``` ps -e``` - Lists every process
``` ps -f``` - Gives full format output
``` ps -ef``` - Makes use of ```e``` and ```f``` together.

BSD Syntax:
```ps a``` - Lists processes for all users.
``` ps u ``` - Gives a user readable output
``` ps x ``` - To list processes that aren't running on terminal.
``` ps aux``` - Combine it all into a single argument

```ps -ef``` and ```ps aux``` result in slightly different but cross-recognizable outputs.

<br>
### Code 

```bash
hacker@processes~listing-processes:~$ ps aux
USER         PID %CPU %MEM    VSZ   RSS TTY      STAT START   TIME COMMAND
root           1  0.0  0.0   1056   640 ?        Ss   19:03   0:00 /sbin/docker-init -- /nix/var/nix/profiles/default/bin/dojo-init /run/dojo/bin/sleep 6h
root           7  0.0  0.0   5052  2560 ?        S    19:03   0:00 /run/dojo/bin/sleep 6h
root          68  0.0  0.0   4132  2560 ?        S    19:03   0:00 /challenge/1942-run-4059
root          72  0.0  0.0   2744  1600 ?        S    19:03   0:00 sleep 6h
hacker        73  0.0  0.0   5360  3840 pts/0    Ss+  19:03   0:00 /run/dojo/bin/ssh-entrypoint
hacker        90  0.0  0.0   5360  3840 pts/1    Ss   19:03   0:00 /run/dojo/bin/ssh-entrypoint
hacker       112  0.0  0.0   5368  3840 pts/1    S    19:05   0:00 /run/dojo/bin/bash
hacker       129  0.0  0.0   7868  3520 pts/1    R+   19:06   0:00 ps aux
hacker@processes~listing-processes:~$ /challenge/1942-run-4059
Yahaha, you found me! Here is your flag:
pwn.college{4w2bJs_AQ7J7g2f_6lOh1LUlkc_.dhzM4QDL1ADO0czW}
Now I will sleep for a while (so that you could find me with 'ps').
```
<br>
### Flag: pwn.college{4w2bJs_AQ7J7g2f_6lOh1LUlkc_.dhzM4QDL1ADO0czW}

## 

<br>
### Lesson: 

<br>
### Code 

```bash

```
<br>
### Flag: 

## 

<br>
### Lesson: 

<br>
### Code 

```bash

```
<br>
### Flag: 

## 

<br>
### Lesson: 

<br>
### Code 

```bash

```
<br>
### Flag: 

## 

<br>
### Lesson: 

<br>
### Code 

```bash

```
<br>
### Flag: 

## 

<br>
### Lesson: 

<br>
### Code 

```bash

```
<br>
### Flag: 

## 

<br>
### Lesson: 

<br>
### Code 

```bash

```
<br>
### Flag: 

## 

<br>
### Lesson: 

<br>
### Code 

```bash

```
<br>
### Flag: 

## 

<br>
### Lesson: 

<br>
### Code 

```bash

```
<br>
### Flag: 

## 

<br>
### Lesson: 

<br>
### Code 

```bash

```
<br>
### Flag: 

## 

<br>
### Lesson: 

<br>
### Code 

```bash

```
<br>
### Flag: 

