****************************multiple threading 

there are two ways of creating the thread = 
1. extends class as a  Thread
2. making interface which is runnable. 

A. extends class as a  Thread=>

step 1) extends class with Thread.
step 2) rewrite the run method .
step 3) in the main thread class create objects of thread class and start the thread with the start method 


example =


class Hi extends Thread{
    public void run(){
        for(int i =0 ;i<5;i++){
            System.out.println("hi");
        }
    }
}

class Hello extends Thread{
    public void run(){
        for(int i =0 ;i<5;i++){
            System.out.println("hello");
        }
    }
}



 class Mainclasss {
    public static void main(String[] args) {
        Hi obj1=new Hi();
        Hello obj2 = new Hello();
        obj1.start();
        obj2.start();
        
    }
}



B. making inteface which is runnable 

step 1) implement a class as a runnable 
step 2) first create object of a class 
step 3) create thread objects and pass step 1 objects as a runable states
step 4) THEN starts a thread.


exmaple=

class Hi implements Runnable{
    public void run(){
        for(int i =0 ;i<5;i++){
            System.out.println("hi");
        }
    }
}

class Hello implements Runnable{
    public void run(){
        for(int i =0 ;i<5;i++){
            System.out.println("hello");
        }
    }
}


class HelloWorld {
    public static void main(String[] args) {
        Runnable obj1=new Hi();
        Runnable obj2 = new Hello();
        Thread t1=new Thread(obj1);
        Thread t2=new Thread(obj2);
        t1.start();
        t2.start();
        
    }
}


