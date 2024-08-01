---
title: Fail-Fast机制
date: 2024-08-01 16:12:32
tags: Java
---

Fail-Fast是一种理念，它是在进行系统设计时优先考虑异常情况，一旦发生异常，直接停止并上报。

例如：

```java
public int divide(int divisor, int dividend){
    if (dividend == 0) {
        throw new RuntimeException("被除数不能为0");    //这里就是fail-fast的体现
    }
    return divisor / dividend;
}
```

### 集合类中的Fail-Fast

Java中的Fail-Fast一般指的是Java框架中的集合的错误检测机制，为的是预防当多个线程对集合进行结构性改变时，可能会触发Fail-Fast机制，这时会抛出`ConcurrentModificationException`异常。然而单线程场景也会发生这种异常，这里直接说明分析结果：

当使用foreach遍历集合时对集合元素进行**add / remove**时，就会抛出`ConcurrentModificationException`

我们知道foreach底层其实就是iterator和while循环实现的，报错是调用iterator的next方法，该方法调用了`checkForComodification()`方法：

```java
final void checkForComodification() {
    if (modCount != expectedModCount)
        throw new ConcurrentModificationException();
}
```

很明显报错是比较上面两个变量不一致导致的，我们看下这两个变量到底表示啥：

- modCount：ArrayList中的一个成员变量，它表示集合实际被修改的此时，当ArrayList创建时就存在，初始值0。
- expectedModCount：是iterator的一个成员变量，iterator是ArrayList的内部类，只有当ArrayList调用iterator()方法时才会被创建，且**expectedModCount的初始值就是modCount的值**，只有该迭代器修改了集合，expectedModCount才会修改。

#### 结论

remove/add操作隶属于ArrayList的方法，调用它们只会触发修改modCount，而不会修改expectedModCount，而在iterator中遍历，需要调用iterator的remove/add方法删除/添加元素。

我们来看下iterator的remove方法

<img src="https://i-blog.csdnimg.cn/blog_migrate/b94c4a7dee993c7ab560bb7879246bad.png" alt="img" style="zoom:33%;" />

最后的赋值语句想必都能理解了吧

参考:[fail-fast 机制是什么？(详解)_fail fast-CSDN博客](https://blog.csdn.net/OYMNCHR/article/details/124515536)
