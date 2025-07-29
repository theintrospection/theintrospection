# __const__

`const` in C++ simply means:  
> **This value cannot be changed after it is initialized** (for the thing that `const` applies to).  
---

## 1️⃣ Basic const variables
```cpp
cpp

const int x = 10; // must be initialized immediately
x = 20; // ❌ ERROR: can't modify
```
- Good for constants that shouldn't change.
- Must be initialized when declared.

## 2️⃣ const with pointers
The **position** of `const` relative to `*` matters a lot.

### (a) Pointer to const data
```cpp
cpp

cosnt int* p = &x; // or int const* p
*p = 5; // ❌ can't change value through p
p = &y; // ✔ can point to something else
```
Meaning: "I proise not to modify the data via this pointer."
---

### (b) Const pointer
```cpp
cpp

int y = 5;
int* const p = &y;
*p = 6; // ✔ can modity value
p = &x; // ❌ can't change the pointer itself
```
Meaning: "The pointer will always point to the same location."
---

### (c) Const pointer to const data
```cpp
cpp

const int* const p = &x;
*p = 5; // ❌ can't modify value
p = &y; // ❌ can't change pointer
```
Meaning: "The pointer will never change, and the data it points to won't change."
---

___waiting for completion...___



