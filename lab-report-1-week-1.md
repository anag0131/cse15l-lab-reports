# Lab Report 1 #
---
Welcome to Lab Report 1! In this lab, we will learn how to connect to a remote server as well as use ssh and scp keys. I have listed steps below as well as images of my examples
---


**Step 1 : Installing VS Code**

-Install VS Code by downloading it from the website (clicking the download button)

-Once installed, navigate to the computer’s downloads folder and drag the VS Code download to the applications folder

-Once in the applications folder, open up the package and your screen should look similar to the image above (Mine looks slightly different because I already had VS Code downloaded)
![Image](https://user-images.githubusercontent.com/114611146/193357481-e43074ef-c3a2-4138-a15a-c8cc3ea9f88f.png)

**Step 2 : Remotely Connecting**

-Once in VS Code, navigate to the terminal by clicking terminal and then new terminal on the top right toolbar. Now you are in the terminal

-Once in the terminal, type in ssh cs15lfa22zz@ieng6.ucsd.edu  but replace the zz with your class ID which is the last two numbers of your CSE 15L account

-This step may not work for you if you have recently changed your CSE 15L account password, as was the case for me, so instead, you can type yourucsdaccountusername@ieng6.ucsd.edu

-When prompted with yes or no questions enter yes and when prompted for a password, enter either the password for your CSE 15L account or ucsd student account depending on which username you used to remotely connect 

![Image](https://user-images.githubusercontent.com/114611146/193357622-a9f595f5-6b88-408d-bf7d-93b1a26fe26d.png)

**Step 3 : Trying some commands**

-Try some of the following commands by typing them in the same terminal where you remotely connecting : 
1. ls <directory> where <directory> is /home/linux/ieng6/cs15lfa22/cs15lfa22abc, where the abc is one of the other group members’ username
2. cp /home/linux/ieng6/cs15lfa22/public/hello.txt ~/
3. cat /home/linux/ieng6/cs15lfa22/public/hello.txt
4. (commands taken from lab instructions on CSE 15L Website)
  
-The ls command I used is supposed to list the contents of a user’s directory. Because there were login issues and my group member had to use her ucsd username instead of class ID, it wasn’t able to load the contents of her directory

![Image](https://user-images.githubusercontent.com/114611146/193357684-a16a4ccc-fde7-452f-9257-838b4d559a42.png)
  
**Step 4 : Moving Files with scp**
  
-Now that you are connected to the remote computer, this step intends to copy files from your computer to the remote computer using scp

-First, create a new file in your VS Code by clicking file and new file. Name the file WhereAmI.java and copy the following code below : 
  
  class WhereAmI {
  public static void main(String[] args) {
    System.out.println(System.getProperty("os.name"));
    System.out.println(System.getProperty("user.name"));
    System.out.println(System.getProperty("user.home"));
    System.out.println(System.getProperty("user.dir"));
  }
}

  
-Then in a new terminal, to ensure the code runs, type javac WhereAmI.java and hit enter, then type java WhereAmI. Once it has ran, it should show you where on your computer, the file is saved

  
-To move the file to the remote computer, remotely connect to the computer again by typing scp WhereAmI.java cs15lfa22zz@ieng6.ucsd.edu:~/ or whatever username you used followed by :~/

![Image](https://user-images.githubusercontent.com/114611146/193357724-49cfa1cb-80ae-4247-974a-024a2c9c78fc.png)
  
**Step 5 : Setting an SSH key**
  
-Here, we can create ssh keys to ensure that we don’t always have to type our passwords when connecting back and forth between our personal and remote computers

-To do this, type the following into your personal computer : ssh-keygen and when prompted for a password, hit enter to make this your default password
  
-Then, on your personal computer terminal, log back into the remote computer using ssh
  
-Then, on the computer with the terminal, enter mkdir .ssh to connect this password key to the remote computer. Once finished, log out of the remote server

-Go back to your personal terminal and enter scp /your original path followed by your username for the remote computer:~/.ssh/authorized_keys 
  
![Image](https://user-images.githubusercontent.com/114611146/193357787-10483553-bd58-4a32-9cf1-3ffae21d1e99.png)
  
![Image](https://user-images.githubusercontent.com/114611146/193357782-7e748381-73eb-4063-807e-5eac2f0682e4.png)
  


**Step 6 : Optimize Remote Running**
  
-To directly run commands on a remote server, you can put the command in quotations after connecting to the remote server as shown below 

  
![Image](https://user-images.githubusercontent.com/114611146/193357860-bfb71ed7-0ae7-47cc-98af-ba66eb590600.png)
  
-You can also run many commands at once on the same terminal by separating them with a comma
  
---
Hope you enjoyed this lab and were able to learn how to remotely connect to a computer just like I was!
  
-Ananya Nag
