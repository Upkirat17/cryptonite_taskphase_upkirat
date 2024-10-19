## Listing Processes

### Lesson:  
Learned how to use the ```ps``` funcion along with it's arguemtents like ```ef``` and ```aux```.

```ps``` - Lists the processes running <br>    
Standard Syntax:
```ps -e``` - Lists every process <br>  
```ps -f``` - Gives full format output <br>  
```ps -ef``` - Makes use of ```e``` and ```f``` together. <br>  

BSD Syntax:
```ps a``` - Lists processes for all users. <br>  
```ps u ``` - Gives a user readable output. <br>  
```ps x ``` - To list processes that aren't running on terminal. <br>  
```ps aux``` - Combine it all into a single argument. <br>  

```ps -ef``` and ```ps aux``` result in slightly different but cross-recognizable outputs. <br>  

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

## Killing Processes

### Lesson: 
Learned how to terminate a process using the ```kill``` command. Also got reminded of how piping works in the example question and applied that very principle in the answer too. 

<br>  

### Code 

```bash
hacker@processes~killing-processes:~$ ps -ef | grep dont_run
hacker        73      71  0 19:17 ?        00:00:00 /challenge/dont_run
hacker       116      75  0 19:19 pts/0    00:00:00 grep --color=auto dont_run
hacker@processes~killing-processes:~$ kill 73
hacker@processes~killing-processes:~$ ps -ef
UID          PID    PPID  C STIME TTY          TIME CMD
root           1       0  0 19:17 ?        00:00:00 /sbin/docker-init -- /nix/var/nix/profiles/default/bin/dojo-init /run/dojo/bin/sleep 6h
root           7       1  0 19:17 ?        00:00:00 /run/dojo/bin/sleep 6h
hacker        74       1  0 19:17 ?        00:00:00 sleep 6h
hacker        75       0  0 19:17 pts/0    00:00:00 /run/dojo/bin/ssh-entrypoint
hacker        81       0  0 19:17 pts/1    00:00:00 /run/dojo/bin/ssh-entrypoint
hacker       117      75  0 19:19 pts/0    00:00:00 ps -ef
hacker@processes~killing-processes:~$ /challenge/run
Great job! Here is your payment:
pwn.college{wAEU0npf7byZz0lWvfU8ySaFSWp.dJDN4QDL1ADO0czW}
```
<br>  

### Flag: pwn.college{wAEU0npf7byZz0lWvfU8ySaFSWp.dJDN4QDL1ADO0czW}

## Interrupting Processes


### Lesson: 
Leanred how to interrupt a program without terminating it by pressing ```Ctrl + C```

<br>  

### Code 

```bash
hacker@processes~interrupting-processes:~$ /challenge/run
I could give you the flag... but I won't, until this process exits. Remember,
you can force me to exit with Ctrl-C. Try it now!
^C
Good job! You have used Ctrl-C to interrupt this process! Here is your flag:
pwn.college{EZlmVjKAi87EAJ_TrIZJFORR_L3.dNDN4QDL1ADO0czW}
```
<br>  

### Flag: pwn.college{EZlmVjKAi87EAJ_TrIZJFORR_L3.dNDN4QDL1ADO0czW}

## Suspending Processes

### Lesson: 
Learned how to suspend processes to the background by holding ```Ctrl+Z```. Also learned that a copy of the process can be launched while it's suspended to the background.
<br>  

### Code 

```bash
hacker@processes~suspending-processes:~$ /challenge/run
I'll only give you the flag if there's already another copy of me running in
this terminal... Let's check!

UID          PID    PPID  C STIME TTY          TIME CMD
root          82      65  0 19:31 pts/0    00:00:00 bash /challenge/run
root          84      82  0 19:31 pts/0    00:00:00 ps -f

I don't see a second me!

To pass this level, you need to suspend me and launch me again! You can
background me with Ctrl-Z or, if you're not ready to do that for whatever
reason, just hit Enter and I'll exit!
^Z
[1]+  Stopped                 /challenge/run
hacker@processes~suspending-processes:~$ /challenge/run
I'll only give you the flag if there's already another copy of me running in
this terminal... Let's check!

UID          PID    PPID  C STIME TTY          TIME CMD
root          82      65  0 19:31 pts/0    00:00:00 bash /challenge/run
root          89      65  0 19:31 pts/0    00:00:00 bash /challenge/run
root          91      89  0 19:31 pts/0    00:00:00 ps -f

Yay, I found another version of me! Here is the flag:
pwn.college{ULcb4WQ1Yj4Ij-bxqC5pXtKU2zI.dVDN4QDL1ADO0czW}
```
<br>  

### Flag: pwn.college{ULcb4WQ1Yj4Ij-bxqC5pXtKU2zI.dVDN4QDL1ADO0czW}

## Resuming Processes


### Lesson: 
Learned how to resume processes by using ```fg``` command that puts a suspended task back onto the terminal.
<br>

### Code 

```bash
hacker@processes~resuming-processes:~$ /challenge/run
Let's practice resuming processes! Suspend me with Ctrl-Z, then resume me with
the 'fg' command! Or just press Enter to quit me!
^Z
[1]+  Stopped                 /challenge/run
hacker@processes~resuming-processes:~$ fg
/challenge/run
I'm back! Here's your flag:
pwn.college{gsbWaIL5yk3p6s5yFLfqp6sijs9.dZDN4QDL1ADO0czW}
Don't forget to press Enter to quit me!

Goodbye!
```
<br>  

### Flag: pwn.college{gsbWaIL5yk3p6s5yFLfqp6sijs9.dZDN4QDL1ADO0czW}

## Backgrounding Processes

<br>  

### Lesson:
Learned how to resume suspended processes in the background using ```bg``` command.
<br>  

### Code 

```bash
hacker@processes~backgrounding-processes:~$ /challenge/run
I'll only give you the flag if there's already another copy of me running *and
not suspended* in this terminal... Let's check!

UID          PID STAT CMD
root          82 S+   bash /challenge/run
root          84 R+   ps -o user=UID,pid,stat,cmd

I don't see a second me!

To pass this level, you need to suspend me, resume the suspended process in the
background, and then launch a new version of me! You can background me with
Ctrl-Z (and resume me in the background with 'bg') or, if you're not ready to
do that for whatever reason, just hit Enter and I'll exit!
^Z
[1]+  Stopped                 /challenge/run
hacker@processes~backgrounding-processes:~$ bg
[1]+ /challenge/run &

Yay, I'm now running the background! Because of that, this text will probably
overlap weirdly with the shell prompt. Don't panic; just hit Enter a few times
to scroll this text out.
hacker@processes~backgrounding-processes:~$ /challenge/run
I'll only give you the flag if there's already another copy of me running *and
not suspended* in this terminal... Let's check!

UID          PID STAT CMD
root          82 S    bash /challenge/run
root          92 S    sleep 6h
root          93 S+   bash /challenge/run
root          95 R+   ps -o user=UID,pid,stat,cmd

Yay, I found another version of me running in the background! Here is the flag:
pwn.college{cVh5plnkHUHUAocHSAr88qgAyb4.ddDN4QDL1ADO0czW}
```
<br>  

### Flag: pwn.college{cVh5plnkHUHUAocHSAr88qgAyb4.ddDN4QDL1ADO0czW}

## Foregrounding Processes 

<br>  

### Lesson: 
Learned how to move a backgrounded process to the foreground using ```fg```. 
<br>  

### Code 

```bash
hacker@processes~foregrounding-processes:~$ /challenge/run
To pass this level, you need to suspend me, resume the suspended process in the
background, and *then* foreground it without re-suspending it! You can
background me with Ctrl-Z (and resume me in the background with 'bg') or, if
you're not ready to do that for whatever reason, just hit Enter and I'll exit!
^Z
[1]+  Stopped                 /challenge/run
hacker@processes~foregrounding-processes:~$ bg
[1]+ /challenge/run &



Yay, I'm now running the background! Because of that, this text will probably
overlap weirdly with the shell prompt. Don't panic; just hit Enter a few times
to scroll this text out. After that, resume me into the foreground with 'fg';
I'll wait.
hacker@processes~foregrounding-processes:~$ fg
/challenge/run
YES! Great job! I'm now running in the foreground. Hit Enter for your flag!

pwn.college{0vq-4iPv6DdAVay_LG4z7Pz2RYE.dhDN4QDL1ADO0czW}
```
<br>  

### Flag: pwn.college{0vq-4iPv6DdAVay_LG4z7Pz2RYE.dhDN4QDL1ADO0czW}

## Starting Backgrounded Processes

### Lesson: 
Learned how start processes in the background using ```&```
<br>  

### Code 

```bash
hacker@processes~starting-backgrounded-processes:~$ /challenge/run &
[1] 82



Yay, you started me in the background! Because of that, this text will probably
overlap weirdly with the shell prompt, but you're used to that by now...

Anyways! Here is your flag!
pwn.college{EGpT_gNBuS-YS_bRef5D3LoX9W0.dlDN4QDL1ADO0czW}
```
<br>

### Flag: pwn.college{EGpT_gNBuS-YS_bRef5D3LoX9W0.dlDN4QDL1ADO0czW}

<br>

## Process Exit Codes

### Lesson: 
Learned how to access the exit code of the most recently terminated command using ```?``` and prepending it with ```$```.
Process:
1. Run the command
2. ```echo $?```      
<br>  

### Code 

```bash
hacker@processes~process-exit-codes:~$ /challenge/get-code
Exiting with an error code!
hacker@processes~process-exit-codes:~$ echo $?
19
hacker@processes~process-exit-codes:~$ /challenge/submit-code 19
CORRECT! Here is your flag:
pwn.college{YnfHfWCxrRalJViaQ8l4O71K84_.dljN4UDL1ADO0czW}
```
<br>  

### Flag: pwn.college{YnfHfWCxrRalJViaQ8l4O71K84_.dljN4UDL1ADO0czW}

<br>

