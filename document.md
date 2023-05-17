https://levelup.gitconnected.com/react-native-authentication-flow-the-simplest-and-most-efficient-way-3aa13e80af61

0
```
React Native Authentication Flow, the Simplest and Most Efficient Way

Connect with API, persists data, and recover them in future sessions

- Lucas Garcez
- Follow?
- Published in Level Up Coding
- 3 minutes read
- April fifth twenty-twenty-one
```

1
```
- Photo by Chris Panas on Unsplash

Almost all apps need authentication flow because they contain contents that authorized users should only access.

This article will explain how created a React Native authentication flow that connects to APIs, persists data to be recovered in future sessions, and provides an efficient way for the whole application to subscribe to the auth state changes.
```

2
```
The focus here is to build the entire structure for the flow described above, not create the App from scratch. But you can access the complete code
- repository here.

Authenticated and unauthenticated users

In React Native, a common way to separate these users is to create different "groups" screens. One for unauthenticated users, which contains screens like sign in and sign up, and the other for the authenticated users, containing screens like home, settings, and all others related to the user content.
```

3
```
The react-navigation library will help create these groups, more specifically, the
- createStackNavigator
function.
- AppStack,
the first group, will contain the
home screen,
and the
AuthStack
will include the
sign screen.
```

4
```
line 1:
- import
- space
- opening curly brace
- create stack navigator in camel case
- space
- from
- space
- single quote
- at sign
- react dash navigation slash stack
- single quote
- semicolon
- new line
```

5
```
line 2:
- C.O.N.S.T
- space
- stack capital in the first character
- space
- equals
- space
- create stack navigator in camel case
- opening curly brace
- closing curly brace
- semicolon
- new line
line 3:
- new line
```

6
```
line 4:
- C.O.N.S.T.
- space
- app stack in camel case capital in the first character of the first word
- space
- equals
- space
- opening curly brace
- closing curly brace
- space
- equals
- greater than
- space
- opening curly brace
- new line
line 5:
- indent
- return
- space
- opening parenthesis
- new line
```

7
```
line 6:
- indent
- indent
- less than
- stack dot navigator capital in the first character of every word
- greater than
- new line
line 7:
- indent
- indent
- indent
- less than
- stack dot screen capital in the first character of every word
- space
- name
- equals
- double quote
- home screen screen capital in the first character of every word
- double quote
- space
- component
- equals
- opening curly brace
- home screen in camel case capital in the first character of the first word
- closing curly brace
- space
- slash
- greater than
```

8
```
line 8:
- indent
- indent
- less than
- slash
- stack dot navigator capital in the first character of every word
- greater than
- new line
line 9:
- indent
- closing parenthesis
- semicolon
- new line
line 10:
- closing curly brace
- semicolon
- new line
line 11:
- new line
```

9
```
line 12:
- C.O.N.S.T.
- space
- auth stack in camel case capital in the first character of the first word
- space
- equals
- space
- opening curly brace
- closing curly brace
- space
- equals
- greater than
- space
- opening curly brace
- new line
line 13:
- indent
- return
- space
- opening parenthesis
- new line
```

10
```
line 14:
- indent
- indent
- less than
- stack dot navigator capital in the first character of every word
- greater than
- new line
line 15:
- indent
- indent
- indent
- less than
- stack dot screen capital in the first character of every word
- space
- name
- equals
- double quote
- sign screen screen capital in the first character of every word
- double quote
- space
- component
- equals
- opening curly brace
- sign screen in camel case capital in the first character of the first word
- closing curly brace
- space
- slash
- greater than
```

11
```
line 16:
- indent
- indent
- less than
- slash
- stack dot navigator capital in the first character of every word
- greater than
- new line
line 17:
- indent
- closing parenthesis
- semicolon
- new line
line 18:
- closing curly brace
- semicolon
- new line

- R.N. auth dash stack dot tsx capital on the first character of words auth and stack
hosted with red hear emoji by
- GitHub

- view raw?
```

12
```
Create a
- Router
component responsible for choose which stack show depending on whether the user is authenticated or not. The stacks need to be inside the
- NavigationContainer,
a component from react-navigation that manages the navigation tree and navigation state.
```

13
```
line 1:
- import
- space
- opening curly brace
- navigation container in camel case capital in the first character of the first word
- closing curly brace
- space
- from
- space
- single quote
- at sign
- react dash navigatoin slash native
- single quote
- semicolon
- new line
line 2:
- new line
```

14
```
line 3:
- import
- space
- opening curly brace
- app stack in camel case capital in the first character of the first word
- closing curly brace
- space
- from
- space
- single quote
- dot slash app stack in camel case capital in the first character of the first word
- single quote
- semicolon
- new line
line 4:
- import
- space
- opening curly brace
- auth stack in camel case capital in the first character of the first word
- closing curly brace
- space
- from
- space
- single quote
- dot slash auth stack in camel case capital in the first character of the first word
- single quote
- semicolon
- new line
line 5:
- new line
line 6:
- new line
```

15
```
line 7:
- export
- space
- C.O.N.S.T.
- space
- router capital in the first character
- space
- equals
- space
- opening parenthesis
- closing parenthesis
- space
- equals
- greater than
- space
- opening curly brace
- new line
line 8:
- slash
- slash
- More capital in the first characer explanations about "authData" in camel case in double quote below
- new line
```

16
```
line 9:
- indent
- return
- space
- opening parenthesis
- new line
line 10:
- indent
- indent
- less than
- navigation container in camel case capital in the first character of the first word
- greater than
- new line
line 11:
- indent
- indent
- indent
- opening curly brace
- auth data in camel case
- space
- question mark
- space
- less than
- app stack in camel case capital in the first character of the first word
- space
- slash
- greater than
- space
- colon
- space
- less than
- auth stack in camel case capital in the first character of the first word
- space
- slash
- greater than
- closing curly brace
- new line
```

17
```
line 12:
- indent
- indent
- less than
- slash
- navigation container in camel case capital in the first character of the first word
- greater than
- new line
line 13
- indent
- closing parenthesis
- semicolon
- closing curly brace
- semicolon

- R.N. auth dash router dash init dot tsx capital on the first character of words auth and router
hosted with red hear emoji by
- GitHub

- view raw?
```

18
```
The
- authData
represents the user authentication state, in other words, if there is an authentication user or not. The
- authData cannot be a simple property from the
- Router
because others components can update it from different places in the App, so it's necessary another solution. An excellent alternative to resolve that is to use the React Context.
```

19
```
quoted text: "Context provides a way to pass data through the component tree without having to pass props down manually at every level, and any component in the tree can "listener" Context changes."
```

20
```
Use React Context to provide the authData

The Context needs to provide the
- authData
itself, a function to sign in, a function to sign out, and a loading state. The sign-in function will connect with the API and update the
- authData based on the response. The sign-out function will clean the data, and in some cases, connect with API to invalidate a token or something like that. The loading state is necessary because the authentication process is an async task, connected with API as the local persistent. So the data shape can like that:
```

21
```
line 1:
- type
- space
- auth context data in camel case capital in the first character of the first word
- space
- equals
- space
- opening curly brace
- nee line
line 2:
- indent
- auth data in camel case
- question mark
- colon
- space
- auth data in camel case capital in the first character of the first word
- semicolon
- new line
```

22
```
line 3:
- indent
- loading
- colon
- space
- boolean
- semicolon
- new line
line 4:
- indent
- sign in in camel case
- opening parenthesis
- closing parenthesis
- colon
- space
- promise capital in the first character
- less than
- void
- greater than
- semicolon
- new line
```

23
```
line 5:
- indent
- sign out in camel case
- opening parenthesis
- closing parenthesis
- colon
- space
- void
- semicolon
- new line
line 6:
- closing curly brace
- semicolon
- new line
line 7:
- new line
```

24
```
line 8:
- type
- space
- auth data in camel case capital in the first character of the first word
- space
- equals
- space
- opening curly brace
- new line
line 9:
- indent
- token
- colon
- space
- string
- semicolon
- new line
line 10:
- indent
- email
- colon
- space
- string
- semicolon
- new line
```

25
```
line 11:
- indent
- name
- colon
- space
- string
- semicolon
- new line
line 12:
- closing curly brace
- semicolon

- R.N. auth dash auth context data dot T.S. capital on the first character of words the first auth word, the second auth word, the word context and the word data
hosted with red heart emoji by
- GitHub

- view war
```

26
```
With these
- types
to orientate, we can create the Context, called by
- AuthContext,
and your relative provider, called by
- AuthProvide.

The code below is a slightly longer but we can read from top to bottom.
Every part has a comment that explains what is and what the intention is.
```

27
```
line 1:
- import
- space
- react capital at the first character
- comma
- space
- opening curly brace
- create context in camel case
- comma
- space
- use state in camel case
- comma
- space
- use context in camel case
- closing curly brace
- space
- from
- space
- single quote
- react
- single quote
- semicolon
- new line
```

28
```
line 2:
- import
- space
- opening curly brace
- auth data in camel case
- comma
- space
- auth service in camel case
- closing curly brace
- space
- from
- space
- single quote
- dot dot slash services slash auth service in camel case
- single quote
- semicolon
- new line
line 3:
- new line
```

29
```
line 4:
- C.O.N.S.T.
- auth context in camel case capital in the first character of the first word
- space
- equals
- space
- create context in camel case
- less than
- auth context data camel case capital in the first character of the first word
- greater than
- opening parenthesis
- opening curly brace
- closing curly brace
- space
- as
- space
- auth context data camel case capital in the first character of the first word
- closing parenthesis
- semicolon
- new line
line 5:
- new line
```

30
```
line 6:
- C.O.N.S.T.
- auth provider in camel case capital in the first character of the first word
- colon
- space
- react capital in the first character dot F.C.
- space
- equals
- space
- opening parenthesis
- opening curly brace
- children
- closing curly brace
- closing parenthesis
- space
- equals
- greater than
- space
- opening curly brace
- new line
```

31
```
line 7:
- indent
- C.O.N.S.T.
- space
- opening bracket
- auth data in camel case
- comma
- space
- set auth data in camel case
- closing bracket
- space
- equals
- space
- use state in camel case
- less than
- auth data in camel case capital in the first character of the first word
- greater than
- opening parenthesis
- closing parenthesis
- semicolon
- new line
line 8:
- new line
```

32
```
line 9:
- indent
- slash
- slash
- The loading part will be explained in the persist step session
- new line
line 10:
- indent
- C.O.N.S.T.
- space
- opening bracket
- loading
- comma
- space
- set loading in camel case
- closing bracket
- space
- equals
- space
- use state in camel case
- opening parenthesis
- true
- closing parenthesis
- semicolon
- new line
line 11:
- new line
```

33
```
line 12:
- indent
- C.O.N.S.T.
- space
- sign in in camel case
- space
- equals
- space
- async
- space
- opening parenthesis
- closing parenthesis
- space
- equals
- greater than
- space
- opening curly brace
- new line
line 13:
- indent
- indent
- slash
- slash
- call the service passing credential (email and password).
- new line
line 14:
- indent
- indent
- slash
- slash
- In a real App this data will be provided by the user from some InputText components.
- new line
```

34
```
line 15:
- indent
- indent
- C.O.N.S.T.
- space
- underscore auth data in camel case
- space
- equals
- space
- await
- space
- auth service in camel case dot sign in in camel case
- opening parenthesis
- new line
line 16:
- indent
- indent
- indent
- single quote
- lucas garcez at email dot com
- single quote
- comma
- new line
line 17:
- indent
- indent
- indent
- single quote
- one two three four five six
- single quote
- comma
- new line
line 18:
- indent
- indent
- closing parenthesis
- semicolon
- new line
line 19:
- new line
```

35
```
line 20:
- indent
- indent
- slash
- slash
- Set the data in the context, so the App can be notified
- new line
line 21:
- indent
- indent
- slash
- slash
- and send the user to the AuthStack
- new line
line 22:
- indent
- indent
- set auth data in camel case
- opening parenthesis
- underscore auth data in camel case
- closing parenthesis
- semicolon
- new line
line 23:
- closing curly brace
- semicolon
- new line
line 24:
- new line
```

36
```
line 25:
- indent
- indent
- C.O.N.S.T.
- space
- sign out in camel case
- space
- equals
- space
- async
- space
- opening parenthesis
- closing parenthesis
- space
- equals
- greater than
- space
- opening curly brace
- new line
line 26:
- indent
- indent
- slash
- slash
- Remove data from context, so the App can be notified
- new line
line 27:
- indent
- indent
- slash
- slash
- and sent the user to the AuthStack
- new line
```

37
```
line 28:
- indent
- indent
- set auth data in camel case
- opening parenthesis
- undefined
- closing parenthesis
- semicolon
- new line
line 29:
- closing curly brace
- semicolon
- new line
line 30:
- new line
```

38
```
line 31:
- indent
- return
- space
- opening parenthesis
- new line
line 32:
- indent
- indent
- slash
- slash
- This component will be used to encapsulate the whole App,
- new line
line 33:
- indent
- indent
- slash
- slash
- so all components will have access to the Context
- new line
line 34:
- indent
- indent
- less than
- auth context in camel case capital in the first character of the first word dot provider capital in the first character
- space
- value
- equals
- opening curly brace
- opening curly brace
- auth data in camel case
- comma
- space
- loading
- comma
- space
- sign in in camel case
- comma
- space
- sign out in camel case
- closing curly brace
- closing curly brace
- greater than
- new line
```

39
```
line 35:
- indent
- indent
- indent
- opening curly brace
- children
- closing curly brace
- new line
line 36:
- less than
- slash
- auth context in camel case capital in the first character of the first word dot provider capital in the first character
- greater than
- new line
line 37:
- indent
- closing parenthesis
- semicolon
- new line
line 38:
- closing curly brace
- semicolon
- new line

- R.N. auth dash auth dash initial dot T.S.X. capital on the first character of words the first auth word and the second auth word
hosted with red heart emoji by
- GitHub

- view raw?
```

40
```
To any component listener authentication status changes and call the sign-in and sign-out functions, the
- App
root components should encapsulate the Router with the AuthProvider.
```

41
```
line 1:
- import
- space
- react capital in the first character
- space
- from
- space
- single quote
- react
- single quote
- semicolon
- new line
line 2:
- import
- space
- opening curly brace
- router capital in the first character
- closing curly brace
- space
- from
- space
- single quote
- dot slash S.R.C. slash routes slash router capital in the first character
- single quote
- semicolon
- new line
```

42
```
line 3:
- import
- space
- opening curly brace
- auth provider in camel case capital in the first character of the first word
- closing curly brace
- space
- from
- space
- single quote
- dot slash S.R.C. slash contexts slash auth capital in the first character
- single quote
- semicolon
- new line
line 4:
- new line
```

43
```
line 5:
- C.O.N.S.T.
- slash
- app capital in the first character
- space
- equals
- space
- opening parenthesis
- closing parenthesis
- space
- equals
- greater than
- space
- opening curly brace
- new line
line 6:
- indent
- return
- space
- opening parenthesis
line 7:
- indent
- indent
- less than
- auth provider in camel case capital in the first character of the first word
- greater than
- new line
```

44
```
line 8:
- indent
- indent
- indent
- less than
- router capital in the first character of the first word
- space
- slash
- greater than
- new line
line 9:
- indent
- indent
- less than
- slash
- auth provider in camel case capital in the first character of the first word
- greater than
- new line
line 10:
- indent
- closing parenthesis
- semicolon
- new line
line 11:
- closing curly brace
- semicolon
- new line
line 12:
- new line
line 13:
- export
- space
- default
- space
- app capital in the first character
- semicolon

- R.N. auth dash app dot T.S.X. capital on the first character of words auth word and app word
hosted with red heart emoji by
- GitHub

- view raw?
```

45
```
To facilitate the access to
- AuthContext
we can create a simple
- React Hooks
that abstracts the context connections logic.
```

46
```
line 1:
- function
- space
- use auth in camel case
- opening parenthesis
- closing parenthesis
- colon
- space
- auth context data in camel case capital in the first character of the first word
- space
- opening curly brace
- new line
line 2:
- indent
- C.O.N.S.T.
- space
- context
- space
- equals
- space
- use context in camel case
- opening parenthesis
- auth context in camel case capital in the first character of the first word
- closing parenthesis
- semicolon
- new line
line 3:
- new line
```

47
```
line 4:
- indent
- if
- space
- opening parenthesis
- exclamation mark
- context
- closing parenthesis
- space
- opening curly brace
- new line
line 5:
- indent
- indent
- throw
- space
- new
- space
- error capital in the first character
- opening parenthesis
- single quote
- useAuth must be used within an AuthProvider
- single quote
- closing parenthesis
- semicolon
- new line
```

48
```
line 6:
- indent
- closing curly brace
- new line
line 7:
- new line
line 8:
- indent
- return
- space
- context
- semicolon
- new line
line 9:
- closing curly brace

- R.N. auth dash use auth dot T.S.X. capital on the first character of words the first auth word and the second auth word
hosted with red heart emoji by
- GitHub

- view raw?
```

49
```
The
- Router
component will use the
- useAuth
hooks to decide which correct stack to display and show a
- Loading
component if data is not ready.
```

50
```
line 1:
- import
- space
- react capital in the first character
- space
- from
- space
- single quote
- react
- single quote
- semicolon
- new line
line 2:
- import
- space
- opening curly brace
- button capital in the first character
- comma
- space
- text capital in the first character
- comma
- space
- view capital in the first character
- closing curly brace
- space
- from
- space
- single quote
- react dash native
- single quote
- semicolon
- new line
line 3:
- new line
```

51
```
line 4:
- import
- space
- opening curly brace
- styles
- closing curly brace
- space
- from
- space
- single quote
- dot slash styles
- single quote
- semicolon
- new line
line 5:
- import
- space
- opening curly brace
- use auth in camel case
- closing curly brace
- space
- from
- space
- single quote
- dot dot slash contexts slash auth capital in the first character of the word auth
- single quote
- semicolon
- new line
line 6:
- new line
line 7:
- slash
- slash
- SIGN IN SCREEN
- new line
```

52
```
line 8:
- export
- space
- C.O.N.S.T.
- space
- sign in screen in camel case capital in the first character of the first word
- space
- equals
- space
- opening parenthesis
- closing parenthesis
- space
- equals
- greater than
- space
- opening curly brace
- new line
line 9:
- indent
- C.O.N.S.T.
- space
- auth
- space
- equals
- space
- use auth in camel case
- opening parenthesis
- closing parenthesis
- semicolon
- new line
line 10:
- new line
```

53
```
line 11:
- indent
- return
- space
- opneing parenthesis
- new line
line 12:
- indent
- indent
- less than
- view capital in the first character
- space
- style
- equals
- opening curly brace
- styles dot container
- closing curly brace
- greater than
- new line
line 13:
- indent
- indent
- indent
- less than
- text capital in the first character
- greater than
- Sign In Screen
- less than
- slash
- text capital in the first character
- greater than
- new line
line 14:
- indent
- indent
- indent
- less than
- button capital in the first character
- space
- title
- equals
- double quote
- Sign In
- double quote
```

54
```
- space
- on press in camel case
- equals
- opening curly brace
- auth dot sign in with sign in text in camel case
- closing curly brace
- space
- slash
- greater than
- new line
line 15:
- indent
- indent
- less than
- slash
- view capital in the first character
- greater than
- new line
line 16:
- indent
- closing parenthesis
- semicolon
- new line
line 17:
- indent
- closing curly brace
- semicolon
- new line
line 18:
- new line
line 19:
- slash
- slash
- HOME SCREEN
- new line
```

55
```
line 20:
- export
- space
- C.O.N.S.T.
- space
- home screen in camel case capital in the first character of the first word
- space
- equals
- opening parenthesis
- closing parenthesis
- space
- equals
- greater than
- space
- opening curly brace
- new line
line 21:
- indent
- C.O.N.S.T.
- space
- auth
- space
- equals
- space
- use auth in camel case
- opening parenthesis
- closing parenthesis
- semicolon
- new line
line 22:
- new line
```

56
```
line 23:
- indent
- return
- space
- opening parenthesis
- new line
line 24:
- indent
- indent
- less than
- view capital in the first character
- space
- style
- equals
- opening curly brace
- styles dot container
- closing curly brace
- greater than
- new line
line 25:
- indent
- indent
- indent
- less than
- text capital in the first character
- greater than
- HOME SCREEN
- less than
- slash
- text capital in the first character
- greater than
- new line
```

57
```
line 26:
- indent
- indent
- less than
- button capital in the first character
- space
- title
- equals
- double quote
- Sign Out
- double quote
- space
- on press in camel case
- equals
- opening curly brace
- auth dot sign out with the text sign out in camel case
- closing curly brace
- space
- slash
- greater than
- new line
line 27:
- indent
- indent
- less than
- slash
- view capital in the first character
- greater than
- new line
line 28:
- indent
- closing parenthesis
- semicolon new line
line 29:
- closing curly brace
- semicolon
```

58
```
Persist data

The last problem to be resolved is persistence. Up to now, when the App is closed and opened, all data is lost, because the Context only exists in the App's memory. The
- @react-native-async-storage/async-storage
library will handle this and persist the data. As
AppProvider
concentrate the auth state changes, then this is the most suitable location to put the persistence logic.
```

59
```
- When the App starts: Check the storage; if there are data, update the
  - authData
state.
- When the user sign in: Saves the
  - authData
from API at the storage.
- When the user sign out: Remove the
  - authData
from the storage.
```

60
```
slash slash ...other imports new line
import space asyn storage in camel case capital in the first character of the first word space from space single quote at sign react dash native dash community slash async dash storage single quote semicolon new line
new line
C.O.N.S.T. space auth provider in camel case capital in the first character of the first word colon space react capital in the first character dot F.C. all capital space equals space opening parenthesis opening curly brace children closing curly brace closing parenthesis space equals greater than space opening curly brace new line
indent C.O.N.S.T. space opening bracket auth data in camel case comma space set auth data in camel case closing bracket space equals space use state in camel case less than auth data in camel case capital in the first character of the first word greater than opening parenthesis closing parenthesis semicolon new line
indent slash slash the AuthContext start with loading equals true new line
indent slash slash and stay like this, until the data be loaded from Async Storage new line
indent C.O.N.S.T. space opening bracket loading comma space set loading in camel case closing bracket space equals space use state in camel case opening parenthesis true closing parenthesis semicolon new line
new line
indent use effect in camel case opening parenthesis opening parenthesis closing parenthesis space equals greater than space opening curly brace new line
indent indent slash slash Every time the App is opened, this provider is rendered new line
indent indent slash slash and call the loadStorageData function. new line
indent indent load stoarge data in camel case opening parenthesis closing parenthesis semicolon new line
indent closing curly brace comma space opening bracket closing bracket closing parenthesis semicolon new line
new line
indent async space function space load storage data in camel case opening parenthesis closing parenthesis colon space promise capital in the first character less than void greater than space opening curly brace new line
indent indent try space opening curly brace new line
indent indent indent slash slash Try get the data from Async Storage new line
indent indent indent C.O.N.S.T. auth data serialized in camel case space equals space await space async storage in camel case capital in the first character of the first word dot get item in camel case opening parenthesis single quote at sign auth data in camel case capital in the first character of the first word single quote closing parenthesis semicolon new line
indent indent indent if space opening parenthesis auth data serialized in camel case closing parenthesis space opening curly brace new line
indent indent indent indnet 
```

61
```

```

62
```

```

63
```

```