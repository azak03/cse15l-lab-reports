# Lab Report: How to Log in to your ieng6 Course Account
This tutorial will teach you how to install 

## Step 1: Installing VSCode
To begin, you need to install **VSCode** from the following link: [VSCode Download](https://code.visualstudio.com/)	

Once you have it installed, it should look like *this:*
![image](https://user-images.githubusercontent.com/97641168/149599480-a2ec6eac-7cbe-4774-9653-c748941fcbbe.png)

## Step 2: Remotely Connecting

The next step is to open the **terminal** window from VSCode, and input the following command:

$ ssh cs15lwi22**ID**@ieng6.ucsd.edu

Note that you must replace ID with your unique student course account ID.

Once you have completed this step and inputted your student password, you should see the following:
![image](https://user-images.githubusercontent.com/97641168/149599537-c4fd61f8-5707-48ac-836c-ce10e3b7a41e.png)

## Step 3: Ensure you are connected

To ensure you're connected correctly, try out some commands! For example, the "ls" command will list the current directory of the server you have connected to.
An example of this can be seen here:

![image](https://user-images.githubusercontent.com/97641168/149599922-a42ecc08-2d29-455d-9eff-07c8c9d92151.png)

## Step 4: File transfer with SCP

To transfer files from your client to the server, use the **scp** command in the terminal, specifying the file name and then the host address:

$ scp filename.java cs15lwi22**ID**@ieng6.ucsd.edu:~/

As an example, here is what transfering a local file in VSCode, WhereAmI.java, to the host should look like:
![image](https://user-images.githubusercontent.com/97641168/149600053-04bd2147-af74-4ca3-bd0b-9cd51313bc11.png)

## Step 5: Setting an SSH key

Setting an SSH key will allow you to log in to the server without having to input your student password every time you connect.

To begin, run the following command:
$ ssh-keygen
If you don't already, you may need the following ssh-add steps from [here.](https://docs.microsoft.com/en-us/windows-server/administration/openssh/openssh_keymanagement#user-key-generation)

Next, you will need to SCP the generated .ssh file to the server:
$ scp /Users/**YOURNAME**/.ssh/id_rsa.pub cs15lwi22**ID**@ieng6.ucsd.edu:~/.ssh/authorized_keys

Notice that the prompt to input a password no longer appears:

![image](https://user-images.githubusercontent.com/97641168/149600969-f85ff122-1ee2-4005-9b3a-fd73544c707f.png)

## Step 6: Optimize and improve your setup

If you want to run multiple commands on the host, you can separate your commands with semicolons!

![image](https://user-images.githubusercontent.com/97641168/149601646-6a0f95a6-fa3b-45c3-86d3-2ba0faa7bb15.png)

