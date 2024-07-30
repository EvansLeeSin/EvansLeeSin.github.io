---
title: a=a+b与a+=b的区别
date: 2024-07-15 15:26:53
tags: Java
---
首先了解下运算符的使用

**整数相加**：

- 当两个操作数都是整数类型时（如 `byte`、`short`、`int`、`long`），`+` 运算符会执行整数加法。
- 如果操作数是 `byte` 或 `short` 类型，Java 会先将它们提升（widening）到 `int` 类型，然后执行加法操作，结果是 `int` 类型。
- 如果其中一个操作数是 `long` 类型，结果将是 `long` 类型。

**浮点数相加**：

- 如果操作数中有一个是 `float` 类型，结果是 `float` 类型。
- 如果操作数中有一个是 `double` 类型，结果是 `double` 类型。

**字符串连接**：

- 如果其中一个操作数是字符串（`String`）类型，`+` 运算符会进行字符串连接，结果是一个新的字符串。

```java
byte a = 127;
byte b = 127;
b = a + b; // error : cannot convert from int to byte
b += a; // ok
```

所以byte类型相加会提升为int，再次赋值b会报错

+= 隐式的将加操作的结果类型**强制转换为持有结果的类型**。如果两个整型相加，如 byte、short 或者 int，首先会将它们提升到 int 类型，然后在执行加法操作，**然后结果会被强制转换为byte**。

