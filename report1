# Lab Report 1 - Remote Access and FileSystem
Welcome, incoming 15L students ! As you begin your journey in CSE 15L , you will need to access a course-specific account. However, it can be a bit overwhelming if you're not familiar with the process. In this tutorial, we'll walk you through the steps to log into a course-specific account on ieng6, so you can focus on learning and excelling in your coursework without any unnecessary stress.

## Part 1 - Your CSE15L Account 
You can find your **course-specific account** here at [sdacs.ucsd.edu](https://sdacs.ucsd.edu/~icc/index.php) and use these logins to access your account:
![Image](no-1.png)
Next follow the instructions from this link exactly to reset your password [ [TUTORIAL] How to Reset your CSE 15L Password](https://drive.google.com/file/d/17IDZn8Qq7Q0RkYMxdiIR0o6HJ3B5YqSW/view?usp=share_link)


## Part 2 - Visual Studio Code
*If you already have Visual Studio Code installed you can skip this step.*
<br /> Proceed the Visual Studio Code website [Visual Studio Code]( https://code.visualstudio.com/) and follow the instructions to download it. 
<br /> Once you have downloaded it, opening Visual Studio Code should look like this: 
<br /> ![Image](VS_Code_(Insiders).png)

## Part 3 – Remotely Connecting
In this part we will be connecting to a remote server, to do this we need to first download Git 
### Downloading Git
Follow this link [Git download website]( https://gitforwindows.org/ ) and download Git. Keep everything default as you proceed through the steps of downloading. 

### Using Bash on Windows in VScode 
Visual Studio Code on Windows uses PowerShell by default as the integrated terminal. 
<br /> To use Bash from Visual Studio Code follow the instructions from this post on [stackoverflow](https://stackoverflow.com/questions/42606837/how-do-i-use-bash-on-windows-from-the-visual-studio-code-integrated-terminal/50527994#50527994 ) 

### Connecting to Remote Server 
Open a terminal on VS code (Ctrl or Command + ') or click new Terminal through the menu options. 
<br /> You should have bash opened in your terminal due to the previous step, if not you can easily swap to it by clicked the + on the bottom right of the terminal. 
<br /> Now you should see the $ symbol in your terminal. You should then type in cs15lsp23zz@ieng6.ucsd.edu but replace the zz with the letters associated with your CSE15L account. 
<br /> After clicking enter you should see something like this (if this your first time) :  
```
⤇ ssh cs15lsp23zz@ieng6.ucsd.edu
The authenticity of host 'ieng6.ucsd.edu (128.54.70.227)' can't be established.
RSA key fingerprint is SHA256:ksruYwhnYH+sySHnHAtLUHngrPEyZTDl/1x99wUQcec.
Are you sure you want to continue connecting (yes/no/[fingerprint])? 

```
<br /> Then type yes and press enter, then give your password.
<br /> Don't worry if you cannot see anything type out as you are inputting your password, its meant to not be visble. 
```
# On your client
⤇ ssh cs15lsp23zz@ieng6.ucsd.edu
The authenticity of host 'ieng6-202.ucsd.edu (128.54.70.227)' can't be established.
RSA key fingerprint is SHA256:ksruYwhnYH+sySHnHAtLUHngrPEyZTDl/1x99wUQcec.
Are you sure you want to continue connecting (yes/no/[fingerprint])? 
Password: 

```
Once you have entered your password you should get this message in the terminal 

``` 
# Now on remote server
Last login: Sun Jan  2 14:03:05 2022 from 107-217-10-235.lightspeed.sndgca.sbcglobal.net
quota: No filesystem specified.
Hello cs15lsp23zz, you are currently logged into ieng6-203.ucsd.edu

You are using 0% CPU on this system

Cluster Status 
Hostname     Time    #Users  Load  Averages  
ieng6-201   23:25:01   0  0.08,  0.17,  0.11
ieng6-202   23:25:01   1  0.09,  0.15,  0.11
ieng6-203   23:25:01   1  0.08,  0.15,  0.11

Sun Jan 02, 2022 11:28pm - Prepping cs15lsp23

```
Now your terminal is connected to a computer in the CSE basement, and any commands you run will run on that computer! 

## Part 4 - Run Some Commands
Now try runnning some commands in the terminal. 
<br /> Here are some commands you should try running: 
* cd
* ls -lat 
* ls -a 
* ls <directory> where <directory> is /home/linux/ieng6/cs15lsp23/cs15lsp23abc, where the abc is one of the other group members’ username
* cp /home/linux/ieng6/cs15lsp23/public/hello.txt ~/
* cat /home/linux/ieng6/cs15lsp23/public/hello.txt
 
<br /> Here is an example of what running the ls - lat returns: 

``` 
 [aqnguyen@ieng6-201]:~:12$ ls -lat
total 88
-rw-r--r--   1 aqnguyen ieng6_staff  1089 Apr  9 12:27 .modulesbegenv
-rw-r-----   1 aqnguyen ieng6_staff     0 Apr  9 11:31 .motd
-rw-------   1 aqnguyen ieng6_staff   149 Apr  6 14:58 .bash_history
drwxr-s---   6 aqnguyen ieng6_staff  4096 Apr  6 14:58 .
-rw-r-----   1 aqnguyen ieng6_staff     7 Apr  6 14:53 hello.txt
drwxr-sr-x   2 aqnguyen ieng6_staff  4096 Apr  6 14:48 perl5
drwxr-sr-x   3 aqnguyen ieng6_staff  4096 Apr  6 14:48 .local
drwxr-sr-x   3 aqnguyen ieng6_staff  4096 Apr  6 14:48 .config
drwxr-sr-x   3 aqnguyen ieng6_staff  4096 Apr  6 14:48 .cache
drwxr-sr-x 174 root     ieng6_staff 16384 Apr  4 12:35 ..
-rwxr-x---   1 aqnguyen ieng6_staff   290 Apr  3  2019 .zshrc
-rwxr-x---   1 aqnguyen ieng6_staff   481 Apr  3  2019 .zshenv
-rwxr-x---   1 aqnguyen ieng6_staff  1931 Apr  3  2019 .zprofile
-rwxr-x---   1 aqnguyen ieng6_staff  1961 Apr  3  2019 .profile
-rwxr-x---   1 aqnguyen ieng6_staff   837 Apr  3  2019 .procmailrc
-rwxr-x---   1 aqnguyen ieng6_staff   431 Apr  3  2019 .login
-rwxr-x---   1 aqnguyen ieng6_staff   155 Apr  3  2019 .locallogin
-rwxr-x---   1 aqnguyen ieng6_staff  1692 Apr  3  2019 .kshrc
-rwxr-x---   1 aqnguyen ieng6_staff  1931 Apr  3  2019 .cshrc
-rwxr-x---   1 aqnguyen ieng6_staff  1721 Apr  3  2019 .bashrc
-rwxr-x---   1 aqnguyen ieng6_staff   975 Apr  3  2019 .bash_profile


```

Here is an examples of what is returned when running ls -a:
  
```
[aqnguyen@ieng6-201]:~:14$ ls -a
.   .bash_history  .bashrc  .config  .kshrc  .locallogin  .modulesbegenv  .procmailrc  .zprofile  .zshrc     perl5
..  .bash_profile  .cache   .cshrc   .local  .login       .motd           .profile     .zshenv    hello.txt         
```

## Part 5 - Logging out 
To log out of the remote server in your terminal, use: 
1. Ctrl- D 
2. Type the `exit` command in the terminal 
 
## Conclusion 
Congratulations, you've successfully logged into your course-specific account on ieng6! By following the steps outlined in this tutorial, you should now be able to access your programming assignments and course materials with ease. We hope this tutorial has been helpful for both incoming 15L students and anyone else who may need to access ieng6 in the future. As you continue your journey in computer science, remember that logging into ieng6 is just the first step. With hard work, dedication, and a willingness to learn, you'll be well on your way to becoming a skilled programmer and problem solver. Good luck, and happy coding!
