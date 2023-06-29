0
```
strings and string literals
article
zero five slash two seven slash two zero two three
twenty two contributors
feedback
in this article
string versus system.string
declaring and initializing strings
immutability of strings
quoted string literals
show nine more
verbatim string literals
raw string literals
format strings
substrings
accessing individual characters
null strings and empty strings
using StringBuilder for fast string creation
strings, extension methods and LINQ
related articles
show less
a string is an object of type string whose value is text
internally, the text is stored as a sequential read dash only collection of char objects
there's no null dash terminating character at the end of a C sharp string; therefore a C sharp string can contain any number of embedded null characters (single quote backslash zero single quote)

```

1
```
the length property of a string represents the number of char objects it contains, not the number of unicode characters
to access the individual unicode code points in a string, use the stringinfo object
string versus system dot string
in C sharp, the string keyword is an alias for string; therefore, string and string are equivalent
it's recommended to use the provided alias string as it works even without using system semicolon
the string class provides many methods for safely creating, manipulating, and comparing strings
in addition, the C sharp language overloads some operators to simplify common string operations

```

2
```
for more information about the keyword, see string
for more information about the type and its methods, see string.
declaring and initializing strings
you can declare and initialize strings in various ways, as shown in the following example:
C sharp
copy
slash slash space declare without initializing new line
string space message one semicolon new line new line
slash slash space initialize to null new line
string space message two space equals space null semicolon new line new line
slash slash space initialize as an empty string new line
slash slash space use the empty constant instead of the literal double quote double quote new line
string space message three space equals space system first character uppercase dot string first character uppercase dot empty first character uppercase semicolon new line new line

```

3
```
slash slash space initialize with a regular string literal new line
string space old path first character uppercase space equals space double quote C. colon backslash backslash program first character uppercase space files first character uppercase backslash backslash microsoft first character uppercase space visual first character uppercase space studio first character uppercase eight point zero double quote semicolon new line new line
slash slash space initialize with a verbatim string literal new line
string space new path first character uppercase space equals space at sign double quote C. colon backslash program first character uppercase space files first character uppercase backslash microsoft first character uppercase space visual first character uppercase space  studio first character uppercase space nine point zero double quote semicolon new line new line

```

4
```
slash slash space use system dot string if you prefer new line
system first character uppercase dot string first character uppercase space greeting space equals space double quote hello first character uppercase space world first character uppercase exclamation mark double quote semicolon new line new line
slash slash space in local variables (I.E. within a method body) new line
slash slash space you can use implicit typing
V.A.R. space temp space equals space double quote uppercase I. single quote M. space still space a space strongly dash typed space system first character uppercase dot string first character uppercase exclamation mark double quote semicolon new line new line

```

5
```
slash slash space use a C.O.N.S.T. string to prevent single quote message four single quote from new line
slash slash space being used to store another string value new line
C.O.N.S.T. space string space message four space equals space double quote you space can single quote T. space get space rid space of space me exclamation mark double quote semicolon new line new line
slash slash space use the string constructor only when creating new line
slash slash space a string from a char asterisk, char opening bracket closing bracket, or S. byte asterisk see new line

```

6
```
slash slash space system dot string documentation for details new line
char opening bracket closing bracket space letters space equals space opening curly brace space single quote uppercase A. single quote comma space single quote uppercase B. single quote comma space single quote uppercase C. single quote space closing curly brace semicolon new line
string space alphabet space equals space new space string opening parentheses letters closing parentheses semicolon
you don't use the new operator to create a string object except when initializing the string with an array of chars
initialize a string with the empty constant value to create a new string object whose string is of zero length

```

7
```
the string literal representation of a zero dash length string is double quote double quote
by initializing strings with the empty value instead of null, you can reduce the chances of a null reference exception occurring
use the static is null or empty opening parentheses string closing parentheses method to verify the value of a string before you try to access it
immutability of strings
string objects are immutable: they can't be changed after they've been created
all of the string methods and C sharp operators that appear to modify a string actually return the results in a new string object
in the following example, when the contents of S. one and S. two are concatenated to form a single string, the two original strings are unmodified

```

8
```
the plus equals operator creates a new string that contains the combined contents
that new object is assigned to the variable S. one, and the original object that was assigned to S. one is released for garbage collection because no other variable holds a reference to it
C sharp
copy
string space S. one space equals space double quote uppercase A. space string space is space more space double quote semicolon new line
string space S. two space equals space double quote than space the space sum space of space its space chars perios double quote semicolon new line new line

```

9
```
slash slash space concatenate s1 and s2. this actually creates a new new line
slash slash space string object and stores it in S. one, releasing the new line
slash slash space reference to the original object new line
S. one space plus equals space S. two semicolon new line new line
system first character uppercase dot console first character uppercase dot write first character uppercase line first character uppercase opening parentheses S. one closing parentheses semicolon new line
slash slash space output: a string is more than the sum of its chars.
because a string "modification" is actually a new string creation, you must use caution when you create references to strings

```

10
```
if you create a reference to a string, and then "modify" the original string, the reference will continue to point to the original object instead of the new object that was created when the string was modified
the following code illustrates this behavior
C sharp
copy
string space S.T.R. one space equals space double quote hello first character uppercase space double quote semicolon new line
string space S.T.R. two space equals space S.T.R. one semicolon new line
S.T.R. one space plus equals space double quote world first character uppercase double quote semicolon new line new line
system first character uppercase dot console first character uppercase dot write first character uppercase line first character uppercase opening parentheses S.T.R. two closing parentheses semicolon new line

```

11
```
slash slash output: hello
for more information about how to create new strings that are based on modifications such as search and replace operations on the original string, see how to modify string contents.
quoted string literals
quoted string literals start and end with a single double quote character (double quote) on the same line
quoted string literals are best suited for strings that fit on a single line and don't include any escape sequences
a quoted string literal must embed escape characters, as shown in the following example:
C sharp
copy
string space columns space equals space double quote column first character uppercase space one backslash T. column first character uppercase space two backslash T. column first character uppercase space three double quote semicolon new line

```

12
```
slash slash output: column one column two column three new line new line
string space rows space equals space double quote row first character uppercase space one backslash R. backslash N. row first character uppercase space two backslash R. backslash N. row first character uppercase space three double quote semicolon new line
slash asterisk space output new line
row one new line
row two new line
row three new line
asterisk slash new line new line
string space title space equals space double quote backslash double quote the first character uppercase space backslash U. zero zero uppercase C. sic olean space harp first character uppercase backslash double quote comma space by space samuel first character uppercase space taylor first character uppercase space coleridge first character uppercase double quote semicolon semicolon new line

```

13
```
slash slash output: double quote the Æolean harp double quote, by samuel taylor coleridge
verbatim string literals
verbatim string literals are more convenient for multi dash line strings, strings that contain backslash characters, or embedded double quotes
verbatim strings preserve new line characters as part of the string text
use double quotation marks to embed a quotation mark inside a verbatim string
the following example shows some common uses for verbatim strings

```

14
```
C sharp
copy
string space title space equals space double quote backslash double quote the first character uppercase space backslash U. zero zero uppercase C. six olean space Harp first character uppercase backslash double quote comma space by space samuel first character uppercase space  taylor first character uppercase space coleridge first character uppercase double quote semicolon new line
slash slash output: double quote the Æolean harp double quote, by samuel taylor coleridge new line new line
string space file path first character uppercase space equals space at sign double quote uppercase C. colon backslash users first character uppercase backslash scoleridge backslash documents first character uppercase backslash double quote semicolon new line
slash slash output: C. colon backslash users backslash scoleridge backslash Documents backslash new line new line

```

15
```
string space text space equals space at sign double quote my first character uppercase space pensive space SARA all character uppercase space exclamation mark space thy space soft space cheek space reclined new line
indent thus first character uppercase space on space mine space arm comma space most space soothing space sweet space it space is new line
indent to first character uppercase space sit space beside space our space cot first character uppercase comma dot dot dot double quote semicolon new line
slash asterisk space output colon new line
my pensive sara exclamation mark thy soft cheek reclined new line
indent thus on mine arm, most soothing sweet it is new line

```

16
```
indent to sit beside our cot coma dot dot dot new line
asterisk slash new line new line
string space quote space equals space at sign double quote her first character uppercase space name space was space double quote double quote sara first character uppercase period double quote double quote double quote semicolon new line
slash slash output colon her name was double quote sara period double quote
raw string literals
beginning with C sharp eleven, you can use raw string literals to more easily create strings that are multi dash line, or use any characters requiring escape sequences
raw string literals remove the need to ever use escape sequences
you can write the string, including whitespace formatting, how you want it to appear in output

```

17
```
a raw string literal
starts and ends with a sequence of at least three double quote characters (double quote double quote double quote)
you're allowed more than three consecutive characters to start and end the sequence in order to support string literals that contain three (or more) repeated quote characters
single line raw string literals require the opening and closing quote characters on the same line
multi dash line raw string literals require both opening and closing quote characters on their own line
in multi dash line raw string literals, any whitespace to the left of the closing quotes is removed from all lines of the raw string literal
in multi dash line raw string literals, whitespace following the opening quote on the same line is ignored

```

18
```
in multi dash line raw string literals, whitespace only lines following the opening quote are included in the string literal
the following examples demonstrate these rules
C sharp
copy
string space single line first character uppercase space equals space double quote double quote double quote friends first character uppercase say double quote hello double quote as they pass by period double quote double quote double quote semicolon new line
string space multi line first character uppercase space equals space double quote double quote double quote new line
indent double quote hello first character uppercase space world first character uppercase exclamation mark double quote space is space typically space the space first space program space someone space writes period new line

```

19
```
indent double quote double quote double quote semicolon new line
string space embedded X.M.L. all character uppercase space equals space double quote double quote double quote new line
indent less than element space A.T.T.R. space equals space double quote content double quote greater than new line
indent indent less than body space style equals double quote normal double quote greater than new line
intent indent indent here first character uppercase space is space the space main space text new line
indent indent less than slash body greater than new line
indent indent less than footer greater than new line

```

20
```
indent indent indent excerpts first character uppercase space from space double quote an first character uppercase space amazing space story double quote new line
indent indent less than slash footer greater than new line
indent less than slash element space greater than new line
indent double quote double quote double quote semicolon new line
slash slash space the line double quote less than element A.T.T.R. equals double quote content double quote greater than double quote starts in the first column period new line
slash slash space all whitespace left of that column is removed from the string new line
string space raw string first character uppercase literal first character uppercase delimiter first character uppercase space equals space double quote double quote double quote double quote new line

```

21
```
indent raw first character uppercase space string space literals space are space delimited new line
indent by space a space string space of space at space least space three space double space quotes comma new line
indent like space this colon space double quote double quote double quote new line
indent double quote double quote double quote double quote semicolon
the following examples demonstrate the compiler errors reported based on these rules
C sharp
copy
slash slash space C.S. eight nine nine seven colon unterminated raw string literal period new line
V.A.R. space multi line first character uppercase start first character uppercase space equals space double quote double quote double quote this first character uppercase new line

```

22
```
indent is space the space beginning space of space a space string new line
indent double quote double quote double quote semicolon new line new line
slash slash space C.S. nine thousand colon raw string literal delimiter must be on its own line period new line
V.A.R. space multi line first character uppercase end first character uppercase space equals space double quote double quote double quote new line
indent this double quote space is space the space beginning space of space a space string space double quote double quote double quote semicolon new line new line
slash slash space C.S. eight nine nine nine colon line does not start with the same whitespace as the closing line new line

```

23
```
slash slash space of the raw string literal new line
V.A.R. space no out first character uppercase denting first character uppercase space equals space double quote double quote double quote new line
indent a first character uppercase space line space of space text period new line
trying first character uppercase space to space outdent space the space second space line period new line
indent double quote double quote double quote semicolon
the first two examples are invalid because multiline raw string literals require the opening and closing quote sequence on its own line
the third example is invalid because the text is outdented from the closing quote sequence

```

24
```
you should consider raw string literals when you're generating text that includes characters that require escape sequences when using quoted string literals or verbatim string literals
raw string literals will be easier for you and others to read because it will more closely resemble the output text
for example, consider the following code that includes a string of formatted J.S.O.N.
C sharp
copy
string space json string first character uppercase space equals space double quote double quote double quote new line
opening curly brace new line
half indent double quote date first character uppercase double quote colon space double quote twenty nineteen dash O. eight dash O. one uppercase T. zero zero colon zero zero colon zero zero dash O. seven colon zero zero double quote comma new line

```

25
```
half indent double quote temperature first character uppercase celsius first character uppercase double quote colon space twenty five comma new line
half indent double quote summary first character uppercase double quote colon space double quote hot first character uppercase double quote comma new line
half indent double quote dates first character uppercase available first character uppercase double quote colon space opening bracket new line
indent double quote twenty nineteen dash O. eight dash O. one uppercase T. zero zero colon zero zero colon zero zero dash O. seven colon zero zero double quote comma new line

```

26
```
indent double quote twenty nineteen dash O. eight dash zero two uppercase T. zero zero colon zero zero colon zero zero dash O. seven colon zero zero double quote comma new line
half indent closing bracket colon new line
half indent double quote temperature first character uppercase ranges first character uppercase double quote colon space opening curly brace new line
indent double quote cold first character uppercase colon space opening curly brace new line
indent half indent double quote high first character uppercase double quote colon space twenty comma new line
indent half indent double quote low first character uppercase double quote colon space minus ten new line

```

27
```
indent closing curly brace comma new line
indent double quote hot first character uppercase double quote comma space opening curly brace new line
indent half indent double quote high first character uppercase double quote colon space sixty comma new line
indent half indent double quote low first character uppercase double quote colon space twenty new line
indent closing curly brace new line
indent indent indent closing curly brace comma new line
half indent double quote sumamry first character uppercase words first character uppercase double quote colon space opening bracket new line
indent double quote cool first character uppercase double quote comma new line
indent double quote windy first character uppercase double quote comma new line

```

28
```
indent double qutoe humid first character uppercase double quotenew line
half indent closing bracket new line
closing curly brace new line
double quote double quote double quote semicolon
compare that text with the equivalent text in our sample on J.S.O.N. serialization, which doesn't make use of this new feature
string escape sequences
escape sequence character name unicode encoding
backslash single quote single quote zero X. zero zero twenty seven
backslash double quote double quote zero X. zero zero twenty two
backslash backslash backslash zero X. zero zero five C.
backslash zero null zero X. zero zero zero zero
backslash A. alert zero X. zero zero zero seven
backslash B. backspace zero X. zero zero zero eight

```

29
```
backslash F. form feed zero X. zero zero zero C.
backslash N. new line zero X. zero zero zero A.
backslash R. carriage return zero X. zero zero zero D.
backslash T. horizontal tab zero X. zero zero zero nine
backslash V. vertical tab zero X. zero zero zero eight
backslash U. unicode escape sequence (U.T.F. dash sixteen) backslash U. uppercase H. uppercase H. uppercase H. uppercase H. (range: zero zero zero zero to uppercase F. uppercase F. uppercase F. uppercase F.; example: backslash U. zero zero uppercase E. seven equals double quote ç double quote)
backslash U. unicode escape sequence (U.T.F. dash thirty two) backslash uppercase U. zero zero uppercase H. uppercase H. uppercase H. uppercase H. uppercase H. uppercase H. (range: zero zero zero zero zero zero to one zero uppercase F. uppercase F. uppercase F. uppercase F.; example: backslash uppercase U. zero zero zero one uppercase F. four seven uppercase D. equals double quote alien double quote)

```

30
```
backslash X. unicode escape sequence similar to double quote backslash U. double quote except with variable length backslash X. uppercase H. opening bracket uppercase H. closing bracket opening bracket uppercase H. closing bracket opening bracket uppercase H. closing bracket (range: zero to uppercase F. uppercase F. uppercase F. uppercase F.; example: backslash X. zero zero uppercase E. seven or backslash X. zero uppercase E. seven or backslash X. uppercase E. seven equals double quote ç double quote)

```

31
```
warning
when using the backslash X. escape sequence and specifying less than four hex digits, if the characters that immediately follow the escape sequence are valid hex digits (I.E. zero to nine, A. to F., and A. to F.), they will be interpreted as being part of the escape sequence

```

32
```
for example, backslash X. uppercase A. one produces double quote ¡ double quote, which is code point U. plus zero zero A. one
however, if the next character is double quote A double quote or double quote A. double quote, then the escape sequence will instead be interpreted as being backslash X. uppercase A. one uppercase A. and produce double quote ਚ double quote, which is code point U. plus zero A. one A.
in such cases, specifying all 4 hex digits (E.G. backslash X. zero zero uppercase A. one) will prevent any possible misinterpretation.

```

33
```
Note
at compile time, verbatim and raw strings are converted to ordinary strings with all the same escape sequences
therefore, if you view a verbatim or raw string in the debugger watch window, you will see the escape characters that were added by the compiler, not the verbatim or raw version from your source code
for example, the verbatim string at sign double quote uppercase C. colon backslash files dot T.X.T. double quote will appear in the watch window as double quote uppercase C. colon backslash backslash files dot T.X.T. double quote
format strings
a format string is a string whose contents are determined dynamically at run time

```

34
```
format strings are created by embedding interpolated expressions or placeholders inside of braces within a string
everything inside the braces (opening curly brace dot dot dot closing curly brace) will be resolved to a value and output as a formatted string at run time
there are two methods to create format strings: string interpolation and composite formatting
string interpolation
interpolated strings are identified by the dollar sign special character and include interpolated expressions in braces
if you're new to string interpolation, see the string interpolation - C sharp interactive tutorial for a quick overview
use string interpolation to improve the readability and maintainability of your code
string interpolation achieves the same results as the string dot format method, but improves ease of use and inline clarity

```

35
```
C sharp
copy
V.A.R. space J.H. space equals space opening parentheses first name first character uppercase colon space double quote jupiter first character uppercase double quote comma space last name first character uppercase colon space double quote hammon first character uppercase double quote comma space born colon space seventeen eleven comma space published colon space seventeen sixty one closing parentheses semicolon new line
console first character uppercase dot write first character uppercase line first character uppercase opening parentheses dollar sign double quote opening curly brace J.H. dot first name first character uppercase closing curly brace space opening curly brace J.H. dot last name first character uppercase closing curly brace space was space an space african first character uppercase space american first character uppercase space poet space born space in space opening curly brace J.H. dot born closing curly brace period double quote closing parentheses semicolon new line

```

36
```
console first character uppercase dot write first character uppercase line first character uppercase opening parentheses dollar sign double quote he first character uppercase space was space first space published space in space opening curly brace J.H. dot published closing curly brace space at space the space age space of space opening curly brace J.H. dot published space dash space J.H. dot born closing curly brace period double quote closing parentheses semicolon new line

```

37
```
console first character uppercase dot write first character uppercase line first character uppercase opening parentheses dollar sign double quote he first character uppercase single quote D. space be space over space opening curly brace math first character uppercase dot round first character uppercase opening parentheses opening parentheses twenty eighteen D. space dash space J.H. born closing parentheses space slash space one hundred D. closing parentheses space asterisk space one hundred D. closing curly brace space years space old space today period double quote closing parentheses semicolon new line new line

```

38
```
slash slash space output colon new line
slash slash space jupiter hammon was an affrican american poet born in seventeen eleven period new line
slash slash space he was first published in seventeen sixty one at the age of fifty period new line

```

39
```
slash slash space he'd be over three hundred years old today period
beginning with C sharp ten, you can use string interpolation to initialize a constant string when all expressions used for placeholders are also constant strings.
beginning in C sharp eleven, you can combine raw string literals with string interpolations
you start and end the format string with three or more successive double quotes
if your output string should contain the opening curly brace or closing curly brace character, you can use extra dollar sign characters to specify how many opening curly brace and closing curly brace characters start and end an interpolation
any sequence of fewer opening curly brace or closing curly brace characters is included in the outpu

```

40
```
the following example shows how you can use that feature to display the distance of a point from the origin, and place the point inside braces
C sharp
copy
I.N.T. space uppercase X. space equals space two semicolon new line
I.N.T. space uppercase Y. space equals space three semicolon new line new line
V.A.R. space point message first character uppercase space equals space dollar sign dollar sign double quote double quote the first character uppercase space point space opening curly brace opening curly brace opening curly brace upper case X. closing curly brace closing curly brace comma space opening curly brace opening curly brace uppercase U. closing curly brace closing curly brace closing curly brace space is space opening curly brace opening curly brace math first character uppercase dot S.Q.R.T. first character uppercase opening parentheses uppercase X. space asterisk space uppercase X. space plus space uppercase Y. space asterisk space uppercase Y. closing parentheses closing curly brace closing curly brace space from space the space origin period double quote double quote double quote semicolon new line new line

```

41
```
console first character uppercase dot write first character uppercase line first character uppercase opening parentheses point message first character uppercase closing parentheses semicolon new line

```

42
```
slash slash space output colon new line
slash slash space the point opening curly brace two comma three closing curly brace is three point six O. five five five one two seven five four six three nine eight nine from the origin period
verbatim string interpolation
C sharp also allows verbatim string interpolation, for example across multiple lines, using dollar sign at sign or at sign dollar sign syntax
to interpret escape sequences literally, use a verbatim string literal
an interpolated verbatim string starts with the dollar wign
character followed by the at sign character
you can use the dollar sign and the at sign tokens in any order: both dollar sign at sign double quote dot dot dot double quote and at sign dollar sign double quote dot dot dot double quote are valid interpolated verbatim strings

```

43
```
C sharp
copy
V.A.R. space J.H. space equals space opening parentheses first name first character uppercase colon space double quote jupiter first character uppercase double quote comma space last name first character uppercase colon space double quote hammon first character uppercase double quote comma space born colon space seventeen eleven comma space published colon space seventeen sixty one closing parentheses semicolon new line
console first character uppercase dot write first character uppercase line first character uppercase opening parentheses dollar sign double quote opening curly brace J.H. dot first name first character uppercase closing curly brace space opening curly brace J.H. dot last name first character uppercase closing curly brace new line

```

44
```
indent was space an space african first character uppercase space american first character uppercase space poet space born space in space opening curly brace J.H. dot born closing curly brace period double quote closing parentheses semicolon new line
console first character uppercase dot write first character uppercase line first character uppercase opening parentheses dollar sign double quote he first character uppercase space was space first space published space in space opening curly brace J.H. dot published closing curly brace space at space the space age space of space opening curly brace J.H. dot published space dash space J.H. dot born closing curly brace period double quote closing parentheses semicolon new line

```

45
```
console first character uppercase dot write first character uppercase line first character uppercase opening parentheses dollar sign double quote he first character uppercase single quote D. space be space over space opening curly brace math first character uppercase dot round first character uppercase opening parentheses opening parentheses twenty eighteen D. space dash space J.H. born closing parentheses space slash space one hundred D. closing parentheses space asterisk space one hundred D. closing curly brace space years space old space today period double quote closing parentheses semicolon new line new line

```

46
```
slash slash space output colon new line
slash slash space jupiter hammon new line
slash slash space indent was an affrican american poet born in seventeen eleven period new line
slash slash space he was first published in seventeen sixty one new line

```

47
```
slash slash space at the age of fifty period
composite formatting
the string dot format utilizes placeholders in braces to create a format string
this example results in similar output to the string interpolation method used above
C sharp
copy
V.A.R. space P.W. space equals space opening parentheses first name first character uppercase colon space double quote phillis first character uppercase double quote comma space last name first character uppercase colon space double quote wheatley first character uppercase double quote comma space born colon space seventeen fifty three comma space published colon space seventeen seventy three closing parentheses semicolon new line
console first character uppercase dot write first character uppercase line first character uppercase opening parentheses double quote opening curly brace zero closing curly brace space opening curly brace one closing curly brace space was space an space african first character uppercase space american first character uppercase space poet space born space in space opening curly brace two closing curly brace period double quote comma space P.W. dot first name first character uppercase comma space P.W. dot last name first character uppercase comma space P.W. dot born closing parentheses semicolon new line

```

48
```
console first character uppercase dot write first character uppercase line first character uppercase opening parentheses double quote she first character uppercase space was space first space published space in space opening curly brace zero closing curly brace space at space the space age space of space opening curly brace one closing curly brace period double quote comma space P.W. dot published comma space P.W. dot published space dash space P.W. dot born closing parentheses semicolon new line

```

49
```
console first character uppercase dot write first character uppercase line first character uppercase opening parentheses double quote she first character uppercase single quote D. space be space over space opening curly brace zero closing curly brace space years space old space today period double quote comma space math first character uppercase dot round first character uppercase opening parentheses opening parentheses twenty eighty D. space dash space P.W. dot born closing parentheses space slash space one hundred D. closing parentheses space asterisk space one hundred D. closing parentheses semicolon new line new line

```

50
```
slash slash space output space new line
slash slash space phillis wheatley was an african american poet born in seventeen fifty three period new line
slash slash space she was first published in seventeen seventy three at the age of twenty period new line

```

51
```
slash slash space she'd be over three hundred years old today period
for more information on formatting dot net types, see formatting types in dot net
substrings
a substring is any sequence of characters that is contained in a string
use the substring method to create a new string from a part of the original string
you can search for one or more occurrences of a substring by using the index of method
use the Replace method to replace all occurrences of a specified substring with a new string
like the substring method, replace actually returns a new string and doesn't modify the original string
for more information, see how to search strings and how to modify string contents

```

52
```
C sharp
copy
string space S. three space equals space double quote visual first character uppercase space C sharp space express first character uppercase double quote semicolon new line
system first character uppercase dot console first character uppercase dot write first character uppercase line first character uppercase opening parentheses S. three dot substring first character uppercase opening parentheses seven comma space two closing parentheses closing parentheses semicolon new line
slash slash space output colon double quote C sharp double quote new line new line
system first character uppercase dot console first character uppercase dot write first character uppercase line first character uppercase opening parentheses S. three dot replace first character uppercase opening parentheses double quote C sharp double quote comma space double quote basic first character uppercase double quote closing parentheses closing parentheses semicolon new line

```

53
```
slash slash space output colon double quote visual basic express double quote new line new line
slash slash space index values are zero dash based new line
I.N.T. space index space equals space S. three dot index first character uppercase of first character uppercase opening parentheses double quote uppercase C. double quote closing parentheses semicolon new line
slash slash space index space equals space seven new line
accessing individual characters
you can use array notation with an index value to acquire read dash only access to individual characters, as in the following example

```

54
```
C sharp
copy
string space s five space equals space double quote printing first character uppercase space backwards double quote semicolon new line new line
for space opening parentheses I.N.T. space I. space equals space zero semicolon space I. space less than space S. five dot length first character uppercase semicolon space I. plus plus closing parentheses new line
opening curly brace new line
indent system first character uppercase dot console first character uppercase dot write first character uppercase opening parentheses S. five opening bracket S. five dot length first character uppercase space dash space I. space dash space one closing bracket closing parentheses semicolon new line

```

55
```
closing curly brace
slash slash space output colon double quote S. draw K. cab G.N. it N.I.R.P. double quote
if the string methods don't provide the functionality that you must have to modify individual characters in a string, you can use a string builder object to modify the individual chars double quote in dash place double quote, and then create a new string to store the results by using the string builder methods
in the following example, assume that you must modify the original string in a particular way and then store the results for future use

```

56
```
C sharp
copy
string space question space equals space double quote H. uppercase O. uppercase W. space does all character uppercase space M. uppercase I. uppercase C. uppercase R. uppercase O. uppercase S. uppercase O. uppercase F. uppercase T. space W. uppercase W. uppercase R. uppercase D. space deal all character uppercase space with all character uppercase space the all character uppercase space C. uppercase A. uppercase P. uppercase S. space L. uppercase O. uppercase C. uppercase K. space key all character uppercase question mark double quote semicolon new line
system first character uppercase dot text first character uppercase dot string first character uppercase builder first character uppercase space S.B. space equals space new space system first character uppercase dot text first character uppercase dot string first character uppercase builder first character uppercase opening parentheses question closing parentheses semicolon new line new line

```

57
```
for space opening parentheses I.N.T. space J. space equals space zero semicolon space J. space less than space S.B. dot lentgh first character uppercase semicolon space J. plus plus closing parentheses new line
opening curly brace new line
indent if space opening parentheses system first character uppercase dot char first character uppercase dot is first character uppercase lower first character uppercase opening parentheses S.B. opening bracket J. closing bracket closing parentheses space equals equals space true closing parentheses new line

```

58
```
indent indent S.B. opening bracket J. closing bracket space equals space system first character uppercase dot char first character uppercase dot to first character uppercase upper first character uppercase opening parentheses S.B. opening bracket J. closing bracket closing parentheses semicolon new line
indent else space if space opening parentheses system first character uppercase dot char first character uppercase dot is first character uppercase upper first character uppercase opening parentheses S.B. opening bracket J. closing bracket closing parentheses space equals equals space true closing parentheses new line

```

59
```
indent indent S.B. opening bracket J. closing bracket space equals space system first character uppercase dot char first character uppercase dot to first character uppercase lower first character uppercase opening parentheses S.B. opening bracket J. closing bracket closing parentheses semicolon new line
closing curly brace new line
slash slash space store the new string period new line
string space corrected space equals space S.B. dot to first character uppercase string first character uppercase opening parentheses semicolon new line
system first character uppercase dot console first character uppercase dot write first character uppercase line first character uppercase opening parentheses corrected closing parentheses semicolon new line

```

60
```
slash slash space output colon how does microsoft word deal with the caps lock key
null strings and empty strings
an empty string is an instance of a system dot string object that contains zero characters
empty strings are used often in various programming scenarios to represent a blank text field
you can call methods on empty strings because they're valid system dot string objects
empty strings are initialized as follows
C sharp
copy
string space s space equals space string first character uppercase dot empty semicolon new line
by contrast, a null string doesn't refer to an instance of a system dot string object and any attempt to call a method on a null string causes a null reference exception

```

61
```
However, you can use null strings in concatenation and comparison operations with other strings
The following examples illustrate some cases in which a reference to a null string does and doesn't cause an exception to be thrown
C sharp
copy
string space S.T.R. space equals space double quote hello double quote semicolon new line
string space null S.T.R. first character uppercase space equals space null semicolon new line
string space empty S.T.R. first character uppercase space equals space string first character uppercase dot empty first character uppercase semicolon new line new line
string space temp S.T.R. first character uppercase space equals space S.T.R. space plus space null S.T.R. first character uppercase semicolon new line

```

62
```
slash slash space output of the following line colon hello
console first character uppercase dot write first character uppercase line first character uppercase opening parentheses temp S.T.R. first character uppercase closing parentheses semicolon new line new line
bool space B. space equals space opening parentheses empty S.T.R. first character uppercase space equals equals space null S.T.R. first character uppercase closing parentheses semicolon new line
slash slash space output of the following line: false
console first character uppercase dot write first character uppercase line first character uppercase opening parentheses B. closing parentheses semicolon new line
slash slash space the following line creates a new empty string period

```

63
```
string space new S.T.R. first character uppercase space equals space empty S.T.R. first character uppercase space plus space null S.T.R. first character uppercase semicolon new line new line
slash slash space null strings and empty strings behave differently. the following new line
slash slash space two lines display zero period
console first character uppercase dot write first character uppercase line first character uppercase opening parentheses empty S.T.R. first character uppercase dot length first character uppercase closing parentheses semicolon new line
console first character uppercase dot write first character uppercase line first character uppercase opening parentheses new S.T.R. first character uppercase dot length first character uppercase parentheses semicolon new line
slash slash space the following line raises a null reference exception period

```

64
```
slash slash console dot write line opening parentheses null S.T.R. dot length closing parentheses semicolon new line new line
slash slash space the null character can be displayed and counted comma like other chars period new line
string space S. one space equals double quote backslash X. zero double quote space plus space double quote A.B.C. double quote semicolon new line
string space S. two space equals space double quote A.B.C. double quote space plus space double quote backslash X. zero double quote semicolon new line
slash slash space output of the following line colon asterisk A.B.C. asterisk new line
console first character uppercase dot write first character uppercase line first character uppercase opening parentheses double quote asterisk double quote space plus space S. one space plus space double quote asterisk double quote closing parentheses semicolon new line

```

65
```
slash slash space output of the following line colon asterisk A.B.C. asterisk new line
console first character uppercase dot write first character uppercase line first character uppercase opening parentheses double quote asterisk double quote space plus space S. two space pls space double quote asterisk double quote closing parentheses semicolon new line
slash slash space output of the following line: four
console first character uppercase dot write first character uppercase line first character uppercase opening parentheses S. two dot length first character uppercase closing parentheses semicolon
using string builder for fast string creation

```

66
```
string operations in dot net are highly optimized and in most cases don't significantly impact performance
however, in some scenarios such as tight loops that are executing many hundreds or thousands of times, string operations can affect performance
the string builder class creates a string buffer that offers better performance if your program performs many string manipulations
the string builder string also enables you to reassign individual characters, something the built dash in string data type doesn't support
this code, for example, changes the content of a string without creating a new string
C sharp
copy

system first character uppercase dot text first character uppercase dot string first character uppercase builder first character uppercase space S.B. space equals space new space system first character uppercase dot text first character uppercase dot string first character uppercase builder first character uppercase opening parentheses double quote rat first character uppercase colon space the space ideal space pet double quote closing parentheses semicolon new line

```

67
```
S.B. opening bracket zero closing bracket space equals space single quote uppercase C. single quote semicolon new line
system first character uppercase dot console first character uppercase dot write first character uppercase line first character uppercase opening parentheses S.B. dot to first character uppercase string first character uppercase opening parentheses closing parentheses closing parentheses semicolon new line
slash slash outputs cat colon the ideal pet

```

68
```
in this example, a string builder object is used to create a string from a set of numeric types
C sharp
copy
V.A.R. space S.B. space equals space new space string first character uppercase builder first character uppercase opening parentheses closing parentheses semicolon new line new line
slash slash space create a string composed of numbers zero to nine new line
for space opening parentheses I.N.T. space I. space equals space zero semicolon space I. space less than space ten semicolon space I plus plus closing parentheses new line
opening curly brace new line
indent S.B. dot append first character uppercase opening parentheses I. dot to first character uppercase string first character uppercase opening parentheses closing parentheses closing parentheses semicolon new line

```

69
```
closing curly brace new line
console first character uppercase dot write first character uppercase line first character uppercase opening parentheses S.B. closing parentheses semicolon space space slash slash space displays zero one two three four five six seven eigtht nine new line new line
slash slash space copy one character of the string (not possible with a system dot string) new line
S.B. opening bracket zero closing bracket space equals space S.B. opening bracket nine closing bracket semicolon new line new line
console first character uppercase dot write first character uppercase line first character uppercase opening parentheses S.B. closing parentheses space space slash slash space displays nine one two three four five six seven eight nine

```

70
```
strings, extension methods and L.I.N.Q.
because the string type implements I. enumerable less than T. greater than, you can use the extension methods defined in the enumerable class on strings
to avoid visual clutter, these methods are excluded from intellisense for the string type, but they're available nevertheless
you can also use L.I.N.Q. query expressions on strings
for more information, see L.I.N.Q. and strings
related articles
how to modify string contents: illustrates to transform strings and modify the contents of strings
how to compare strings: shows how to perform ordinal and culture specific comparisions of strings

```

71
```
how to concatenate multiple strings: demonstrates various ways to join multiple strings into one
how to parse strings using string dot split: contains code examples that illustrate how to use the string dot split method to parse strings
how to search strings: explains how to use search for specific text or pattern in strings
how to determine whether a string represents a numeric value: shows how to safely parse a string to see whether it has a valid numeric value
string interpolation: describes the string interpolation feature that provieds a convenient syntax to format strings
basic string operations: provides links to articles that use system dot string and system dot text dot string builder methods to perform basic string operations

```

72
```
parsing strings: describes how to convert string representations of dot net base types to instances of the corresponding types
parsing date and time strings in dot net: shows how to convert a string such as double quote zero one slash twenty four slash twenty O. eight double quote to a system dot date time object
comparing strings: includes information about how to compare strings and provides examples in C sharp and visual basic
using the string builder class: describes how to create and modify dynamic string objects by using the string builder class
L.I.N.Q. and strings: provides information about how to perform various string operations by using L.I.N.Q. querie

```

