title: "Java8 PartII"
date: 2015-05-15 13:41:28
tags:
- Java
- Java8
- new Features

---

## Default Methods
This feature is wired when I first time hear it. Because I always thought that for a interface, method inside it should be leaving blank and just provide signatures.

However, Java 8 bring in  a new keyword `default` in interface, when you want a default implement for a interface method. for example.

```java
interface Printer{
	default void print(){
		System.out.print("I am a printer");
	}
}
```

Wow, you implement a method in a interface, so what is the difference between interface and class. It seems very unreasonable to add this feature to interface, because it confuse the boundary between class(abstract) and interface.

However, it is useful for legency libraries. Especially if you want to add some new method to a exsiting class. For example, **Collections and Set** in Java 8 have a new method called **foreach**. As the Java document says, The old way we do it is to rewrite the interface, and rewirte each class, that may cause problem. So they add default implementation in the interface so the subclass will automatic have the method. (but why not rewrite abstract class and interface? )

Now, What about two interface have the same default method. e.g.

```Java
interface Printer1{
	default void print(){
		System.out.print("I am a printer");
	}
}
interface Printer2{
	default void print(){
		System.out.print("I am a printer");
	}
}

```
Two ways to solve.

1. implement it in your child class.
2. explicitly call with `super`, `Printer1.super.print()`.

Another interesting fact is that interface now can have static method as the helper method for default method.~~~!!!!!!!!!