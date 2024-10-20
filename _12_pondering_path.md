## The PATH variable

### Lesson:
Learned how to remove the disrupt commands by removing the path of all command files for the shell using ```PATH=""```. 
<br>

### Code:
```
hacker@path~the-path-variable:~$ PATH=""
hacker@path~the-path-variable:~$ /challenge/run
Trying to remove /flag...
/challenge/run: line 4: rm: No such file or directory
The flag is still there! I might as well give it to you!
pwn.college{cG1PCpdM0LGzLzw-ztEYvO1MO3d.dZzNwUDL1ADO0czW}
```

<br>

### Flag: pwn.college{cG1PCpdM0LGzLzw-ztEYvO1MO3d.dZzNwUDL1ADO0czW}
<br>

## Setting PATH

### Lesson: 
Learned how to invoke scripts or commands by their bare name by overwriting PATH with their directories. <br>
For eg. ```/challenge/more_commands/win``` would be one way to run the ```win``` command. But it can get annoying typing the entire path again and again if we have multiple commands in the same directory. So, an alternative method could be: <br>
```PATH="/challenge_more_commands"```. <br>
Now, we can invoke the ```win``` command without typing the entire path. The question required ```win``` to be an argument to ```/challenge/run```, so we can just type <br>
```/challenge/run win``` to get the flag.

<br>

### Code:
```
hacker@path~setting-path:~$ PATH="/challenge/more_commands"
hacker@path~setting-path:~$ /challenge/run win
Invoking 'win'....
Congratulations! You properly set the flag and 'win' has launched!
pwn.college{MaxlIhWpnppn40_u371QLXCAQ8-.dVzNyUDL1ADO0czW}
```

<br>

### Flag: pwn.college{MaxlIhWpnppn40_u371QLXCAQ8-.dVzNyUDL1ADO0czW}
<br>

##

### Lesson:

<br>

### Code:
```

```

<br>

### Flag: 
<br>

##

### Lesson:

<br>

### Code:
```

```

<br>

### Flag: 
<br>

