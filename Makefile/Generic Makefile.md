```Makefile
CC = gcc
CFLAGS = -Wall -Wextra
EXECNAME = main.exe
OBJECTS = main.o

all: $(EXECNAME)

$(EXECNAME): $(OBJECTS)
    @$(CC) -o $@ $^
    @@echo Files compiled successfully!

%.o: %.c
    @$(CC) $(CFLAGS) -c -o $@ $^

clear:
    @rm $(OBJECTS) $(EXECNAME)
    @@echo Files deleted successfully!
```
## Special Characters
-**$()** is used to call a variable
-**%.o** and **%.c** allows for any files of these types to use the rules
-**$@** uses built file (left) as a variable
-**$^** uses the required files (right) as a variable
-**@** hides the whole line from displaying
-**@@** hides the next word from displaying
## Conventions
### Variables
-**CC** - C Compiler
-**CFLAGS** - Compiler Flags
### Files
-**all** - argument to compile everything
-**clear** - argument to remove all non-source files
## Execution
The file is executed using:

Windows:
```Powershell
mingw32-make all
```
Linux:
```Bash
make all
```

The executable and object files are deleted using:

Windows:
```Powershell
mingw32-make clear
```
Linux:
```Bash
make clear
```

#Makefile #Compiler #Programming