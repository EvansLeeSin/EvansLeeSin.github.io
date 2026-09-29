---
title: JPA的注意事项
date: 2024-08-09 16:25:07
tags: Java
---

**JpaRepository**开发中最常用

使用方法是在自定义的接口中继承JpaRepository，并且传入泛型，注意泛型的入参含义：第一个参数为要操作的**实体类**，第二个参数为实体类的**主键类型**。

```Java
@Repository
public interface UserRepository extends JpaRepository<User, Integer> {//实体类为User，主键ID为整型
}
```

JpaRepository自带基础的CRUD方法，具体的方法体系如下

:smile:Repository
提供了findBy + 属性 方法
		:smile:CrudRepository
		继承了Repository 提供了对数据的增删改查
			:smile:PagingAndSortRepository:
			继承了CrudRepository 提供了对数据的分页和排序，缺点是只能对所有的数据进行分页或者排序，不能做条件判断
				:smile:JpaRepository： 继承了PagingAndSortRepository
				开发中经常使用的接口，主要继承了PagingAndSortRepository，对返回值类型做了适配
:smile:JpaSpecificationExecutor
提供多条件查询

JpaRepository也支持自定义的接口方法名查询，前提是依据规定的方法名命名规则来写，这样如果符合规则，就不用去写方法的实现。

这里不粘贴规则的表格了，网上都有

#### 特殊参数

可以直接在方法上加上分页或者排序的参数，如下

```java
Page<Spu> findByCategoryId(Long cid, Pageable pageable);

List<Spu> findByCategoryId(Long cid, Sort sort);
```

#### JPA的`@NameQueries`注解

这个注解用在实体类上，加上了以后，Spring会优先查找在Repository里面同名的自定义方法，如果找到了，就执行`@NameQueries`的具体内容，例如：

```java
@NamedQuery(name = "Spu.findByRootCategoryId",query = "select s from Spu s where s.rootCategoryId >= ?1")
```

```java
public List<Spu> findByRootCategoryId(Long rootCategoryId);//此时的这个方法会执行上面注解的JPQL语句，而不走jpa的语法
//还用一种@@NamedNativeQuery使用的是原生SQL
```

#### JPA的`@Query`

@Query用来标注在方法上，来指定本地查询，例如：

```java
@Query(value="select s from Spu s where s.title like %?1" )
public List<Spu> findByTitle(String title);
//有个nativeQuery参数，默认是false，表示value的是JPQL语法，true写的是原生SQL
@Query(value="select * from spu s where s.title like %?1",nativeQuery=true )
public List<Spu> findByTitle(String title);
```

#### JPA`@Param`

```java
@Query(value = "select s from Spu s where s.title in (:titles)")
List<Spu> findByTitle(@Param("titles") List<String> titles);//用来自定义命名参数的名字，供上面的@Query使用
```

