0
```
Getting Started
Why do make files exist?
Make files are used to help decide which parts of a large program need to be recompiled.
In the vast majority of cases, C. or C. plus plus files are compiled.
Other languages typically have their own tools that serve a similar purpose as make.
Make can also be used beyond compilation too, when you need a series of instructions to run depending on what files have changed.
This tutorial will focus on C. slash C. plus plus compilation use case.
Here’s an example dependency graph that you might build with make.
If any file’s dependencies changes, then the file will get recompiled.
In the vase majority of cases, C. or C plus plus files are compiled.
Other languages typically have their own tools that serve a similar purpose as make.

```

1
```
Make can also be used beyond compilation too, when you need a series of instructions to run depending on what files have changed.
This tutorial will focus on the C. slash C. plus plus compilation use case.
Here’s an example dependency graph that you might build with make.
If any file’s dependencies changes, then the file will get recompiled
One dot H. L.I.B.M. L.I.B.C. two dot H. one dot C.P.P. two dot C.P.P. main dot C.P.P.
What alternatives are there to make?
Popular C. slash C. plus plus alternative build systems are S. cons, C. make, bazel, and ninja.
Some code editors like microsoft visual studio have their own built in build tools.
For java, there’s ant, maven, and gradle.

```

2
```
Other languages like go and rust have their own build tools.
Interpreted languages like python, ruby, and javascript don’t require an analogue to make files.
The goal of make files is to compile whatever files need to be compiled, based on what files have changed.
But when files in interpreted languages change, nothing needs to get recompiled.
When the program runs, the most recent version of the file is used.
The versions and types of make
There are a variety of implementations of make, but most of this guide will work on whatever version you’re using.
However, it’s specifically written for G.N.U. make, which is the standard implementation on linux and mac O.S.
All the examples work for make versions three and four, which are nearly equivalent other than some esoteric differences.

```

3
```
Running the examples
To run these examples, you’ll need a terminal and double quote make double quote installed.
For each example, put the contents in a file called make first character uppercase file first character uppercase, and in that directory run the command make.
Let’s start with the simplest of make files
Hello colon echo double quote hello first character uppercase comma world first character uppercase double quote
Note: make files must be indented using T.A.B.S. and not spaces or make will fail.
Here is the output of running the above example
Dollar sign make echo double quote hello first character uppercase comma world first character uppercase double quote hello first character uppercase comma world first character uppercase 

```

4
```
That’s it! If you’re a bit confused. Here’s a video that goes through these steps, along with describing the basic structure of make files.
Make file syntax
 A make file consists of a set of rules.
A rule generally looks like this
Targets colon prerequisites command command command
The targets are file names, separated by spaces.
Typically, there is only one per rule.the
 Commands are a series of steps typically used to make the target opening parentheses S. closing parentheses.
These need to start with a tab character, not spaces.
The prerequisites are also file names, separated by spaces.
These files need to exist before the commands for the target are run.

```

5
```
These are also called dependencies
The essence of make
Let’s start with a hello world example
Hello colon echo double quote hello first character uppercase colon world first character uppercase double quote echo double quote this first character uppercase line will always print comma because the file hello does not exist period double quote
There’s already a lot to take in here.
Let’s break it down
We have one target called hello
This target has two commands
This target has no prerequisites
We’ll then run make hello.
As lon as the hello file does not exist, the commands will run.
If hello does exist, no commands will run.
It’s important to realize that I’m talking about hello as both a target and a file.

```

6
```
That’s because the two are directly tied together.
Typically, when a target is run (A.K.A. when the commands of a target are run), the commands will create a file with the same name as the target.
In this case, the hello target does not create the hello file.
Let’s create a more typical make file dash one that compiles a single C. file.
But before we do, make a file called blah dot C. that has the following contents
Slash slash blah dot C. I.N.T. main opening parentheses closing parentheses opening curly brace return zero closing curly brace
Then create the make file (called make file, as always)
Blah colon C.C. blah dot C. dash O. blash

```

7
```
This time, try simply running make.
Since there’s no target supplied as an argument to the make command, the first target is run.
In this case, there’s only one target (blah).
The first time you run this, blah will be created.
The second time, you’ll see make colon single quote blah single quote is up to date.
That’s because the blah file already exists. But there’s a problem: if we modify blah dot C. and then run make, nothing gets recompiled.
We solve this by adding a prerequisite
Blah colon blah dot C. C.C. blah dot C. dash O. blah
When we run make again, the following set of steps happens:
The first target is selected, because the first target is the default target

```

8
```
This has a prerequisite of blah dot C.
Make decides if it should run the blah target.
It will only run if blah doesn’t exist, or blah dot C. is newer than blah
This last step is critical, and is the essence of make.
What it’s attempting to do is decide if the prerequisites of blah have changed since blah was last compiled.
That is, if blah dot C. is modified, running make should recompile the file.
And conversely, if blah dot C. has not changed, then it should not be recompiled.
To make this happen, it uses the file system timestamps as a proxy to determine if something has changed.
This is a reasonable heuristic, because file timestamps typically will only change if the files are modified.

```

9
```
But it’s important to realize that this isn’t always the case.
You could, for example, modify a file, and then change the modified timestamp of that file to something old.
If you did, make would incorrectly guess that the file hadn’t changed and thus could be ignored.
Whew, what a mouthful.
Make sure that you understand this.
It’s the crux of make files, and might take you a few minutes to properly understand.
Play around with the above examples or watch the video above if things are still confusing.
More quick examples
The following make file ultimately runs all three targets.
When you run make in the terminal, it will build a program called blah in a series of steps

```

10
```
Make selects the target blah, because the first target is the default target
Blah requires blah dot O., so make searches for the blah dot O. target
Blah dot O. requires blah dot C., so make searches for the blah dot C. target
Blah dot C. has no dependencies, so the echo command is run
The C.C. dash C. command is the run, because all of the blah dot O. dependencies are finished
The top C.C. command is run, because all the blah dependencies are finished
That’s it: blah is a compiled C. program
Blah colon blah dot O. C.C. blah dot O. dash O. blah hashtag runs third blah dot O. colon blah dot C. C.C. dash C. blah dot C. dash O. blah dot O. hashtag runs second hashtag typically blah dot C. would already exist, but I want to limit my additional required files blah dot C. colon echo double quote I.N.T. main opening parentheses closing parentheses opening curly brace return zero semicolon closing curly brace double quote greater than blah dot C. hashtag runs first

```

11
```
If you delete blah dot C. all three targets will be rerun.
If you edit it (and thus change the timestamp to newer than blah dot O.), the first two targets will run.
If you run touch blah dot O. (and thus change the timestamp to newer than blah), then only the first target will run.

```

12
```
If you change nothing, none of the targets will run.
Try it out!
This next example doesn’t do anything new, but it is nonetheless a good additional example.
It will always run both targets, because some underscore file depends on other underscore file, which is never created.
Some underscore file colon other underscore file echo double quote shi will always run, and runs second double quote touch some underscore file other underscore file colon echo double quote this will always run, and runs first double quote
Make clean
Clean is often used as a target that removes the output of other targets, but it is not a special word in make.

```

13
```
You can run make and make clean on this to create and delete some underscore file.
Note that clean is doing two new things here
It’s a target that is not first (the default), and not a prerequisite.
That means it’ll never run unless you explicitly call make clean
It’s not intended to be a filename.
If you happen to have a file named clean, this target won’t run, which is not what we want.
See dot P.H.O.N.Y. later in this tutorial on how to fix this some underscore file colon touch some underscore file clean colon R.M. dash F. some underscore file
Variables
Variables can only be strings.

```

14
```
You’ll typically want to use colon equals, but equals also works.
See variables part two.
Here’s an example of using variables:
Files colon equals file one file two
Some underscore file colon dollar sign opening parentheses files closing parentheses echo double quote look at this variable colon double quote dollar sign opening parentheses files closing parentheses touch some underscore file file one colon touch file one file two colon touch file two
Clean colon R.M. dash F. file one file two some underscore file
Single or double quotes have no meaning to make.
They are simply characters that are assigned to the variable.
Quotes are useful to shell slash bash, though, and you need them in commands like print F.
In this example, the two commands behave the same

```

15
```
A. colon equals one two hashtag A. is set to the string double quote one two double quote B. colon equals single quote one two single quote hashtag not recommended period B. is set to the string double quote single quote one two single quote double quote all colon print F. single quote dollar sign A. single quote print F. dollar sign B.
Reference variables using enter dollar sign opening curly brace closing curly brace or dollar sign at sign opening parentheses closing parentheses
X colon equals dude all colon echo dollar sign opening parentheses X. closing parentheses echo dollar sign opening curly brace C. closing curly brace hashtag bad practice, but works echo dollar sign X.
Targets
The all target
Making multiple targets and you want all of them to run? Make an all target.

```

16
```
Since this is the first rule listed, it will run by default if make is called without specifying a target.
All colon one two three
One colon touch one two colon touch two three colon touch three clean colon R.M. dash F. one two three
Multiple targets
When there are multiple targets for a rule, the commands will be run for each target.
Dollar sign at sign is an automatic variable that contains the target name.
All colon F. one dot O. F. two dot O. F. one dot O. F. two dot O. colon echo dollar sign at sign hashtag equivalent to colon hashtag F. one dot O. colon hashtag echo F. one dot O. hashtag F. two dot O. colon hashtag echo F. two dot O.

```

17
```
Automatic variables and wildcards
Asterisk wildcard
Both asterisk and percentage sign are called wildcards in make, but they mean entirely different things, asterisk searches your filesystem for matching filenames.
I suggest that you always wrapt it in the wildcard function, because otherwise you may fall into a common pitfall described below.
Hashtag print out file information about every dot C. file print colon dollar sign opening parentheses wildcard asterisk dot C. closing parentheses L.S. dash L.A. dollar sign question mark

```

18
```
Asterisk may be used in the target, prerequisites, or in the wildcard function.
Danger: asterisk may not be directly used in a variable definitions
Danger: when asterisk matches no files, it is left as it is (unless run in the wildcard function)
Thing underscore wrong colon equals asterisk dot O. hashtag don’t do this exclamation mark single quote asterisk single quote will not get expanded thing underscore right colon equals dollar sign opening parentheses wildcard asterisk dot O. closing parentheses all colon one two three four hashtag fails, because dollar sign opening parentheses thing underscore wrong closing parentheses is the string double quote asterisk dot O. double quote one colon dollar sign opening parentheses thing underscore wrong closing parentheses

```

19
```
Hashtag stays as asterisk dot O. if there are no files that match this pattern colon opening parentheses two colon asterisk dot O. hashtag works as you would expect exclamation mark in this case, it does nothing period three colon dollar sign opening parentheses thing underscore right closing parentheses hashtag same as rule three
Four colon dollar sign opening parentheses wildcard asterisk dot O. closing parentheses

```

20
```
Percentage sign wildcard
Percentage is really useful, but is somewhat confusing because of the variety of situations it can be used in.
When used in double quote matching double quote mode, it matches one or more characters in a string. This match is called the stem.
When used in double quote replacing double quote mode, it takes the stem that was matched and replaces that in a string.
Percentage sign is most often used in rule definitions and in some specific functions.
See these sections on examples of it being used
Static pattern rules
Pattern rules
String substitution
The V. path directive
Automatic variables
There are many automatic variables, but often only a few show up
Hey colon one two hashtag outputs double quote hey double quote comma since this is the target name echo dollar sign at sign hashtag outputs all prerequisites newer than the target echo dollar sign question mark hashtag outputs all prerequisites echo dollar sign caret

```

21
```
Touch hey one colon touch one two colon touch two clean colon R.M. dash F. hey one two
Fancy rules
Implicit rules
Make loves C. compilation.
And everytime it expresses its love, things get confusing. Perhaps the most confusing part of make is the magic slash automatic rules that are made.
Make calls these double quote implicit double quote rules.
I don’t personally agree with this design decision, and I don’t recommend using them, but they’re often used and are thus useful to know.
Here’s a list of implicit rules

```

22
```
Compiling a C. program: N. dot O. is made automatically from N. dot C. with a command of the form dollar sign opening parentheses C. C. closing parentheses dash C. dollar sign opening parentheses C.P.P.F.L.A.G.S. closing parentheses dollar sign opening parentheses C.F.L.A.G.S. closing parentheses dollar sign caret dash O. dollar sign at sign
Compiling a C. plus plus program: N. dot O. is made automatically from N. dot C.C. or N. dot C.P.P. with a command of the form dollar sign opening parentheses C.X.X. dash C. dollar sign opening parentheses C.P.P.F.L.A.G.S. closing parentheses dollar sign opening parentheses C.X.X.F.L.A.G.S. closing parentheses dollar sign caret dash O. dollar sign at sign
Linking a single object file colon N. is made automatically from N. dot O. by running the command dollar sign opening parentheses C.C. closing parentheses dollar sign opening parentheses L.D.F.L.A.G.S. closing parentheses dollar sign caret dollar sign opening parentheses L.O.A.D.L.I.B.E.S. closing parentheses dollar sign opening parentheses L.D.L.I.B.S. closing parentheses dash O. dollar sign at sign

```

23
```
The important variables used by implicit rules are
C.C.: program for compiling C. programs; default C.C.
C.X.X.: program for compiling C. plus plus programs; default G. plus plus
C.F.L.A.G.S.: extra flags to give to the C. compiler
C.X.X.F.L.A.G.S.: extra flags to give to the C. plus plus compiler
C.P.P.F.L.A.G.S.: extra flags to give to the C. preprocessor
L.D.F.L.A.G.S.: extra  flags to give to compilers then they are supposed to invoke the linker
Let’s see how we can now build a C. program without ever explicitly telling make how to do the compilation

```

24
```
C.C. equals G.C.C. hashtag flag for implicit rules C.F.L.A.G.S. equals dash G. hashtag flag for implicit rules period turn on debug info hashtag implicit rule number one colon blah is built via the C. linker implicit rule hashtag implicit rule number two colon blah dot O. is built via the C. compilation implicit rule, because blah dot C. exists
Blah colon blah dot O. blah dot C. colon echo double quote I.N.T. main opening parentheses closing parentheses opening curly brace return zero semicolon closing curly brace double quote greater than blah dot C. clean colon R.M. dash F. blah asterisk
Static pattern rules
Static pattern rules are another way to write less in a makefile, but I’d say are more useful and a bit less double quote magic double quote.

```

25
```
Here’s their syntax
Targets dot dot dot colon target dash pattern colon prereq dash patterns dot dot dot commands
The essence is that the given target is matched by the target dash pattern (via a percentage sign wildcard). Whatever was matched is called the stem.
The stem is then substituted into the prereq dash pattern, to generate the target’s prereqs.
A typical use case is to compile dot C. files into dot O. files.
Here’s the manual way
Objects equals foo dot O. bar dot O. all dot O. all colon dollar sign opening parentheses objects dollar sign hashtag these files compile via implicit rules foo dot O. colon foo dot C. bar dot O. colon bar dot C. all dot O. colon all dot C.

```

26
```
All dot C. colon echo double quote I.N.T. main opening parentheses closing parentheses opening curly brace return zero semicolon closing curly brace double quote greater than all dot C. percentage sign dot C. dolon touch dollar sign at sign clean colon R.M. dash F. asterisk dot c. asterisk dot O. all
Here’s the more efficient way, using a static pattern rule:
Objects equals foo dot O. bar dot O. all dot O. all colon dollar sign opening parentheses objects closing parentheses hashtag these files compile via implicit rules hashtag syntax dash targets dot dot dot colon target dash pattern colon prerq dash patterns dot dot dot

```

27
```
Hashtag in the case of the first target, foo dot O., the target dash pattern matches foo dot O.  and sets the double quote stem double quote to be double quote foo double quote period hashtag it then replaces the single quote percentage single quote in prereq dash patterns with that stem dollar sign opening parentheses objects closing parentheses colon percentage sign period O. colon percentage sign dot C.
All dot C. colon echo double quote I.N.T. main opening parentheses closing parentheses opening curly brace return zero semicolon closing curly brace double quote greater than all dot C. percentage sign dot C. colon touch dollar sign at sign clean colon R.M. dash F. asterisk dot C. asterisk dot O. all

```

28
```
Static pattern rules and filter
While I introduce functions later on, I’ll foreshadow what you can do with them.
The filter function can be used in static pattern rules to match the correct files.
In this example, I made up the dot row and dot result extensions.
O.B.J. underscore files equals foo dot result bar dot O. lose dot O. S.R.V. underscore files equals foo dot raw bar dot C. lose dot C. all colon dollar sign opening parentheses O.B.J. underscore files closing parentheses hashtag note colon P.H.O.N.Y. is important here period without it colon implicit rules will try to build the executable double quote all double quote comma since the prereqs are double quote dot O. double quote files period dot P.H.O.N.Y. colon all hashtag ex one colon dot O. files depend on dot C. files period though we don’t actually make the dot O. file period

```

29
```
Dollar sign opening parentheses filter percentage sign dot O. comma dollar sign opening parentheses O.B.J. underscore files closing parentheses closing parentheses colon percentage sign dot O. colon percentage sign dot C. echo double quote target colon dollar sign at sign prereq colon dollar sign less than double quote

```

30
```
Hashtag ex two colon dot result files depend on dot raw files period though we don’t actually make the dot result file period dollar sign opening parentheses filter percentage sign dot result comma dollar sign opening parentheses O.B.J. underscore files closing parentheses closing parentheses colon percentage sign dot result colon percentage dot raw echo double quote target colon dollar sign at sign prereq colon dollar sign less than double quote percentage sign dot C. percentage dot raw colon touch dollar sign at sign clean colon R.M. dash F. dollar sign opening parentheses S.R.C. underscore files closing parentheses

```

31
```
Pattern rules
Pattern rules are often used but quite confusing.
You can look at them as two ways
A way to define your own implicit rules
A simpler form of static pattern rules
Let’s start with an example first

```

32
```
Hashtag define a pattern rule that compiles every dot C. file into a dot O. file percentage sign dot O. colon percentage dot C. dollar sign opening parentheses C.C. closing parentheses dash C. dollar sign opening parentheses C.F.L.A.G.S. closing parentheses dollar sign opening parentheses C.P.P.F.L.A.G.S. closing parentheses dollar sign less than dash O. dollar sign at sign
Pattern rules contain a single quote percentage sign single quote in the target.
This single quote percentage sign single quote matches any nonempty string, and the other characters match themselves.
Single quote percentage single quote in a prerequisite of a pattern rule stands for the same stem that was matched by the single quote percentage sign single quote in the target.
Here’s another example
Hashtag define a pattern rule that has no pattern in the prerequisites period hashtag this just creates empty dot C. files when needed period percentage sign dot C. colon touch dollar sign at sign

```

33
```
Double dash colon rules
Double dash colon rules are ready used, but allow multiple rules to be defined for the same target.
If these were single colons, a warning would be printed and only the second set of commands would run.
All colon blah blah colon colon echo double quote hello double quote blah colon colon echo double quote hello again double quote
Commands and execution
Command echoing slash silencing
Add an at sign before a command to stop it from being printed
You can also run make with dash S. to add an at sign before each line

```

34
```
All colon
At sign echo double quote this make line will not be printed double quote Echo double quote but this will double quote
Command execution
Each command is run in a new shell (or at least the effect is as such)
All colon C.D. dot dot hashtag the C.D. above does not affect this line, because each command is effectively run in a new shell echo backtick P.W.D. backtick hashtag this C.D. command affects the next because they are on the same line C.D. dot dot semicolon echo backtick P.W.D. backtick hashtag same as above C.D. dot dot semicolon backslash echo backtick P.W.D. backtick
Default shell
Default shell is slash bin slash S.H.
You can change this by changing the variable S.H.E.L.L.

```

35
```
S.H.E.L.L. equals slash bin slash bash cool colon echo double quote hello from bash double quote
Double dollar sign
If you want a string to have a dollar sign, you can use dollar sign dollar sign.
This is how to use a shell variable in bash or S.H.
Note the differences between make file variables and shell variables in this next example.
Make underscore V.A.R. equals I am a make variable all colon hashtag same as running double quote S.H. underscore V.A.R. equals single quote I am a shell variable single quote semicolon echo dollar sign S.H. underscore V.A.R. double quote in the shell S.H. underscore V.A.R. equals single quote I am a shell variable single quote semicolon echo dollar sign dollar sign S.H. underscore V.A.R. hashtag same as running double quote echo I am a make variable double quote in the shell echo dollar sign opening parentheses make underscore V.A.R. closing parentheses

```

36
```
Error handling with dash K., dash I., and dash
Add dash K. when running make to continue running even in the face or errors.
Helpful if you want to see all the errors of make at once.
Add a dash before a command to suppress the error

```

37
```
Add dash I. to make to have this happen for every command.
One colon hashtag this error will be printed but ignored, and make will continue to run dash false touch one
Interrupting or kill make
Note only: if you C.T.R.L. plus C. make, it will delete the newer targets it just made.
Recursive use of make
To recursively call a make file, use the special dollar sign opening parentheses M.A.K.E. closing parentheses instead of make because it will pass flags for you and won’t itself be affected by them.
New underscore contents equals double quote hello colon backslash N. backslash T. touch inside underscore file double quote all colon M.K.D.I.R. dash P. sub D.I.R. print F. dollar sign opening parentheses new underscore contents closing parentheses pipe S.E.D. dash E. single quote S. slash caret slash slash single quote greater than sub D.I.R. slash make file C.D. sub D.I.R. ampersand ampersand dollar sign opening parentheses M.A.K.E. closing parentheses clean colon R.M. dash R.F. sub D.I.R.

```

38
```
Export, environments, and recursive make
When make starts it automatically creates makes variables out of all the environment variables that are set when it’s executed.
Hashtag run this with double quote export shell underscore E.N.V. underscore V.A.R. equals single quote I am an environment variable single quote semicolon make double quote all colon hashtag print out the shell variable echo dollar sign dollar sign shell underscore E.N.V. underscore V.A.R. hashtag print out the make variable echo dollar sign opening parentheses shell underscore E.N.V. underscore V.A.R. closing parentheses

```

39
```
The export directive takes a variable and sets it the environment for all shell commands in all the recipes.
Shell underscore E.N.V. underscore V.A.R. equals shell E.N.V. V.A.R. comma created inside of make export shell underscore E.N.V. underscore V.A.R. all colon echo dollar sign opening parentheses shell underscore E.N.V. underscore V.A.R. closing parentheses echo dollar sign dollar sign shell underscore E.N.V. underscore V.A.R.
As such, when you run the make command inside of make, you can use the export directive to make it accessible to sub dash make commands.

```

40
```
In this example, cooly is exported such that the makefile in subdir can use it.
New underscore contents double quote hello colon backslash N. backslash tech O. backslash dollar sign dollar sign opening parentheses cooly closing parentheses double quote all colon M.K.D.I.R. dash P. sub D.I.R. print F. dollar sign opening parentheses new underscore contents closing parentheses pipe S.E.D. dash E. single quote S. slash caret slash slash single quote greater than sub D.I.R. slash make file at sign echo double quote dash dash dash M.A.K.E.F.I.L.E. C.O.N.T.E.N.T.S. dash dash dash double quote at sign C.D. sub D.I.R. ampersand ampersand cat make file at sign echo double quote dash dash dash E.N.D. M.A.K.E.F.I.L.E. C.O.N.T.E.N.T.S. dash dash dash double quote C.D. sub D.I.R. ampersand ampersand dollar sign opening parentheses M.A.K.E. closing parentheses

```

41
```
Hashtag note that variables and exports period they are set slash affected globally period cooly equals double quote the subdirectory can see me exclamation mark double quote export cooly hashtag this would nullify the line above colon unexport cooly clean colon R.M. dash R.F. sub D.I.R.

```

42
```
You need to export variables to have them run in the shell as well.
One equals this will only work locally export two equals we can run subcommands with this all colon at sign echo dollar sign opening parentheses one closing parentheses at sign dollar sign dollar sign one at sign echo dollar sign opening parentheses two closing parentheses at sign echo dollar sign dollar sign two
Dot E.X.P.O.R.T. underscore A.L.L. underscore V.A.R.I.A.B.L.E.S. exports all variables for you.
Dot E.X.P.O.R.T. underscore A.L.L. underscore V.A.R.I.A.B.L.E.S. colon new underscore contents equals double quote hello colon backslash N. backslash tech O. backslash dollar sign dollar sign opening parentheses cooly closing parentheses double quote cooly equals double quote the subdirectory can see me exclamation mark double quote hashtag this would nullify the line above colon unexport cooly

```

43
```
All colon M.K.D.I.R. dash P. sub D.I.R. print F. dollar sign opening parentheses new underscore contents closing parentheses pipe S.E.D. dash E. single quote S. slash caret slash slash single quote greater than sub D.I.R. slash make file at sign echo double quote dash dash dash M.A.K.E.F.I.L.E. C.O.N.T.E.N.T.S. dash dash dash double quote at sign C.D. sub D.I.R. ampersand ampersand cat make file at sign echo double quote dash dash dash E.N.D. M.A.K.E.F.I.L.E. C.O.N.T.E.N.T.S. dash dash dash double quote C.D. sub D.I.R. ampersand ampersand dollar sign opening parentheses M.A.K.E. closing parentheses clean colon R.M. dash R.F. sub D.I.R.

```

44
```
Arguments to make
There’s a nice list of options that can be run from make.
Check out dash dash dry dash run, dash dash touch, dash dash old dash file.
You can have multiple targets to make, i.e. make clean run text runs the clean goal, then run, and then test.

```

45
```
Variables pt. Two
Flavors and modification
There are two flavors of variables
Recursive (use equals) dash only looks for the variables when the command is used, not when it’s defined.
Simply expanded (use colon equals) dash like normal imperative programming dash dash only those defined so far get expanded
Hashtag recursive variable period this will print double quote later double quote below one equals one dollar sign opening curly brace later underscore variable closing curly brace hashtag simply expanded variable period this will not print double quote later double quote below two colon equals two dollar sign opening curly brace later underscore variable closing curly brace later underscore variable equals later all colon echo dollar sign opening parentheses one closing parentheses echo dollar sign opening parentheses two closing parentheses

```

46
```
Simply expanded (using colon equals) allows you to append to a variable.
Recursive definitions will give an infinite loop error.
One equals hello hashtag one gets defined as a simply expanded variable opening parentheses colon equals closing parentheses and thus can handle appending one colon equals dollar sign opening curly brace one closing curly brace there all colon echo dollar sign opening parentheses one closing parentheses

```

47
```
Question mark equals only sets variables if they have not yet been set
One equals hello one question mark equals will not be set two question mark equals will not be set two question mark equals will be set all colon echo dollar sign opening parentheses one closing parentheses echo dollar sign opening parentheses two closing parentheses
Spaces at the end of a line are not stripped, but those at the start are.
To make a variable with a single space, use dollar sign opening parentheses null string closing parentheses

```

48
```
With underscore spaces equals hello hashtag with underscore spaces has many spaces after double quote hello double quote after equals dollar sign opening parentheses with underscore spaces closing parentheses there null string equals space equals dollar sign opening parentheses null string closing parentheses hashtag make a variable with a single space period all colon echo double quote dollar sign opening parentheses after closing parentheses double quote echo start double quote dollar sign opening parentheses space closing parentheses double quote end
An undefined variable is actually an empty string!
All colon hashtag undefined variables are just empty strings exclamation mark echo dollar sign opening parentheses nowhere closing parentheses
Use plus equals to append
Foo colon equals start foo plus equals more all colon echo dollar sign opening parentheses foo closing parentheses

```

49
```
String substitution is also a really common and useful way to modify variables.
Also check out text functions and filename functions.
Command line arguments and override
You can override variables that come from the command line by using override.
Here we ran make with make option underscore one equals hi
Hashtag overrides command line arguments override option underscore one equals did underscore override hashtag does not override command line arguments option underscore two equals not underscore override all colon echo dollar sign opening parentheses option underscore one closing parentheses echo dollar sign opening parentheses option underscore two closing parentheses
List of commands and define
The define directive is not a function, though it may look that way.

```

50
```
I’ve seen it used so infrequently that I won’t go into details, but it’s mainly used for defining canned recipes and also pairs well with the eval function.
Define slash end E.F. simply creates a variable that is set to a list of commands.
Note here that it’s a bit different than having a semicolon between commands, because each is run in a separate shell, as expected.
One equals export blah equals double quote I was set exclamation mark double quote semicolon echo dollar sign dollar sign blah define two export blah equals double quote I was set exclamation mark double quote echo dollar sign dollar sign blah end E.F.
all colon at sign echo double quote this prints single quote I was set single quote double quote at sign dollar sign opening parentheses one closing parentheses at sign echo double quote this does not print single quote I was set single quote because each command runs in a separate shell double quote at sign dollar sign opening parentheses two closing parentheses

```

51
```
Target dash specific variables
Variables can be set for specific targets
All colon one equals cool all colon echo one is defined colon dollar sign opening parentheses one closing parentheses other colon echo one is nothing colon dollar sign opening parentheses one closing parentheses
Pattern dash specific variables
You can set variables for specific target patterns
Percentage dot C. colon one equals cool blah dot C. colon echo one is defined colon dollar sign opening parentheses one closing parentheses other colon echo one is nothing colon dollar sign opening parentheses one closing parentheses

```

52
```
Conditional part of make files
Conditional if slash else
Foo equals O.K. all colon if E.Q. opening parentheses dollar sign opening parentheses foo closing parentheses colon O.K. closing parentheses echo double quote foo equals O.K. double quote else echo double quote nope double quote end if
Check if a variable is empty
Null string equals foo equals dollar sign opening parentheses null string closing parentheses hashtag end of line semicolon there is a space here all colon if E.Q. opening parentheses dollar sign opening parentheses strip dollar sign opening parentheses foo closing parentheses closing parentheses comma closing parentheses echo double quote foo is empty after being stripped double quote end if if E.Q. opening parentheses opening parentheses dollar sign opening parentheses null string closing parentheses comma closing parentheses echo double quote null string doesn’t even have spaces double quote end if

```

53
```
Check if a variable is defined
If D.E.F. does not expand variable references; it just sees if something is defined at all
Bar equals foo equals dollar sign opening parentheses bar closing parentheses all colon if D.E.F. foo echo double quote foo is defined double quote end if if N.D.E.F. bar echo double quote but bar is not double quote end if

```

54
```
Check if a variable is defined
If D.E.F. does not expand variable references; it just sees if something is defined at all
Bar equals foo equals dollar sign opening parentheses bar closing parentheses all colon if D.E.F. foo echo double quote foo is defined double quote end if if N. def bar echo double quote but bar is not double quote end if
Dollar sign opening parentheses M.A.K.E.F.L.A.G.S.)
This example shows you how to text make flags with find string and M.A.K.E.F.L.A.G.S.
Run this example with make dash I. to see it print out the echo statement.

```

55
```
All colon hashtag search for the double quote dash I. double quote flag period M.A.K.E.F.L.A.G.S. is just a list of single characters comma one per flat period so look for double quote I. double quote in this case period if N.E.Q. opening parentheses comma dollar sign opening parentheses opening parentheses find string I. comma dollar sign opening parentheses M.A.K.E.F.L.A.G.S. closing parentheses closing parentheses closing parentheses echo double quote I was passed to M.A.K.E.F.L.A.G.S. double quote end if
Functions
First functions
Functions are mainly just for text processing.
Call functions with dollar sign opening parentheses F.N. comma arguments closing parentheses or dollar sign opening curly brace F.N. comma arguments closing curly brace.
Make has a decent amount of builtin functions

```

56
```
Bar colon equals dollar sign opening curly brace sub S.T. not comma totally comma double quote I am not superman double quote closing curly brace all colon at sign echo dollar sign opening parentheses bar closing parentheses if you want to replace spaces or commas, use variables
Comma colon equals comma empty colon equals space colon equals dollar sign opening parentheses empty closing parentheses dollar sign opening parentheses empty closing parentheses foo colon equals A.B.C. bar colon equals dollar sign opening parentheses sub S.T> dollar sign opening parentheses space closing parentheses comma dollar sign opening parentheses comma closing parentheses comma dollar sign opening parentheses foo closing parentheses closing parentheses all colon at sign echo dollar sign opening parentheses bar closing parentheses
Do N.O.T. include spaces in the arguments after the first.

```

57
```
That will be seen as part of the string.
Comma colon equals comma empty colon equal space colon equals dollar sign opening parentheses empty closing parentheses dollar sign opening parentheses empty closing parentheses foo colon equals A. B. C. bar colon equals dollar sign opening parentheses sub S.T. dollar sign opening parentheses space closing parentheses comma dollar sign opening parentheses comma closing parentheses comma dollar sign opening parentheses foo closing parentheses closing parentheses all colon hashtag output is double quote comma A. comma B. comma C. double quote period notice the spaces introduced at sign echo dollar sign opening parentheses bar closing parentheses
String substitution
Dollar sign opening parentheses P.A.T. sub S.T. pattern comma replacement comma text closing parentheses does the following

```

58
```
Double quote finds white space dash separated words in text that match pattern and replaces them with replacement.
Here pattern may contain a backtick percentage sign backtick which acts as a wildcard, matching any number of any characters within a word.
If replacement also contains a single quote percentage sign single quote, the single quote percentage sign single quote is replaced by the text that matched the single quote percentage single quote in pattern.
Only the first single quote single quote in the pattern and replacement is treated this way; any subsequent single quote percentage sign single quote is unchanged double quote (G.N.U. docs)
The substitution reference dollar sign opening parentheses text colon pattern equals replacement closing parentheses is a shorthand for this.

```

59
```
There’s another shorthand that replaces only suffixes: dollar sign opening parentheses text colon suffix equals replacement closing parentheses.
No percentage sign wildcard is used here.
Note: don’t add extra spaces for this shorthand. It will be seen as a search or replacement term.
Foo colon equals A. dot O. B. dot O. L. dot A. C. dot O. one colon equals dollar sign opening parentheses P.A.T. sub S.T. percentage sign dot O. comma percentage sign dot C. comma dollar sign opening parentheses foo closing parentheses closing parentheses hashtag this is a shorthand for the above two colon equals dollar sign opening parentheses foo colon percentage sign dot O. equals percentage sign dot C. closing parentheses hashtag this is the suffix dash only shorthand comma and is also equivalent to the above period three colon equals dollar sign opening parentheses foo colon dot C. equals dot C. closing parentheses all colon echo dollar sign opening parentheses one closing parentheses echo dollar sign opening parentheses two closing parentheses echo dollar sign opening parentheses three closing parentheses

```

60
```
The foreach function the foreach function looks like this: dollar sign opening parentheses foreach var comma list comma text closing parentheses.

```

61
```
It converts one list of words (separated by spaces) to another.
V.A.R. is set to each word in list, and text is expanded for each word.
This appends an exclamation after each word
Foo colon equals who are you hashtag for each double quote word double quote in foo comma output that same word with an exclamation after bar colon equals dollar sign opening parentheses foreach W.R.D. comma dollar sign opening parentheses foo closing parentheses comma dollar sign opening parentheses W.R.D. closing parentheses exclamation mark closing parentheses all colon hashtag output is double quote who exclamation mark are exclamation mark you exclamation mark double quote at sign echo dollar sign opening parentheses bar closing parentheses 

```

62
```
The if function
If checks if the first argument is nonempty.
If so, runs the second arguments, otherwise runs the third.
Foo colon equals dollar sign opening parentheses if this dash is dash not dash empty comma then exclamation mark comma else exclamation mark closing parentheses empty colon equals bar colon equals dollar sign opening parentheses if dollar sign opening parentheses empty closing parentheses comma then exclamation mark comma else exclamation mark closing parentheses all colon at sign echo dollar sign opening parentheses foo closing parentheses at sign echo dollar sign opening parentheses bar closing parentheses

```

63
```
The call function
Make supports creating basic functions.
You double quote define double quote the function just by creating a variable, but use the parameters dollar sign opening parentheses zero closing parentheses, dollar sign opening parentheses one closing parentheses, etc.
You then call the function with the special call builtin function.
The syntax is dollar sign opening parentheses call variable comma param comma param closing parentheses.

```

64
```
Dollar sign opening parentheses zero closing parentheses is the variable name, while dollar sign opening parentheses one closing parentheses, dollar sign opening parentheses two closing parentheses, etc. are the params.
Sweet underscore new underscore F.N. equals variable name colon dollar sign opening parentheses zero closing parentheses first colon dollar sign opening parentheses one closing parentheses second colon dollar sign opening parentheses two closing parentheses empty variable colon dollar sign opening parentheses three closing parentheses all colon hashtag outputs double quote variable name colon sweet underscore new underscore F.N. first colon go second colon tigers empty variable colon double quote at sign echo dollar sign opening parentheses call sweet underscore new underscore F.N. comma go comma tigers closing parentheses

```

65
```
The shell function
Shell dash this calls the shells, but it replaces new lines with spaces!
All colon at sign echo dollar sign opening parentheses shell L.S. dash L.A. closing parentheses hashtag very ugly because the newlines are gone exclamation mark
Other features
Include make files the include directive tells make to read one or more other makefiles.

```

66
```
It’s a line in the make file that looks like this
Include file names dot dot dot
This is particularly useful when you use compiler flags like dash M. that create makefiles based on the source.
For example, if some C. files includes a header, that header will be added to a makefile that’s written by G.C.C. I talk about this more in the make file cook book
The V. path directive
Use V. path to specify where some set of prerequisites exist.
The format is V. path less than pattern greater than less than directories comma space slash colon separated greater than less than pattern greater than can have a percentage sign, which makes any zero or more characters.

```

67
```
You can also do this globallyish with the variable P.A.T.H.
V. path percentage sign dot H. dot dot slash headers dot dot slash other dash directory hashtag note colon V. path allows blah dot H. to be found even though blah dot H. is never in the current directory some underscore binary colon dot dot slash headers blah dot H. touch some underscore binary dot dot slash headers colon M.K.D.I.R. dot dot slash headers
Hashtag we call the target blah dot H. instead of dot dot slash headers slash blah dot H. comma because that’s the prereq that some underscore binary is looking for hashtag typically comma blah dot H. would already exist and you wouldn’t need this period

```

68
```
Blah dot H. colon touch dot dot slash headers slash blah dot H. clean colon R.M. dash R.F. dot dot slash headers R.M. dash F. some binary
Multiline
The backslash (double quote backslash double quote) character gives us the ability to use multiple lines when the commands are too long
Some underscore file colon echo this line is too long comma so backslash it is broken up into multiple lines
Dot phony
Adding dot P.H.O.N.Y. to a target will prevent make from confusing the phony target with a file name.

```

69
```
In this example, if the file clean is created, make clean will still be run.
Technically, I should have used it in every example with all or clean, but I didn’t to keep the examples clean.
Additionally, the double quote phony double quote targets typically have names that are rarely file names, and in practice many people skip this.
Some underscore file colon Touch some underscore file touch clean dot P.H.O.N.Y. colon clean clean colon R.M. dash F. some underscore file R.M. dash F. clean
Dot delete underscore on underscore error
The make tool will stop running a rule (and will propagate back to prerequisites) if a command returns a nonzero exit status.
D.E.L.E.T.E. underscore O.N. underscore E.R.R.O.R. will delete the target of a rule if the rule fails in this manner.

```

