## Declaration
The class is the template for the structure while the objects are instances of the class
### Declaring a class
```python
class foo_class:
	pass  # code
```
### Declaring an object
```python
foo_obj_1 = foo_class()
```
*Note: declaring an object without using the **()** constructor will just assign the class itself to the variable instead of an instance of the class; in this case foo_obj_1 will be assigned <class '__main__.foo_class'>*
#### Strongly typed
```python
foo_obj_2: foo_class = foo_class() # strogly typed
```
## Methods
Methods are the functions attributed to a class.
The first parameter (usually named "**self**") is the class itself
### Generic method
```python
def func(self):
	pass  # code
```
### Constructor / Destructor
Constructor is called when the object is created
```python
def __init__(self):
	pass  # code
```
Destructor is called when the object is destroyed
```python
def __del__(self):
	pass  # code
```
### String representation
The method is called when the object is represented (type casted) as a string
```python
def __str__(self):
	pass  # code
```
### Comparison operators
The methods define how the objects behaves when using comparison operators like == , != , > , >= , < , <=
Operator == :
```python
def __eq__(self, other):
	return self.value == other.value  # code
```
Operator != :
```python
def __ne__(self, other):
	return self.value != other.value  # code
```
Operator < :
```python
def __lt__(self, other):
	return self.value < other.value  # code
```
Operator <= :
```python
def __le__(self, other):
	return self.value <= other.value  # code
```
Operator > :
```python
def __gt__(self, other):
	return self.value > other.value  # code
```
Operator >= :
```python
def __ge__(self, other):
	return self.value >= other.value  # code
```
### Arithmetic operators
The methods define how the objects behaves when using arithmetic operators like +, -, \*, /, //, %, \*\*
Operator + :
```python
def __add__(self, other):
	return foo_class(self.value + other.value)  # code
```
Operator - :
```python
def __sub__(self, other):
	return foo_class(self.value - other.value)  # code
```
Operator \* :
```python
def __mul__(self, other):
	return foo_class(self.value * other.value)  # code
```
Operator / :
```python
def __truediv__(self, other):
	return foo_class(self.value / other.value)  # code
```
Operator // :
```python
def __floordiv__(self, other):
	return foo_class(self.value // other.value)  # code
```
Operator % :
```python
def __mod__(self, other):
	return foo_class(self.value % other.value)  # code
```
Operator \*\* :
```python
def __pow__(self, other):
	return foo_class(self.value ** other.value)  # code
```
### Container methods
The methods let the objects behave like containers

Allows using [] to get the value at a specific index key:
```python
def __getitem__(self, index):
	return self.items[index]  # code
```

Allows using [] to set a value at the index key:
```python
def __setitem__(self, index, value):
	self.items[index] = value  # code
```

Allows using the **del** statement to delete the item at the index key:
```python
def __delitem__(self, index):
	del self.items[index]  # code
```

Returns an iterator object which allows the object to be iterated over in a **for** loop:
```python
def __iter__(self):
	return iter(self.items)  # code
```

Returns the next item from the iterator (used in conjunction with \_\_iter\_\_):
```python
def __next__(self):
	if self.index < len(self.items):  # code
		result = self.items[self.index]
		self.index += 1 
		return result 
	else: 
		raise StopIteration
```

Determines if an item is in the object (like using **in**):
```python
def __contains__(self, items):
	return item in self.items  # code
```
### Calllable objects method
Makes objects callable (like functions)
```python
def __call__(self, increment):
	return self.value + increment  # code
```
### Miscellaneous methods
The method is used when the **len()** function is called on an object
```python
def __len__(self):
	return len(self.items)  # code
```
## OOP Principles
### Encapsulation
Encapsulation is the concept of restricting data in a class which is done in Python by naming conventions.

**Public**: intended to be used anywhere
**Protected**: intended to be accessed within the class or subclass
**Private**: intended to only be used from within the class
```python
class foo:
	pub_data = None  # public
	_restr_data = None  # restricted
	__private_data = None  # private; will raise an error when used outside the class
```
### Inheritance
Inheritance allows a class (child or subclass) to inherit properties and methods from another class.
```python
class parent:
	def __init__(self, inp_name):
		self.name = inp_name
	def Print(self):
		print("Hello from parent")

class child(parent):  # class child will inherit the constructor and method Print
	def Print(self):
		print("Hello from child")  # will overwrite the parent method Print for this class
```
### Polymorphism
Polymorphism allows different classes to define methods that are named the same but behave differently based on the caller object.
```python
class foo_1:
	def Greet(self):
		print("Greetings from foo_1 class")
class foo_2:
	def Greet(self):
		print("Greeting from foo_2 class")
# Both foo_1 and foo_2 have a method called Greet()

obj1 = foo_1()
obj2 = foo_2()
obj_list = [obj1, obj2]

for obj_itr in obj_list:  # Using polymorphism for the iterator
	obj_itr.Greet()
```
### Abstraction
Abstract classes in Python cannot be instantiated and are meant to be subclassed. They can define abstract methods that must be implemented by the subclasses.
```python
from abc import ABC, abstractmethod  # abstract classes library

class animal(ABC):  # abstract class
	@abstractmethod
	def Speak(self):
		pass

class dog(animal):
	def Speak(self):
		return "Bark"
```
#Python #OOP #Classes #Objects #Methods #Encapsulation #Inheritance #Polymorphism #Abstraction #AbstractClasses #Programming