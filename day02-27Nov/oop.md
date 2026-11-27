# Day 2 — OOP

**Topic:** Fundamentals

---

## 1. Difference between procedural programming and object-oriented programming.

### Answer

Procedural programming is built from functions and steps. Object-oriented programming is built from classes and objects.

- Procedural code is a list of functions that run one after another.
- The data and the functions stay separate, so many functions can use the same data.
- In OOP, related data and functions live together inside a class.
- An object keeps its own data and works through its own methods.
- OOP adds encapsulation, inheritance, polymorphism, and abstraction, which helps when the program gets large.

### Interview

Procedural programming organizes a program as functions that run step by step. The data and the functions stay separate. Object-oriented programming organizes a program as classes and objects, so the data and the functions that use it live together. OOP also gives encapsulation, inheritance, polymorphism, and abstraction. That makes it a better fit for large programs that need to be reused and changed safely.

#### Example

```cpp
#include <iostream>
using namespace std;

// Procedural: the data and the function are separate.
int marks = 85;

void showMarks() {
    cout << "Procedural marks: " << marks << endl;
}

// OOP: the data and the function live together in the class.
class Student {
public:
    int marks = 90;

    void showMarks() {
        cout << "OOP marks: " << marks << endl;
    }
};

int main() {
    showMarks();

    Student s1;
    s1.showMarks();
    return 0;
}
```

---

## 2. Advantages and disadvantages of OOP.

### Answer

OOP helps large programs stay organized. It costs extra complexity, so a tiny program may not need it.

**Advantages**

- Reuse: a new class can inherit an existing class instead of copying code.
- Safety: encapsulation keeps data private and allows access through methods.
- Easier changes: you update one class instead of searching the whole program.
- Flexibility: polymorphism lets the same method name do different work.
- Organization: each class has its own data and its own job.

**Disadvantages**

- Harder to learn at the start because of classes, objects, and the four pillars.
- Often needs more code than a short procedural program.
- Each object uses extra memory.
- Features such as virtual functions add a small runtime cost.
- A small script usually stays simpler as plain functions.

### Interview

OOP gives reuse, safer data, easier changes, flexibility, and a program split into classes. The cost is more to learn, often more code, extra memory, and a little runtime overhead. It is a strong choice for a large application. A short, simple program can stay procedural.

#### Example

```cpp
#include <iostream>
using namespace std;

class Student {
private:
    int marks = 85; // the data stays inside the class

public:
    void showMarks() {
        cout << "Marks: " << marks << endl;
    }
};

int main() {
    Student s1;
    s1.showMarks(); // the program uses the data through a method
    return 0;
}
```

---
