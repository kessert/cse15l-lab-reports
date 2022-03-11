The following differences were found using the `diff` command comparing the bash output of our implementation and the lecturer's implementation. Using the lines shown by diff I looked into which .md file it was testing in order to compare the two.

For test 2, since there were newlines in some outputs the diff started getting offset, so I had to manually find the .md for each; which were really close to the lines stated.

```
> Is our implementation's result
< Is lucturer's implementation result
```

## Test 1
![](https://raw.githubusercontent.com/kessert/cse15l-lab-reports/main/5_1.PNG)
![](https://raw.githubusercontent.com/kessert/cse15l-lab-reports/main/5_2.PNG)

Looking at how markdown interprets the text, there should be no links, meaning the lecturer's implementation (`[]`) was correct.

Our code doesn't check the inside of the parenthesis once it obtains them. In order to fix our code, we'd have to ensure there is no space in the URL by checking for `.indexOf(" ")`.

## Test 2
![](https://raw.githubusercontent.com/kessert/cse15l-lab-reports/main/5_3.PNG)
![](https://raw.githubusercontent.com/kessert/cse15l-lab-reports/main/5_4.PNG)
![](https://raw.githubusercontent.com/kessert/cse15l-lab-reports/main/5_5.PNG)

Not visible in the screenshot is the link leading to `(foo)`. Both results include the blackslashes, which means they are both wrong; however the second (lecturer's) implementation is *less* wrong, since it includes the final parenthesis.

For the lecturer's implementation, fixing this would require knowing what backslash can and can't alter. `(\foo)` would include it, but `\(foo\)` doesn't. From my testing on commonmark, I can infer that checking for a non-alphabetical character after a \ should result in a removed backslash. If it is alphabetical, it should be kept. This would have to be added on to the initial code after obtaining the content within parenthesis.