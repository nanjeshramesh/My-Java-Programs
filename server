import java.io.*;
import java.net.*;
class Multiserve implements Runnable
{
static ServerSocket ss;
static Socket s;
public void run()
{
String name=Thread.currentThread().getName();
for(;;)
{
try
{
System.out.println("Thread "+name+" ready to accept...");
s=ss.accept();
System.out.println("Thread "+name+" accepted a connection");
PrintStream ps= new PrintStream(s.getOutputStream());
ps.println("Thread "+name+"contacted ypu");
ps.close();
s.close();
}
catch(Exception e) {}
}
}
public static void main(String args[ ]) throws Exception 
{
Multiserve ms=new Multiserve();
ss=new ServerSocket(999);
Thread t1=new Thread(ms,"one");
Thread t2=new Thread(ms,"two");
t1.start();
t2.start();
}
}
