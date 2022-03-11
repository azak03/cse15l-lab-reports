# Lab Report: SH Testing

## Implementation:

To find the results, echo $file was added to script.sh, allowing me to clearly see the file name of each test. Then, the results were exported to results.txt for both markdown parse implementations. The results were compared using a difference checker website, diffchecker.com

## Test One:

This was test 395:

![image](https://user-images.githubusercontent.com/97641168/157915631-ce9a45f7-ff07-49b4-b8c9-dd4718bd477e.png)

The results of test 395 on the given markdown implementation:

![image](https://user-images.githubusercontent.com/97641168/157914614-1f85f85f-c721-40f4-b3ae-81a55c9d542a.png)

Results on my implementation:

![image](https://user-images.githubusercontent.com/97641168/157914572-5ba73ea8-3bbb-4f64-b90b-f7b02705ca7c.png)

My implementation was incorrect in this case, and the given implementation was correct.
The cause of this problem in my implementation comes from line 22:

![image](https://user-images.githubusercontent.com/97641168/157915320-fe3b7074-d6bf-4feb-9003-20d5b1051804.png)

Because no open bracket was found, it has a value of -1, but the code only checks if it isn't 0. This means .charAt is called on -1 - 1, which is -2. This is why the error refers to an out of bounds range of -2.

## Test Two:

This was test 567:

![image](https://user-images.githubusercontent.com/97641168/157919050-86c5f4af-c140-4604-97cf-a10ef5e7af77.png)

Results on given implementation:

![image](https://user-images.githubusercontent.com/97641168/157918845-a9d21856-f726-4eba-b166-fc71291e2cd3.png)

Results on my implementation:

![image](https://user-images.githubusercontent.com/97641168/157918691-387c3e79-518f-42fb-8ea7-353c6a64d8da.png)

According to spec.commonmark.org testing, both cases here are incorrect. Because [foo]: /url1 is included in the test file, the true link should not be blank and should not be "not a link" but should actually be to the URL in the last line, which is the current url with "/url1" added. 

![image](https://user-images.githubusercontent.com/97641168/157919941-dcb16be6-afab-4539-814d-23efa553c3df.png)

The solution would be to add a check for a colon similar to how brackets are checked for, and keep track of the URL stored after the colon.
