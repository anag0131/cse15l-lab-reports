# Lab Report 2
**Part 1: Simple Search Engine**






---
```
#code block
class Handler implements URLHandler {
    // The one bit of state on the server: a number that will be manipulated by
    // various requests.
    String num = "empty";

    public String handleRequest(URI url) {
        if (url.getPath().equals("/")) {
            return String.format("Number: %d", num);
        } else if (url.getPath().equals("/increment")) {
            num = "empty";
            return String.format("String incremented! it is now" + num);
        } else {
            System.out.println("Path: " + url.getPath());
            if (url.getPath().contains("/add")) {
                String[] parameters = url.getQuery().split("=");
                if (parameters[0].contains("s")) {
                    num += " ";
                    num +=  ", " +  parameters[1];
                    return String.format(" " + num);
                }
            }
            
        }
        return "404";
        
    }
}

class SearchEngine {
    public static void main(String[] args) throws IOException {
        if(args.length == 0){
            System.out.println("Missing port number! Try any number between 1024 to 49151");
            return;
        }

        int port = Integer.parseInt(args[0]);

        Server.start(port, new Handler());
    }
}



```
In this code block, I modified handleRequest to increment an empty string if the path contains "/increment". Otherwise, to add a new string, if the path contains/add, then if it contains s = (newstring), it will
split the url into a new substring containing only whatever is after the equals sign. This is the new string to be added. It adds this new string to the existing list.


***Screenshots***


![Image](https://user-images.githubusercontent.com/114611146/195947890-ead1d07b-1262-413d-925d-9dba613939dd.png)


This is an example of what the webpage looks like after adding /increment to the path. A new empty string is added 

Methods called : handleRequest

What it does : 
checks if the path = /increment. if it does, adds an empty string and returns it

---



![Image](https://user-images.githubusercontent.com/114611146/195946354-8b80603b-3dfb-4447-ac12-27eaa76a8b68.png)

This is what the webpage looked like after adding the string blue, it is added to the list by adding /add/?s=blue to the path

Methods called : handleRequest

What it does : checks if the path contains /add. If it does, uses getQuery and split to split the URL path to only focus on the string after add. Then, that string is split into one string containing whatever is before the equals sign, and one containing what is after the equals sign. In this case, the string after the equals sign is added to the original string and the new list is returned  

---

![Image](https://user-images.githubusercontent.com/114611146/195948113-db279885-fb21-4234-84ef-dff524bf888f.png)

This is what the webpage looked like after adding more strings using the same method above of adding to the path

---

![Image](https://user-images.githubusercontent.com/114611146/195946335-24a23131-a22c-4e90-ad5d-c9cbcdb127bd.png)

If the path contains no icrement or /add, and something new is added to the path it returns a 404 error

---

# **Part 2 : Failure Inducing Inputs**

---
For ArrayLists.java 

Tests that fail: 

![Image](https://user-images.githubusercontent.com/114611146/195951610-7c988c62-3e94-435e-9eaa-bc730baf608d.png)

For testReverseInPlace2():

* Input = {3,2,1,0}
* Output = {0,1,1,3}
* Why it fails : The test for reverseInPlace fails because the method reverseInPlace reverses the values by changing arr[i] each time which loses the original value so that original value cannot be switched anymore.
* To fix this bug : make a temp variable or temp array that holds the original values before they are reversed


For testReversed()

* Input = {2,3,10,12}
* Output = {0,0,0,0}
* Bug = each element of the original array is set to the new array and then returned. Because the new array has default values of 0, the original array values are all turned to 0 and then returned. 
* To fix this bug : replace arr[i] = newArray[arr.length - i - 1] with newArr[i] = arr[arr.length-i-1] which essentially changes each element of the new array to be the reversed order elements of the original array. Then, instead of returning the original array, return the new array. 
