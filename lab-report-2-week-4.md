# Lab Report - Week 4

## Code Change 1
### Screenshot of Code Change Diff
![11](/cse15l-lab-reports/pics/labreport_week4/11.png)
### Link to the File
[Link to breaking-test.md](https://github.com/c1peng/markdown-parse/blob/main/breaking-test.md)
### Symptom
```Java
Exception in thread "main" java.lang.OutOfMemoryError: Java heap space
        at java.base/java.util.Arrays.copyOfRange(Arrays.java:3822)
        at java.base/java.lang.StringLatin1.newString(StringLatin1.java:769)
        at java.base/java.lang.String.substring(String.java:2709)
        at MarkdownParse.getLinks(MarkdownParse.java:24)
        at MarkdownParse.main(MarkdownParse.java:33)
```
### Description
The value of currentIndex doesn't update correctly, so the content in the while() kept running and running again. So we added a break; if there is no more "[" in the rest of String. Other than that, once we add a "()" in the link, the program return to half of the correct link. Therefore, we add an if() to update the value of currentIndex. 


## Code Change 2
### Screenshot of Code Change Diff
![22](/cse15l-lab-reports/pics/labreport_week4/22.png)
### Link to the File
[Link to breaking-test_2.md](https://github.com/c1peng/markdown-parse/blob/main/breaking-test_2.md)
### Symptom
```Java
Exception in thread "main" java.lang.StringIndexOutOfBoundsException: begin -2, end -1, length 24
        at java.base/java.lang.String.checkBoundsBeginEnd(String.java:4601)
        at java.base/java.lang.String.substring(String.java:2704)
        at MarkdownParse.getLinks(MarkdownParse.java:21)
        at MarkdownParse.main(MarkdownParse.java:36)
```
### Description
The close parenthesis is missing and the program cannot cut the correct link to return. We added an if() to return toReturn directly once there is no more a close parenthesis in the rest of String. 


## Code Change 3
### Screenshot of Code Change Diff
![33](/cse15l-lab-reports/pics/labreport_week4/33.png)
### Link to the File
[Link to breaking-test_3.md](https://github.com/c1peng/markdown-parse/blob/main/breaking-test_3.md)
### Symptom
```Java
null
```
### Description
We added an empty .md file and let the program analyze it. The program didn't report errors, and the program works well with the empty file. 