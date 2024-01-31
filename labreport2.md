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

## My files randomly stopped working last minute! I will visit tutor hours and get it fixed!


## Part 2
Showing with `ls`  
- The absolute path to the private key for your SSH key for logging into ieng6:
  <img width="738" alt="Screenshot 2024-01-30 at 11 35 51 PM" src="https://github.com/daxpatel5/cse15l-lab-reports/assets/83134389/9b73beef-3811-4177-8597-8d466ccfaa27">  
- The absolute path to the public key for your SSH key for logging into ieng6:
  <img width="741" alt="Screenshot 2024-01-30 at 11 18 58 PM" src="https://github.com/daxpatel5/cse15l-lab-reports/assets/83134389/61f46a59-2f45-4f77-ac75-02c782684743">  
- A terminal interaction where you log into your ieng6 account without being asked for a password    
<img width="701" alt="Screenshot 2024-01-30 at 11 52 01 PM" src="https://github.com/daxpatel5/cse15l-lab-reports/assets/83134389/92c7a953-b0e9-428a-ac1c-5412d59a673c">


## Part 3
Over the last 2 weeks I learned that it is indeed possible to run remote servers from teh comfort of my own bed! I used to think of servers as this continuous collection of black colored hot boxes with a thousand blinking lights on them; turns out, it can look like a CSE basement computer too!  

> Dax Patel
