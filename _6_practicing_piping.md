## Redirecting Output 
It was simple, just redirect PWN to a file named COLLEGE

<br>

### command: ![image](https://github.com/user-attachments/assets/968e0bdf-a91a-4e54-8423-4e9191a65d52)


### flag: pwn.college{kcCEiOarYzzlvOffaCJMcXQ-IsR.dRjN1QDL1ADO0czW}

<br><br>

## Redirecting more output

This program was fun imo. Had to redirect ```/challenge/run``` to a file called ```myfile``` and then reading it using ```cat```
<br>

### command: ![image](https://github.com/user-attachments/assets/0b77f2e7-95d3-4ea8-ad40-85c85ba7cfad)


### flag: pwn.college{sKEJIY5arPHpJvpV3XnFrpVauwK.dVjN1QDL1ADO0czW}
<br><br>

## Appemding Output
The question was slightly tricky to understand but a few minutes of trial and error got me the flag. Tried the program multiple times in different ways to understand exactly what was happening.
<br>

### command: ![image](https://github.com/user-attachments/assets/db2fca98-2c3f-4257-9c17-6a231256da6f)
![image](https://github.com/user-attachments/assets/d77d40b3-3351-47e3-8671-bcca8ddd297b)



### flag: pwn.college{4Qp7FqnU6dFqfkI6D780hKV4FBL.ddDM5QDL1ADO0czW}
<br><br>

## Redirecting Errors

Very simple. Just had to type out the command as given in the question.
<br>

### command: ![image](https://github.com/user-attachments/assets/908aaa39-d005-43a8-a031-45fab8bb9eb1)


### flag: pwn.college{M3OHgi6Bl9-XSeCAtqchasPa2Ng.ddjN1QDL1ADO0czW}
<br><br>

##  Redirecting Input
Just had to redirect ```COLLEGE` ``` to a file called ```PWN``` and then redirecting that file to ```/challenege/run```

<br>

### command: ![image](https://github.com/user-attachments/assets/7bf11287-2ab7-4ec9-b75b-3567f848eb54)


### flag: pwn.college{sOUoBUvhbQnReNpCs9kVuO6f_Qi.dBzN1QDL1ADO0czW}
<br><br>

## Grepping stored results
Simple concept, simple execution. Run command, store output in a file, use that output as the input of another command and boom!
<br>

### command: ![image](https://github.com/user-attachments/assets/e0f21248-2031-44fe-ab46-6fa106d2a26b)


### flag: pwn.college{IeP2PT3n99YFHTuDDdDIdAcEkHc.dhTM4QDL1ADO0czW}
<br><br>

## Grepping live output
This is another way to do the same thing as the previous question. The pipe operator was introduced which eliminates the need for a new file.
<br>

### command: ![image](https://github.com/user-attachments/assets/a5489bf0-c79e-4a0b-aefa-aac212076a90)


### flag: pwn.college{4DtMftRnxUSFaRk7-q8DQswmhDY.dlTM4QDL1ADO0czW}
<br><br>

## Greppinng errors
Learned how to change one file descriptor to another using ```>&```. 
<br>

### command: ![image](https://github.com/user-attachments/assets/f2cb7579-da17-48ef-90fb-4f3ac4c01413)


### flag: pwn.college{Quh6KidET9eL6FXtKVXFJI4vKTL.dVDM5QDL1ADO0czW}
<br><br>

## Duplicating piped date with tee

Learned how to pipe a command using tee. Took a very long time, but I finally understood how the pipe command works.

<br>

### command: ![image](https://github.com/user-attachments/assets/8ecc377c-00b5-497f-a52b-42ebb7fb88c7)


### flag: pwn.college{gnTGENUBd8kT2dBIOtuKBU0xEI6.dFjM5QDL1ADO0czW}
<br><br>

## Writing to multiple programs
Learned how to redirect to multiple files using tee.
<br>

### command: ![image](https://github.com/user-attachments/assets/2d80feee-dfd1-41a0-81b6-6fa69e7811f1)


### flag: pwn.college{c2XcXY5aex49JahAGA8VxHNry7T.dBDO0UDL1ADO0czW}****
<br><br>

## Split-piping stderr and stdout

I struggled a lot with this one. Kept messing up the syntax by doing ```>>``` instead of ```> >``` and the same thing with ```2> >```. Finally got it right after reading online explanations on how to redirect stdout and stderr at the same time. I'm not able to figure how to use ```|``` though.
<br>

### command: ![image](https://github.com/user-attachments/assets/18bf367f-eb2b-4f9f-8bdb-1a146853aa64)


### flag: ``pwn.college{8x_tPl1fvNFANiVc5fqiarzCMuO.dFDNwYDL1ADO0czW}``
<br><br>

