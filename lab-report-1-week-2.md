# How to login to ieng6
## Step 1: Install VSCode
- Visit https://code.visualstudio.com and press the big blue download button

![Visual Studio Code](Capture1.png)

- Go through the download process until you end up with a blank VSCode window open

## Step 2: Remotely Connect
- This assumes you already know your account for `[username]@ieng6.ucsd.edu`, if not, look it up [here](https://sdacs.ucsd.edu/~icc/index.php)
- Open a terminal in VSCode at the top left of the page

![VSCode Window](Capture2.png)

- Type `ssh [username]@ieng6.ucsd.edu`, then your UCSD password. You should be remotely connected!

![SSH Terminal](Capture3.png)

## Step 3: Run Commands
- As long as you see your account before your terminal input, all commands are in the linux server!
- Run `ls` to see all the files in your directory, `cd [name]` to open any folders in it, etc.

![Terminal Commands](Capture4.png)

## Step 4: Move files with SCP
- Press Ctrl+D to go back to your local computer. Create a file you want to transfer!
- Copy the path of that file's directory and use `cd "[path]"` to open in the terminal

![Termianl Go-to Directory](Capture5.png)

- Type `scp [filename w/ extension] [username]@ieng6.ucsd.edu:~/`. Enter your password again if it prompts you. Your file is now in that main directory!

![SCP File Copy](Capture6.png)

## Step 5: SSH Keys
- Arguably the hardest part, in your local computer type `ssh-keygen`, press enter through the options, and you should end up with a randomart in your terminal

![SSH Keygen](Capture7.png)

- Type `scp [path to .pub key] [username]@ieng6.ucsd.edu:~/.ssh/authorized_keys`, make sure you either use a full path or go to that directory in terminal to use the relative path
- When you ssh into the remote computer now, it shouldn't ask for a password anymore!

## Step 6: Optimize remote running
- Transferring files and then sshing and then compiling and then running is tedious. You can do it all in one command line!
- Type `ssh [username]@ieng6.ucsd.edu "javac [your file]; java [your file];", assuming you have a java file SCPed into the computer, it will connect and run all in one command!

![Terminal One-liner](Capture8.png)