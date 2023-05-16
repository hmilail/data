0
```
Tutorial: Introduction
```

1
```
We're about to embark on a journey of building universal app.
```

2
```
In this tutorial, we'll create a universal app that runs on Android, iOS, and the web; all with a single codebase.
```

3
```
Let's get started!
```

4
```
About this tutorial
```

5
```
The objective of this tutorial is to get started with Expo and become familiar with the Expo SDK.
```

6
```
It'll cover the following topics:
```

7
```
- Create an Expo App
```

8
```
Break down the app layout and implement it with flexbox
```

9
```
Use each platform's system UI to select an image from the media library
```

10
```
Create a sticker modal using the
- less than
- modal capital in the first character of the first word
- greater than
and
- less than
- flast list in camel case capital in the first character of the first word
- greater than
components from React Native
```

11
```
Add touch gestures to interact with a sticker
```

14
```
Use third-party libraries to capture a screenshot and save it to the disk
```

15
```
Handle platform differences between Android, iOS, and web
```

16
```
Finally, go through the process of configuring a status bar, a splash screen, and an icon to complete the app
```

17
```
These topics will provide a good foundation for learning the fundamentals of building a mobile app.
```

18
```
The tutorial is self-paced and can take two to three hours to complete.
```

19
```
To keep it beginner friendly, we divided the tutorial into eight chapters so that you can follow along or put it down and come back to it later.
```

20
```
Each chapter also contains all the necessary code so that you can follow along by creating an app from scratch or using Snack examples to copy and paste the code if you get lost.
```

21
```
Before we get started, take a look at what we'll build. It's an app named
- sticker
- smash
that runs on Android, iOS, and the web:
```

22
```
The complete source code for this tutorial is available on
- Snack.
```

23
```
How to use this tutorial
```

24
```
We believe in learning by doing so this tutorial emphasizes doing over explaining.
```

25
```
You can follow along the journey of building the app by creating the app from scratch.
```

26
```
highlighted parts says "highlighted in yellow"
```

27
```
Throughout the tutorial, any important code or code that has changed between examples will be highlighted in yellow.
```

28
```
You can hover over the highlights (on desktop) or tap them (on mobile) to see more context on the change.
```

29
```
For example, the code highlighted in the snippet below explains what it does:
```

30
```
- Hello world capital in the first character of the first word
- Open in Snack
```

31
```
highlighted part of the code
```

32
```
- line 6:
  - less than
  - text capital in the first character
  - greater than
  - hello world capital in the first character of the first word
  - exclamation mark
  - less than
  - slash
  - text capital in the first character
  - greater than
```

33
```
full form of code
```

34
```
line 1:
- import
- space
- opening curly brace
- space
- style sheet in camel case capital in the first character of the first word
- comma
- space
- text capital in the first character
- comma
- space
- view capital in the first character
- space
- closing curly brace
- space
- from
- space
- single quote
- react dash native
- single quote
- semicolon
- new line
line 2:
- new line
```

35
```
line 3:
- export
- space
- default
- space
- function
- space
- app capital in the first character
- opening parenthesis
- closing parenthesis
- space
- opening curly brace
- new line
```

36
```
line 4:
- indent
- return
- space
- opening parenthesis
- new line
```

37
```
line 5:
- indent
- indent
- less than
- view capital in the first character
- space
- style
- equals
- opening curly brace
- styles
- dot
- container
- closing curly brace
- greater than
- new line
```

38
```
line 5:
- indent
- indent
- less than
- view capital in the first character
- space
- style
- equals
- opening curly brace
- styles
- dot
- container
- closing curly brace
- greater than
- new line
```

39
```
line 6:
- indent
- indent
- indent
- less than
- text capital in the first character
- greater than
- less than
- hello world capital in the first character of the first word
- exclamation mark
- slash
- text capital in the first character
- greater than
- new line
```

40
```
line 7:
- indent
- indent
- less than
- slash
- view capital in the first character
- greater than
- new line
```

41
```
line 8:
- indent
- closing parenthesis
- semicolon
- new line
```

42
```
line 9:
- closing curly brace
- new line
line 10:
- new line
```

43
```
line 11:
- C.O.N.S.T.
- space
- styles
- space
- equals
- space
- style sheet in camel case capital in the first character of the first word
- dot
- create
- opening parenthesis
- opening curly brace
- new line
```

43
```
line 12:
- indent
- container
- colon
- space
- opening curly brace
- new line
```

44
```
line 13:
- indent
- indent
- flex
- colon
- space
- one
- comma
- new line
```

45
```
line 14:
- indent
- indent
- background color in camel case
- colon
- space
- single quote
- hash F.F.F.
- single quote
- comma
- new line
```

46
```
line 15:
- indent
- indent
- align items in camel case
- colon
- space
- single quote
- center
- single quote
- comma
- new line
```

47
```
line 16:
- indent
- indent
- justifyContent in camel case
- colon
- space
- single quote
- center
- single quote
- comma
- new line
```

48
```
line 17:
- indent
- closing curly brace
- comma
- new line
```

49
```
line 18:
- closing curly brace
- closing parenthesis
- semicolon
```

50
```
Wait, what is this "Open in Snack" button?
```

51
```
Snack is a web-based editor that works similarly to an Expo project.
```

52
```
It's a great way to share code snippets and experiments without downloading any tools on your computer.
```

53
```
Go ahead and press the above button.
```

54
```
You will see the above code running in a Snack.
```

55
```
Try to switch between iOS, Android, or the web tabs.
```

56
```
You can also open it on your device in the Expo Go app from the
- My device capital in the first character of the first word
tab.
```

57
```
Throughout this tutorial, use Snack to copy and paste the code into your project on your computer.
```

58
```
We will continue to provide Snacks for each module, but
- we recommend you create the app on your machine to go through the experience of building the app.
```

59
```
Next step
```

60
```
Create your first app with
```

61
```
if you're already familiar with Expo, feel free to jump ahead to specific chapters.
```

62
```
However, if you'd like to start from scratch,
```

63
```
continue to the next chapter in which we will learn how to create your first app with Expo.
```