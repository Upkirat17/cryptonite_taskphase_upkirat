## Becoming root with su

### Lesson: 
Learned how to get root access using ```su```. This method is now obsolete though as it requires the user to enter root password which most modern machines don't come with.

<br>

### Code:
```bash
hacker@users~becoming-root-with-su:~$ su
Password:
root@users~becoming-root-with-su:/home/hacker# cat /flag
pwn.college{0-c_tfPyfmCl5lnRlcYK6FC59Wk.dVTN0UDL1ADO0czW}
```

<br>

### Flag: pwn.college{0-c_tfPyfmCl5lnRlcYK6FC59Wk.dVTN0UDL1ADO0czW}

<br>

## Other users wit su

### Lesson:
Learned how to switch to other users using ```su```. <br>
The syntax is just ```su [username]``` and then enter password for that user.
<br>

### Code:
```bash
hacker@users~other-users-with-su:~$ su zardus
Password:
zardus@users~other-users-with-su:/home/hacker$ /challenge/run
Congratulations, you have become Zardus! Here is your flag:
pwn.college{At7zPk5163q4kl90eKttYq7M6N3.dZTN0UDL1ADO0czW}
```

<br>

### Flag: pwn.college{At7zPk5163q4kl90eKttYq7M6N3.dZTN0UDL1ADO0czW}

<br>

## Cracking passwords

### Lesson:
Learned how to crack passwords using John the Ripper program. The password is shown next to the user name in paranthesis ```()```
<br>

### Code:
```bash
johhacker@users~cracking-passwords:~$ john /challenge/shadow-leak
Loaded 1 password hash (crypt, generic crypt(3) [?/64])
Press 'q' or Ctrl-C to abort, almost any other key for status
0g 0:00:00:19 1% 2/3 0g/s 264.7p/s 264.7c/s 264.7C/s samsung..britney
aardvark         (zardus)
1g 0:00:00:21 100% 2/3 0.04597g/s 267.7p/s 267.7c/s 267.7C/s Johnson..buzz
Use the "--show" option to display all of the cracked passwords reliably
Session completed
hacker@users~cracking-passwords:~$ su zardus
Password:
zardus@users~cracking-passwords:/home/hacker$ /challenge/run
Congratulations, you have become Zardus! Here is your flag:
pwn.college{wJF-Mzpya1SIz5fDcAVU6BIUtXx.ddTN0UDL1ADO0czW}
```

<br>

### Flag: pwn.college{wJF-Mzpya1SIz5fDcAVU6BIUtXx.ddTN0UDL1ADO0czW}

<br>

## Using sudo

### Lesson:
Learned about the ```sudo``` command, which allows you to launch commands without opening a different shell. 
<br>

### Code:
```bash
hacker@users~using-sudo:~$ sudo cat /flag
pwn.college{Q-arhLVTSuqwJatlhUKhfCtcTKQ.dhTN0UDL1ADO0czW}
hacker@users~using-sudo:~$
```

<br>

### Flag: pwn.college{Q-arhLVTSuqwJatlhUKhfCtcTKQ.dhTN0UDL1ADO0czW}

<br>

