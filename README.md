Object Oriented Programming in Java
===

- Object Oriented Programming is one of the programming paradigm, which provides a set of functionalities and principles to follow while developing an application in a maintainable and scalable way, which provides a lot of advantages like code reusability, flexibility and lot more.

- well these are not specific to an particular programming language can be used in all programming languages that supports OOPS concepts like python, java, cpp and more.

## Core concepts of OOP
1. Class
2. Object
3. Inheritance
4. Abstraction
5. Encapsulation
6. Polymorphism



## 1. Class and Object  

In simple terms a class is blueprint of an object which includes set of properties and Object is an instance of a class which can created by from class.

Example: Consider a candle mould which is a blueprint of candle as a class which can create many candles and those candles are objects. Look at below code snippet for code implementation of above example.
```java
class CandleMould {   // class
    void makeCandle(int n) {
        System.out.println("Making candle" + " " + n);
    }
}

public class Main {
    public static void main(String[] args) {
        CandleMould mould_1 = new CandleMould(); // object 1 of class CandleMould
        CandleMould mould_2 = new CandleMould(); // object 2 of class CandleMould
        mould_1.makeCandle(1);
        mould_2.makeCandle(2);
    }
}

```

## 2. Inheritance

Inheriting or acquiring properties from the parent class by a child class is know as **Inheritance**
- There are mainly 5 types:
1. Single Inheritance
2. Multilevel Inheritance
3. Multiple Inheritance
4. Hierarchical Inheritance
5. Hybrid Inheritance

**Example:** As child of your father you have authority to get the share in property or assets of your family, that mean a child class can access the methods and properties of parent class.
``` java
//Single Inheritance
class Parent {
    String familyName = "xyz";
    int wealth = 200000;
}
class Child extends Parent {

}
public class Main {
    public static void main(String[] args) {
        Child obj = new Child();
        String familyName = obj.familyName;
        int wealth = obj.wealth;
        System.out.println(familyName+" "+ wealth);
    }
}
```
In the above snippet child class doesn't contain any data but it is accessing from parent class with inheritance.

Remaining types are various levels of parent and child classes in inheritance

## 3. Abstraction

Hiding the complex implementations and showing only the functionality to user is know as **Abstraction**  

**Example:** Consider about TV remote we don't know how its built and how complex it is in implementation but it is easy and simple to use by the user by hiding the implementation.

```java
// abstraction of buttons
abstract class TVRemote{
    abstract void turnOnTV();
    abstract void turnOffTv();
}
//implementation
class Buttons extends TVRemote {
    void turnOnTV() {
        System.out.println("Turning on TV");
    }
    void turnOffTv() {
        System.out.println("Turning off TV");
    }
}
public class Main {
    public static void main(String[] args) {
        Buttons remote = new Buttons();
        remote.turnOnTV();
        remote.turnOffTv();
    }
}
```

## 4. Encapsulation
Group the data and methods in a particular class and not allowing other classes to access the data directly but only possible by methods of the class. we have to define setter and getter to methods to initialize data and to get the data.

**Example:** whenever we are on conversation we don't directly speak about our details unless the opposite person asks about specific data like our name,age and etc..
```java
class Person {

    private String name; // data-> name

    public void setName(String myName){ // method to initialize or to change the value
        name = myName;
    }
    public String getName(){ // method to get the name
        return name;
    }
}
class Main {
    public static void main(String[] args) {
        Person obj = new Person();
        obj.setName("John Wick"); // setting the value by methods of person class
        String name = obj.getName(); //getting th value of person name
        System.out.println("My name is "+name);
    }
}
```

## 5. Polymorphism

**Poly** means many and **Morph** means shape, having ability to change the execution of the programme according the different functionalities is know as **Polymorphism**
- There are mainly two types  
    **1. Compile time polymorphism** - the state of execution will be declared at complie time which is static in nature   

    a. Method overloading - can be defined as methods with same name but different parameters
    ``` java
    class Calculator {
        int add (int a, int b){ // method with two parameters but same name
            return a+b;
        }
        int add (int a, int b, int c){ //method with three parameters but same name
            return a+b+c;
        }
    }
    public class Main {
        public static void main(String[] args) {
            Calculator object = new Calculator();
            System.out.println(object.add(1,2));
            System.out.println(object.add(3,6,7));
        }
    }
    ```
    b. Operator Overloading  - java doesn't supprots operator overloading

    **2. Runtime polymorphism** - the execution state of programme will be declared at runtime which is dynamic in nature  

    a. Method Overriding - Overriding the execution of a method by another method having same name and same parameters but belongs to different class is known as method overriding.

    ``` java
    // method overriding
    class calculator {
        int add (int a, int b){
            return a+b;
        }
    }
    class AdvanceCalculator extends calculator {
        int add (int a, int b) {
            return a+b+10;
        }
    }
    public class Main {
        public static void main(String[] args) {
            AdvanceCalculator obj = new AdvanceCalculator();
            int result = obj.add(1,4);
            System.out.println(result);
        }
    }

    ```

- These principles are most popular and widely used in all industry level development of applications.



