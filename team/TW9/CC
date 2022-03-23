import java.net.*;
import java.io.*;

public class ContentsClient {
    public static void main(String args[]) throws Exception {
        Socket sock = new Socket("127.0.0.1", 4000);

        // reading the file name from keyboard. uses input stream
        System.out.print("Enter the file name");
        BufferedReader keyRead = new BufferedReader(new InputStreamReader(System.in));
        String fname = keyRead.readLine();

        // sending the file name to server . uses PrintWriter
        OutputStream ostream = sock.getOutputStream();
        PrintWriter pwrite = new PrintWriter(ostream, true);
        pwrite.println(fname);
        // receiving the contents from server. uses input Stream
        InputStream istream = sock.getInputStream();
        BufferedReader socketRead = new BufferedReader(new InputStreamReader(istream));

        String str;
        while ((str = socketRead.readLine()) != null) {
            System.out.println(str);
        }
        System.out.println("Client Connection Closed");
        pwrite.close();
        socketRead.close();
        keyRead.close();
    }
}
