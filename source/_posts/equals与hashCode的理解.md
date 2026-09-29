---
title: equals与hashCode的理解
date: 2024-07-15 17:03:43
tags: Java
---

在Java中，通常重写equals方法时，通常也需要重写hashCode方法，这是因为两者在Java容器类如HashMap、HashSet都会依赖于hashCode的实现，下面说明为什么会有这样的依赖

Java程序设计中的一个重要原则是:

**"如果两个对象是相等的，那么他们的equals方法应该要返回true，且它们的hashCode需要返回相同结果"**

但因为是重写的equals和hashCode，决定权交给了程序员自己，所以我们没法保证上面的原则一定是严格遵守的。

首先看hashCode：假如两个对象的hashCode值相同，那么它们会在散列表中产生哈希冲突，依据hashCode特性，我们没法保证两个对象相同或不同，所以在容器里我该怎么存储它呢

再看equals：在上面不清楚对象是否相同的基础上，我们重写equals来判断两个对象是否相同。

可结合HashMap的put源码实现来解释equals和hashCode的依赖关系：

put时，若插入位置为空直接插入，否则，判断新加元素是否与当前元素相同，**首先判断hash值**，不同直接跳过；hash值相同再调用equals方法。

