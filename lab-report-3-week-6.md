# Lab Report - Week 6

## Group Choice Option 1: Streamlining ssh Configuration
### .ssh/config file
![111](/cse15l-lab-reports/pics/labreport_week6/111.png)

I used notepad to directly edit the config file. After that, it shows "bad permission" after `ssh ucsd` (on Windows). Then I googled the problem and solved it. 
1. Right-click .ssh
2. Properties - Security - Advanced
3. DISABLE INHERITANCE
4. Apply
### `ssh` command login
![222](/cse15l-lab-reports/pics/labreport_week6/222.png)

I changed the ieng6 to ucsd and used `ssh ucsd` to log into the remote server. 

### `scp` command copying a file
![333](/cse15l-lab-reports/pics/labreport_week6/333.png)

I used `scp -r ../cse15l-lab-reports ucsd:~/` to copy the folder that contains lab reports to the root folder of my account. 