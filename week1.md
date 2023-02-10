# Week 1 Lab Report
#### Sitting in CSE 15L and struggling to remotely connect? I've got you covered.

## Step 1: Install Visual Studio (VS) Code
#### If you previously took a CSE course here at UC San Diego (e.g. CSE 11), you most likely already have VS code installed (I did). If not, navigate to https://code.visualstudio.com/download and follow the onscreen instructions to download for your specific operating system. If everything goes to plan, you'll end up with something similar to this:

![image](https://user-images.githubusercontent.com/54877475/212776819-7b28b961-6d9d-4d51-9cd1-de0c566be2b2.png)

## Step 2: Connect to the Remote Server
#### From here on, my instructions will be more helpful for Windows users since I use a Windows operating system. 
#### Firstly, I needed to install Git at https://www.atlassian.com/git/tutorials/install-git#windows. Make sure you enable the setting that allows you to use Git Bash *NOT FROM THE COMMAND PROMPT*. Then open up VS code and on the top left corner, click "Terminal" and then "New Terminal." You'll see it open up along the bottom of your screen: 
![image](https://user-images.githubusercontent.com/54877475/212778116-e5304e88-d810-4d80-83de-748e643332ad.png)

#### Now, on the top right corner of the terminal you'll see a down arrow next to "powershell" and the plus sign. Hit this arrow and select "Git Bash." You're now ready to enter some commands!

#### To begin remotely connecting, type `ssh cs15l[YOUR CLASS QUARTER][YOUR ASSIGNED USERNAME]@ieng6.ucsd.edu` after the dollar sign. For instance, I typed `ssh cs15lwi23aps@ieng6.ucsd.edu`. Hit enter and type `yes` to the next question, then enter your password. Note that you won't be able to see what you've typed in the password field so type carefully! If all is fine and dandy, you'll see this (with your own username): 

![image](https://user-images.githubusercontent.com/54877475/212779417-56d27ade-0537-402b-9fcd-f92cb2afe68e.png)

## Step 3: Try Some Commands
#### Now play around with some commands to learn what they do. Here's my piece of experimentation: 

#### I started on my local system, using `pwd` to print the current working directory and `cd` to change the directory to my computer's "Downloads" folder. Now in this folder, I used `ls` to list my downloaded files (sorry, nothing spicy there).

![image](https://user-images.githubusercontent.com/54877475/212780506-379b9588-345f-4dfd-823a-cc7fc0c0bdcc.png)

#### Connecting to the remote server, I used `cd` into the "Downloads" folder but since the system contains no such directory, I am left with an error.

![image](https://user-images.githubusercontent.com/54877475/212780487-a390c3a6-e754-4762-9f1a-26963bff19f2.png)

### *Congratualations, you're done! Now Joe is probably going to make you write a guide just like the one you're reading. Hopefully there's a guide for that too?*
