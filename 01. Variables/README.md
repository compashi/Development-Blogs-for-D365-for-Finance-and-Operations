# Variables in X++

### Introduction 

A variable is a storage location paired with an identifier (name) which contains a value (known or unknown depending if it was initialized).

### Variable Names

The identifier (name) of the variable points to a memory location where information of a specific data type is stored. The syntax rules for variable names are as follows:

- Names must be limited to ASCII letters, digits, and the underscore character. All hex values with 0x7f and below are supported
- Letters can be either uppercased of lowercased
- Names are not case sensitive i.e. aa and AA are treated as the same name
- The first character must be either a letter or the underscore character
- Variable names can be thousands of characters long

According to Microsoft's convention, variable names should begin with a lowercase letter. Variables of specialized types should be named as:

> CustTable          custTable;
> CustInvoiceJournal custInvoiceJour;

The example shows how variables are declared in `myMethod`:

```x++
private void myMethod(int _num, str _myParameter2) 
{
	str I;
	str AxaptaAllowsVeryLongVariableNamesWhichTireOurFingers;
} 
```

### Naming Convention

The conventions are as follows:

- Variables of Primitive or composite data types should be named logically
- Specialized type variable should have the same name but starting with a lower case letter
- Prefix should added to distinguish between multiple variables that have the same specialized types
- One charactered variables should only be used for looping purposes

> int         i;               // Primitive data type
> MyObject    myObject;        // Self-defined class object
> CustTable   custTable;       // Specialized type 
> InvoiceJour invoiceJour;     // Specialized type

### Variable Declaration

Variable must be declared before it is used in any X++ statement. When a variable is declared, memory is allocated and is initialized to its default value, unless initialized. Exceptions may arise where the developer will need to dynamically allocate memory using the **new** method.

Variables can be declared and initialized with a value in the same statement, this allows the developer to save time and lines of code.

> real   pi           = 3.1415926539;
> Access accessObject = new Access();

X++ also allows multiple declaration i.e. a single statement to declare and initialize more than one variable.

> int i, j=0;
> int a[100, 5], b=1;

### Variable Scopes

A scope defines the area in which an item can be accessed:

- Instance variables which are declared in class declarations, can be accessed from any methods in the class, or from methods that extend the class
- Local variables can be accessed only in the block in which they were defined (variables created by developers have local scope)

```x++
class myClass 
{
	int myVariable;
	
	void myMethod()
	{
		int myMethodVariable;
	}
}
```

- `myVariable` is declared in `myClass`
- `myMethodVariable` is declared in `myMethod`
- `myMethod` can access both myVariable and `myMethodVariable`
- `myMethodVariable` can only be used in `myMethod`

### References

- [Variables](https://msdn.microsoft.com/en-us/library/aa871634.aspx?f=255&MSPPError=-2147217396)
- [Variable Names](https://msdn.microsoft.com/en-us/library/aa606689.aspx)
- [Naming Convention](https://msdn.microsoft.com/en-us/library/aa632638.aspx)
- [Variable Declaration](https://msdn.microsoft.com/en-us/library/aa598112.aspx)
- [Variable Scope](https://msdn.microsoft.com/en-us/library/aa624361.aspx)