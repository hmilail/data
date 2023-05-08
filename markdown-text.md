```
/java_teaching_mobile_app/assets/custom_script/
```

```
We're about to embark on a journey of building universal apps. In this tutorial, we'll create a universal app that runs on Android, iOS, and the web; all with a single codebase. Let's get started!
```

```
About this tutorial
```

```
The objective of this tutorial is to get started with Expo and become familiar with the Expo SDK. It'll cover the following topics:
```

```
Create an Expo App
```

```
Break down the app layout and implement it with flexbox
```

```
Use each platform's system UI to select an image from the media library
```

```
Create a sticker modal using the
less than
Modal
greater than
and
less than
FlatList
greater than
components from React Native
```

```
Add touch gestures to interact with a sticker
```

```
Use third-party libraries to capture a screenshot and save it to the disk
```

```
Handle platform differences between Android, iOS, and web
```

```
Finally, go through the process of configuring a status bar, a splash screen, and an icon to complete the app
```

```
These topics will provide a good foundation for learning the fundamentals of building a mobile app. The tutorial is self-paced and can take two to three hours to complete.
```

```
To keep it beginner friendly, we divided the tutorial into eight chapters so that you can follow along or put it down and come back to it later.
```

```
Each chapter also contains all the necessary code so that you can follow along by creating an app from scratch or using Snack examples to copy and paste the code if you get lost.
```

```
Before we get started, take a look at what we'll build. It's an app named StickerSmash that runs on Android, iOS, and the web:
```

```
The complete source code for this tutorial is available on Snack.
```

```
How to use this tutorial
```

```
We believe in learning by doing so this tutorial emphasizes doing over explaining. You can follow along the journey of building the app by creating the app from scratch.
```

```
Throughout the tutorial, any important code or code that has changed between examples will be highlighted in yellow. You can hover over the highlights (on desktop) or tap them (on mobile) to see more context on the change.
```

```
For example, the code highlighted in the snippet below explains what it does:
```

```
Hello world
Open in Snack
```

```
import
space
opening curly brace
space
style sheet in camel case with capital S
comma
space
text with capital t
comma
space
```

```
view with capital v
space
closing curly brace
space
from
space
```

```
single quote
react
dash
native
single quote
semicolon
new line
new line
```

```
export
space
default
space
function
app with capital a
opening parenthesis
closing parenthesis
space
opening curly brace
new line
```

```
indent
return
space
opening parenthesis
new line
```

```
indent
indent
less than
view with capital v
space
style
equals
opening curly brace
styles
dot
container
closing curly brace
greater than
new line
```

```
indent
indent
indent
less than
text with capital t
more than
hello world with capital h
exclamation mark
less than
slash
text with capital t
greater than
new line
```

```
indent
indent
less than
slash
view with capital v
greater than
new line
```

```
indent
opening parenthesis
semicolon
new line
```

```
closing curly brace
new line
new line
```

```
C. O. N. S. T.
space
styles
space
equals
space
style sheet in camel case with capital s
dot
create
opening parenthesis
opening curly brace
new line
```

```
indent
container
colon
space
opening curly brace
new line
```

```
indent
indent
flex
colon
space
one
comma
new line
```

```
indent
indent
backgroundColor in camel case
comma
space
single quote
hash
F. F. F.
single quote comma
new line
```

```
indent
indent
align items in camel case
comma
space
single quote
center
single quote
comma
new line
```

```
indent
indent
justify content in camel case
comma
space
single quote
center
single quote
comma
new line
```

```
indent
closing curly brace
comma
new line
```

```
closing curly brace
closing parenthesis
semicolon
```

```
Wait, what is this "Open in Snack" button?
```

```
Snack is a web-based editor that works similarly to an Expo project. It's a great way to share code snippets and experiments without downloading any tools on your computer.
```

```
Go ahead and press the above button. You will see the above code running in a Snack. Try to switch between iOS, Android, or the web tabs. You can also open it on your device in the Expo Go app from the My device tab.
```

```
Throughout this tutorial, use Snack to copy and paste the code into your project on your computer. We will continue to provide Snacks for each module, but we recommend you create the app on your machine to go through the experience of building the app.
```

```
Next step
```

```
Create your first app with
```

```
If you're already familiar with Expo, feel free to jump ahead to specific chapters. However, if you'd like to start from scratch, continue to the next chapter in which we will learn how to create your first app with Expo.
```
