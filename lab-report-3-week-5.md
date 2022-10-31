# Lab Report 3


In this lab report I will go over some command line options and examples of these options for the **grep** command

---

**Option 1 : the -c option** 

the -c option counts the number of lines containing the search term used with the grep command 

*Example 1 :*

![Image](https://user-images.githubusercontent.com/114611146/199065040-83b96bdb-f2ba-485d-bd5e-aab494d6c347.png)

Here, the search term is government, and the -c option returns the number of lines containing the term government in /technical. A reminder is that only using
-c with grep is case sensitive.

*Example 2 :*

![Image](https://user-images.githubusercontent.com/114611146/199065044-f10bb1f4-1c99-4ad4-91f7-3a6ee6ea9805.png)

Here, the search term is Testimony, and the -c option returns the number of lines containing Testimony in /technical. Once, again this is case sensitive so if I had the Testimony in a lower case t, then it would return 0

*Example 3 :*

![Image](https://user-images.githubusercontent.com/114611146/199065045-bca99ced-e79d-47dc-8388-7c408834c5ae.png)

Here, the search term is journal and the -c option with grep finds 102 lines containing the term journal in /technical

**Option 2 : the -n option**

the -n option with grep in the terminal presents the lines matching the search term and contains the line number where the line is found in/terminal before the result 

*Example 1 :*

![Image](https://user-images.githubusercontent.com/114611146/199065046-fdb78343-b854-446a-b5d1-5663ed12ec87.png)

Here, grep -n with search term journal presents all the lines which contain journal in /technical as well as the line numbers they are found on within the directory

*Example 2 :*

![Image](https://user-images.githubusercontent.com/114611146/199065055-20c62775-b327-4fa3-82b5-7b0f8181bb72.png)

Here, grep -n with search term Session presents all the lines which contain Session in /technical as well as the line numbers they are found on within the directory. 
One thing to note here, is that it is case sensitive to Session and a lower case session would not work with only grep -n

*Example 3 :*

![Image](https://user-images.githubusercontent.com/114611146/199065061-4f13da84-e396-4e18-bf4f-efdeb14cb365.png)

Here, grep -n with search term report presents all the lines which contain report in /technical as well as the line numbers they are found on within the directory


**Option 3 : the -i option**

the -i option ignores the case sensitive barriers such as Upper Case. Where previously, grep would not pull results if the search term had different upper case/lower
case from the search term in the directory, now with grep -i, it ignores upper case/lower case

*Example 1 :*

![Image](https://user-images.githubusercontent.com/114611146/199065069-cc32a791-6c94-495a-9e0b-aba32b82683c.png)

Here, grep -i with search term alcohol presents the results even though within /technical only Alcohol is used. It ignores the lower case vs upper case restraint

*Example 2 :*

![Image](https://user-images.githubusercontent.com/114611146/199065079-45dd23c7-154f-4d20-a91b-cf19974fe36c.png)

Here, grep -i with search term session presents the results even though within /technical only Session is used. It ignores the lower case vs upper case restraint

*Example 3 :*

![Image](https://user-images.githubusercontent.com/114611146/199065084-ed5f30b8-567e-43fa-af8b-a62ca3ca5835.png)

Here, grep -i with search term gen presents the results even though within /technical only Gen is used. It ignores the lower case vs upper case restraint


