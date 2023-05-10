```
Configuration with

app

dot

J.S.O.N.

slash

app

dot

config

dot

J.S.
```

```
Learn about what is Expo and how you can dynamically use it by customizing it.
```

```
The Expo config (

app

dot

J.S.O.N.,

app

dot

config

J.S.,

app

dot

config

dot

T.S.)

is used for configuring how a project loads in Expo Go, Expo Prebuild generation, and the OTA update manifest.
```

```
You can think of this as an

indes

dot

H.T.M.L.

but for React Native apps.
```

```
It must be located at the root of your project, next to the

package

dot

J.S.O.N.
```

```
Here is a bare-minimum example:
```

```
opening curly brace

new line

indent

double quote

expo

double quote

colon

space

opening curly brace

new line
```

```
indent

indent

double quote

name

double quote

comma

space

double quote

my app with capital m

double quote

comma

new line
```

```
indent

indent

double quote

slug

double quote

comma

space

double quote

my dash app

double quote

new line
```

```
indent

closing curly brace

new line

closing curly brace
```

```
Most configuration from the Expo config is accessible at runtime from the JavaScript code using

constanst with capital c

dot

expo config in camel case.
```

```
Sensitive Information such as secret keys are removed.
```

```
Properties
```

```
The Expo config configures many things such as app name, icon, spash screen, deep linking scheme, API keys to use for some services and so on.
```

```
For a complete list of available properties, see

app

dot

J.S.O.N.

slash

app

dot

config

dot

J.S.

reference.
```

```
Do you use Visual Studio Code? If so, we recommend that you install the

V.S. code

dash

expo

extension to get auto-completion of properties in

app

dot

J.S.O.N.

files.
```

```
Extending configuration
```

```
Library authors can extend the Expo config by using Expo Config plugins.
```

```
Config plugins are mostly used to configure the

N.P.X.

space

expo

space

prebuild

command
```

```
Dynamic configuration
```

```
For more customization, you can use the JavaScript or TypeScript (

app

dot

config

dot

J.S.

or

app

dot

config

dot

T.S.).

These configs have the following properties:
```

```
- Comments, variables, and single quotes.
```

```
- Importing/requiring other JavaScript files. Using import/export syntax in external files is not supported. All imported files must be transpiled to support your current version of

node

dot

J.S.
```

```
- TypeScript support with nullish coalescing and optional chaining.
```

```
- Updated whenever Metro bundler reloads.
```

```
- Provide environment information to your app.
```

```
- Does not support Promises.
```

```
For example, you can export an object to define your custom config:
```

```
app

dot

config

dot

J.S.

Copy
```

```
C.O.N.S.T.

space

my value in camel case

space

equals

space

single quote

my app all word capital in first character

single quote

semicolon

new line

new line
```

```
module

dot

exports

space

equals

space

opening curly brace

new line
```

```
indent

name

colon

space

my value in camel case

comma

new line
```

```
indent

version

colon

space

process

dot

E.N.V.

dot

my underscore custom underscore project underscore version all capital

space

vertical line

vertical line

space

single quote

one point zero point zero

single quote

comma
```

```
indent

slash

slash

space

All values in extra will be pressed to your app with first word capital in first character

new line
```

```
indent

extra

colon

space

opening curly brace

new line
```

```
indent

indent

fact

colon

space

single quote

kittens are cool

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

semicolon
```

```
The

double quote

extra

double quote

key allows passing arbitrary configuration data to your app. The value of this key is accessed using

expo

dash

constants:
```

```
App dot J.S.

Copy
```

```
import

space

constants

space

from

space

single quote

expo

dash

constants

single quote

semicolon

new line

new line
```

```
Constants

dot

expo config in camel case

dot

extra

dot

fact

space

equals equals equals

space

single quote

kittens are cool

single quote

semicolon
```

```
You can access and modify incoming values by exporting a function that returns an object. This is useful if your project also has an

app

dot

J.S.O.N..
```

```
By default, Expo C.L.I. will read the

app

dot

J.S.O.N.

first and send the normalized results to the

app

dot

config

dot

J.S..
```

```
This functionality is disabled when the

dash

dash

config

is used to specify a custom config.
```

```
The

dash

dash

config

flag is deprecated. For more information, see Migration from

dash

dash

config

in Expo C.L.I..
```

```
For example, your

app

dot

J.S.O.N.

could look like this:
```

```
app

dot

J.S.O.N.

Copy
```

```
opening curly brace

new line

indent

double quote

expo

double quote

colon

space

opening curly brace

new line
```

```
indent

indent

double quote

name

double quote

colon

space

double quote

my app every word capital in first character

new line
```

```
indent

curly brace

new line

curly brace

new line
```

```
And in your

app

dot

config

dot

J.S.,

you are provided with that configuration in the arguments to the exported function:
```

```
app

dot

config

dot

J.S.

Copy
```

```
module

dot

exports

space

equals

space

opening parenthesis

opening curly brace

space

config

space

closing curly brace

closing parenthesis

space

equals

greater than

space

opening curly brace

new line
```

```
indent

console

dot

log

opening parenthesis

config

dot

name

closing parenthesis

semicolon

space

slash

slash

space

prints

space

single quote

my app every word capital in first character

single quote

semicolon

new line
```

```
indent

return

space

opening curly brace

new line
```

```
indent

indent

dot dot dot

config

comma

new line
```

```
indent

closing curly brace

semicolon
```

```
closing curly brace

semicolon
```

```
Switching configuration based on the environment
```

```
It's common to have some different configuration in development, staging, and production environments, or to swap out configuration entirely in order to white label an app.
```

```
To accomplish this, you can use

app

dot

config

dot

J.S.

along with environment variables.
```

```
app

dot

config

dot

J.S.

Copy
```

```
module

dot

exports

space

equals

space

opening parenthesis

closing parenthesis

space

equals

greater than

space

opening curly brace

new line
```

```
indent

if

space

opening parenthesis

process

dot

E.N.V.

dot

my underscore environment all capital

space

equals

equals

equals

space

single quote

production

single quote

closing parenthesis

space

opening curly brace

new line
```

```
indent

indent

return

space

opening curly brace

new line
```

```
indent

indent

indent

slash

asterisk

space

your production config

space

asterisk

slash

new line
```

```
indent

indent

closing curly brace

semiclon

new line
```

```
indent

closing curly brace

space

else

space

opening curly brace

new line
```

```
indent

indent

return

space

opening curly brace

new line
```

```
indent

indent

indent

slash

asterisk

space

your development config

space

asterisk

slash

new line
```

```
indent

indent

closing curly brace

semicolon

new line
```

```
indent

closing curly brace

new line

closing curly brace

semicolon
```

```
To use this configuration with Expo C.L.I. commands, set the environment variable either for specific commands or in your shell profile.
```

```
To set environment variables for specific commands, prefix the command with the variables and values as shown in the example:
```

```
Terminal

Copy

dash

space

my underscore environment all capital

equals

production

space

E.A.S.

update
```

```
This is not anything unique to Expo C.L.I..
```

```
On Windows you can approzimate the above command with:
```

```
Terminal

Copy
```

```
dash

space

N.P.X.

space

cross

dash

E.N.V.

space

my underscore environment all capital

equals

production

space

E.A.S.

space

update
```

```
Or you can use any other mechanism that you are comfortable with for environment variables.
```

```
Using TypeScript for configuration:

app

dot

config

dot

T.S.

instead of

app

dot

config

dot

J.S.
```

```
You can use autocomplete and doc-blocks with an Expo config in TypeScript.
```

```
Create an

app

dot

config

dot

J.S.

with the following contents:
```

```
app

dot

config

dot

T.S.

Copy
```

```
import

space

opening curly brace

space

expo config in camel case with first character in capital

comma

space

config context in camel case with first character in capital

space

closing curly brace

space

from

space

single quote

expo

slash

config

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

opening parenthesis

opening curly brace

space

config

space

closing curly brace

colon

space

config context in camel case with first character in capital

closing parenthesis

comma

space

expo config in camel case with first character in capital

space

equals

greater than

space

opening parenthesis

opening curly brace

new line
```

```
indent

dot dot dot

config

comma

new line
```

```
indent

slug

comma

space

single quote

my

dash

app

single quote

comma

new line
```

```
indent

name

comma

space

single quote

my app every word capital in first character

single quote

comma

new line
```

```
closing curly brace

closing parenthesis

semicolon
```

```
If you want to import other TypeScript files or customize the language features, we recommend using

T.S.

dash

node

as described in Using TypeScript.
```

```
Configuration Resolution Rules
```

```
There are two different types of configs: static (

app

dot

config

dot

J.S.O.N.,

app

dot

J.S.O.N.),

and dynamic (

app

dot

config

dot

J.S.,

app

dot

config

dot

T.S.).
```

```
Static configs can be automatically updated with C.L.I. tools, whereas dynamic configs must be manually updated by the developer.
```

```
1. The static config is read if

app

dot

config

dot

J.S.O.N.

exists (falls back to

app

dot

J.S.O.N.

).
```

```
If no static config exists, then default values are inferred from the

package

dot

J.S.O.N.

and your depedencies.
```

```
2. The dynamic config is read if either

app

dot

config

dot

J.S.

exists. If both exist, then TypeScript config is used.
```

```
3. If the dynamic config returns a function, then the static config is passed to the function with

opening parenthesis

opening curly brace

space

config

space

closing curly brace

closing parenthesis

space

equals

greater than

space

opening parenthesis

opening curly brace

closing curly brace

closing parenthesis.
```

```
This function can then mutate the static config values.
```

```
Think of this like middleware for the final config
```

```
4. The return value from the dynamic config is used as the final config.
```

```
It cannot have any promises.
```

```
5. All functions in the config are evaluated are seialized before any tool in the Expo ecosystem uses it.
```

```
The config must be a J.S.O.N. manifest when it is hosted
```
