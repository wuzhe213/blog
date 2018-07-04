---
title: JMM -- Java Memory Model
categories: []
tags: [Java, JMM]
date: 2018-07-03 15:10:36
---

### Memory areas in a Java program
* shared area to all thread
  * method area
  * heap
* every thread owned area
  * vm stack
  * native method stack
  * PC - program counter register
  

### JMM -- Java Memory Model
* Main memory: <br>
shared by all thread

* working memory:  <br>
owned by individual thread

#### JMM rules
1. a method's primitive type values stored in working memory
2. a method's reference type values stored in main memory, but the reference stored in working memory

  
  
