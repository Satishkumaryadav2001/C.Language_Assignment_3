# C.Language_Assignment_3

Ques 1 What are the primitive data types in C Language? 

Ans: In **C language**, there are **6 primitive data types**:

1. **`int`** – Represents integer numbers (whole numbers).
   - Example: `int x = 5;`

2. **`char`** – Represents a single character.
   - Example: `char letter = 'A';`
   - It typically occupies 1 byte of memory.

3. **`float`** – Represents single-precision floating-point numbers (decimals).
   - Example: `float pi = 3.14f;`
   - Usually occupies 4 bytes.

4. **`double`** – Represents double-precision floating-point numbers (more precise decimals).
   - Example: `double gravity = 9.81;`
   - Usually occupies 8 bytes.

5. **`void`** – Represents the absence of data (used for functions that do not return a value).
   - Example: `void functionName() {}`

6. **`short`** – Represents short integers (usually 2 bytes).
   - Example: `short num = 100;`

---

### 🧠 Key Points:
- **`int`**, **`char`**, **`float`**, and **`double`** are the most commonly used types for basic data storage.
- **`void`** is used when a function does not return any value.

---

These are the **primitive** data types in **C**, and they form the foundation for building more complex data types (arrays, structs, etc.).

Ques 2  What kind of statements can be written outside the function body ?

Ans In **C**, the only type of statement that can be written **outside** the function body is **declarations** (such as variable declarations and function prototypes).

---

### 🔍 Here's the breakdown:

1. **Function Prototypes**:
   - A **function prototype** declares the function's signature, which tells the compiler about the function's name, return type, and parameters before its actual definition.
   - Example:
     ```c
     int add(int, int);  // function prototype (declaration)
     ```

2. **Variable Declarations** (in global scope):
   - **Global variables** are declared outside the function body but **must** be initialized later in the function body or elsewhere.
   - Example:
     ```c
     int x;  // Global variable declaration outside any function
     ```

3. **Preprocessor Directives** (like `#define`, `#include`):
   - These are used outside the function body, typically at the beginning of the code.
   - Example:
     ```c
     #include <stdio.h>  // Preprocessor directive
     ```

---

### ❌ What can't be written outside the function body?
- **Executable statements** like loops (`for`, `while`), conditionals (`if`, `switch`), or function calls cannot be written outside function bodies. They must appear **inside** a function.

---

### ✅ So, **outside the function body**, you can have:
- **Function prototypes**
- **Global variable declarations**
- **Preprocessor directives**

Let me know if you need further clarification! 

Ques 3 What is the size of the float type variable ? 

Ans :  In C, the size of a **`float`** type variable is typically **4 bytes** (32 bits). 

### 🔍 Key Details:
- **Size**: 4 bytes (or 32 bits)
- **Range**: The range of values that a `float` can represent is approximately ±3.4E−38 to ±3.4E+38, with a precision of about 6 to 7 decimal digits.

### Example:
```c
float pi = 3.14159;
```

### 📏 How to check the size programmatically:
You can use the `sizeof` operator to find the size of any type:

```c
#include <stdio.h>

int main() {
    printf("Size of float: %zu bytes\n", sizeof(float));
    return 0;
}
```

This will output:

```
Size of float: 4 bytes
```

However, note that the size can vary on some platforms (e.g., older or embedded systems might have different sizes).


Ques 4 What is the value of an uninitialized variable ?

Ans : In **C**, the value of an **uninitialized variable** is **undefined**. This means that if you declare a variable but don't assign it a value, it can contain any random or garbage value left in memory from previous programs or processes.

### 🔍 Details:

1. **Local variables** (variables declared inside functions):
   - **Uninitialized local variables** have **undefined values**. They could be anything, and using them without initialization can lead to unpredictable behavior or bugs.
   - Example:
     ```c
     int x;  // Uninitialized local variable
     printf("%d", x);  // This will print a random, garbage value
     ```

2. **Global variables** (variables declared outside functions):
   - **Uninitialized global variables** are automatically initialized to **zero** by the compiler. This is a special behavior for global (and static) variables.
   - Example:
     ```c
     int x;  // Global variable, automatically initialized to 0
     printf("%d", x);  // This will print 0
     ```

3. **Static variables** (variables declared with the `static` keyword):
   - Similar to global variables, **uninitialized static variables** are automatically initialized to **zero**.
   - Example:
     ```c
     static int x;  // Static variable, automatically initialized to 0
     printf("%d", x);  // This will print 0
     ```

### 🚨 **Warning**:
- **Using uninitialized local variables** can cause serious bugs, as their values are unpredictable.
- Always **initialize variables** before using them to avoid relying on random values.

Let me know if you need examples or further clarification!


Ques 5  What is the difference between float and double ?

Ans : The key differences between **`float`** and **`double`** in C are related to **precision**, **range**, and **memory size**.

### 🔍 **Differences between `float` and `double`**:

| Feature            | **`float`**                                    | **`double`**                                  |
|--------------------|------------------------------------------------|-----------------------------------------------|
| **Size**           | 4 bytes (32 bits)                             | 8 bytes (64 bits)                             |
| **Precision**      | ~6-7 decimal digits                           | ~15-16 decimal digits                         |
| **Range**          | Approximately ±3.4E−38 to ±3.4E+38            | Approximately ±1.7E−308 to ±1.7E+308          |
| **Default**        | Single-precision floating-point               | Double-precision floating-point               |
| **Memory Usage**   | Uses less memory                             | Uses more memory                             |
| **Performance**    | Faster on systems with limited resources (less precision) | Slower on systems with limited resources (higher precision) |
| **Usage**          | Typically used when memory is a concern and less precision is acceptable | Used when more precision is needed (e.g., scientific calculations) |

### 🚨 **Example Code**:

```c
#include <stdio.h>

int main() {
    float f = 3.14159265359f;  // 'f' is used to indicate a float
    double d = 3.14159265359;  // Double by default
    
    printf("Float value: %f\n", f);  // Displays up to 6-7 significant digits
    printf("Double value: %lf\n", d);  // Displays up to 15-16 significant digits
    
    return 0;
}
```

### 🧠 **Summary**:
- **`float`** is used for **single precision** (less memory, lower precision).
- **`double`** is used for **double precision** (more memory, higher precision).

In general, **`double`** is preferred when you need more **accuracy** in calculations, especially in scientific or financial applications.


Ques 6 What is the full form of ASCII ?

Ans :   The full form of **ASCII** is **American Standard Code for Information Interchange**. 

### 🔍 **What is ASCII?**
- It is a character encoding standard used for representing **text** and **control characters** in computers and communication devices.
- ASCII uses **7 bits** to represent each character, allowing it to represent **128 unique characters** (including letters, digits, punctuation marks, and control characters).

### 🧠 **Examples**:
- **`A`** in ASCII is represented as **65**.
- **`a`** is represented as **97**.
- **Space** is represented as **32**.

Let me know if you'd like more details about ASCII!


Ques 7  What is the difference between a keyword and a function ? 


Ans :  The difference between a **keyword** and a **function** in C programming can be understood in terms of **their purpose**, **usage**, and **role** in the language.

### 🔍 **Difference between Keyword and Function**:

| **Aspect**         | **Keyword**                                         | **Function**                                        |
|--------------------|-----------------------------------------------------|-----------------------------------------------------|
| **Definition**     | A **reserved word** that has a **special meaning** in the language syntax. It cannot be used as an identifier (variable name, function name, etc.). | A **block of code** designed to perform a specific task. Functions are **user-defined** or **library-defined**. |
| **Purpose**        | Keywords are part of the **syntax** and structure of the language. They define how the program is structured and how control flows. | Functions allow you to **modularize** your code. They enable **code reuse** and organize logic into smaller, manageable pieces. |
| **Example**        | `int`, `if`, `return`, `while`, `for`, `static` (These are **C keywords**) | `printf()`, `scanf()`, `main()`, `add()` (These are **functions** in C) |
| **Usage**          | Keywords are used to control the flow, define data types, or perform specific tasks that are predefined by the language. | Functions are used to **define behavior** and **process logic**. Functions can either be built-in (like `printf()`) or user-defined (like `add()` in your own program). |
| **Modifiable?**    | No, keywords **cannot** be changed, redefined, or used as identifiers. They have fixed roles in the language. | Yes, functions can be **created**, **modified**, and **called** by programmers. |

---

### 🧠 **Key Takeaways**:

- **Keywords**: Predefined by the language. They cannot be redefined and control the program’s structure.
- **Functions**: Can be created, modified, and used by the programmer to perform specific tasks or calculations.

Let me know if you'd like more details or examples!

Ques 8 Explore the use of type modifiers in C language. 

Ans : In **C programming**, **type modifiers** are used to **alter** or **extend** the size and range of basic data types like `int`, `char`, `float`, and `double`. They allow you to specify **whether the variable should be signed or unsigned**, or whether the variable should be **shortened** or **extended** in size.

### 🔍 **List of Type Modifiers in C**:

1. **`signed`**:
   - The `signed` modifier is used to specify that a variable can hold both **positive** and **negative** values.
   - By default, integer types (`int`, `char`, etc.) are **signed**, meaning they can store both negative and positive values.
   - **Example**: `signed int a;`
   
2. **`unsigned`**:
   - The `unsigned` modifier is used to specify that a variable can only hold **positive** values (including zero).
   - This effectively doubles the **positive range** of the variable, since it doesn’t need to store negative numbers.
   - **Example**: `unsigned int b;`
   
3. **`short`**:
   - The `short` modifier is used to reduce the size of the data type. It creates a **shorter** version of the type.
   - It is typically used with integer types (`int`) to store smaller values, usually using 2 bytes.
   - **Example**: `short int c;` (typically 2 bytes)

4. **`long`**:
   - The `long` modifier is used to **increase** the size of the data type. It allows the variable to hold **larger values**.
   - It is typically used with integer types (`int`) to store larger values, usually using 4 bytes or more.
   - **Example**: `long int d;` (typically 4 bytes)

5. **`long long`**:
   - The `long long` modifier is used to extend the size of the integer type even more, usually used for storing very large integers.
   - **Example**: `long long int e;` (typically 8 bytes)

6. **`long double`**:
   - The `long double` modifier is used with floating-point types to increase precision. It allows the variable to store **larger and more precise decimal values** than `float` and `double`.
   - **Example**: `long double f;` 

### 🧠 **Combined Modifiers**:
- You can combine these modifiers to customize the size and range of the variable.
  - **Example 1**: `unsigned long int g;` (A long integer that can only store positive values)
  - **Example 2**: `signed short int h;` (A short integer that can store both positive and negative values)
  - **Example 3**: `unsigned long long int i;` (An extended integer for larger positive values)

### 💡 **Size of Data Types**:
| Data Type      | Size (Typically) | Range (Approx.)              |
|----------------|------------------|------------------------------|
| `char`         | 1 byte           | -128 to 127 (signed)         |
| `unsigned char`| 1 byte           | 0 to 255                     |
| `short`        | 2 bytes          | -32,768 to 32,767            |
| `unsigned short`| 2 bytes         | 0 to 65,535                  |
| `int`          | 4 bytes          | -2,147,483,648 to 2,147,483,647 |
| `unsigned int` | 4 bytes          | 0 to 4,294,967,295           |
| `long`         | 4 bytes          | -2,147,483,648 to 2,147,483,647 |
| `long long`    | 8 bytes          | -9.22E18 to 9.22E18          |
| `float`        | 4 bytes          | ±3.4E−38 to ±3.4E+38         |
| `double`       | 8 bytes          | ±1.7E−308 to ±1.7E+308       |
| `long double`  | 8 bytes or more | ±1.7E−308 to ±1.7E+308 (more precision than double) |

### 🚨 **Important Notes**:
- **Size**: The exact size of data types can vary depending on the system architecture (e.g., 32-bit vs 64-bit systems).
- **Default behavior**: `int` is signed by default, so if you don't specify the modifier, it will treat it as signed.
- **Range Extension**: Using `unsigned` allows for a larger **positive range**, but no negative values. On the other hand, `signed` can store both positive and negative values but with a smaller range for positive numbers.

### 🧠 **Example Code**:
```c
#include <stdio.h>

int main() {
    short int a = -32000;    // short int (2 bytes, signed by default)
    unsigned int b = 300000; // unsigned int (4 bytes, no negative values)
    long long int c = 9223372036854775807; // long long int (8 bytes)

    printf("short int a: %d\n", a);
    printf("unsigned int b: %u\n", b);
    printf("long long int c: %lld\n", c);

    return 0;
}
```

### ✅ **Summary**:
- **Type modifiers** allow you to **adjust** the **size** and **range** of the variables.
- **Common modifiers** include `signed`, `unsigned`, `short`, `long`, and `long long`.
- These modifiers help manage **memory usage** and **data range** depending on your needs.

Let me know if you need more examples or further explanations!

Ques 9  Can you assign a character constant in an int variable ?

Ans: Yes, you **can** assign a **character constant** to an **`int`** variable in C.

In C, a **character constant** (e.g., `'A'`, `'b'`) is actually represented by its **ASCII value**, which is an integer. So, assigning a character constant to an `int` variable will store the **ASCII value** of the character in the integer variable.

### 🔍 **Example**:

```c
#include <stdio.h>

int main() {
    int num;
    char ch = 'A';  // character constant

    // Assigning the character constant to an int variable
    num = ch;

    printf("The ASCII value of '%c' is: %d\n", ch, num);
    return 0;
}
```

### 🧠 **Explanation**:
- The character `'A'` has an **ASCII value** of **65**.
- When you assign `'A'` to an `int` variable, the integer variable stores the **ASCII value** 65, which is the integer representation of `'A'`.

### Output:
```
The ASCII value of 'A' is: 65
```

### 🚨 **Important Notes**:
- **Character constants** (like `'A'`, `'1'`, `'%'`) are treated as **integers** (their ASCII values) when assigned to an `int`.
- **Int to char conversion**: You can also do the reverse. If you assign an integer to a `char` variable, it will store the corresponding character for that integer value (within the valid ASCII range).

Let me know if you have more questions or need further clarification!

Ques 10 State the following statement as true or false -”Every block of code is a function”. 

Ans : The statement **"Every block of code is a function"** is **false**.

### Explanation:
- In C, a **block of code** is simply a **group of statements** enclosed in **curly braces `{}`**, and it does not necessarily have to be a **function**.
- A **function** is a specific type of block of code that has:
  - A **name**.
  - A **return type**.
  - **Parameters** (optional).
  - A **return statement** (optional, depending on the return type).
  
### Example:
- A **block of code**:
  ```c
  {
      int x = 5;
      printf("%d", x);
  }
  ```
  This is just a block of code, not a function.
  
- A **function**:
  ```c
  int add(int a, int b) {
      return a + b;
  }
  ```
  This is a **function** with a name, parameters, and a return type.

### Conclusion:
- **Not every block of code is a function**. Functions are specific blocks of code that have a defined structure and purpose in the program.
- 
