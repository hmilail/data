0
```
﻿coursera.org/learn/c-sharp-for-dot-net/supplement/Eknuj/learn-more-about-arrays-strings >> learn.microsoft.com/en-us/dotnet/csharp
/programming-guide/strings
coursera.org/learn/c-sharp-for-dot-net/supplement/Eknuj/learn-more-about-arrays-strings >> javatpoint.com/c-sharp-strings


…


C. sharp strings
In C sharp, string is an object of system dot string class that represent sequence of characters.
We can perform many operations on strings such as concatenation, comparison, getting substring, search, trim, replacement et cetera.
String versus string first character uppercase

```

1
```
In C. sharp, string (italicized) is keyword which is an alias for system dot string class.
That is why string and string first character uppercase are equivalent.
We are free to use any naming convention.
String S. one equals double quote hello double quote double slash creating string using string keyword

```

2
```
String first character uppercase S. two equals double quote welcome double quote semicolon slash slash creating string using string first character uppercase class
C sharp string example
Using system semicolon.
Public class string example.
Opening curly brace.

```

3
```
Public static void main opening parentheses string opening bracket closing bracket argos closing parentheses.
Opening curly brace.
String S. one equals double quote hello double quote semicolon.
Char opening bracket closing bracket C.H. equals opening curly brace single quote C. single quote comma single quote S. single quote comma single quote H. single quote comma single quote A. single quote comma single quote R. single quote comma single quote P. single quote closing curly brace semicolon.

```

4
```
String S. two equals new string opening parentheses C.H. closing parentheses semicolon.

```

5
```
Console dot write line opening parentheses S. one closing parentheses semicolon.
 Console dot write line opening parentheses S. two closing parentheses semicolon.
Closing curly brace.
Closing curly brace.
Output:
Hello.
C. sharp.
C. sharp string methods.
Method name, description.

```

6
```
Clone opening parentheses closing parentheses, it is used to return a reference to this instance of string.
Compare opening parentheses string comma string closing parentheses, it is used to compares two specified string objects.
It returns an integer that indicates their relative position in the sort order.
Compare ordinal opening parentheses string comma string closing parentheses, it is used to compare two specified string objects by evaluating the numeric values of the corresponding char objects in each string.

```

7
```
Compare to opening parentheses string closing parentheses, it is used to compare this instance with a specified string object.
It indicates whether this instance precedes, follows or appears in the same position in the sort order as the specified string.

```

8
```
Concat opening parentheses string comma string closing parentheses, it is used to concatenate two specified instances of string.
Contains opening parentheses string closing parentheses, it is used to return a value indicating whether a specified substring occurs within this string.

```

9
```
Copy opening parentheses string closing parentheses, it is used to create a new instance of string with the same value as a specified string.
Copy to opening parentheses I.N.T. thirty two comma char opening bracket closing bracket comma I.N.T. thirty two comma I.N.T. thirty two closing parentheses, it is used to copy a specified number of characters from a specified position in this instance to a specified position in an array of unicode characters.

```

10
```
Ends with opening parentheses string closing parentheses, it is used to check that the end of this string instance matches the specified string.

```

11
```
Equals opening parentheses string comma string closing parentheses, it is used to determine that two specified string objects have the same value
Format opening parentheses string comma object closing parentheses, it is used to replace one or more format items in a specified string with the string representation of a specified object

```

12
```
Get enumerator opening parentheses, it is used to retrieve an object that can iterate through the individual characters in this string.

```

13
```
Get hash code opening parentheses closing parentheses, it returns the hash code for this string.
Get type opening parentheses closing parentheses, it is used to get the type of the current instance.

```

14
```
Get type code opening parentheses closing parentheses, it is used to return the type code for class string.
Index of opening parentheses string closing parentheses, it is used to report the zero dash based index of the first occurrence of the specified string in this instance.

```

15
```
Insert opening parentheses I.N.T. thirty two comma string closing parentheses, it is used to return a new string in which a specified string is inserted at a specified index position.

```

16
```
Intern opening parentheses string closing parentheses, it is used to retrieve the system’s reference to the specified string.
Is interned opening parentheses string closing parentheses, it is used to retrieve a reference to a specified string.

```

17
```
Is normalized opening parentheses closing parentheses, it is used to indicate that this string is in unicode normalization from C.
Is null of empty opening parentheses string closing parentheses, it is used to indicate that the specified string is null (in bold text) or an empty string.

```

18
```
Is null or white space opening parentheses string closing parentheses, it is used to indicate whether a specified string is null (in bold text), empty, or consists only of white dash space characters.

```

19
```
Join opening parentheses string comma string opening bracket closing bracket closing parentheses, it is used to concatenate all the elements of a string array, using the specified separator between each element.

```

20
```
Last index of opening parentheses char closing parentheses, it is used to report the zero dash based index position of the last occurrence of a specified character within string.

```

21
```
Last index of any opening parentheses char opening bracket closing bracket closing parentheses, it is used to report the zero dash based index position of the last occurrence in this instance of one or more characters specified in a unicode array.

```

22
```
Normalize opening parentheses closing parentheses, it is used to return a new string whose textual value is the same as this string, but whose binary representation is in unicode normalization from C.

```

23
```
Pad left opening parentheses I.N.T. thirty two closing parentheses, it is used to return a new string that rights aligns the character in this instance by padding them with spaces on the left.

```

24
```
Pad right opening parentheses I.N.T. thirty two closing parentheses, it is used to return a new string that left dash aligns the characters in this string by padding them with spaces on the right.

```

25
```
Remove opening parentheses I.N.T. thirty two closing parentheses, it is used to return a new string in which all the characters in the current instance beginning at a specified position and continuing through the last position, have been deleted.

```

26
```
Replace opening parentheses string comma string closing parentheses, it is used to return a new string in which all occurrences of a specified string in the current instance are replaced with another specified string.

```

27
```
Split opening parentheses char opening bracket closing bracket closing parentheses, it is used to split a string into substrings that are based on the characters in an array.

```

28
```
Starts with opening parentheses string closing parentheses, it is used to czech whether the beginning of this string instance matches the specified string.

```

29
```
Substring opening parentheses I.N.T. thirty two closing parentheses, it is used to retrieve a substring from this instance.
The substring starts at a specified character position and continues to the end of the string.

```

30
```
To char array opening parentheses closing parentheses, it is used to copy the characters in this instance to a unicode character array.
To lower opening parentheses closing parentheses, it is used to convert string into lower case.

```

31
```
To lower invariant opening parentheses closing parentheses, it is used to return convert string into lower using the casing rules of the invariant culture.
To string opening parentheses closing parentheses, it is used to return instance of string.

```

32
```
To upper opening parentheses closing parentheses, it is used to convert string into uppercase.
Trim opening parentheses closing parentheses, it is used to remove all leading and trailing white dash space characters from the current string object.

```

33
```
Trim end char opening parentheses opening bracket closing bracket closing parentheses, it is used to remove all trailing occurrences of a set of characters specified in an array from the current string object.

```

34
```
Trim start opening parentheses opening parentheses opening bracket closing bracket closing parentheses, it is used to remove all leading occurrences of a set of characters specified in an array from the current string object

```

