<Curses.h> is a Unix library that used when making CLI (command line interfaces).
## Installing the Library
Can be installed on Linux using
```bash
sudo apt-get install libncurses5-dev
```
## Creating a simple program
### Header
```C
#include <curses.h>
```
### Defining keybinds
Some keybinds are not defined by default therefore you need to define them using the corresponding **ASCII** code.
```C
#define ESC 27
#define ENTER 10
```
### Initializing ncurses
```C
void init_curses(void){
	initscr();
	raw();
	keypad(stdscr, true);
	noecho();
	curs_set(0);
}
```

- ```initscr()``` prepares the terminal for the ncurses library
- ```raw()``` configures the terminal to **raw** mode where Input Processing, Special Key Processing, Signal Handling and Echoing are disabled
- ```keypad(stdscr, true)``` 
