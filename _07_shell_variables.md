## Printing Variables

### Code:
```bash
hacker@variables~printing-variables:~$ echo $FLAG
pwn.college{4IucZUNqGq0dqZuiuuvo5QbMlgN.ddTN1QDL1ADO0czW}
```
<br>

### Lesson
Learned how to print variables in Linux.
<br>

### Flag: ```pwn.college{4IucZUNqGq0dqZuiuuvo5QbMlgN.ddTN1QDL1ADO0czW}```
<br>

## Setting Variables

### Code:
```bash
hacker@variables~setting-variables:~$ PWN=COLLEGE
You've set the PWN variable properly! As promised, here is the flag:
pwn.college{Et9m_RQ4vvjEVyuNxoGQHSdnIjD.dlTN1QDL1ADO0czW}
```
<br>

### Lesson
Learned how to set variables and also learned that ```$``` is only used to 'access' variables and not 'set' them. Adding any sort of spacing while setting a variable will result in it getting assuemed to be a command by the terminal. 
<br>

### Flag: ``` pwn.college{Et9m_RQ4vvjEVyuNxoGQHSdnIjD.dlTN1QDL1ADO0czW} ```

## Multi-word Variables

### Code:
```bash
hacker@variables~multi-word-variables:~$ PWN="COLLEGE YEAH"
You've set the PWN variable properly! As promised, here is the flag:
pwn.college{oMdv6U3GVIhUCknpFBdGmW9dV8c.dBjN1QDL1ADO0czW}
hacker@variables~multi-word-variables:~$
```
<br>

### Lesson
Learned that you can't add a space when assigning variables  without using ```" "```. 

<br>

### Flag: ```pwn.college{oMdv6U3GVIhUCknpFBdGmW9dV8c.dBjN1QDL1ADO0czW} ```
<br>

## Exporting Variables

### Code:
```bash
hacker@variables~exporting-variables:~$ PWN=COLLEGE
You've set the PWN variable to the proper value!
hacker@variables~exporting-variables:~$ export PWN
You've set the PWN variable to the proper value!
hacker@variables~exporting-variables:~$ COLLEGE=PWN
You've set the PWN variable to the proper value!
You've set the COLLEGE variable to the proper value!
hacker@variables~exporting-variables:~$ /challenge/run
CORRECT!
You have exported PWN=COLLEGE and set, but not exported, COLLEGE=PWN. Great
job! Here is your flag:
pwn.college{ogj_AKweDZ62cLrpFmYSYOwZn51.dJjN1QDL1ADO0czW}
You've set the PWN variable to the proper value!
You've set the COLLEGE variable to the proper value!

```
<br>

### Lesson
Learned how variable inheritance works and how child shells won't inherit variables unless they are explicitly exported.
<br>

### Flag: ``` pwn.college{ogj_AKweDZ62cLrpFmYSYOwZn51.dJjN1QDL1ADO0czW} ```

## Printing Exported Variables

### Code:
```bash
hacker@variables~printing-exported-variables:~$ env $FLAG
env: ‘pwn.college{4ZO4ViBmvjirgOK0ooBNgsRIOLs.dhTN1QDL1ADO0czW}’: No such file or directory

```
<br>

### Lesson
Learned the ```env``` command and how it works. 
```env``` basically prints out every exported variable in a shell and using ```$FLAG``` with it gave me the flag.
<br>

### Flag: ``` pwn.college{4ZO4ViBmvjirgOK0ooBNgsRIOLs.dhTN1QDL1ADO0czW}```

<br>

## Storing Command Output

### Code:
```bash
hacker@variables~storing-command-output:~$ PWN=$(/challenge/run)
Congratulations! You have read the flag into the PWN variable. Now print it out
and submit it!
hacker@variables~storing-command-output:~$ echo $PWN
pwn.college{cC__-gqcYnTxUdn9RTP4ys4fSKV.dVzN0UDL1ADO0czW}

```
<br>

### Lesson
Learned how to store the output of a command directly into a variable. 
<br>

### Flag: ``` pwn.college{cC__-gqcYnTxUdn9RTP4ys4fSKV.dVzN0UDL1ADO0czW}```

## Reading Input

### Code:
```bash
hacker@variables~reading-input:~$ read PWN
COLLEGE
You've set the PWN variable properly! As promised, here is the flag:
pwn.college{MDEYZM7bSyd_KGdGe_dLYKDUfef.dhzN1QDL1ADO0czW}
```
<br>

### Lesson
Learned how to use ```read``` to take inputs to variables.
<br>

### Flag: ``` pwn.college{MDEYZM7bSyd_KGdGe_dLYKDUfef.dhzN1QDL1ADO0czW} ```
<br>

## Reading Files

### Code:
```bash
hacker@variables~reading-files:~$ read PWN < /challenge/read_me
You've set the PWN variable properly! As promised, here is the flag:
pwn.college{QfhGvXLl9_QYBJ8M_sicRdl9M9q.dBjM4QDL1ADO0czW}
```
<br>

### Lesson
Learned how to read output for a command and store it in a variable in a single command.
<br>

### Flag: ``` pwn.college{QfhGvXLl9_QYBJ8M_sicRdl9M9q.dBjM4QDL1ADO0czW} ```

