title: "Java8 part1"
date: 2015-05-13 22:00:01
tags:
- Java
- features
- intro

---

Java 8 is really exciting by adding so many features to it.

1. lamada expression
2. method reference
3. functional interface
4. new Date/Time Api 
5. others(Nashom Javasciprt, Base64)


## lamada expression

lamada express are use to implement some inferface (funciontal interface) which used in annoymouse inner class way.

for example:

```java
List<Integer> list = (List<integer>)Arrays.asList(1,2,3);
Collections.sort(list, (a,b) -> a > b );
```
- braces can be ignore
- `return` can be ignore
- type parameter can be ignore, compiler will infers it.

## method reference

A pointer refence to a method, following method can be refer:
1. static method
2. instance method
3. constructor (by using `new` method)

example:

```java
ArrayList::new;
System.out::println;
```

There are two types in **java.util.function**.
> *Supplier*: accepts no arguments and produce a result of some arbitrary type.
> *Consumer*: take one argument and no output.
