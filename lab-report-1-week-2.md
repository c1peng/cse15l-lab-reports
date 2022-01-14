# Lab Report - Week 2

## Set-up
### Installing [Vitual Studio Code](https://code.visualstudio.com/)

1. Click Download: 
![1](/cse15l-lab-reports/pics/labreport_week2/1.png)
2. Open the file you just downloaded
3. Follow the steps to install

### Remotely Connecting

1. (For Windows Users) [Install OpenSSH](https://docs.microsoft.com/en-us/windows-server/administration/openssh/openssh_install_firstuse)
2. Look up or course-specific account for CSE 15L in the [link](https://sdacs.ucsd.edu/~icc/index.php)
3. Connect to ieng6
   - Open a Terminal (Ctrl/Command + ` in VS Code)
   - Enter `ssh <your+course+account>@ieng6.ucsd.edu`
   - (If it's your first connection to this server) Enter Yes
   - Enter your password (Password won't be shown)
   - Successful Login: ![2](/cse15l-lab-reports/pics/labreport_week2/2.png)


### Trying Some Commands
#### Basic commands table

|Command|Parameter|Description|
|:----:|:----:|:----:|
|cd ~|home|go to the home directory|
|cd \<directory>|destination directory|go to the destination directory|
|ls -lat|all server details|list all server details in the current directory|
|ls -a|hidden file|list all files in the current directory|
|ls \<directory>|destination directory|list all files in the destination directory|
|cp \<file> \<directory>|file location, destination directory|copy the file to thedestination directory|
|cat \<file>|file location|show the content of the file|
|exit|/|log out your session|

## Optimizing

### Moving Files with `scp`
1. Log out
2. Create a file called `ASampleMDFile.md`
3. Use `scp <file location> <your+course+account>@ieng6.ucsd.edu:~/` to copy the file to your home directory of the server
4. Log in and enter `ls` to see if the file is copied successfully
5. Sccessful Copy![3](/cse15l-lab-reports/pics/labreport_week2/3.png)
6. Log out

### Setting an SSH Key
1. Generate an SSH Key
   - Open A Terminal
   - Enter `ssh-keygen`
   - It returns like this: ![4](/cse15l-lab-reports/pics/labreport_week2/4.png)
2. (For Windows User) Follow the extra `ssh-add` steps [here](https://docs.microsoft.com/en-us/windows-server/administration/openssh/openssh_keymanagement#user-key-generation)
3. Login and Enter `mkdir .ssh`
4. Logout
5. Enter `scp <your+SSH+keys.pub+location> <your+course+account>@ieng6.ucsd.edu:~/.ssh/authorized_keys`
6. Try login, and you will see you don't need password now. ![5](/cse15l-lab-reports/pics/labreport_week2/5.png)
7. Logout

### Optimizing Remote Running
- If you want to access the server without login and logout, Enter `ssh <your+course+account>@ieng6.ucsd.edu "<command>; <command>..."` in your Terminal. 
  - such as listing the home directory on server. Enter `ssh <your+course+account>@ieng6.ucsd.edu "ls"`![6](/cse15l-lab-reports/pics/labreport_week2/6.png)
  - such as running Java Program on server. Enter `ssh <your+course+account>@ieng6.ucsd.edu "javac OtherMain.java; java WhereAmI"`![7](/cse15l-lab-reports/pics/labreport_week2/7.png)
- Try to press ↑ to recall your last command