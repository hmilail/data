```
Add custom native code
```

```
Learn how to add custom native code to your Expo project.
```

```
The Expo Go app is a great tool to get started --
```

```
it exists to help developers quickly get projects off the ground, experiment with ideas (such as on Snack) and share their work with minimal friction.
```

```
Expo Go makes this possible by including a feature-rich native runtime made up of every module in the Expo SDK, so all you need to do to use a module is install the package and reload your app.
```

```
The tradeoff is that Expo Go does not allow you to add custom native code, you can only use native modules built into the Expo SDK.
```

```
There are many great libraries available outside of the Expo SDK, and you may even want to build your own native library.
```

```
You can leverage these libraries with development builds, or by using prebuild to generate the native projects, or both.
```

```
You can also continue using EAS Build to release your app, no changes are required.
```

```
Adding custom native code with development builds
```

```
To make use of third-party libraries with custom native code and continue with the same developer experience of Expo Go, you can migrate to using development builds.
```

```
Development builds are like your own personal version of Expo Go --
```

```
they include the native runtime that powers your app, and you control what is included in that native runtime by adding or removing packages in your

package dot json.
```

```
Development builds allow you to continue to build your app in JavaScript while taking advantage of the full ecosystem of native packages available for Expo and React Native projects.
```

```
Learn how to start using custom native code in your app by switching from Expo Go to development builds in the Getting Started guide for development builds.
```

```
Generate native projects with prebuild
```

```
If you would like to move from a JavaScript based project and take ownership over the iOS and Android native projects,
```

```
you can generate them by running

npx

space

expo

space

prebuild,
```

```
or

npx

space

expo

space

run

colon

opening bracket

ios

vertical line

android

closing bracker
```

```
(which will run

prebuild

automatically).
```

```
You can also use development builds in this context --
```

```
the easiest way to do this is to run

npx

space

expo

space

install

space

expo

dash

D.E.V.

dash

client
```

```
before

prebuild

or

run

and it's also possible to add the library at any later time.
```

```
Terminal

Copy

hash space Build your native Android project

new line
```

```
dash

space

N.P.X.

space

expo

space

run

colon

android

new line

new line
```

```
hash space Build your native I.O.S. project
new line
```

```
hash

space

N.P.X.

expo

run

colon

I.O.S.
```

```
N.P.X.

space

expo

space

run

colon

android

requires Android Studio SDK to be installed. See the setup environment guide.
```

```
N.P.X.

space

expo

space

run

colon

I.O.S.

requires XCode (macOS only) installed on your computer. See the setup environment guide.
```

```
Using the run commands will initially prebuild your project to generate all of the native code within your project directory.
```

```
If you manually modify the android or ios directory,
```

```
you won't be able to safely re-run
N.P.X.
space
expo
space
prebuild,
this is known as the bare workflow.
```

```
Your app can still run in Expo Go, however, any custom native code won't be accessible if it's not already present in the Expo Go app.
```

```
If you install a package with an Expo

config plugin,

you'll need to add the plugin to the

plugins

array in the project's

app dot json,
```

```
then re-run

N.P.X.

space

expo

space

prebuild

to sync the changes before rebuilding the native app.
```

```
Often this does things like adding required permissions to the

android manifest dot X.M.L.

or

info dot P. list.
```

```
You may need to run

npx

space

expo

space

prebuild

space

dash

dash

clean

depending on how complex the plugin is; this will delete and re-generate the native project files from scratch.
```

```
Manually changing the native project files
```

```
If you've made manual modifications to your

android

or

ios

directory,
```

```
you'll need to manually setup new packages because running

npx

space

expo

space

prebuild
```

```
may not work as expected with an unpredictable project state (think of this like running

yarn

after manually modifying your

node underscore modules

directory).
```

```
If you want to make static changes to your native project files like the iOS

android manifest dot X.M.L.

or

info dot P. list

and still have access to prebuilding, check out the config plugins guide to see how you can hook into the prebuild process to make those changes.
```

```
Reverting changes from

npx

space

expo

space

run

colon

opening bracket

android

vertical line

ios

closing bracket
```

```
If you've decided that you want to roll your app back to being fully managed (no iOS and Android projects in your project directory),
```

```
you can check out your most recent commit before executing
```

```
npx

space

expo

space

run

colon

opening bracket

android

vertical line

ios

closing bracket,

then run

N.P.M.

install

again to restore the state of your

node underscore modules

directory.
```

```
Developing apps with custom native code
```

```
Once you have customized the native code in your project, you can use the

expo

dash

D.E.V.

dash

client

package to create a development build and retain the convenience of working with just JavaScript and/or TypeScript in Expo Go.
```

```
You can create a development build for your managed or bare workflow.
```

```
Releasing apps with custom native code to production
```

```
When you're ready to ship your app, you can build it with EAS Build the same as you were building it before adding custom native code.
```

```
Alternatively, you can archive and sign it locally. Unsurprisingly, we recommend EAS Build!
```

```
Terminal

Copy
```

```
hash

space

Install the C.L.I.

new line
```

```
hash

space

N.P.M.

i

dash

G.

space

E.A.S.

dash

C.L.I.

new line

new line
```

```
hash

space

Build your app!

new line
```

```
hash

space

E.A.S.

space

build

dash

P.

space

all
```

```
Creating native modules
```

```
The Expo Module A.P.I. enables developers to build modules for Expo and React Native projects using Swift, Kotlin, and TypeScript. We use it for most modules in the Expo SDK.
```

```
Learn more about the Expo Module API design considerations.
```

```
Another option is to use React Native's Core Native Modules API which may require some C++ knowledge in addition to Objective-C and Java.
```

```
Most React Native modules in the ecosystem are built using this API because it is and always has been part of React Native, while the Expo Module API is new and intended to solve many of the pain points of using the core API.
```
