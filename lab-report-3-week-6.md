# Lab Report: Streamlining SSH Configuration

## Step 1: Setting up SSH config file

![image](https://user-images.githubusercontent.com/97641168/153780335-19b61c3e-7db6-40fd-b466-268920220711.png)

In this image, we set up the config file in our C:/Users/user/.ssh folder. This config specifies:
Line 1: The Host alias

Line 2: The host name, AKA the url of the server to connect to

Line 3: The user, your ieng6 account name.

Once this is configured, you are free to enter the terminal in VScode and connect with the chosen Host alias.

## Step 2: Connecting with the new alias

![image](https://user-images.githubusercontent.com/97641168/153780370-baedd431-2f4b-484b-ae3a-f5162af88b86.png)

Instead of typing the full URL, we only had to type the chosen alias "ieng6." This made the process way simpler than typing "sch cs15lwi22ahp@ieng6.ucsd.edu." 
Combining this with the SSH keygen saves significant time, as now it's as simple as a short command with no password needed!

## Step 3: SCP test with the new alias

![image](https://user-images.githubusercontent.com/97641168/153780591-553bc08b-11f5-47d5-8feb-c593c424afb5.png)

As you can see, instead of having to type the full host to SCP the file to, we only had to use our "ieng6" alias. This saves significant time when transferring files!
