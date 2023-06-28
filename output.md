0
```
further reading on conditional statements
operators
C sharp provides a number of operators
many of them are supported by the built dash in types and allow you to perform basic operations with values of those types
those operators include the following groups
arithmetic operators that perform arithmetic operations with numeric operands
comparison operators that compare numeric operands
boolean logical operators that perform logical operations with bool operands
bitwise and shift operators that perform bitwise or shift operations with operands of the integral types
equality operators that check if their operands are equal or not
read more

...

C sharp operators and expressions
article
zero three slash zero nine slash two zero two three
in this article
operator precedence
operator associativity
operand evaluation
C sharp language specification

```

1
```
see also
C sharp provides a number of operator
many of them are supported by the built dash in types and allow you to perform basic operations with values of those types
those operators include the following groups
arithmetic operators that perform arithmetic operations with numeric operands
comparision operators that compare numeric operands
boolean logical operators that perform logical operations with bool operands
bitwise and shift operators that perform bitwise or shift operations with operands of the integral types
equality operators that check if their operands are equal or not
typically, you can overload those operators, that is, specify the operator behavior for the operands of a user dash defined type
the simplest C sharp expressions are literals (for example, integer and real numbers) and names of variables

```

2
```
you can combine them into complex expressions by using operators
operator precedence and associativity determine the order in which the operations in an expression are performed
you can use parentheses to change the order of evaluation imposed by operator precedence and associativity
in the following code, examples of expressions are at the right dash hand side of assignments
C sharp
copy
INT space A comma space B comma space C semicolon new line
A space equals space seven semicolon new line
b space equals space A semicolon new line
C space equals space B plus plus semicolon new line
b space equals space A space plus space B space asterisk space C semicolon new line

```

3
```
C space equals space A space greater than equals one hundred space question mark space B space colon space C space slash space ten semicolon new line
a space equals space opening parentheses INT closing parentheses uppercase M ath dot uppercase S QRT opening parentheses B space asterisk space B space plus space C space asterisk space C closing parentheses semicolon new line new line
string space S space equals space double quote uppercase S T ring space literal double quote semicolon new line
char space L space equals S opening bracket S dot length space minus space one closing bracket semicolon new line new line
VAR space numbers space equals space new space uppercase L ist less than INT greater than opening parentheses new opening bracket closing bracket space opneing curly brace space one comma space two comma space three space closing curly brace closing parentheses semicolon new line

```

4
```
b space equals space numbers dot uppercase F ind uppercase L ast opening parentheses N space equal greater than space N space greater than space one closing parentheses semicolon
typically, an expression produces a result and can be included in another expression
a void method call is an example of an expression that doesn't product a result
it can be used only as a statement as the following example shows
C sharp
copy
uppercase C onsole dot uppercase W rite line opening parentheses double quote uppercase H ello comma space world exclamation mark double quote closing parentheses semicolon

```

5
```
here are some other kinds of expressions that C sharp provides
interpolated string expressions that provide convenient syntax to create formatted string
C sharp
copy
run
VAR space R space equals space two point three semicolon new line
VAR space message space equals space dollar sign double quote uppercase T he area of a circle with radius space opening curly brace R closing curly brace is space opening curly brace uppercase M ath dot uppercase P uppercase I space asterisk space R space asterisk space R colon uppercase F three closing curly brace dot double quote semicolon new line
uppercase C onsole dot uppercase W rite uppercase L ine opening parentheses message closing parentheses semicolon new line

```

6
```
slash slash space uppercase O utput colon new line
slash slash space uppercase T he area of a circle with radius two point three is sixteen point six one nine period
lambda expressions that allow you to create anonymous functions
C sharp
copy
run
INT opening bracket closing bracket space numbers space equals space opening curly brace space two comma space three comma space four comma space five space closing curly brace semicolon new line
VAR space maximum uppercase S quare space equals space numbers dot uppercase M ax opening parentheses X space equals greater space X space asterisk space X closing parentheses semicolon new line
uppercase C onsole dot uppercase W riteline opening parentheses maximum uppercase S quare closing parentheses semicolon new line

```

7
```
slash slash space uppercase O utput colon new line
slash slash space twenty five
query expressions that allow you to use query capabilities directly in C sharp
C sharp
copy
run
VAR space scores space equals space new opening bracket closing curly bracket space opening curly brace space ninety comma space ninety seven comma space seventy eight comma space sixty comma space eighty five space closing curly brace semicolon new line
uppercase I uppercase E numerable less than INT greater than space high uppercase S cores uppercase Q uery space equals new line
indent from space score space in space scores new line
indent where space score space greater than eighty new line

```

8
```
indent order by space score space descending new line
indent select space score semicolon new line
uppercase C onsole dot uppercase W rite uppercase L ine opening parentheses string dot uppercase J oin opening parentheses double quote space double quote comma space high uppercase S cores uppercase Q uery closing parentheses closing parentheses semicolon new line
slash slash space uppercase O utput colon new line
slash slash space ninety seven ninety eighty five new line
you can use an expression body definition to provide a concise definition for a method, constructor, property, indexer, or finalizer
operator precedence
in an expression with multiple operators, the operators with higher precedence are evaluated before the operators with lower precedence

```

9
```
in the following example, the multiplication is performed first becase it has higher precedence than addition
C sharp copy run
VAR space A space equals space two space plus space two space asterisk space two semicolon new line
uppercase C onsole dot uppercase W rite uppercase L ine opening parentheses A closing parentheses semicolon space slash slash space space output colon space six
use parentheses to change the order of evaluation imposed by operator precedence
C sharp
copy
run
VAR space A space equals space opening parentheses two space plus space two closing parentheses space asterisk space two semicolon new line
uppercase C onsole dot uppercase W rite uppercase L ine opening parentheses A closing parentheses semicolon space slash slash space space output colon space eight

```

10
```
the following table lists the C sharp operators starting with the highest precedence to the lowest
the operators within each row have the same precedence
operators
category or names
X dot y, f opening parentheses X closing parentheses, a opening bracket I closing bracket, X question mark dot Y, X question mark opening bracket Y closing bracket, X plus plus, X minus minus, X exclamation mark, new, type of, checked, unchecked, default, name of, delegate, size of, stack ALLOC, X dash greater than Y
primary
plus X, minus X, exclamation mark X, tilde X, plus plus X, minus minus X, caret X, opening parentheses T closing parentheses X, await, ampersand X, asterisk X, true and false

```

11
```
unary
X dot dot Y
range
switch, with
switch and with expressions
X space asterisk space Y, X space slash space Y, S space percentage space Y
multiplicative
X space plus space Y, space space minus space Y
additive
X space less than less than space Y, X space greater than greater than Y, X greater than greater than greater than Y
shift
X space less than space Y, X space greater than space Y, X space less than equals space Y, X space greater than space Y, is, as
relational and type dash testing

```

12
```
X space equals equals space Y, X space exclamation mark space Y
equality
X space ampersand space Y
boolean logical AND or bitwise logical AND
X space caret space Y
boolean logical XOR or bitwise logical XOR
X space pipe space Y
boolean logical OR or bitwise logical OR
X space ampersand ampersand space Y
conditional AND
X space pipe pipe space Y
conditional OR
X space question mark question mark space Y
null dash coalescing operator
C space question mark space T space colon space F
conditional operator
X space equals space Y, X space plus equals space Y, X space minus equals space Y, X space asterisk equals space Y, X space slash equals space Y, X space percentage equals space Y, X space ampersand equals space Y, X space pipe equals space Y, X space caret equals space Y, X space less than less than equals space Y, X space greater than greater than equals space Y, X space greater than greater than greater than equals space Y, X space question mark question mark equals space Y, equals greater than

```

13
```
assignment and lambda declaration
operator associativity
when operators have the same precedence, associativity of the operators determines the order in which the operations are performed
left dash associative operators are evaluated in order from left to right

```

14
```
except for the assignment operators and the null dash coalescing operators, all binary operators are left dash associative
for example, A space plus space B space minus space C is evaluated as opening parentheses A space plus space space B closing parentheses space minus space C
right dash associative operators are evaluated in order from right to left
the assignment operators, the null dash coalescing operators, lambdas, and the conditional operator question mark colon are right dash associative
for example, x space equals space Y space equals space Z is evaluated as X space equals space opening parentheses y space equals space Z closing parentheses
important
in an expression of the form uppercase P question mark dot uppercase A zero question mark dot uppercase A one, if uppercase P is null, neither uppercase A zero nor uppercase A one are evaluated

```

15
```
similarly, in an expression of the form uppercase P question mark dot uppercase A zero dot uppercase A one, because A zero isn't evaluated when uppercase P is null, neither is uppercase A zero dot uppercase A one
see the C sharp language specification for more details
use parentheses to change the order of evaluation imposed by operator associativity
C sharp
copy
run
INT space A space equals space thirteen space slash space five space slash space two semicolon new line
INT space B space equals space thirteen space slash space opening parentheses five space slash space two closing parentheses semicolon new line

```

16
```
uppercase C onsole dot uppercase W rite uppercase L ine opening parentheses dollar sign double quote A space equals space opening curly brace A closing curly brace comma space B space equals space opening curly brace B closing curly brace double quote closing parentheses semicolon space space slash slash space output colon space A space equals space one comma space B space equals space six
operand evaluation
unrelated to operator precedence and associativity, operands in an expression are evaluated from left to right.
the following examples demonstrate the order in which operators and operands are evaluated
expression
order of evaluation
A space plus space B

```

17
```
A, B, plus
A space plus space B space asterisk space C
A, B, C, asterisk, plus
A space slash space B space plus space C space asterisk space D
A, B, slash, C, D, asterisk, plus
A space slash space opening parentheses B space plus space C closing parentheses space asterisk space D
A, B, D, plus, slash, D, asterisk
typically, all operator operands are evaluated
however, some operators evaluate operands conditionally
that is, the value of the leftmost operand of such an operator defines if (or which) other operands should be evaluated
these operators are the conditional logical AND (ampersand amersand) OR (pipe pipe) operators, the null dash coalescing operators question mark question mark and question mark question mark equals, the null dash conditional operators question mark

```

18
```
and question mark opening bracket closing bracket, and the conditional operator question mark colon
for more information, see the description of each operator
C sharp language specification
for more information, see the following sections of the C sharp language specification
expressions
operators
see also
C sharp reference
operator overloading
expression trees

...

operators precedence
operator precedence determines the grouping of terms in an expression
this affects the evaluation of an expression
certain operators have higher precedence than others; for example, the multiplication operator has higher precedence than the addition operator
for example X space equals space seven space plus space three space asterisk space two; here, X is assigned thirteen, not twenty because operator asterisk has higher precedence than plus, so the first evaluation takes place for three asterisk two and then seven is added into it

```

19
```

...

C sharp operators precedence
operator precedence determines the grouping of terms in an expression
the affects evaluation of an expression
certain operators have higher precedence than others; for example, the multiplication operator has higher precedence than the addition operator
for example X space equals space seven space plus space three space asterisk space two; here, X is assigned thirteen, not twenty because operator asterisk has higher precedence than plus, so the first evaluation takes place for three asterisk two and then seven is added into it

```

20
```
here, operators with the highest precedence appear at the top of the table, those with the lowest appear at the bottom
within an expression, higher precedence operators are evaluated first
category
operator
associativity
postfix
opening parentheses closing parentheses space opening bracket closing bracket space dash greater than space period space plus plus space minus minus
left to right
unary
plus space minus space exclamation mark space tilde space plus plus space minus minus space opening parentheses type closing parentheses asterisk space ampersand space size of

```

21
```
right to left
multiplicative
asterisk space slash space percentage
left to right
additive
plus space minus
left to right
shift
less than less than space greater than greater than
left to right
relational
less than space less than equals space greater than space greater than equals space
left to right
equality
equals equals space exclamation mark equals
left to right
bitwise AND
ampersand
left to right
bitwise XOR
caret
left to right
bitwise OR
pipe
left to right
logical AND
ampersand ampersand
left to right
logical OR
pipe pipe
left to right
conditional
question mark colon
right to left
assignment

```

22
```
equals space plus equals space minus equals space asterisk equals space slash equals space percentage equals space greater than greater than equals space less than less than equals space ampersand equals space caret equals space pipe equals
right to left
comma
comma
left to right
example
live demo
using uppercase S ystem semicolon new line
name space space operators uppercase A ppl space opening curly brace new line
indent class space uppercase P rogram space opening curly brace new line
indent indent static space void space uppercase M ain opening parentheses string opening bracket closing bracket space args closing parentheses space opening curly brace new line
indent indent indent INT space A space equals space twenty semicolon new line
indent indent indent INT space B space equals space ten semicolon new line

```

23
```
indent indent indent INT space C space equals space fifteen semicolon new line
indent indent indent INT space D space equals space five semicolon new line
indent indent indent INT space E semicolon new line
indent indent indent E space equals space opening parentheses A space plus space B closing parentheses space asterisk space C space slash space D semicolon indent space slash slash space opening parentheses space thirty space asterisk space fifteen space closing parentheses space slash space five new line
indent indent indent uppercase C onsole dot uppercase W rite uppercase L ine opening parentheses double quote uppercase V alue of space opening parentheses A space plus space B closing parentheses space asterisk space C space slash space D space is space colon space opening curly brace zero closing curly brace double quote comma space E closing parentheses semicolon new line new line

```

24
```
indent indent indent E space equals space opening parentheses opening parentheses A space plus space B closing parentheses space asterisk space C closing parentheses space slash space D semicolon indent space slash slash space opening parentheses thirty space asterisk space fifteen closing parentheses space slash space five new line
indent indent indent uppercase C onsole dot uppercase W rite uppercase L ine opening parentheses double quote uppercase V alue of space opening parentheses opening parentheses A space plus space B closing parentheses space asterisk space C closing parentheses space slash space D space is space colon space opening curly brace zero closing curly brace double quote comma space E closing parentheses semicolon new line new line

```

25
```
indent indent indent E space equals space opening parentheses A space plus space B closing parentheses space asterisk space opening parentheses C space slash space D closing parentheses semicolon indent space slash slash space opening parentheses thirty closing parentheses space asterisk space opening parentheses fifteen slash five closing parentheses space opening curly brace zero closing curly brace double quote comma space E closing parentheses semicolon new line new line

```

26
```
indent indent indent E space equals space A space plus space opening parentheses B space asterisk space C closing parentheses space slash space D semicolon indent space slash slash space twenty space plus space opening parentheses one hundred fifty slash five closing parentheses space opening curly brace zero closing curly brace double quote comma space E closing parentheses semicolon new line

```

27
```
uppercase C onsole dot uppercase R ead uppercase L ine opening parentheses closing parentheses semicolon new line
indent indent closing curly brace new line
indent closing curly brace new line
closing curly brace
when the above code is complated and executed, it produces the following result
uppercase V alue of space opening parentheses A space plus space B closing parentheses space asterisk space C space slash space D space is space colon space ninety new line

```

28
```
uppercase V alue of space opening parentheses opening parentheses A space plus space B closing parentheses space asterisk space C closing parentheses space slash space D space is space colon space ninety

...

conditional statements
if, if dot dot else if, switch
the if, if dash else and switch statements select statements to execute from many possible paths based on the value of an expression
the if statement executes a statement only if a provided boolean expression evaluates to true
the if dash else statement allows you to choose which of the two code paths to follow based on boolean expression

```

29
```
the switch statement selects a statement list to execute based on a pattern match with an expression

...

selection statements - if, if dash else, and switch
article
zero four slash two eight slash two zero two three
four contributions
feedback
in this article
the if statement
the switch statement
C sharp language specification
see also
the if, if dash else and switch statements selects statements to execute from many possible paths based on the value of an expression
the if statement executes a statement only if a provided boolean expression evaluates to true
the if dash else statement allows you to choose which of the two code paths to follow based on a boolean expression

```

30
```
the switch statement selects a statement list to execute based on a pattern match with an expression
the if statement
an if statement can be any of the following two forms
an if statement with an else part selects one of the two statements to execute based on value of a boolean expression, as the following example shows
C sharp
copy
run
uppercase D isplay uppercase W eather uppercase R eport opening parentheses fifteen point zero closing parentheses semicolon space space slash slash space uppercase O utput colon space uppercase C old period new line
uppercase D isplay uppercase W eather uppercase R eport opening parentheses twenty four point zero closing parentheses semicolon space space slash slash space uppercase O utput colon space uppercase P erfect exclamation mark new line new line

```

31
```
void space uppercase D isplay uppercase W eather uppercase R eport opening parentheses double space temp uppercase I N uppercase C elsius closing parentheses new line
opening curly brace new line
indent if space opening curly brace temp uppercase I N uppercase C elsius space less than space twenty point zero closing parentheses new line
indent opening curly brace new line
indent indent uppercase C onsole dot uppercase W rite uppercase L ine opening parentheses double quote uppercase C old period double quote closing parentheses semicolon new line
indent closing curly brace new line

```

32
```
indent else new line
indent opening curly brace new line
indent indent uppercase C onsole dot uppercase W rite uppercase L ine opening parentheses double quote uppercase P erfact exclamation mark double quote closing parentheses semicolon new line
indent closing curly brace new line
closing curly brace
an if statement without an else part executes its body only if a boolean expression evaluates to true, as the following example shows
C sharp
copy 
run
uppercase D isplay uppercase M easurement opening parentheses forty five closing parentheses semicolon space space slash slash space uppercase O utput colon space uppercase T he measurement value is forty five new line
uppercase D isplay uppercase M easurement opening parentheses dash three closing parentheses semicolon space space slash slash space uppercase O utput colon space uppercase W arning colon space not acceptable value exclamation mark space uppercase T he measurement value is space dash three new line new line

```

33
```
void space uppercase D isplay uppercase M easurement opening parentheses double space value closing parentheses new line
opening curly brace new line
indent if space opening parentheses value space less than space zero space pipe pipe space value space greater than space one hundred closing parentheses new line
indent opening curly brace new line
indent indent uppercase C onsole dot uppercase W rite opening parentheses double quote uppercase W arning colon space not acceptable value exclamation mark space double quote closing parentheses semicolon new line

```

34
```
indent closing curly brace new line new line
indent uppercase C onsole dot uppercase W rite uppercase L ine opening parentheses dollar sign double quote uppercase T he measurement value is space opening curly brace value closing curly brace double quote closing parentheses semicolon new line
closing curly brace
you can next if statements to check multiple conditions, as the following example shows
C sharp
copy
run
uppercase D isplay uppercase C haracter opening parentheses single quote f single quote closing parentheses semicolon space space slash slash space uppercase O utput colon space uppercase A space lowercase letter colon space F new line

```

35
```
uppercase D isplay uppercase C haracter opening parentheses single quote uppercase R single quote closing parentheses semicolon space space slash slash space uppercase O utput colon space uppercase A N space uppercase letter colon space uppercase R new line
uppercase D isplay uppercase C haracter opening parentheses single quote eight single quote closing parentheses semicolon space space slash slash space uppercase O utput colon space uppercase A space digit colon space eight new line
uppercase D isplay uppercase C haracter opening parentheses single quote comma single quote closing parentheses semicolon space space slash slash space uppercase O utput colon space uppercase N ot alphanumeric character colon space comma new line new line

```

36
```
void space uppercase D isplay uppercase C haraacter opening parentheses char space CH closing parentheses new line
opening curly brace new line
indent if space opening parentheses dot uppercase I S uppercase U pper opening parentheses CH closing parentheses closing parentheses new line
indent opening curly brace new line
indent indent uppercase C onsole dot uppercase W rite uppercase L ine opening parentheses dollar sign double quote uppercase A N space uppercase letter colon space opening curly brace CH closing curly brace double quote closing parentheses semicolon new line

```

37
```
indent closing curly brace new line
indent else space if space opening parentheses char dot uppercase I S uppercase L ower opening parentheses CH closing parentheses closing parentheses new line
indent opening curly brace new line
indent indent uppercase C onsole dot uppercase W rite uppercase L ine opening parentheses dollar sign double quote uppercase A space digit colon space opening curly brace CH closing curly brace double quote closing parentheses semicolon new line
indent closing curly brace new line
indent else new line
indent opening curly brace new line

```

38
```
indent indent uppercase C onsole dot uppercase W rite uppercase L ine opening parentheses dollar sign double quote uppercase N ot alphanumeric character colon space opening curly brace CH closing curly brace double quote closing parentheses closing parentheses semicolon new line
indent closing curly brace new line
closing curly brace
in an expression context, you can use the conditional operator question mark colon to evaluate one of the two expressions based on the value of a boolean expression
the switch statement
the switch statement selects a statement list to execute based on a pattern match with a match expression, as the following example shows
C sharp
copy
uppercase D isplay uppercase M easurement opening parentheses dash four closing parentheses semicolon space space slash slash space uppercase O utput colon space uppercase M easured value is space dash four semicolon space too low period new line

```

39
```
uppercase D isplay uppercase M easurement opening parentheses five closing parentheses semicolon space space slash slash space uppercase O utput colon space uppercase M easured value is five period new line
uppercase D isplay uppercase M easurement opening parentheses thirty closing parentheses semicolon space space slash slash space uppercase O utput colon space uppercase M easured value is thirty semicolon space too high period new line
uppercase D isplay uppercase M easurement opening parentheses double dot uppercase N A uppercase N closing parentheses semicolon space space slash slash space uppercase O utput colon uppercase F ailed measurement period new line new line

```

40
```
void space uppercase D isplay uppercase M easurement opening parentheses double space measurement closing parentheses new line
opening curly brace new line
indent switch space opening parentheses measurement closing parentheses new line
indent opening curly brace new line
indent indent case space less than space zero point zero colon new line
indent indent indent uppercase C onsole dot uppercase W rite uppercase L ine opening parentheses dollar sign double quote uppercase M easured value is space opening curly brace measurement closing curly brace semicolon space too low period double quote closing parentheses semicolon new line

```

41
```
indent indent indent break semicolon new line new line
indent indent case space greater than space fifteen point zero colon new line
indent indent indent uppercase C onsole dot uppercase W rite uppercase L ine opening parentheses dollar sign double quote uppercase M easured value is space opening curly brace measurement closing curly brace semicolon space too high period double quote closing parentheses semicolon new line
indent indent indent break semicolon new line new line
indent indent case space double dot uppercase N A uppercase N colon new line

```

42
```
indent indent indent uppercase C onsole dot uppercase W rite uppercase L ine opening parentheses double quote uppercase F ailed measurement period double quote closing parentheses semicolon new line
indent indent indent break semicolon new line new line
indent indent default colon new line
indent indent indent uppercase C onsole dot uppercase W rite uppercase L ine opening parentheses dollar sign double quote uppercase M easured value is space opening curly brace measurement closing curly brace period double quote closing parentheses semicolon new line
indent indent indent break semicolon new line
indent closing curly brace new line
closing curly brace
at the preceding example, the switch statement uses the following patterns
a relational pattern (available in C sharp nine point zero and later): to compare an expression with a constant

```

43
```
a constant pattern: test if an expression result equals a constant
important
for information about the patterns supported by the switch statement, see patterns
the preceding example also demostrates the default case
the default case specifies statements to execute when a match expression doesn't match any other case pattern
if a match expression doesn't match any case pattern and there's no default case, constrol falls through a switch statement
a switch statement executes the statement list in the first switch section whose case pattern matches a match expression and whose case guard, if present, evaluates to true
a switch statement evaluates case patterns in text order from top to bottom

```

44
```
the compiler generates an error when a switch statement contains an unreachable case
that is a case that is already handled by an uppercase or whose pattern is impossible to match
note
the default case can appear in any place within a switch statement
regardless of its posiiton, the default case is evaluated only if all other case patterns aren't matched o the goto default semicolon statement is executed in one of the switch sections
you can specifi multiple case patterns for one section of a switch statement, as the following example shows
C sharp
copy
uppercase D isplay uppercase M easurement opening parentheses dash four closing parentheses semicolon space space slash slash space uppercase O utput colon space uppercase M easured value is space dash four semicolon space out of an acceptable range period new line

```

45
```
uppercase D isplay uppercase M easurement opening parentheses fifty closing parentheses semicolon space space slash slash space uppercase O utput colon space uppercase M easured value is fifty period new line
uppercase D isplay uppercase M easurement opening parentheses one hundred and thirty two closing parentheses semicolon space space slash slash space uppercase O utput colon space uppercase M easured valus is one hundred and thirty two semicolon space out of an acceptable range period new line new line
void space uppercase D isplay uppercase M easurement opening parentheses INT space measurement closing parentheses new line

```

46
```
opening curly brace new line
indent switch space opening parentheses measurement closing parentheses new line
indent opening curly brace new line
indent indent case space less than space zero colon new line
indent indent case space greater than space one hundred colon new line
indent indent indent uppercase C onsole dot uppercase W rite uppercase L ine opening parentheses dollar sign double quote uppercase M easured value is space opening curly brace measurement closing curly brace semicolon space out of an acceptable range dot double quote closing parentheses semicolon new line
indent indent indent break semicolon new line new line
indent indent default colon new line
indent indent indent uppercase C onsole dot uppercase W rite uppercase L ine opening parentheses dollar sign double quote uppercase M easured value is opening curly brace measurement closing curly brace period double quote closing parentheses semicolon new line

```

47
```
indent indent indent break semicolon new line
indent closing curly brace new line
closing curly brace
within a switch statement, control can't fall through from one switch section to the next
as the examples in this section show, typically you use the break statement at the end of each switch section to pass control out of a switch statement
you can also use the return and throw statements to pass control out of a switch statement
to imitate the fall dash through behavior and pass control to other switch section, you can use the goto statement

```

48
```
in an expression context, you can use the switch expression to evaluate a single expression from a list of candidate expressions based on a pattern match with an expression
case guards
a case pattern may be not expressive enough to specify the condition for the execution of the switch section
in such a case, you can use a case guard
that is an additional condition that must be satisfied together with a matched pattern
a case guard must be a boolean expression
you specify a case guard after the when keyaord that follows a pattern, as the following example shows
C sharp
copy
uppercase D isplay uppercase M easurements opening parentheses three comma space four closing parentheses semicolon space space slash slash space uppercase O utput colon space uppercase F irst measurement is three comma space second measurement is four period new line

```

49
```
uppercase D isplay uppercase M easurements opening parentheses five comma space five closing parentheses semicolon space space slash slash space uppercase O utput colon space uppercase B oth measurements are valid and equal to five period new line new line
void space uppercase D isplay uppercase M easurements opening parentheses INT space A comma space INT space B closing parentheses new line
opening curly brace new line
indent switch space opening parentheses opening parentheses A comma space B closing parentheses closing parentheses new line
indent opening curly brace new line

```

50
```
indent indent case space opening parentheses greater than space zero comma space greater than space zero closing parentheses space when space A space equals equals space B colon new line
indent indent indent uppercase C onsole dot uppercase W rite uppercase L ine opening parentheses dollar sign double quote uppercase B oth measurements are valid and equal to space opening curly brace A closing curly brace period double quote closing parentheses semicolon new line
indent indent indent break semicolon new line new line
indent indent case space opening parentheses greater than space zero comma space greater than space zero closing parentheses colon new line
indent indent indent uppercase C onsole dot uppercase W rite uppercase L ine opening parentheses dollar sign double quote uppercase F irst measurement is space opening curly brace A closing curly brace comma space second measurement is space opening curly brace B closing curly brace period double quote closing parentheses semicolon new line

```

51
```
indent indent indent break semicolon new line new line
indent indent default colon new line
indent indent indent uppercase C onsole dot uppercase W rite uppercase L ine opening parentheses double quote uppercase O ne or both measurements are not valid period double quote closing parentheses semicolon new line
indent indent indent break semicolon new line
indent closing curly brace new line
closing curly brace
the preceding example uses positional patterns with nested relational patterns

```

52
```
C sharp language specification
for more information, see the following sections of the C sharp language specification
the if statement
the switch statement
for more information about patterns, see the patterns and pattern matching section of the C sharp language specification
see also
C sharp reference
conditional operator question mark colon
logical operators
patterns
switch expression
add missing cases to switch statement (style rule IDE zero zero one zero)

...

loops: do dot dot while, while, for foreach
the iteration statements repeatedly execute a statement or a block of statements
the for statement executes its body while a specified boolean expression evaluates to true
the foreach statement enumerates the elements of a collection and executes its body for each element of the collection

```

53
```
the do statement conditionally executes its body one or more times
the while statement conditionally executes its body zero or more times
at any point within the body of an iteration statement, you can break out of the loop using the break statement
you can step to the next iteration in the loop using the continue statement

...

iteration statements - for, foreach, do, and while
article
zero four slash one two slash two zero two three
two contributions
feedback
in this article
the for statement
the foreach statement
the do statement
the while statement
show two more
C sharp language specification
see also
show less
the iteration statements repeatedly executes a statement of a block of statements

```

54
```
the for statement executes its body while a specified boolean expression evaluates to true
the foreach statement enumerates the elements of a collection and executes its body for each element of the collection
the do statement conditionally executes its body one or more times
the while statement conditionally executes its body zero or more times
at any point within the body of an iteration statement, you can break out of the loop using the break statement
you can step to the next iteration in the loop using the continue statement
the for statement
the for statement executes a statement or a block of statements while a specified boolean expression evaluates to true
the following example shows the for statement that executes its bod while an integer counter is less than three

```

55
```
C sharp
copy
run
for space opening parentheses INT space I space equals space zero semicolon space I space less than space three semicolon space I plus plus closing parentheses new line
opening curly brace new line
indent uppercase C onsole dot uppercase W rite opening parentheses I closing parentheses semicolon new line
closing curly brace new line
slash slash space uppercase O utput colon newline
slash slash space zero one two
the preceding example shows the elements of the for statement
the initializer section that is executed only once, before entering the loop
typically, you declare and initilize a local loop variable in that section
the declared variable can't be accessed from outside the for statement

```

56
```
the initializer section in the preceding example declares and initializes an interger counter variable
C sharp
copy
INT space I space equals space zero
the condition section that determines if the next iteration in the loop should be executed
if it evaluates to true or isn't present, the next iteration is executed; otherwise, the loop is exited
the condition section must be a boolean expression
the condition section in the preceding example checks if a counter value is less than three
C sharp
copy
I space less than space three
the iterator section that defines what happens after each execution of the body of the loop
the iterator section in the preceding example increments the counter

```

57
```
C sharp
copy
I plus plus
the body of the loop, which must be a statement or a block of statements
the iterator section can contain zero or more of the following statement expressions, separated by commas
prefix or postfix increment expression, such as plus plus I or I plus plus
prefix or postfix decrement expression, such as minus minus I or I minus minus
assignment
invocation of a method
await expression
creation of an object by using the new operator
if you don't declare a loop variable in the initializer section, you can use zero or more of the expressions from the preceding list in the initializer section as well
the following example shows several less common usages of the initializer and iterator sections assigning a value to an external variable in the initializer section, invoking a method in both the initializer and the iterator sections, and changing the values of two variables in the iterator section

```

58
```
C sharp
copy
run
INT space I semicolon new line
INT space J space equals space three new line
for space opening parentheses I space equals space zero comma space uppercase C onsole dot uppercase W rite uppercase L ine opening parentheses dollar sign double quote uppercase S tart colon space I equals opening curly brace I closing curly brace comma space J equals opening curly brace J closing curly brace double quote closing parentheses semicolon space I space less than space J semicolon space I plus plus comma space J minus minus comma space uppercase C onsole dot uppercase W rite uppercase L ine opening parentheses dollar sign double quote uppercase S tep colon space I equals opening curly brace I closing curly brace comma space J equals opening curly brace J closing curly brace double quote closing parentheses closing parentheses new line

```

59
```
opening curly brace new line

```

60
```
indent slash slash dot dot dot new line
closing curly brace new line
slash slash space uppercase O utput colon new line
slash slash space uppercase S tart colon space I equals zero comma space J equals three new line
slash slash space uppercase S tep colon space I equals one comma space J equals two new line
slash slash space uppercase S tep colon space I equals two comma space J equals one
all the sections of the for statement are optional
for example, the following code defines the infinited for loop
C sharp
copy
for space opening parentheses space semicolon space semicolon space closing parentheses new line
opening curly brace new line
indent slash slash dot dot dot new line

```

61
```
closing curly brace
the foreach statement
the foreach statement executes a statement or a block of statements for each element in an instance of the type that implements the systems dot collections dot I enumerable or system dot collections dot generic dot I enumerable less than uppercase T greater than interface, as the following example shows
C sharp
copy
run
VAR space FIB uppercase N umbers space equals space new space uppercase L ist less than INT greater than space opening curly brace space zero comma space one comma space one comma space two comma space three comma space five comma space eight comma space thirteen space closing curly brace semicolon new line
foreach space opening parentheses INT space element space in space FIB uppercase N umbers closing parentheses new line

```

62
```
opening curly brace new line
indent uppercase C onsole dot uppercase W rite opening parentheses dollar sign double quote opening curly brace element closing curly brace space double quote closing parentheses semicolon new line
closing curly brace new line
slash slash space uppercase O utput colon new line
slash slash space zero space one space one space two space three space five space eight space thirteen
the foreach statement isn't limited to those types
you can use it with an instance of any type that satisfies the following conditions

a type has the public parameterless uppercase G et uppercase E numerator method
beginning with C sharp nine point O, the uppercase G et uppercase E numerator method can be a type's extension method

```

63
```
the return type of the uppercase G et uppercase E numerator method has the public uppercase C urrent property and the public parameterless uppercase M ove uppercase N ext method whose return type is bool
the following example uses the foreach statement with an instance of the system dot span less than uppercase T greater than type, which doesn't implement any interfaces
C sharp
copy
uppercase S pan less than INT greater than space numbers space equals space new space INT space opening bracket closing bracket space opening curly brace space three comma space fourteen comma space fifteen comma space ninety two comma space six space closing curly brace new line

```

64
```
foreach space opening parentheses INT space number space in space numbers closing parentheses new line
opening curly brace new line
indent uppercase C onsole dot uppercase W rite opening parentheses dollar sign double quote opening curly brace number closing curly brace space double quote closing parentheses semicolon new line
closing curly brace new line
slash slash space uppercase O utput colon new line
slash slash space three space fourteen space fifteen space ninety two space six
if the enumerator's current property returns a reference return value (ref space uppercase T where uppercase T is the type of a collection element), you can declare an iteration variable with the REF or REF space read only modifier, as the following example shows

```

65
```
C sharp
copy
uppercase S pan less than INT greater than space storage space equals space stack ALLOC space INT opening bracket ten closing bracket semicolon new line
INT space num space equals space zero semicolon new line
foreach space opening parentheses REF space INT space item space in space storage closing parentheses new line
opening curly brace new line
indent item space equals space num plus plus semicolon new line
closing curly brace new line
foreach space opening parentheses REF read only space var space item space in space storage closing parentheses new line

```

66
```
opening curly brace new line
indent uppercase C onsole dot uppercase W rite opening parentheses dollar sign double quote opening curly brace item closing curly brace space double quote closing parentheses semicolon new line
closing curly brace new line
slash slash space uppercase O utput colon new line
slash slash space zero space one space two space three space four space five space six space seven space eight space nine
if the source collection of the foreach statement is empty, the body of the foreach statement isn't executed and skipped
if the foreach statement is applied to null, a null reference exception is thrown
await foreach
you can use the await foreach statement to consume an asynchronous stream of data, that is, the collection type that implements the I async enumerable less than uppercase T greater than interface

```

67
```
each iteration of the loop may be suspended while the element is retrieved asynchronously
the following example shows how to use the await foreach statement
C sharp
copy
await space foreach space opening parentheses VAR space item space in space uppercase G enerate uppercase S equence uppercase A sync opening parentheses closing parentheses closing parentheses new line
opening curly brace new line
indent uppercase C onsole dot uppercase W rite uppercase L ine opening parentheses item closing parentheses semicolon new line
closing curly brace new line
you can also use the await foreach statement with an instance of any type that satisfies the following conditions

```

68
```
a type has the public parameterless uppercase G et uppercase A sync uppercase E numerator method
that method can be a type's extension method can be a type's extension method
the return type of the uppercase G et uppercase A sync uppercase E numerator method has the public uppercase C urrent property and the parameterless uppercase M ove uppercase N ext uppercase A sync method whose return type is uppercase task less than bool greater than, value task less than bool greater than, or any other awaitable type whose awaiter's uppercase G et uppercase R esult method returns a bool value
by default, stream elements are processed in the captured context

```

69
```
use the task async enumerable extensions dot configure await extension method
for more information about synchronization contexts and capturing the current context, see consuming the asynchronous streams tutorial
type of an iteration variable
you can use the var keyword to let the compiler infer the type of an iteration variable in the foreach statement, as the following code shows
C sharp
copy
foreach space opening parentheses VAR space item space in space collection closing parentheses space opening curly brace space closing curly brace
you can also explicitly specify the type of an iteration variable, as the following code shows
C sharp
copy
uppercase I uppercase E numerable less than uppercase T greater than space collection space equals space new space uppercase T opening bracket five closing bracket semicolon new line

```

70
```
foreach space opening parentheses uppercase V space item space in space collection closing parentheses space opening curly brace space closing curly brace
in the preceding form, type uppercase T of a collection element must be implicitly or explicitly convertible to type uppercase V of an iteration variable
if an explicit conversion from uppercase T to uppercase V fails at run time, the foreach statement throws an invalid cast exception
for example, if uppercase T is a non dash sealed class type, uppercase V can be any interface type, even the one that uppercase T doesn't implement
at run time, the type of a collection element may be the one that derives from uppercase T and actually implements V

```

71
```
if that's not the case, an invalid cast exception is thron
the do statement
the do statement executes a statement or a block of statements while a specified boolean expression evaluates to true
becuase the expression is evaluated after each execution of a loop, a do loop executes one or more times
the do loop differs from the while loop, which executes zero or more times
the following example shows the usage of the do statement
C sharp
copy
run
INT space N space equals zero semicolon new line
do new line
opening curly brace new line
indent uppercase C onsole dot uppercase W rite opening parentheses N closing parentheses semicolon new line

```

72
```
indent N plus plus semicolon new line
closing curly brace space while space opening parentheses N space less than space five closing parentheses semicolon new line
slash slash space uppercase O utput colon new line
slash slash space zero one two three four
the while statement
the while statement executes a statement or a block of statements while a specified boolean expression evaluates to true
because that expression is evaluated before each execution of the loop, a while loop executes zero or more times
the whiel loop differs from the do loop, which executes one or more times
the following example shows the usage of the while statement
C sharp copy run

```

73
```
INT space N space equals space zero semicolon new line
while space opening parentheses N space less than space five closing parentheses new line
opening curly brace new line
indent uppercase C onsole dot uppercase W rite opening parentheses N closing parentheses semicolon new line
indent N plus plus semicolon new line
closing curly brace new line
slash slash space uppercase O utput colon new line
slash slash space zero one two three four five six
C sharp language specification
for more information, see the following sections of the C sharp language specification
the for statement
the foreach statement
the do statement
the while statement
for more information about features added in C sharp eight point O and later, see the following feature proposal notes

```

74
```
async streams (C sharp eight point zero)
extension get enumerator support for foreach loops (C sharp nine point zero)
see also
C sharp reference
using foreach with arrays
iterators

...

jump statements
in C sharp, jump statements are used to transfer control from one point to another point in the program due to some specified code while executing the program
there are five keywords in the jump statements

...

C sharp
jump statements (break, continue, goto return and throw)
in C sharp, jump statements are used to transfer control from one point to another point in the program due to some specified code while executing the program

```

75
```
there are five keywords in the jump statements
break
continue
goto
return
throw
break statement
the break statement is used to terminate the loop or statement in which it present
after that, the control will pass to the statements that present after the break statement, if available
if the break statement present in the nexted loop, then it terminates only those loops which contains break statement
flowchart
condition true conditional code break statement false
example
C sharp
slash slash space C sharp program to illustrate the new line
slash slash space use of break statement new line
using space system first character uppercase semicolon new line new line

```

76
```
class space geeks first character uppercase space opening curly brace new line new line
indent slash slash space main method new line
indent static space public space void space main first character capital opening parentheses closing parentheses new line
indent opening curly brace new line new line
indent indent slash slash space geeks for geeks is printed only two times new line
indent indent slash slash space because of break statement
indent indent for space opening parentheses INT space I space equals space one semicolon space I space less than space four semicolon space I plus plus closing parentheses new line
indent indent opening curly brace new line
indent indent indent if space opening parentheses I space equals equals space three closing parentheses new line

```

77
```
indent indent indent indent break semicolon new line new line
indent indent indent console first character uppercase dot write first character uppercase line first character uppercase opening parentheses double quote geeks for geeks double quote closing parentheses semicolon new line
indent indent closing curly brace new line
indent closing curly brace new line
closing curly brace
output
geeks for geeks
geeks for geeks
continue statement
this statement is used to skip over the execution part of the loop on a certain condition
after that, it transfers the control to the beginning of the loop
basically, it skips its following statements and continues with the next iteration of the loop

```

78
```
enter loop test expression of loop true continue yes no remaining body of loop false statement just below loop
example
C sharp
slash slash space C sharp program to illustrate the new line new line
slash slash space use of continue statement new line
using space system first character uppercase semicolon new line new line
class space geeks first character uppercase space opening curly brace new line new line
indent slash slash space main method new line
indent public space static space void space main first character uppercase opening parentheses closing parentheses new line
indent opening curly brace new line new line
indent indent slash slash space this will skip four to print new line

```

79
```
indent indent for space opening parentheses INT space I space equals space one semicolon space I space less than equals space ten semicolon space I plus plus closing parentheses space opening curly brace new line new line
indent indent indent slash slash space if the value of I becomes four then new line
indent indent indent slash slash space it will skip four and send the new line
indent indent indent slash slash space transfer to the for loop and new line
indent indent indent slash slash space continue with five new line
indent indent indent if space opening parentheses I space equals equals space four closing parentheses new line
indent indent indent indent continue semicolon new line new line

```

80
```
indent indent indent console first character uppercase dot write first character uppercase line first character uppercase opening parentheses I closing parentheses semicolon new line
indent indent closing curly brace new line
indent closing curly brace new line
closing curly brace
output
one
two
three
five
six
seven
eight
nine
ten
goto statement
this statement is used to transfer control to the laveled statement in the program
the label is the valid identifier and placed just before the statement from where the control is transferred
statement one statement two statement three goto statement one
example
C sharp
slash slash space C sharp program to illustrate the new line
slash slash space use of goto statement new line

```

81
```
using space system first character uppercase semicolon new line new line
class space geeks first character uppercase space opening curly brace new line new line
indent slash slash space main method new line
indent static space public space void space main first character uppercase opening parentheses closing parentheses new line
indent opening curly brace new line
indent indent INT space number space equals space twenty semicolon new line
indent indent switch space opening parentheses number closing parentehses space opening curly brace new line new line
indent indent case space five colon new line
indent indent indent console first character uppercase dot write first character uppercase line first character uppercase opening parentheses double quote case space five double quote closing parentheses semicolon new line

```

82
```
indent indent indent break semicolon new line
indent indent case space ten colon new line
indent indent indent console first character uppercase dot write first character uppercase line first character uppercase opening parentheses double quote case space ten double quote closing parentheses semicolon new line
indent indent indent break semicolon new line
indent indent case space twenty colon new line
indent indent indent console first character uppercase dot write first character uppercase line first character uppercase opening parentheses double quote case space twenty double quote closing parentheses semicolon new line new line
indent indent indent slash slash space goto statement transfer new line

```

83
```
indent indent indent slash slash space the control to case five new line
indent indent indent goto space case space five semicolon new line new line
indent indent default colon new line
indent indent indent console first character uppercase dot write first character uppercase line first character uppercase opening parentheses double quote no match found double quote closing parentheses semicolon new line new line
indent indent closing curly brace new line
indent closing curly brace new line
closing curly brace
output
case twenty
case five
return statement
this statement terminates the execution of the method and returns the control to the calling method
it returns an optional value
if the type of method is void, then the return statement can be excluded

```

84
```
example
C sharp
slash slash space C sharp program to illustrate the new line
slash slash space use of return statement new line
using space system first character uppercase semicolon new line new line
class space geeks first character uppercase space opening curly brace new line new line
indent slash slash space creating simple addition function new line
indent static space int space addition first character uppercase opening parentheses INT space A closing parentheses new line
indent opening curly brace new line new line
indent indent slash slash space add two value and new line
indent indent slash slash space return the result of addition new line
indent indent INT space add space equals space A space plus space A semicolon new line new line

```

85
```
indent indent slash slash space using return statement new line
indent indent return space add semicolon new line
indent closing curly brace new line new line
indent indent slash slash space main method new line
indent static space public space void space main first character uppercase opening parentheses closing parentheses new line
indent opening curly brace new line
indent indent INT space number space equals space two semicolon new line new line
indent indent slash slash space calling addition function new line
indent indent INT space result space equals space addition first character uppercase opening parentheses number closing parentheses semicolon new line
indent indent console first character uppercase dot write first character uppercase line first character uppercase opening parentheses double quote the addition is opening curly brace zero closing curly brace double quote comma space result closing parentheses semicolon new line

```

86
```
indent closing curly brace new line
closing curly brace
output
the addition is four
throw statement
this is used to create an object of any valid exception class with the help of new keyword manually
the valid exception must be derived from the exception class
example
C sharp
slash slash space C sharp program to illustrate the use new line
slash slash space of throw keyaord new line
using space system first character uppercase semicolon new line new line
class space geeks first character uppercase space opening curly brace new line new line

```

87
```
indent slash slash space taking null in the string new line
indent static space string space sub space equals space null semicolon new line new line
indent slash slash space method to display subject name new line
indent static space void space display subject opening parentheses string space sub one closing parentheses new line
indent opening curly brace new line
indent indent if space opening parentheses sub one space equals equals space null closing parentheses new line
indent indent indent throw space new space null first character uppercase reference first character uppercase exception first character uppercase opening parentheses double quote exception message double quote closing parentheses semicolon new line new line
indent closing curly brace new line new line

```

88
```
slash slash space main method new line
static space void space main first character uppercase opening parentheses string opening bracket closing bracket space ARGS closing parentheses new line
opening curly brace new line new line
indent slash slash space using try catch block to new line
indent slash slash space handle the exception new line
indent try new line
indent opening curly brace new line
indent indent slash slash space calling the static method new line
indent indent display subject opening parentheses sub closing parentheses semicolon new line
indent closing curly brace new line new line
indent catch opening parentheses exception first character uppercase space EXP closing parentheses semicolon new line
indent opening curly brace new line
indent indent console first character uppercase dot write first character uppercase line first character uppercase opening parentheses EXP dot message first character uppercase space closing parentheses semicolon new line

```

