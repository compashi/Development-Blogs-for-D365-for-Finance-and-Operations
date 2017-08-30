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

## References

- [Composite Data Types](https://msdn.microsoft.com/en-us/library/aa882886.aspx)
- [Array](https://msdn.microsoft.com/en-us/library/aa653716.aspx)