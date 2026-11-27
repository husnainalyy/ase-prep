# Day 1 — OOP

**Topic:** Fundamentals

---

## 1. What is Object-Oriented Programming (OOP), and why do we use it?

### Answer

Object-oriented programming is a way of writing code by grouping related data and actions into classes and objects.

- A class is the blueprint. It describes the data and the actions.
- An object is one real item made from that class, with its own data.
- OOP keeps a big program organized because each class has one clear job.
- We use it for reuse, easier changes, safer data, and room to grow.
- Remember the four pillars: encapsulation, inheritance, abstraction, and polymorphism.

### Interview

Object-oriented programming is a way of writing programs with classes and objects. A class is the plan, and an object is one real item made from that plan. We use it so the code is easier to reuse, easier to change, safer, and easier to grow. It stands on four pillars: encapsulation, inheritance, abstraction, and polymorphism.

#### Example

```cpp
#include <iostream>
#include <string>
using namespace std;

class Student {
public:
    int age;
    string name;

    void study() {
        cout << "Student is studying" << endl;
    }
};

int main() {
    Student s1;
    s1.age = 11;
    s1.name = "Ali";
    s1.study();
    return 0;
}
```

---

## 2. What is the difference between a class and an object?

### Answer

A class is the blueprint. An object is one real item made from that blueprint.

- The class describes the data and the methods. Creating the class does not create a usable item yet.
- An object is created from the class and stores its own values.
- One class can make many objects, and each object can hold different data.
- Car design is the class. A red Civic, a Honda, and a Toyota are objects made from it.
- Color, speed, and weight are the data. Start and stop are the methods.

### Interview

A class is a blueprint that defines the properties and methods. An object is an instance of that class. The class describes the structure, and each object uses that structure with its own data. Car is the class. One red car in the program is an object of that class.

#### Example

```cpp
#include <iostream>
#include <string>
using namespace std;

class Car {
public:
    string color;

    void start() {
        cout << "Car is starting" << endl;
    }
};

int main() {
    Car car1;          // object made from the Car class
    car1.color = "Red";
    car1.start();
    return 0;
}
```

---

## 3. What are the four pillars of OOP? Explain each with a real-world example.

### Answer

The four pillars are encapsulation, inheritance, polymorphism, and abstraction.

**Encapsulation** — protect the data

- Keep data private and change it only through methods.
- Real life: an ATM uses your PIN and shows your balance. It never shows the check happening inside the bank.

**Inheritance** — reuse code

- A child class receives the data and methods of a parent class.
- Real life: Dog inherits from Animal, so a dog can eat, and it also has its own bark.

**Polymorphism** — one name, many forms

- The same method name can do different work in different classes.
- Real life: every animal has speak(). A dog barks and a cat meows.

**Abstraction** — hide the complicated parts

- Show only what is needed and hide how it works.
- Real life: you drive a car with the wheel and the pedals. You do not handle the engine parts yourself.

### Interview

The four pillars are encapsulation, inheritance, polymorphism, and abstraction. Encapsulation protects data by controlling who can use it. Inheritance lets one class reuse another class. Polymorphism lets the same method name behave in different ways. Abstraction hides the inner details and shows only what is needed. Together they make code reusable, safer, and easier to change.

#### Example

```cpp
#include <iostream>
using namespace std;

// Abstraction: Student says what is required, not how each student does it.
class Student {
public:
    virtual void showResult() = 0;
};

// Inheritance: SchoolStudent is a Student.
class SchoolStudent : public Student {
private:
    int marks = 85; // Encapsulation: marks stays private.

public:
    void showResult() override { // Polymorphism: its own version of showResult.
        cout << "School Student Marks: " << marks << endl;
    }
};

class CollegeStudent : public Student {
private:
    int marks = 90;

public:
    void showResult() override {
        cout << "College Student Marks: " << marks << endl;
    }
};

int main() {
    SchoolStudent s1;
    CollegeStudent s2;

    s1.showResult();
    s2.showResult();
    return 0;
}
```

---
