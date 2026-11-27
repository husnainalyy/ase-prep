# Day 3 — OOP

**Topic:** Fundamentals

---

## 1. Difference between a member variable and a member function.

### Answer

A member variable stores data. A member function does work with that data. Both belong to the class.

- A member variable is also called a data member. It holds a value, such as a name or a mark.
- A member function is also called a method. It is an action, such as showing the name or updating the mark.
- The variable is the state of the object. The function is the behavior.
- Each object gets its own copy of a normal member variable. The function is shared and runs on the object you call it with.
- A function can read and change the variables of its own object.

### Interview

A member variable stores data inside the class, and a member function is an action the class can perform. The variable is the state, such as a student's name. The function is the behavior, such as printing that name. Each object keeps its own variable values, and it uses the functions to work with them.

#### Example

```cpp
#include <iostream>
#include <string>
using namespace std;

class Student {
public:
    string name; // member variable: data

    void study() { // member function: an action
        cout << name << " is studying" << endl;
    }
};

int main() {
    Student s1;
    s1.name = "Ali";
    s1.study();
    return 0;
}
```

`name` holds Ali. `study()` uses that stored name and prints `Ali is studying`.

---

## 2. What are access modifiers? Explain public, private, and protected.

### Answer

An access modifier decides who is allowed to use a member. In C++ the three are public, private, and protected.

- **public:** any code that has the object can use the member. This is the open door.
- **private:** only functions inside the same class can use the member. Code outside, including a child class, cannot touch it.
- **protected:** the class itself and its child classes can use the member. Unrelated code cannot.
- A `class` hides its members by default, so an unmarked member is private. A `struct` is public by default.
- Keep data private and offer public functions to read or change it. That is encapsulation.

### Interview

Access modifiers control who can use a class member. Public members are open to everyone. Private members can be used only inside that class. Protected members can be used inside the class and inside classes that inherit from it. In a C++ class, members are private unless you mark them otherwise. We usually keep data private and expose public functions.

#### Example

```cpp
#include <iostream>
using namespace std;

class Student {
private:
    int marks; // only Student can touch this

protected:
    int rollNo; // Student and its child classes can touch this

public:
    void setMarks(int m) { marks = m; }
    int getMarks() { return marks; }
};

class Topper : public Student {
public:
    void setRoll(int r) { rollNo = r; } // allowed: protected
    void show() {
        cout << "Roll: " << rollNo << endl;
        cout << "Marks: " << getMarks() << endl; // use the public function
    }
};

int main() {
    Topper t;
    t.setMarks(90);
    t.setRoll(12);
    t.show();
    return 0;
}
```

`main` cannot write `t.marks` or `t.rollNo`. Marks stay private, so `main` goes through `setMarks`. The child class can use `rollNo` because it is protected.
