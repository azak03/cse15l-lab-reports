# Lab Report: Markdown Parse Report

## Example 1: firstline.md

Failure-inducing file:
[Link](https://github.com/azak03/markdown-parse/blob/main/test-file.md)

The issue produced by this file (we actually made an image tag to hi.png, not a link tag!):

![image](https://user-images.githubusercontent.com/97641168/151644437-1501a321-b92c-4c8c-84a2-c3092da1dfcc.png)

The committed solution:

![image](https://user-images.githubusercontent.com/97641168/151644553-3453d32e-0191-4399-90b4-d6efa7640cef.png)

Explanation:

This bug is the result of not checking whether or not the brackets include a "!" before to indicate whether or not the tag is an image or link tag. A symptom of this is the parser reading the image URL as a web link despite it being specified as an image, so the image pointing to "hi.png" actually returns as a web link URL in the output when it shouldn't. This can clearly cause confusion if this program was being used publicly.

## Example 2: noParen.md

Failure-inducing file:
[Link](https://github.com/azak03/markdown-parse/blob/main/noParen.md)

The error produced by this file:

![image](https://user-images.githubusercontent.com/97641168/151641352-85e83804-ef37-475a-a998-3c91804f583c.png)

The committed solution:

![image](https://user-images.githubusercontent.com/97641168/151641430-2f45824e-fb87-427f-8f1f-50d988f566c3.png)

Explanation:

This bug occurs because the program tries to locate the first open paranthesis in noParen.md, which doesn't exist and therefore returns -1. A symptom of this bug is that toReturn.add gets called passing -1 + 1 (0) and -1 in the markdown.substring, causing an error. This is solved by checking if there is no available open paranthesis (== -1 check) to ensure this error does not occur.

# Example 3: firstline.md

Failure-inducing file:
[Link](https://github.com/azak03/markdown-parse/blob/main/firstline.md)

The error produced by this file:

![image](https://user-images.githubusercontent.com/97641168/151641012-3a83b22b-fcf1-454e-b2c9-cd5d4a726c4b.png)

The committed solution:

![image](https://user-images.githubusercontent.com/97641168/151644641-0ba011d7-56a5-41a5-b7eb-8be592f84fcc.png)

Explanation:

In this situation, the bug is that the check for the image tag "!" 1 character before the bracket leads to a markdown.charAt call to -1 if the first bracket is the first character of the file. As a result, the symptom is that the program fails to read the file and instead produces an out of bounds error by trying to call markdown.charAt(-1). This is solved by using an if check to make sure that the open bracket is at an index greater than 0 before checking the character before it.
