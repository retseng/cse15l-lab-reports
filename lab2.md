# Lab Report 2 - 04/16/24
## Part 1
### Code
```import java.io.IOException;
import java.net.URI;
import java.util.*;

class Handler implements URLHandler {
    // The one bit of state on the server: a number that will be manipulated by
    // various requests.
    int num = 0;
    ArrayList<String> array = new ArrayList<String>();

    public String handleRequest(URI url) {
        String[] parameters = url.getQuery().split("=");
        if (url.getQuery().contains("s=") && url.getQuery().contains("user=")) {
            String str = parameters[1];
            int end = str.indexOf("&");
            String message = str.substring(0, end);
            String text = parameters[2] + ":" + message;
            array.add(text);
            String fullText = "";
            for(int i = 0; i<array.size(); i++){
                fullText += array.get(i);
                fullText += "\n";
            }
            return fullText;
         } else{
            return "404 Not Found!";
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

        Server.start(port, new Handler());
    }
}
```
## Example Output
![Image](lab2_1.png)
![Image](lab2_2.png)
