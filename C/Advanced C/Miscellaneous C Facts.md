## \_Noreturn Keyword
*Note: this is part of C11 standard*

Indicates that a function does not return to the caller
It also helps the compiler with:
1. Optimization - the compiler may make certain optimization knowing it doesn't need to keep track of a return value or follow the normal return path
2. Static analysis - the compiler can generate warnings if code appears to continue after a \_Noreturn function (helps in finding bugs)

*Note: this function will generate undefined behavior if the function returns to the caller*
### Syntax
```C
#include <stdnoreturn.h>  /* _Noreturn header */

_Noreturn void exit_function(void){
	/* Code */
	exit(EXIT_SUCCESS);  /* A way to terminate the program */
}
```
For pre-C11 standard **\_\_attribute\_\_((noreturn))** is used instead, however it is not part of the C standard
```C
void __attribute__((noreturn)) exit_function(void){
	/* Code */
	exit(EXIT_SUCCESS);  /* A way to terminate the program */
}
```
## No Arguments vs Void
The following code declares a function that takes an unspecified number of arguments:
```C
int func(){
/* Code */ 
}
```
The code above can generate undefined behavior if the function is called with more than 0 arguments

The following code declares a function that takes no arguments
```C
int func(void){
/* Code */
}
```
The  code above will always trigger compilation errors when called with arguments and as such, should be always used over the unsafe version

*Note: in C++ both codes will be compiled as a no-argument function but the latter one is still preferred*
#C #UndefinedBehaviour #UnsafeCode#Programming