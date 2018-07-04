---
title: Java Multithread 01 -- Thread/Runnable
tags: [java, multithread]
categories: []
date: 2018-07-04 11:07:01
---


Two ways to do multithread in java: 
1. Thread 
2. Runnable

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




