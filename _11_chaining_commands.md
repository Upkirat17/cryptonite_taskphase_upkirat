## Chaining with Semicolons

### Lesson:
Learned how to chain commands using semicolon ```;```, which is the easiest way to chain commands.
eg. ```command1; command2```
<br>

### Code:
```
hacker@chaining~chaining-with-semicolons:~$ /challenge/pwn; /challenge/college
Yes! You chained /challenge/pwn and /challenge/college! Here is your flag:
pwn.college{4vHuM1KCuOX8VhD6MOCsm9vgpZh.dVTN4QDL1ADO0czW}

```
<br>

### Flag: pwn.college{4vHuM1KCuOX8VhD6MOCsm9vgpZh.dVTN4QDL1ADO0czW}

<br>

## Your first shell script

### Lesson:
Learned how to create my own shell and execute a chain of commands using it. <br>
The creation of a shell wasn't taught in the modules so I ended up referring to geeksforgeeks.com
Steps to create a shell:
```touch [filename].sh``` - Create the file
``` chmod +x /[filename].sh``` - Give executing permissions
``` nano [filename].sh``` - Open command line text-editor to write commands
``` bash [filename].sh``` - Run the shell

<br>

### Code:
```
hacker@chaining~your-first-shell-script:~$ touch x.sh
hacker@chaining~your-first-shell-script:~$ chmod ugo+rwx x.sh
hacker@chaining~your-first-shell-script:~$ nano x.sh
hacker@chaining~your-first-shell-script:~$ bash x.sh
Great job, you've written your first shell script! Here is the flag:
pwn.college{4A30W_BtEUAECJV5Iia6A9ytV0J.dFzN4QDL1ADO0czW}
hacker@chaining~your-first-shell-script:~$
```
<br>

### Flag: pwn.college{4A30W_BtEUAECJV5Iia6A9ytV0J.dFzN4QDL1ADO0czW}

<br>

## Redirecting Script Output

### Lesson:
Learned how to pipe multiple outputs into a single command using chained commands in a shell and the pipe operator ```|```.
It was simple. Create the output.sh file, chain the given commands in it using semicolon ```;```, and run <br>
```bash output.sh | /challenge/solve```.
<br>

### Code:
```
hacker@chaining~redirecting-script-output:~$ touch output.sh
hacker@chaining~redirecting-script-output:~$ chmod +x /output.sh
chmod: cannot access '/output.sh': No such file or directory
hacker@chaining~redirecting-script-output:~$ chmod +x output.sh
hacker@chaining~redirecting-script-output:~$ nano  output.sh
hacker@chaining~redirecting-script-output:~$ bash output.sh | /challenge/solve
Correct! Here is your flag:
```
<br>

### Flag: pwn.college{84l0DCkDdMbPnt-dS75xSk54ERQ.dhTM5QDL1ADO0czW}

<br>

## Executable Shell Scripts

### Lesson:
Learned how to execute a shell script without the use of bash.
It can be simply done by providing the relative or the absolute path of the shell script.
<br>

### Code:
```
hacker@chaining~executable-shell-scripts:~$ touch script.sh
hacker@chaining~executable-shell-scripts:~$ chmod ugo+x script.sh
hacker@chaining~executable-shell-scripts:~$ nano script.sh
hacker@chaining~executable-shell-scripts:~$ ./script.sh
Congratulations on your shell script execution! Your flag:
pwn.college{0GiQk5gzRfT3WXdv56gIzSkEVtL.dRzNyUDL1ADO0czW}
```
<br>

### Flag: pwn.college{0GiQk5gzRfT3WXdv56gIzSkEVtL.dRzNyUDL1ADO0czW}

<br>
