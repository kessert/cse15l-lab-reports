# Snippet.. stuff

## The Snippet Tests
![](https://raw.githubusercontent.com/kessert/cse15l-lab-reports/main/4_11.PNG)

I gave each snippet its own file and checked the files with JUnit.

Snippet 1 should produce `[%60google.com, google.com, ucsd.edu]`. (The backtick seems to turn into %60 in the link)

Snippet 2 should produce `[a.com, a.com(()), ucsd.edu]`

Snippet 3 should produce `[https://ucsd-cse15l-w22.github.io/]`

### [My Implementation](https://github.com/kessert/markdown-parse)
![](https://raw.githubusercontent.com/kessert/cse15l-lab-reports/main/4_12.PNG)
Complete failures across the board for the snippets.

### [Their Implementation](https://github.com/pvijay03/markdown-parse)
![](https://raw.githubusercontent.com/kessert/cse15l-lab-reports/main/4_13.PNG)
Snippet 2 had slightly different values from my implementation, but still failed all snippets.

## Possible fixes

### Snippet 1
There's two cases that'd have to be covered by a fix:
- There's an ending backtick inside any of the URL
- There's a starting backtick before the `(link)`

The tricky part would be figuring out if it's a starting or ending backtick; in that it starts a `codeblock` or ends one. Backslashed ones wouldn't count, and you'd have to count across the entire file to track up to the link's. For that reason, I feel like it'd take more than 10 lines, since that doesn't even take into account finding a starting backtick that swallows a link `[like](this)`.

### Snippet 2
Similar to the first one, you'll have to keep track of every starting and ending bracket and parenthesis that is and isn't a part of markdown syntax. That's really complex and would take a lot more than 10 lines.

### Snippet 3
I think fixing newline cases as very doable; just remove the newlines and empty space before considering a link. By doing that, you can just focus on the brackets and parenthesis like we already have in the code now.