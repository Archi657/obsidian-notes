### OOP
Oriented Object Programming

#### Encapsulation
Private methods, and add get and set methods.
#### Inheritance
Reuse code in child (extends) if type is diff (implements)
#### Polymorphism
Overload - overwritting
#### Abstraction


**Method overloading vs Method overriding**

Overloading = Different args/quantity `func(int x), func(int x, int y)`
cannot change return type (void funct/int funct).

Overriding = extend a class and override a method.

**Stack - Heap memory**

Stack -> dedicated for the program (variables-parameters) 
Heap -> dynamic memory, new Objs

**Shallow copy - deep copy**

Shallow = Object object2 = object1 point to the same object
Deep = Object object2 = new Object()

**Garbage Collector**
Ensure that resources are used efficency 

**Abstract class**
Class that we want to be extended Enemy -> Ghost
`public abstract class Enemy` -> cannot create enemy object while only can use `public class Ghost extends Enemy`

**Super keyword**
From the Ghost class, super.method() will call the method from Enemy class.
Mostly used for contructores so that we call parameters.

**Generics**
Accepts any kind of value type. `Test<T>`
`List<Integer> list = new ArrayList<>();` 
**Keywords**
Final = never gonna change, overrided or extended.
Protected = Inside same package can be modified

**equals() vs = =**
references comparison = is more about the adress, so if two objects point to the same memory location, and equals() about the content/value.

**Singleton Class**
Can instanciated only once `private static Singleton sing = new Singleton`
then a method `public static Singleton getSingleton()` and create the object as `Singleton sing = Singleton.getSingleton();`

**Composition**
Object inside an object
```Java
public class Person {
	private Job job;
	
	Person(){
		this.job = new Job();
		Sout(job.salary)
	}
}
```

**Static block**
Excecute before main method runs
```Java
public class Main{
	static{
		sout("run first")
	}
	
}

```