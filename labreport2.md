# Lab Report 2
> Last Edited: 30 January, 2024  
> Dax Patel

## Part 1  
Code for ChatServer:  
```
import java.io.IOException;
import java.net.URI;
import java.util.ArrayList;

class ChatServer implements URLHandler {

  ArrayList<String> lines = new ArrayList<>();

  public String handleRequest(URI url) throws IOException {

    if(url.getPath().equals("/add-message")) {

      String query = url.getQuery();
      String[] split = query.split("&");
      String message = split[0];
      String user = split[1];

      if(message.startsWith("s=") && user.startsWith("user=")){

        message = message.substring(2);
        user = user.substring(5);
        lines.add(user+": "+message);
        return History();
      }
    }
    else{
        return "Invalid input! Try again!";
      }
    return null;
  }

  public String History(){
    String messageList="";

    for(String msg: lines)
      messageList+=msg+"\n";

    return messageList;
  }
  
}

```
Example 1 of `/add-message`  
> Screenshot goes here  
Methods called:
Arguments/Values of variables
Change of values and why

Example 2 of `/add-message`  
> Screenshot goes here  
Methods called:
Arguments/Values of variables
Change of values and why


## Part 2
Showing with `ls`  
- The absolute path to the private key for your SSH key for logging into ieng6:  
> Screenshot goes here
- The absolute path to the public key for your SSH key for logging into ieng6:  
> Screenshot goes here
- A terminal interaction where you log into your ieng6 account without being asked for a password    
> Screenshot goes here


## Part 3
Over the last 2 weeks I learned that it is indeed possible to run remote servers from teh comfort of my own bed! I used to think of servers as this continuous collection of black colored hot boxes with a thousand blinking lights on them; turns out, it can look like a CSE basement computer too!  

> Dax Patel
