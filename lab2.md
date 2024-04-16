# Part 1
'''import java.io.IOException;
import java.net.URI;

class Handler implements URLHandler {
    // The one bit of state on the server: a number that will be manipulated by
    // various requests.
    int num = 0;

    public String handleRequest(URI url) {
        String[] parameters = url.getQuery().split("=");
        if (url.getQuery().contains("s=") && url.getQuery().contains("user=")) {
            String str = parameters[1];
            int end = str.indexOf("&");
            String message = str.substring(0, end);
            return String.format("%s:%s", parameters[2], message);
         }
         else{
            return "404 Not Found!";
         }
    }
}
'''
'''class ChatServer {
    public static void main(String[] args) throws IOException {
        if(args.length == 0){
            System.out.println("Missing port number! Try any number between 1024 to 49151");
            return;
        }

        int port = Integer.parseInt(args[0]);

        Server.start(port, new Handler());
    }
}
'''
