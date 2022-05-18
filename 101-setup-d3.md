# Setting up your text editor

## Live Server

When you're working with D3 and external data files, you can't just open the `index.html` like you're used to. [Live Server](https://marketplace.visualstudio.com/items?itemName=ritwickdey.LiveServer) will be used to run a little baby server on our machines so we can preview our content.

### Installing Live Server

1. Open Visual Studio Code
2. From the top menu, select `View > Extensions`.
3. Search for **Live Server**
4. Click it, then click Install.

Alternatively, you can just [click this link](https://marketplace.visualstudio.com/items?itemName=ritwickdey.LiveServer).

### Confirm Live Server was installed

Find the bottom bar in VS Code, the one that is purple or blue or some other fun color. Maybe it says **Spaces: 4** or **UTF-8**. On the far right should be the text "Go Live". You don't need to click it, just confirm you see it there!

## Prettier

Different people write their code differently, *especially* in the JavaScript world. Semicolons, parentheses, `var` and `const` and `let` and a thousand other options await you. For example, these two blocks of code are the same:

```js
function activate() {
    console.log("I've been activated!");
}

var timer = setTimeout(activate, 2500);
```

```js
const activate = () => console.log("I've been activated!")

const timer = setTimeout(activate, 2500)
```

[Prettier](https://prettier.io/) is a **code formatter** that helps ensure that everyone writes their code the same(-ish) way.

### Install Prettier

1. Open Visual Studio Code
2. From the top menu, select `View > Extensions`.
3. Search for **Prettier**
4. Click it, then click Install.

Alternatively, you can just [click this link](https://marketplace.visualstudio.com/items?itemName=esbenp.prettier-vscode).

### Set up Prettier

I have opinions about the way your code should be formatted! Smoe of this is personal preference, but some of explicitly makes D3 easier to cut and paste (I'm lazy!).

1. Open `Code (or File) > Preferences > Settings`
2. Search for **Prettier arrow** and set **Prettier: Arrow Parens** to `avoid`.
3. Search for **Prettier print** and set **Prettier: Print Width** to `120`.
4. Search for **Prettier semi** and *uncheck* **Whether to add a semicolon at the end of every line**.

### Confirm Prettier is working

Open up a new file and paste in the following code:

```js
function test(d) {

console.log("this is some code"); }
```

Open the Command Palette by pressing Command+Shift+P on OS X or Ctrl+Shift+P on Windows. Search for "Format document" and click it. Your code should reformat like this:

```js
function test(d) {
  console.log("this is some code")
}
```