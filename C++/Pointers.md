# 📌 Pointers in C++ (With Stack & Heap Memory Diagram)

A **pointer** in C++ is a variable that stores the **memory address** of another variable.

Example:
```cpp
int a = 10;
int* p = &a;   // p stores the address of a
Here:

a contains 10

p contains address of a

🧠 How Memory Works in C++ (Stack vs Heap)
C++ divides memory into two major areas:

1️⃣ Stack Memory
Stores local variables, function calls, pointer variables

Automatically managed

Fast access

2️⃣ Heap Memory
Used for dynamic memory allocation

We use new and delete

Manually managed

🗂️ Main Memory Diagram (Stack + Heap + Pointer)
Below is a simple ASCII diagram to visualize pointers, stack, and heap:

pgsql
Copy code
+--------------------------------------------------------+
|                        MAIN MEMORY                     |
+--------------------------------------------------------+

        STACK MEMORY                      HEAP MEMORY
   (Stores variables & pointers)    (Stores dynamically allocated data)

   +-----------------------+        +------------------------------+
   | int a = 10;           |        | new int(20);                 |
   |                       |        | (Dynamically allocated block)|
   +-----------------------+        +------------------------------+
   | p (pointer)           |----->  | 20                           |
   | stores address of a   |        | (Stored at heap address 1000)|
   +-----------------------+        +------------------------------+

               ↑
               | p = &a (pointer to stack variable)
               |

🧪 Example 1: Pointer to Stack Variable
cpp
Copy code
#include <iostream>
using namespace std;

int main() {
    int a = 10;
    int* p = &a;

    cout << "a = " << a << endl;
    cout << "Address of a = " << p << endl;
    cout << "Value using pointer = " << *p << endl;

    return 0;
}
✔ Explanation
a is stored in stack

p is also stored in stack

p contains the address of a

*p gives the value stored at that address

🧪 Example 2: Pointer with Heap Memory
cpp
Copy code
int* p = new int(20);   // stored in heap
Diagram
lua
Copy code
Stack                               Heap
+---------------+           +-------------------+
| p = 1000      | ------->  | 20  (at addr 1000)|
+---------------+           +-------------------+
❗Important
To free heap memory:

cpp
Copy code
delete p;
🧩 Null Pointer
A pointer that stores no valid address.

cpp
Copy code
int* p = nullptr;
Used for safety to avoid accessing garbage memory.

🧩 Dangling Pointer
Pointer pointing to freed or invalid memory.

cpp
Copy code
int* p = new int(5);
delete p;     // memory freed
cout << *p;   // ❌ dangling pointer
🧩 Pointer to Array
cpp
Copy code
int arr[3] = {10, 20, 30};
int* p = arr;   // p points to arr[0]
Access:

cpp
Copy code
cout << *(p + 1);   // 20
📝 Short Exam Answer
A pointer in C++ stores the memory address of another variable.
Pointers are stored in stack memory, but they can point to both stack and heap variables.
Heap memory is dynamically allocated using new and freed using delete.

The stack contains:

Local variables

Pointer variables

The heap contains:

Dynamically allocated memory

Pointers allow efficient memory management and dynamic data structures.
