## Introduction
Header files (**.h**) are a way to interface functions, data structures and macros between C/C++ files.
To simplify the management of the project files, the header files should have the same name as the source ones.
## Contents
Anything only declared in the source file will be static to that file, only accessible to calls from that file.
Everything that should be accessible when including the header file should be declared here such as:
### Header guards
Headers guards are used to protect the header from being included multiple times.
They can be declared using the traditional preprocessor method or using the modern pragma directive which is compatible in most modern systems.

Using preprocessor ifndef (universal, works on any compiler and standard):
```C
#ifndef __HEADER_NAME_H__
#define __HEADER_NAME_H__

// code

#endif
```

Using the pragma directive (can be compiler specific):
```C
#pragma once

// code
```
### Function declarations
The declaration will be used as the interface to the other files and should match the implementation in the source file:
```C
// header file (header.h):
#ifndef __HEADER_H__
#define __HEADER_H__

void func1(int param1, int param2);

#endif

// source file (header.c):
void func1(int param1, int param2){
// implementation
}
```
### Declarations for data structures
```C
#ifndef __HEADER_H__
#define __HEADER_H__

typedef struct Data_t{
	int num;
	float flt;
}Data_t;  // valid

union DataUnion{
	char* name;
	short code;
};  // also valid

#endif
```

Empty Data structures (called **Opaque**) such as **structs and unions** can also be declared, their implementation being in the source file in order to hide the details; *this is not recommended if hiding the details is not necessary*
```C
#ifndef __HEADER_H__
#define __HEADER_H__

struct dataType;  // opaque struct
typedef struct dataType dataType;  // also opaque struct

#endif
```
### Macros and Variables
```C
#ifndef __HEADER_H__
#define __HEADER_H__

#define PI 3.14

extern int counter;  // the int variable "counter" is declared in the source file

#endif
```
## Linking Headers
To link headers to source files (.c, .cpp as well as other types) the header must be included the source file like this:
```C
#include "header_name.h"

// source code
```
Where **header_name** is the name of the header file

*Note: if the header is not location dependent (most often for system directory headers), use <> instead of ""*
```C
#include <location_independent.h>  // system header
#include "location_dependent.h"  // local header
```
The exact location can also be specified:
```C
#include "file1/header_file.h"
```
The location of the file is relative to the location of the header file
### Linking external libraries using the compiler
External libraries and headers can be linked directly with the compiler:
```bash
gcc program.c -l<library_name> (optional) -L<library_directory>
```
- -l<library_name> looks for files with the prefix lib and the suffix .a (for static) and .so (for shared) and link them during the compilation
- -L<library_directory> specifies the location of the library if used (else it will look in the system library for the file)

For example the following code will link the math(math.h) library:
```bash
gcc program.c -lm
```

And the following will search for the library libmylibrary in /bin/lib:
```bash
gcc program.c -lmylibrary -L/bin/lib
```
## Precompiled Headers (.gch Files)
Header file can be compiled to binary to speed up the linking process.
The binary header files are called **precompiled headers** and take the **.gch** extension

*Note: you still need to have the original header files to be able to use them; the compiled will find automatically if .gch files are in the project (can also be explicitly stated but usually is not needed)*

To compile header files into precompiled .gch headers:
```bash
gcc -o header_name.h.gch -c header_name.h
```
*Note: if the precompiled headers have different levels of optimization that the rest of the project, incompatibilities can occur*
## Including C++ Header Content
C++ content can be declared using the **Extern "C"** keyword:
```Cpp
// C++ source file
void ExternFunc(void){
// implementation
}
```
```C
// C header file
extern "C" {
void ExternFunc(void);
};
```
*Note: when using a C++ function in a C project, you must compile with g++ instead of gcc*

Using Extern "C" removes the name mangling (caused by C++ overloads) and other C++ optimizations that can cause unexpected behavior in C, therefore allowing the use of C++ style code in C without side effects

#C #Cpp #header #interface #crosslanguage #Linker #Compiler #Programming
