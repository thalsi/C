# C++
Learn c++ and oops concepts wit examples

## Differences between OOP and other programming styles
- Object-Oriented Programming (OOP) has become widely popular due to its many advantages over other programming styles such as Procedural Programming and Functional Programming.
- Alternative methods to OOP include:
1. Procedural Programming
  - Procedural Programming is a programming style that is based on a set of procedures or functions, where each function is a sequence of instructions that performs a specific task. It focuses on the sequence of must-follow steps that to accomplish a specific task. In contrast, OOP focuses on the objects and their interactions to solve problems.
2. Functional Programming
  - Functional Programming is a programming style that focuses on the use of functions that produce output based on their input, without modifying any external state. It is based on mathematical functions and is characterized by immutability and statelessness. In contrast, OOP is based on objects and their states, and it is designed to manage complex, stateful systems.
3. Structured or modular programming.
4. Imperative programming.
5. Declarative programming.
6. Logical programming.

- Most advanced programming languages enable developers to combine models, because they can be used for different programming methods. For example, JavaScript can be used for OOP and functional programming.

## Benefits of OOP over other programming
- Modularity
- Reusability
- Productivity
- Easily upgradable and scalable
- Interface descriptions
- Security
- Flexibility

## What are examples of object-oriented programming languages?
1. popular pure OOP languages include:
    - Ruby
    - Scala
    - Emerald
2. Programming languages designed primarily for OOP include:
    - Java
    - Python
    - C++
3. Other programming languages that pair with OOP include:
    - Visual Basic .NET
    - PHP
    - JavaScript



## Advantages of OOP
- Classes provide easy “building blocks” for faster coding and make code highly maintainable
- Create more stable and consistent code
- Make large and complex code bases more efficient and manageable
- Teams working from the same code base will benefit from existing well-written classes
- Java in particular enforces OOP, which creates good habits (but may be challenging for beginners)

## 1. OOPs Concepts
1. What is the opp?
    - OPP status for Object-Oriented Programming .Procedural programming is about writing procedures or functions that perform operations on the data, while object-oriented programming is about creating objects that contain both data and functions.

2.  advantages over procedural programming
    - OOP is faster and easier to execute
    - OOP provides a clear structure for the programs
    - OOP helps to keep the C++ code DRY "Don't Repeat Yourself", and makes the code easier to maintain, modify and debug
    - reusable ,  less code and shorter development time


3. The four pillars of object-oriented programming are:

- Inheritance: child classes inherit data and behaviors from the parent class
- Encapsulation: containing information in an object, exposing only selected information
- Abstraction: only exposing high-level public methods for accessing an object
- Polymorphism: many methods can do the same task

## 2. Class and Objects
- Classes and objects are the two main aspects of object-oriented programming.

| Class | Objects |
| :---: |  :---:  |
| Fruit | Apple   |
|       | Mango   |
|       | Banana  |

| Class | Objects |
| :---: |  :---:  |
| Car   |   bmw   |
|       |   volo  |
|       |   Benz  |

- A class is like a blueprint for an objects
- which holds its own data members and member functions
- Attributes and methods are basically variables and functions that belongs to the class.
- a car is an object. The car has attributes, such as weight and color, and methods, such as drive and brake.

```
class MyClass {       // The class
  public:             // Access specifier
    int myNum;        // Attribute (int variable)
    string myString;  // Attribute (string variable)
};

  MyClass myObj;  // Create an object of MyClass
```

### 1. Multiple Objects

```
class Car {
  public:
    string brand;   
    string model;
    int year;
};

  Car carObj1;
  carObj1.brand = "BMW";
  carObj1.model = "X5";

  Car carObj2;
  carObj2.brand = "Ford";
  carObj2.model = "Mustang";
```

### 2 . properties
```
class Car {
  public:
    string brand;   //properties
    string model;  //properties
    int year;
};

  Car carObj1;
  carObj1.brand = "BMW";
  carObj1.model = "X5";
```

### 3 . Methods
- Methods are functions that belongs to the class.
- There are two ways to define functions that belongs to a class:
    - Inside class definition
    - Outside class definition

#### 1. Inside class definition
```
class MyClass {        // The class
  public:              // Access specifier
    void myMethod() {  // Method/function defined inside the class
      cout << "Hello World!";
    }
};

int main() {
  MyClass myObj;     // Create an object of MyClass
  myObj.myMethod();  // Call the method
  return 0;
}
```

#### 2. Outside  class definition
- scope resolution :: operato

```
class MyClass {        // The class
  public:              // Access specifier
    void myMethod();   // Method/function declaration
};

// Method/function definition outside the class
void MyClass::myMethod() {
  cout << "Hello World!";
}

int main() {
  MyClass myObj;     // Create an object of MyClass
  myObj.myMethod();  // Call the method
  return 0;
}
```

## 3. Constructors
- A constructor in C++ is a special method that is automatically called when an object of a class is created. ( parentheses mean in "()" )
- The constructor has the same name as the class, it is always public, and it does not have any return value.

```
class MyClass {     // The class
  public:           // Access specifier
    MyClass() {     // Constructor
      cout << "Hello World!";
    }
};

int main() {
  MyClass myObj;    // Create an object of MyClass (this will call the constructor)
  return 0;
}
```

## 4. Access Specifiers
- Access specifiers define how the members (attributes and methods) of a class can be accessed. In the example above, the members are public - which means that they can be accessed and modified from outside the code.

- Three access specifiers:
    1. public - members are accessible from outside the class
    2. private - members cannot be accessed (or viewed) from outside the class
    3. protected - members cannot be accessed from outside the class, however, they can be accessed in inherited classes. You will learn more about Inheritance later.
- It is possible to access private members of a class using a public method inside the same class. See the next chapter (Encapsulation) on how to do this.
- It is considered good practice to declare your class attributes as private (as often as you can). This will reduce the possibility of yourself (or others) to mess up the code. This is also the main ingredient of the Encapsulation concept
- By default, all members of a class are private if you don't specify an access specifier

```
class MyClass {
  public:    // Public access specifier
    int x;   // Public attribute
  private:   // Private access specifier
    int y;   // Private attribute
};

int main() {
  MyClass myObj;
  myObj.x = 25;  // Allowed (public)
  myObj.y = 50;  // Not allowed (private)
  return 0;
}
```

## 5. Encapsulation
- The meaning of Encapsulation, is to make sure that "sensitive" data is hidden from users. To achieve this, you must declare class variables/attributes as private (cannot be accessed from outside the class). If you want others to read or modify the value of a private member, you can provide public get and set methods.
- It is considered good practice to declare your class attributes as private (as often as you can). Encapsulation ensures better control of your data, because you (or others) can change one part of the code without affecting other parts
- Increased security of data

```
class Employee {
  private:
    // Private attribute
    int salary;

  public:
    // Setter
    void setSalary(int s) {
      salary = s;
    }
    // Getter
    int getSalary() {
      return salary;
    }
};

int main() {
  Employee myObj;
  myObj.setSalary(50000);
  cout << myObj.getSalary();
  return 0;
}
```

## 6. Inheritance
- it is possible to inherit attributes and methods from one class to another. We group the "inheritance concept" into two categories:
    - derived class (child) - the class that inherits from another class
    - base class (parent) - the class being inherited from
- To inherit from a class, use the : symbol.
- It is useful for code reusability: reuse attributes and methods of an existing class when you create a new class.
- Types of Inheritance 
    1. Single Inheritance.
    2. Multiple Inheritance.
    3. Multilevel Inheritance.
    4. Hierarchical Inheritance.
    5. Hybrid Inheritance.

```
// Base class
class Vehicle {
  public:
    string brand = "Ford";
    void honk() {
      cout << "Tuut, tuut! \n" ;
    }
};

// Derived class
class Car: public Vehicle {
  public:
    string model = "Mustang";
};

int main() {
  Car myCar;
  myCar.honk();
  cout << myCar.brand + " " + myCar.model;
  return 0;
}
```

## 7. Polymorphism
Polymorphism means "many forms", and it occurs when we have many classes that are related to each other by inheritance.

Like we specified in the previous chapter; Inheritance lets us inherit attributes and methods from another class. Polymorphism uses those methods to perform different tasks. This allows us to perform a single action in different ways.

For example, think of a base class called Animal that has a method called animalSound(). Derived classes of Animals could be Pigs, Cats, Dogs, Birds - And they also have their own implementation of an animal sound (the pig oinks, and the cat meows, etc.):

- The following two types of polymorphism are useful in OOP:
1. Compile-time polymorphism
    - Also called static binding polymorphism, it means binding occurs at compile time. Method overloading is an example of compile-time polymorphism. It allows programmers to use objects of the same name while their parameters can be different.
2. Runtime polymorphism
    - Runtime polymorphism involves dynamic binding. Method overriding is an example of runtime polymorphism. In this process, an object binds with the functionality at the run time.

```
// Base class
class Animal {
  public:
    void animalSound() {
      cout << "The animal makes a sound \n";
    }
};

// Derived class
class Pig : public Animal {
  public:
    void animalSound() {
      cout << "The pig says: wee wee \n";
    }
};

// Derived class
class Dog : public Animal {
  public:
    void animalSound() {
      cout << "The dog says: bow wow \n";
    }
};

int main() {
  Animal myAnimal;
  Pig myPig;
  Dog myDog;

  myAnimal.animalSound();
  myPig.animalSound();
  myDog.animalSound();
  return 0;
}
```

- Polymorphism refers to the ability to perform a certain action in different ways. In Java, polymorphism can take two forms: method overloading and method overriding.

Method overloading happens when various methods with the same name are present in a class. When they are called, they are differentiated by the number, order, or types of their parameters. Method overriding occurs when a child class overrides a method of its parent.

1. Static polymorphism (method overloading)
```
class  Bird  {
public  void  fly()  {
System.out.println("The bird is flying.");
}
public  void  fly(int height)  {
System.out.println("The bird is flying "  + height +  " feet high.");
}
public  void  fly(String name,  int height)  {
System.out.println("The "  + name +  " is flying "  + height +  " feet high.");
}
}


class  TestBirdStatic  {
public  static  void  main(String[] args)  {
Bird myBird =  new Bird();
myBird.fly();
myBird.fly(10000);
myBird.fly("eagle", 10000);
}
}
```

2. Dynamic polymorphism (method overriding)
```
class  Animal  {
public  void  eat()  {
System.out.println("This animal eats insects.");
}
}

class  Bird  extends Animal {
public  void  eat()  {
System.out.println("This bird eats seeds.");
}
}

class  TestBirdDynamic  {
public  static  void  main(String[] args)  {
Animal myAnimal =  new Animal();
myAnimal.eat();
Bird myBird =  new Bird();
myBird.eat();
}
}
```

## 8. Abstraction
Abstraction aims to hide complexity from users and show them only relevant information. For example, if you’re driving a car, you don’t need to know about its internal workings.

The same is true of Java classes. You can hide internal implementation details using abstract classes or interfaces. On the abstract level, you only need to define the method signatures (name and parameter list) and let each class implement them in their own way.

- Abstraction in Java:

- Hides the underlying complexity of data
- Helps avoid repetitive code
- Presents only the signature of internal functionality
- Gives flexibility to programmers to change the implementation of abstract behavior
- Partial abstraction (0-100%) can be achieved with abstract classes
- Total abstraction (100%) can be achieved with interfaces

```
abstract  class  Animal  {
// abstract methods
abstract  void  move();
abstract  void  eat();
// concrete method
void  label()  {
System.out.println("Animal's data:");
}
}
```

```
class  Bird  extends Animal {
void  move()  {
System.out.println("Moves by flying.");
}
void  eat()  {
System.out.println("Eats birdfood.");
}
}

class  Fish  extends Animal {
void  move()  {
System.out.println("Moves by swimming.");
}
void  eat()  {
System.out.println("Eats seafood.");
}
}
```

```
class  TestBird  {
public  static  void  main(String[] args)  {
Animal myBird =  new Bird();
myBird.label();
myBird.move();
myBird.eat();
}
}

class  TestFish  {
public  static  void  main(String[] args)  {
Animal myFish =  new Fish();
myFish.label();
myFish.move();
myFish.eat();
}
}
```

### 1. Interfaces
An interface is a 100% abstract class. It can only have static, final, and public fields and abstract methods. It’s frequently referred to as a blueprint of a class as well. Java interfaces allow you to implement multiple inheritances in your code, as a class can implement any number of interfaces. Classes can access an interface with the implements keyword.

```
interface  Animal  {
public  void  eat();
public  void  sound();
}

interface  Bird  {
int numberOfLegs = 2;
String outerCovering =  "feather";
public  void  fly();
}
```

```
class  Eagle  implements Animal, Bird {
public  void  eat()  {
System.out.println("Eats reptiles and amphibians.");
}
public  void  sound()  {
System.out.println("Has a high-pitched whistling sound.");
}
public  void  fly()  {
System.out.println("Flies up to 10,000 feet.");
}
}
```

```
class  TestEagleInterfaces  {
public  static  void  main(String[] args)  {
Eagle myEagle =  new Eagle();

myEagle.eat();
myEagle.sound();
myEagle.fly();

System.out.println("Number of legs: "  + Bird.numberOfLegs);
System.out.println("Outer covering: "  + Bird.outerCovering);
}
}
```
