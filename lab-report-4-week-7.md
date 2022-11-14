# Lab Report 4


**Part 1 : Changing the name of the start parameter to base**

Task : change all instances of start to base using Vim Commands


1. Within Terminal : vim DocSearchServer.java --> enter key
  
  This should open the file in the Vim Terminal

  ![Image](https://user-images.githubusercontent.com/114611146/201738032-c46d90f7-2998-4654-b551-bb5b532b59e2.png)
  
  ![Image](https://user-images.githubusercontent.com/114611146/201738018-bc4ccc5e-918b-4770-9b56-6683eda8d60e.png)
  
  

2. :%s/start/base/g --> enter key 
  
  This finds all instances of the string start and replaces it with base 
  
  ![Image](https://user-images.githubusercontent.com/114611146/201738128-cc993692-2387-4c88-a01b-b42b4f7aaf87.png)
  
  After the Enter key is hit, the changes will show in the vim terminal 
  
  ![Image](https://user-images.githubusercontent.com/114611146/201738131-13b884be-207f-452b-b80c-4517f9af7ddd.png)
  
  
3. :wq --> enter key
  
  This saves all changes to the file and exits the terminal. Now, the file has the saved changes
  
  ![Image](https://user-images.githubusercontent.com/114611146/201738160-ad757192-25a1-4a11-8fee-652f3c1a430d.png)
  
  ![Image](https://user-images.githubusercontent.com/114611146/201738156-0bd6e54a-6f6d-48a6-9439-43ca6ba784d2.png)
  
  
  
**Part 2: Running on a remote server **

When using strategy 1 of SCP the file and making the changes on VSCode, it took me 1 minute and 13 seconds

When using strategy 2 of vim commands to make the changes in the remote server, it took me 47 seconds

Therefore, strategy 2 was faster 

1. Of the two strategy files, I prefer using Vim Commands to make the changes in a remote server. This is because you don't need to scp the file into the remote
 server but can instead use vim to clone and then search through the file. Additionally, vim allows you to find and replace all instances of a string using only 
 one command whereas if I were to change it manually on vscode, I would have to search each line for the instance of the string. 
 
2. What factors into my decision is that there were multiple instances where Start had to be changed into Base. Because of this, it is much faster to find and replace
 all instances of the string in Vim. Otherwise, it would be time consuming to comb through each line and manually find and replace the 3 instances of start and then spend additional
 time saving changes. Additionally, had there been 10 or more instances of Start, it would have been so much more time consuming to find and replace every instance using stratgey 1

  
