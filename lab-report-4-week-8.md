# Lab Report: Snippet Testing

## Implementations:

For this test, the following Github markdown parse implementations were used:

My markdown parse: [Github](https://github.com/azak03/markdown-parse)

Reviewed markdown parse: [Github](https://github.com/ExtraExaByte/MarkDownParse)

## Tests: 

For each of these, the following snippet files were used:

Snippet 1:

![image](https://user-images.githubusercontent.com/97641168/156126051-e7c3c079-2af8-4854-a306-629c981d4601.png)

Snippet 2:

![image](https://user-images.githubusercontent.com/97641168/156126098-020d9a01-f478-4c8f-b826-2fe5d627f2de.png)

Snippet 3:

![image](https://user-images.githubusercontent.com/97641168/156126167-71c5ee1d-768f-4c87-8e0a-4de403b32daa.png)

MarkdownParseTest for both markdown parse implementations:

![image](https://user-images.githubusercontent.com/97641168/156127790-ed3a9784-357c-40f7-980f-5a86f132c8da.png)

## First Snippet Analysis:

What should be expected: [`google.com, google.com, ucsd.edu]

Results on my markdown parse:

![image](https://user-images.githubusercontent.com/97641168/156129582-b86532cb-788f-492a-9a65-055bd01ee0d6.png)

Results on reviewed markdown parse:

![image](https://user-images.githubusercontent.com/97641168/156129809-51aff76e-1a69-4e3e-8c8d-811ce65f4b4a.png)

Potential fix:

A simple fix for this issue could be achieved by checking for backticks within the string of the brackets [] itself. If there is not a closing backtick present, then the URL should be disregarded by changing the currentIndex variable to skip over the line.

## Second Snippet Analysis:

What should be expected: [a.com, a.com(()), example.com]

Results on my markdown parse:

![image](https://user-images.githubusercontent.com/97641168/156130366-8d577160-e9a4-4c91-95ef-890ba952e7bf.png)

Results on reviewed markdown parse:

![image](https://user-images.githubusercontent.com/97641168/156130502-83a1a74b-f552-4abd-bd5a-2273be7aa97c.png)

Potential fix:

A fix for this issue could be achieved by keeping track of the paranthesis/brackets in the line. If a opening paranthesis is found, a variable could be incremented and checked to see that each closing paranthesis is equal to the amount of opening paranthesis. As for whether or not this would be 10 lines is a bit complicated, because it involves creating multiple new variables and if statements for each of those variable conditions to analyze if the format is valid.

## Third Snippet Analysis:

What should be expected: [https://ucsd-cse15l-w22.github.io/]

Results on my markdown parse:

![image](https://user-images.githubusercontent.com/97641168/156131191-f4a7aac1-8804-4238-89ea-44bceea54466.png)

Results on reviewed markdown parse:

![image](https://user-images.githubusercontent.com/97641168/156131316-75160912-ec48-4608-b776-81218c4fa448.png)

Potential fix:

A quick fix for these issues can be achieved by ensuring that each link includes a closing paranthesis, otherwise it is invalid. As for the spaces issue, they should be filtered out of the URL since they cannot contain spaces and newlines anyway. This may be possible with a String.replace filter. 
