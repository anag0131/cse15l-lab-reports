# Lab Report 2
**Part 1: Simple Search Engine**
---
Code block:
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


![Image]("https://user-images.githubusercontent.com/114611146/195947890-ead1d07b-1262-413d-925d-9dba613939dd.png")


This is an example of what the webpage looks like after adding /increment to the path. A new empty string is added 



![Image]("https://user-images.githubusercontent.com/114611146/195948088-443b7bb4-9731-43b9-bf2b-ceae2e0a3b3b.png")

This is what the webpage looked like after adding the string blue, it is added to the list by adding /add/?s=blue to the path


![Image]("https://user-images.githubusercontent.com/114611146/195948113-db279885-fb21-4234-84ef-dff524bf888f.png")

This is what the webpage looked like after adding more strings using the same method above of adding to the path

