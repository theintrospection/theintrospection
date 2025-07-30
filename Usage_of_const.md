# __const__

`const` in C++ simply means:  
> **This value cannot be changed after it is initialized** (for the thing that `const` applies to).  
---

## 1️⃣ **Basic const variables**
```cpp
cpp

const int x = 10; // must be initialized immediately
x = 20; // ❌ ERROR: can't modify
```
- Good for constants that shouldn't change.
- Must be initialized when declared.

## 2️⃣ **const with pointers**
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

## 3️⃣ **const with function parameters**
### (a)Pass by const reference
```cpp
cpp
void print(const std::string& s) {
    std::cout << s;
}
```
- Prevents modification inside function.
- Avoids copying large objects.

### (b) **Pass pointer to const**
```cpp
cpp
void show(const int* p) {
    std::cout << *p;
}
```
- You can't change the data inside the function through p.

## 4️⃣ **const with member functions**
**In classes, marking a member function as const means it doesn't modify the object's members.**
```cpp
cpp

class Myclass {
    int value;
public:
    int getValue() const { return value; } // won't modify members
};
```
## 5️⃣ **const global vaariables**
**Global constants are often declared `const` (or `constexpr` in modern C++):**
```cpp
cpp

const double PI = 3.1415925;
```
**If you want them shared across translation units, use:**
```cpp
cpp

extern const double PI;
```
in header and define it in one `.cpp`.
---

## 6️⃣ **const + cosntexpr**
- `const` = value doesn't change after initialization.
- `constexpr` = value known at compile time.
```cpp
cpp

const int = 5;          // value fixed at runtime.
constexpr int b = 5;    // value fixed at compile time
```
**`constexpr` variables cannot be modified at runtime.**They are fixed and immutable once compiled.

### 🔷**Why `constexpr` exists**
It allows **compile-time constants** to be used where compile-time evaluation is required, e.g.:
```cpp
cpp

constexpr int size = 5;
int arr[size]; // ✅ OK

const int size2 = getValue();
int arr2[Size2]; // ❌ error in C++ (size not known at comlile time)
```
### 🟡 You may also confused about why `int arr2[size2]` throws an error. Isn't `size2` is already initialized?

> In standard C++ (before C++ 14's relaxed rules for some contexts), the size of a built-in array must be a **comlile-time constant expression** -- something the compiler can determine without runing your program.

___waiting for completion...___



