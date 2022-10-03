
# Concerns to be addressed after workout 

**How the fuck is a char pointer a string?**

**Wtf is the difference between char * argv[] and char ** argv?**

**How tf does the first decay into the second one?** 

# Notes on Pointers
*Thank you to mycodeschool for [this invaluable resource](https://www.youtube.com/playlist?list=PL2_aWCzGMAwLZp6LMUKI3cc7pgGsasm2_), as well as multiple threads on Stack Overflow for helping me.*

## Creating Pointers 
A pointer is a variable that stores the memory address of *another* variable in a program. When a variable stores the memory address of another variable, it's said to **reference** the variable. When a pointer is used to access the actual value stored at the address that it is pointing to, it's said to **dereference** that variable.

Creating a pointer is as simple as using a `*` before a variable name and using the `&` operator to *reference* that variable's memory address.
```cpp
#include <iostream>
int main()
{
    char response = 'Y';
    char *ptrResponse = &response;
    std::cout << 'ptrResponse:' << ptrResponse << '\n'; \
    // you will see a memory address in hexadecimal printed to the console
}
```
## Common Beginner Errors When Working With Pointers

### Type to Pointer Conversion Errors
If you're creating a new pointer variable and forget to use the `&` reference operator to retrieve the memory address of a variable, the compiler sees you trying to copy-assign *a type variable to a to a pointer variable*. 
```cpp
char initial = 'S';
char *pTc = initial;
```
This won't even compile, and you'll get a `error: invalid conversion from ‘char’ to ‘char*’ [-fpermissive]` error.

### Pointer To Type Conversion Errors
If you define a pointer and dereference the variable it's pointing to to change the value and *accidentally* use the `&` operator, you'll get a an `invalid conversion error from TYPE* to TYPE` error. That's because dereferencing a pointer makes you deal with a literal/the corresponding data type, not a memory address. 
```cpp
double speed = 100;
double *pTD = &speed;
*pTD = &10;

```
This won't compile. 
# Footnotes
Just remember that for `printf()`:
* `%d`: `int`
* `%c`: `char`
* `%f`" `float`


I'll never understand why `d` was used for `int`...
