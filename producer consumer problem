/* Producer Consumer Demo */
class Queue
{
int n;
boolean avail=false;
synchronized int get()
{
while(avail==false)
{
try
{
wait();
}
catch(InterruptedException e){ }
}
avail=false;
System.out.println("Got:"+n);
System.out.println("Notifying Producer");
notify();
return(n);
}
synchronized void put(int n)
{
while(avail==true)
{
try
{
wait();
}
catch(InterruptedException e){ }
}
this.n=n;
avail=true;
System.out.println("Put:"+n);
System.out.println("Notifying Consumer");
notify();
}
}
/* Producer class */
class Producer extends Thread
{
Queue q;
Producer(Queue q)
{
this.q=q;
}
public void run()
{
for(int i=0;i<5;i++)
q.put(i);
System.exit(0);
}
}
/* Consumer class */
class Consumer extends Thread
{
Queue q;
int value;
Consumer(Queue q)
{
this.q=q;
}
public void run()
{
while(true)
{
value=q.get();
}
}
}
/* Main class */
class ProducerConsumerDemo
{
public static void main(String args[])
{
Queue q=new Queue();;
Producer p=new Producer(q);
Consumer c=new Consumer(q);
p.start();
c.start();
}
}
