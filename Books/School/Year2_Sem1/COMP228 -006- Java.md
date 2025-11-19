---
lastSync: Mon Nov 17 2025 11:32:23 GMT-0500 (Eastern Standard Time)
---
# Java 
2 MCQ (midterm and final, 5% each for a total of 10%. Closed book)
## Week 1: Intro to Java

Class names are always uppercase
Remember to write comment (author name, date, and short description of program/code)

per project: needs 1 main method (driver class)

Git link of zip file (prof preference)

Properties ->       ->Import External JARs

Remember DO NOT create a README file in new repo (messes up since readme has an initial commit)

printf = formatted output
System.out.printf( "Sum is %d%n", sum );  
– Format specifier %d is a placeholder for an int value  
– The letter d stands for “decimal integer.”


//Demo of JOption pane used in labs 

import javax.swing.JOptionPane;  
public class Addition  
{ public static void main(String [] args)  
{  
int num1, num2, result;  
num1 = Integer.parseInt(JOptionPane.showInputDialog(null, "Enter an integer: "));  
num2 = Integer.parseInt(JOptionPane.showInputDialog(null, "Enter another integer :  
"));  
result = num1 + num2;  
JOptionPane.showMessageDialog(null, "The result is " + result + "." ) ;  
}  
}

showInputDialog (input window)
showMessageDialog (message window)

## Week 2: 
New Class

_variable names_ start with a _lowercase_ character
_classes_ start with an _uppercase_ character
**packages** use only _lowercase_ characters
_methods_ start with a _lowercase_ character

**Object**
An instance of a class


A **class** in Java is a collection of instance variables, which describe the properties of class objects, and methods, which describe the behaviors.

## Week 3:

Lab 2 Demo
Static methods: Does not require an instance of a class

Java **random** class (import java.util.Random;)
System.out.println(randomGenerator.nextInt(10) + 1);  (range of 1-10 using random generator)


**Secure random**: (import java.security.SecureRandom;)
SecureRandom generates more non predictable random numbers as it implements Cryptographically Secure  
Pseudo-Random Number Generator (CSPRNG) as compared to Random class which uses  
Linear Congruential Generator (LCG).

Program Modules: Modularity adds a higher level of aggregation above packages. The key new language element is the **module**—a uniquely named, reusable group of related packages, as well as resources

Method calls: calling a method in a class
MyClass myObject = new MyClass(); 
myObject.instanceMethod();

**argument promotion**—converting an argument’s value, if possible, to the type that the method expects to receive in its corresponding **parameter.**

## Week 4: 

**Static classes:**
Every object has its own copy of all the instance variables of the class. In certain cases, only one copy of a particular variable should be shared by all objects of a class.

A static field—called a class variable—is used in such cases. A static variable represents classwide information—all objects of the class share the same piece of data. The declaration of a static variable begins with the keyword static.


**Final**
You can declare some or all of a class's methods final. You use the final keyword in a method declaration to indicate that the method cannot be overridden by subclasses.

**Enum**
An **enum type** is a special data type that enables for a variable to be a set of predefined constants. The variable must be equal to one of the values that have been predefined for it. Common examples include compass directions (values of NORTH, SOUTH, EAST, and WEST) and the days of the week.

Because they are constants, the names of an enum type's fields are in uppercase letters.
 public enum Day {SUNDAY, MONDAY, TUESDAY, WEDNESDAY,THURSDAY, FRIDAY, SATURDAY } 

## Week 5 

**Abstract class:** A class which is declared as abstract is known as an *abstract class*. It can have abstract and non-abstract methods. It needs to be extended and its method implemented (not implemented by default). It cannot be instantiated. 

**Interface:** Class-like construct. It is a blueprint of a class. It has static constants and abstract methods. 


### Class 2/Lab (October 2)
**JavaFX**

AWT (abstract windows toolkit) java.awt -> JavaX.Swing -> JavaFX


JavaFX pane class is a layout container which can contain other JavaFX components internally and lay them out.


## Week 6 

### Class 1 (Online)




Week 7: JavaFX

D:\Programs\openjfx-21.0.8_windows-x64_bin-sdk\javafx-sdk-21.0.8\lib
## Week 8: JavaFX GUIs (Nov 3?)

Event Handling





## Week 9/10: Exception Handling (Nov. 10)

try, catch, finally










Integration of Java with databases



## Week 10: Collections/ Arrays  
*Write Java Applications - Database Records?*

generate Arrays: are typesafe

non generate: can push any type

ArrayList (FIFO)
ArrayList cars = new ArrayList();
cars.add(321)
cars.add("bmw")
[321, bmw]


enhanced for loop 
for (String i : cars)

**Queue** 



**Stack**

Stack Integer> stack = new Stack  Integer>> ();


**LinkedList**
	





Week 11: Multithreading


Week 12: Java Collections Framework


Week 13: Collection Classes

Week 14: 

