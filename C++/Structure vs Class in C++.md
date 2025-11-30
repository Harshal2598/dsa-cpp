# 🧱 Structure vs Class in C++

In C++, **structures (struct)** and **classes** are both user-defined data types.  
However, they differ mainly in **default access control**, **features**, and **usage**.

---

# 🔍 Definition

## **Structure (struct)**
- A struct is a user-defined data type used to group **related variables**.
- Mostly used for **data storage**.
- Members are **public by default**.

## **Class**
- A class is a blueprint for creating **objects** (Object-Oriented Programming).
- Used to store **data + functions** together.
- Members are **private by default**.

---

# 🆚 Difference Between Structure and Class in C++

| Feature | Structure (`struct`) | Class (`class`) |
|--------|------------------------|------------------|
| **Default Access** | Public | Private |
| **Data + Functions** | Allowed (in C++ struct) | Allowed |
| **Encapsulation Level** | Low | High |
| **Inheritance** | Supports but defaults to public inheritance | Supports but defaults to private inheritance |
| **Usage** | Grouping related data | Object-oriented programming |
| **Constructors/Destructors** | Supported | Supported |
| **Access Modifiers** | Can use public/private/protected | Can use public/private/protected |
| **When to Use** | Simple data models | Complex data with behavior |

---

# ✔ Example of Structure

```cpp
#include <iostream>
using namespace std;

struct Student {
    string name;
    int age;
};

int main() {
    Student s;
    s.name = "Harshal";
    s.age = 21;

    cout << s.name << " " << s.age;
}
```

# ✔ Example of Class
```cpp
#include <iostream>
using namespace std;

class Student {
private:
    string name;
    int age;

public:
    void setData(string n, int a) {
        name = n;
        age = a;
    }

    void showData() {
        cout << name << " " << age;
    }
};

int main() {
    Student s;
    s.setData("Harshal", 21);
    s.showData();
}
