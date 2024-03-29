# C++
Learn c++ and oops concepts wit examples


## 1. OOPs Concepts
1. What is the opp?
    - OPP status for Object-Oriented Programming .Procedural programming is about writing procedures or functions that perform operations on the data, while object-oriented programming is about creating objects that contain both data and functions.

2.  advantages over procedural programming
    - OOP is faster and easier to execute
    - OOP provides a clear structure for the programs
    - OOP helps to keep the C++ code DRY "Don't Repeat Yourself", and makes the code easier to maintain, modify and debug
    - reusable ,  less code and shorter development time

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
## 8. Abstraction
