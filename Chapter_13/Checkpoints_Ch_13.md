# Checkpoint Answers Chapter 13 #
## 13.1 ##
**(a)**
```Java    
class A {
	abstract void unfinished() {
	}
}
```  
Not legal code because an abstract method have a body. Another problem is that A is not abstract but it contains an abstract method.  

**(b)**  
```Java
public class abstract A {
	abstract void unfinished();
}
```
Not legal because the first use of the abstract keyword is misplaced, shall be placed before the keyword class.   

**(c)**  
```Java
class A {
	abstract void unfinished();
}
```
Not legal, the class must be abstract if the method shall be abstract.  

**(d)**  
```Java
abstract class A {
	protected void unfinished();
}
```
Not legal since there is no body for the non abstract method.  

**(e)**  
```Java  
abstract class A {
	abstract void unfinished();
}
```  
Legal code.
  
**(f)**  
```Java  
abstract class A {
	abstract int unfinished();
}
```   
Legal code.

## 13.2 ##
Abstract classes prevents a developer from instantiating the base class, because a developer has marked it as having missing functionality.  

It also provides compile-time safety so that you can ensure that any classes that extend your abstract class provide the bare minimum functionality to work, and you don't need to worry about putting stub methods that inheritors somehow have to magically know that they have to override a method in order to make it work.  

Read more at: [StackExchange - Why should I declare a class as an abstract class?](http://programmers.stackexchange.com/questions/96947/why-should-i-declare-a-class-as-an-abstract-class)  

## 13.3 ##
**(a)**  
An abstract class can be used just like a non-abstract class except that you cannot use the new operator to create an instance from the abstract class.  

**(b)**  
An abstract class can be extended.  

**(c)**  
A subclass of a non-abstract superclass can be abstract.  

**(d)**  
A subclass can override a concrete method in a superclass to define it as abstract.  

**(e)**  
An abstract method cannot be static.  

## 13.4 ##
There will be an attempt, at runtime, to create a Double object out of an Number object. But this will not work because the Number object is in based on an Integer object.  

## 13.5 ##
The code from this checkpoint will fail at runtime because a Double object is attempted to be stored where an Integer object is supposed to be stored.  

## 13.6 ##
```Java  
public class Test {
	public static void main(String[] args) {
 		Number x = 3;
 		System.out.println(x.intValue());
		System.out.println(x.doubleValue());
 	}
}
```  
The above code will output:  
```  
3  
3.0  
``` 
 
## 13.7 ##
The problem with the code in this checkpoint is that x is of type Number and the method compareTo(Integer) is undefined for the type Number.  

## 13.8 ##
This checkpoint is about the same code that was discussed in checkpoint 13.7. The problem with the code is now tried to be fixed with a cast. There is however a mistake made when introducing the cast. A corrected working version can be seen below.  
```Java  
public class Test {
	public static void main(String[] args) {
		Number x = new Integer(3);
		System.out.println(x.intValue());
		System.out.println(((Integer) x).compareTo(new Integer(4)));
	}
}
```  
## 13.9 ##
It is not possible to create an Calendar object using the Calendar class. This is so because Calendar is an abstract class.  

## 13.10 ##
The add method in the Calendar class is abstract.  

## 13.11 ##
A calendar set to the current time can be created in the following way.  
```Java  
Calendar calendar = new GregorianCalendar();  
```  

## 13.12 ##
```Java  
// c is a Calendar instance  
c.get(Calendar.YEAR)	// get the year  
c.get(Calendar.MONTH)	// get the month  
c.get(Calendar.DATE)	// get the date  
c.get(Calendar.HOUR)	// get the hour  
c.get(Calendar.MINUTE)	// get the minute  
c.get(Calendar.SECOND)	// get the second  
```  

## 13.13 ##
Suppose A is an interface. It it then **not** possible to create an instance using new A().  