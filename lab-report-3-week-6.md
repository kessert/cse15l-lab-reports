# Copying Whole Directories

![scp -r](https://raw.githubusercontent.com/kessert/cse15l-lab-reports/main/3_1.PNG)

Using `scp -r` will copy over the full (specified) directory, which I use in the image above. I'm already in markdown-parse, so `.` will just take the current directory and throw it in my ieng6 computer, inside a directory of the name "markdown-parse".


![Running test](https://raw.githubusercontent.com/kessert/cse15l-lab-reports/main/3_2.PNG)

To check this worked, I ssh into it and compile and run the command. It brought everything needed over! Both my machine and the linux one give the OK with 6 tests.


![The command](https://raw.githubusercontent.com/kessert/cse15l-lab-reports/main/3_3.PNG)
![The result](https://raw.githubusercontent.com/kessert/cse15l-lab-reports/main/3_4.PNG)

..Now the part that frustrated me for way too long. Here I combine it all into one command and run it, but what I hadn't learned until asking was that there's an [issue](https://piazza.com/class/kxs0toocqhv4og?cid=354) with the default java version. I've been doing it right all along, but the javac and java were wrong versions when trying it in the command this way. In my photos above though, I implement the fix and get the anticlimatic "OK (6 tests)". Was it worth it? No, no it wasn't. At least the pain will result in a full-credit lab report. Right?