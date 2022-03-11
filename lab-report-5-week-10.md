# Lab Report - Week 10

## How did I find the tests with different results: 

I didn't use `diff` because this command doesn't work on Windows. I added `echo $file` to the script.sh, like this: 

![11111](/cse15l-lab-reports/pics/labreport_week10/11111.png)

Accoding to the outputs from running the script.sh, I found my outputs from 12.md and 484.md are different from the professor's. 

## For each Test: 

### Test 12.md: 
#### The correct output: 

![22222](/cse15l-lab-reports/pics/labreport_week10/22222.png)

#### My output is: 

![33333](/cse15l-lab-reports/pics/labreport_week10/33333.png)

Note: Yes, I added an `if` to tell me whether it's in a loop or not. 

#### Bug: 
I used `jdb` to find out the reason why it got into an infinite loop. I found that the variable `closeParen` didn't change each time. It is the variable `openParen` to define `closeParen`, and `openParen` is `-1`. So like the selected part in the screenshot, I tried to add an `if` to check if the `openParen` is `-1`, then break. The output becomes the same as the correct output. 

![44444](/cse15l-lab-reports/pics/labreport_week10/44444.png)

### Test 484.md: 
#### The correct output: 

![55555](/cse15l-lab-reports/pics/labreport_week10/55555.png)

#### My output is: 

![66666](/cse15l-lab-reports/pics/labreport_week10/66666.png)

#### Bug: 
I found that if the `markdown` contains `()`, then the program will throw an exception. So like the selected part in the screenshot, I added an `if` to check if there are not more than one pair of `()`, then return an empty string, because `()` is empty. The output becomes the same as the correct output. 

![77777](/cse15l-lab-reports/pics/labreport_week10/77777.png)