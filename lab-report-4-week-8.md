# Lab Report - Week 8

## A link to markdown-parse repository and a link to the reviewed one
[My MarkdownParse](https://github.com/c1peng/markdown-parse)\
[The MarkdownParse I reviwed](https://github.com/jpolitz?tab=repositories)\
Note: I don't know which repository I have to review, so I chose Joe's repository. 

## For Test 1 2 3: 
- It should be 
  1. `[url.com, google.com, google.com, ucsd.edu]`
  2. `[a.com, a.com, example.com]`
  3. `[https://www.twitter.com, https://ucsd-cse15l-w22.github.io/, github.com, https://cse.ucsd.edu/]`
- The screeshot of the code to test: 
![1111](/cse15l-lab-reports/pics/labreport_week8/1111.png)
- I first ran the code with three tests, there are unrelated signs in the links. So I add a look to delete the signs one by one by using the method .replace() from String. 
- For the code I reviewed, I did the same thing. But some links is ignored. So I fixed it by changing the number of nextClosedBracket. 
## Questions: 
1. Do you think there is a small (<10 lines) code change that will make your program work for snippet 1 and all related cases that use inline code with backticks? If yes, describe the code change. If not, describe why it would be a more involved change.
```
            if (toAdd.contains("\n")) {
                closeParen = markdown.indexOf("\n", openParen);
                toAdd = markdown.substring(openParen + 1, closeParen).trim();
            }
            while (toAdd.contains("(") || toAdd.contains(")") || toAdd.contains("`")) {
                if (toAdd.contains("`")) {
                    toAdd = toAdd.replace("`", "");
                } else if (toAdd.contains(")")) {
                    toAdd = toAdd.replace(")", "");
                } else if (toAdd.contains("(")) {
                    toAdd = toAdd.replace("(", "");
                }
            }
```
There are 12 lines for my code to change and there are many lines to test if there are unrelated signs. 

1. Do you think there is a small (<10 lines) code change that will make your program work for snippet 2 and all related cases that nest parentheses, brackets, and escaped brackets? If yes, describe the code change. If not, describe why it would be a more involved change.

The test 1 and test 2 are using the same code to deal with. 

1. Do you think there is a small (<10 lines) code change that will make your program work for snippet 3 and all related cases that have newlines in brackets and parentheses? If yes, describe the code change. If not, describe why it would be a more involved change.
```
String toAdd = "";
            if (nextCloseBracket + 1 == openParen) {
                toAdd = markdown.substring(openParen + 1, closeParen).trim();
            } else if (markdown.substring(nextCloseBracket+1, openParen).contains("]")) {
                toAdd = markdown.substring(openParen + 1, closeParen).trim();
            }
```
For test 3, I added less than 10 lines because I only change the closebracket position and it works. 
