---
title: Java Multithread 01 -- Thread/Runnable
tags: [java, multithread]
categories: []
date: 2018-07-04 11:07:01
---


Two ways to do multithread in java: 
1. Thread 
2. Runnable

<!--more-->

### Thread

class thread
```java
public class Calc extends Thread {
    
}
````

class main
```java
public class Main {
  Calc c1 = new Calc();
  Calc c2 = new Calc();
  
  c1.start();
  c2.start();
}
```

program above can run, but did nothing.
to do something, class Calc should override run method
```java
public class Calc extends Thread {
    @Override
    public void run() {
        System.out.println("Calculating");
    }
}
```

### Runnable
class implements Runnable
```java
public class Hiker implements Runnable {

    @Override
    public void run() {
        System.out.println("Hiking");
    }
}
```

instance as parameter of a new thread
```java
public class Main {

    public static void main(String[] args) {

        Thread t3 = new Thread(new Hiker());
        Thread t4 = new Thread(new Hiker());

        t3.start();
        t4.start();

    }
}
```

### Compare thread and runnable
1. runnale no need inherit, so it has chance to  inherit other class 
2. same runnable can be a running in many threads
```java
public class Main {

    public static void main(String[] args) {

        Hiker hiker = new Hiker();
        Thread t3 = new Thread(hiker);
        Thread t4 = new Thread(hiker);

        t3.start();
        t4.start();

    }
}
```

### Thread status
1. New
2. Runnable
3. Running
4. Blocking 
5. Dead

reasons blocked:
 1. sleep()
 2. wait()
 3. join()
 4. access I/O
 5. access a synchronized resource 
    1. instance method
    2. class method
    3. code block



