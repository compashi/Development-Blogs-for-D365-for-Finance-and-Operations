# Composite Data Types

## Introduction 

The composite data types in X++ are listed in the following table:

| Composite Data Types    | Description |
| ----------------------- | ----------- |
| Arrays                  | List of sequential data of the same type and name, seperated by indexes |
| Containers              | Dynamic list of items containing primitive or composite data types |
| Classes as Data Types   | Blue print for an object that describes varables and methods for instances (object) of the `class` |
| Delegates as Data Types | Delegate collects methods that subscribe to it. It specifies the signature that must be shared by its subscribers. A delegate when called, calls each of its subscriber. |
| Tables as Data Types    | A database instance to hold fields and handle `class` definitions |
| Collections             | Allows the user to create `arrays`, `lists`, `sets`, `maps`, and `structs` that can hold any data type or objects |

### Arrays

An array is a collection of variables that are all of the same type. Values are looked up using indexes. Each index represents a unique cell/variable. Seperate statements are used to initialize each cell/variable of an array.

X++ has three kinds of arrays:

- Dynamic
- Fixed-length
- Partly on disk

Even though X++ supports one-dimensional arrays, there are workarounds to work with multi-dimensional arrays.

One important thing to note with arrays in X++ is that its starting index is set to 1 rather than 0 as with other programming languages as Java or C#. The following snippets show how to work with arrays in X++.

```c++
int myArray[5];    // Array declaration, a total of 10 int varaibles can be stored in a sequence

myArray[1] = 10;    // Array cell initialization [10, 0, 0, 0, 0]

int value = myArray[4];     // Array cell referencing
```

The following example shows how dynamic arrays can be used:

```c++
int dynamicArray[];     // undefinite length array
```

The following example shows how fixed length arrays can be used:

```c++
str fixedLengthArray[100];      // 100 string cell fixed length array
```

The following example shows how partly on disk arrays can be used:

```c++
int only5CellsInMemory[100, 5];     // 100 int cell, among which 5 indexes will be in memory, rest 95 on disk

boolean dynamicInMemoryArray[, 100];    // 100 indexes in memory in a dynamic array
```

### Multi-Dimensional Array

Languages such as Java, C++, C# or others allow creation of multi-dimensional arrays i.e. array or arrays. This is not the case with X++, they only work with one-dimensional array. One way to exploit one-dimensional array is to look at how 2D array can be represented as 1D array, as the case with pointers in C++.

```c++
real array2D[10][3];    // C++ declaration of 2D array, an array has 10 arrays, each with size 3 i.e. 10 rows, 3 columns

real array1D[10 * 3];   // 10 rows * 3 columns = 30 cells, conversion of 2D into 1D array
```

If we look at the indexing of a 2D array we get the following for X++ based indexing (note that in X++, indexing starts at with index value 1):

```c++
[( 1,1) ( 1,2) ( 1,3)]
[( 2,1) ( 2,2) ( 2,3)]
       .....
[( 9,1) ( 9,2) ( 9,3)]
[(10,1) (10,2) (10,3)]
```

This can be see as the following in a 1D array:

```c++
[ 1  2  3]
[ 4  5  6]
[ 7  8  9]
    ...
[25 26 27]
[28 29 30]
```

Therefore the array[i][j] can be represented using the formula array[(i-1)*j + j], this allows downcasting of a 2D array into a 1D array.

To use dimensions of greater than 2, similar steps have to be performed to carry them out in a one-dimensional array.

## References

- [Composite Data Types](https://msdn.microsoft.com/en-us/library/aa882886.aspx)
- [Array](https://msdn.microsoft.com/en-us/library/aa653716.aspx)
- [Multiple Array Indexes](https://msdn.microsoft.com/en-us/library/aa673457.aspx)