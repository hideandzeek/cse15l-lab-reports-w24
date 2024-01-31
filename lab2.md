# lab report 2

Zeke Wang

## part 1

code: 
```
import java.io.IOException;
import java.net.URI;

class ChatHandler implements URLHandler {
    String chatLog = "";

    public String handleRequest(URI url) {
        if (url.getPath().equals("/")) {
            return chatLog;
        } else {
            if (url.getPath().contains("/add-message")) {
                String[] parameters = url.getQuery().split("&");
                String user = "";
                String message = "";
                for (String parameter : parameters) {
                    String[] keyValue = parameter.split("=");
                    if (keyValue[0].equals("s")) {
                        message = keyValue[1];
                    } else if (keyValue[0].equals("user")) {
                        user = keyValue[1];
                    }
                }
                if (!user.isEmpty() && !message.isEmpty()) {
                    chatLog += user + ": " + message + "\n";
                }
                return chatLog;
            } else {
                return "404 Not Found!";
            }
        }
    }
}

class ChatServer {
    public static void main(String[] args) throws IOException {
        if(args.length == 0){
            System.out.println("Missing port number! Try any number between 1024 to 49151");
            return;
        }

        int port = Integer.parseInt(args[0]);

        Server.start(port, new ChatHandler());
    }
}
```
screenshots: 
![Image](p1s1.png)
In this screenshot, after I typed in the URL, the first methods called were `handleRequest()` in the `ChatHandler` class which is followed by other methods in the class like `split()`, `replace()`, and `isEmpty()`. The chatlog is initially empty, but after the URL the message parameter `s` changes from empty to `i had a farm` and the `user` changes to `old macdonald`. Finally, the `+` characters from the spaces are replaced with spaces. 

![Image](p1s2.png)
This second screenshot shows the same thing. The same `handleRequest()` method and then `split()`, `replace()`, and `isEmpty()` are called. This time, the parameters are changed to different values; `s` becomes `ee i ee i`, and `user` becomes `kid1`. The same happens later with `s` to `oo` and user to `kid2`. Finally the `+` is changed to spaces. 

## part 2

