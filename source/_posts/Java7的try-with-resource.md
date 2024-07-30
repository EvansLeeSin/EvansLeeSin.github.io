---
title: Java7的try-with-resource
date: 2024-07-22 15:57:00
tags: Java
---

try-with-resource(try-catch-finally)是Java7中全新引入的异常捕获机制，它能让开发人员不用显式的释放try-catch语句块中使用的资源。但有个前提条件就是这个资源**必须实现**`java.lang.AutoCloseable`接口，才可以被执行关闭。

## 源码分析结果

1. 实现`AutoCloseable`接口，其实是编译器显式的给代码添加了`finally`方法，省去开发人员手动关闭资源的操作。
2. `try`语句中越是最后使用的资源，越是最早被关闭

## 异常处理机制

- 只要实现了AutoCloseable接口的类，并且在try里声明了对象，那么无论是否发生异常，`close`操作都会被执行。
- `try`中的异常，我们一般就通过`e.getMessage()`就能获取到，对于`close()`方法抛出的异常，使用`e.getSuppressed()`方法会返回一个被叫做*包含所有被抑制以传递此异常的异常的数组*。

## 注意点

注意`try-with-resource`中只有声明了的资源才会被调用`close()`方法,而Java BIO中有大量的装饰器模式。

```Java
//当调用装饰器的close方法时，本质上是调用了装饰器包装的流对象的close方法
GZIPOutputStream out = new GZIPOutputStream(new FileOutputStream(new File("out.txt")));
```

需要单独声明各种底层资源对象才可以保证所有的资源被正确的close()被调用

```Java
//编译器会自动生成fout.close()的代码，这样就能保证所有流正常关闭。
FileOutputStream fout = new FileOutputStream(new File("out.txt"));
GZIPOutputStream out = new GZIPOutputStream(fout);
```

