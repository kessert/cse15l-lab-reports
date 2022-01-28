# Markdown Parser Bug Fixes
## Bug 1: 


### [Test File 1](https://github.com/kessert/markdown-parse/blob/main/test-file2.md)
![Visual Studio Code](/2_11.png)
![Visual Studio Code](/2_12.png)


This first file contained no links, brackets, or parenthesis in it. When running it, the program gets an IndexOutOfBounds error on the line where we're trying to substring a link. The reason why this occurred was because indexOf() returns -1 when it doesn't find anything, and the program didn't understand that and took it as an actual usable index.

## Bug 2: 

### [Test File 2](https://github.com/kessert/markdown-parse/blob/main/test-file3.md)
![Visual Studio Code](/2_21.png)
![Visual Studio Code](/2_22.png)

This second file contains just opening brackets and parenthesis, which caused the program to error again with IndexOutOfBounds. The reason this happened was because, again, it used -1 as an index when a close parenthesis did not exist, causing an error. The previous fix only accounted for if there was no opening bracket, which there was, so a similar problem occurred.

## Bug 3: 

### [Test File 3](https://github.com/kessert/markdown-parse/blob/main/test-file4.md)
![Visual Studio Code](/2_31.png)
![Visual Studio Code](/2_32.png)

The last file was formatted as if it were an image link, but the "link" was just text. The reason this happened was because the program assumes inside where the link should be in markdown is valid, when ideally it would check if it actually is a link. It doesn't cover all cases, but in cases where the "link" doesn't contain a period, now it's treated as invalid since there should at the bare minimum be a file extension.