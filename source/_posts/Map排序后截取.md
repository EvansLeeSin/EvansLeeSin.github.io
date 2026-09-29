---
title: Map排序后截取
date: 2024-09-04 12:00:00
tags: Java
---

```java
public static <K extends Comparable, V extends Comparable> Map<K, V> sortMapByValues(Map<K, V> aMap,long limitSize) {
    HashMap<K, V> finalOut = new LinkedHashMap<>();
    aMap.entrySet()
            .stream()
            // 排序
            .sorted((p1, p2) -> p2.getValue().compareTo(p1.getValue()))
            // 截取前limitSize个
            .limit(limitSize)
            .collect(Collectors.toList()).forEach(ele -> finalOut.put(ele.getKey(), ele.getValue()));
    return finalOut;
}
```
