Tuples are usually used for returning multiple read-only variables
## Declaration
```Python
test_tuple = (1,2,3,4)
type_tuple: tuple = (1,) # strongly typed; the tuple has a single element
```
### Constructor
```Python
tuple()
```
==IMPORTANT==: As tuples are **immutable** (you cannot change a tuple after it is created), the constructor should not be used unless an empty tuple must be returned.
## Characteristics
Tuples:
-**Immutable** (the elements cannot be changed after creation)
-Ordered
-Can have duplicates
-Indexed
-Can have different data types within a single tuple
## Methods
### count()
Syntax:
```Python
tuple.count(element)
```

Returns the number of occurrences of a specified element in the tuple.
```Python
count_tuple = (1,1,"a", [3,4], (7,"test"))
print(count_tuple.count(1)) # prints 2
```
### index()
Syntax:
```Python
tuple.index(element, start(optional), end(optional))
```

Returns the first index at which a specified element is found in the tuple. If the element is not found, it raises a *ValueError*.
```Python
index_tuple = (1,2,3,4,5)
print(index_tuple.index(2)) # prints 1
print(index_tuple.index(3, 1, 4)) # prints 2; searches between the indices 1 and 4
```

#Python #DataStructures #Tuples #SimpleDataStructures #Programming