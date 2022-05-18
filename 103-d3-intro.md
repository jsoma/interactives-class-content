# Your D3 setup

We're going to focus on **reading D3** as opposed to a deep understanding of it. While a deep understanding is great, spending forever picking apart the specifics of this or that takes precious time away from actually building things.

The D3 community is all about sharing, and it's remarkably easy to jump off of someone else's work to get where you're trying to go. Since there are only so many kinds of charts out there there's a good chance you'll find 

## Confirm your setup

First, make sure you've installed both the Live Server and Prettier plugins for Visual Studio Code.

## Use that setup

Download [d3-countries-scatter.zip](d3-countries-scatter.zip) and open up the zip.

Use `File > Open Folder` to open the folder that contains all of the files. You should see five files:

|filename|description|
|---|---|
|countries.csv|A CSV file of different probably-lies information about various countries|
|d3.v7.min.js|Version 7 of the D3.js library|
|index.html|The HTML file that you're going to open|
|script.js|The code that creates the chart|

### Step 1: Open `countries.csv`

First, open up `countries.csv`. Look at it. What are the column names?

It isn't very exciting, but now you know what it is.

### Step 2: Open `d3.v7.min.js`

When you open up this super-famous D3 library, you immediately see it is *wild*. It looks something like this:

```js
!function(t,n){"object"==typeof exports&&"undefined"!=typeof module?n(exports):"function"==typeof define&&define.amd?define(["exports"],n):n((t="undefined"!=typeof globalThis?globalThis:t||self).d3=t.d3||{})}(this,(function(t){"use strict";function n(t,n){return null==t||null==n?NaN:t<n?-1:t>n?1:
```

What kind of genius does it take to write code like that?! Turns out... an inhuman one: this isn't code anyone wrote, it's [**minified code**](https://en.wikipedia.org/wiki/Minification_\(programming\)), code that has been automatically shrunken down to fit in less space.

You can [compare it to the non-minified d3.js code here](https://cdnjs.cloudflare.com/ajax/libs/d3/7.4.4/d3.js) to see the difference.

Right now it isn't a big deal, just know that it exists. Eventually you'll learn about the process that code goes through in order to become minified!

### Step 3: Open `index.html` and fail

First, open `index.html` in your browser. Are you excited? Are you ready to see a magical D3 visualization???

Sorry, *you aren't going to see anything*. If you open up the Console (`View > Developer > View JavaScript Console`) you'll see an error that looks something like this:

```
Access to fetch at 'file:///Users/blahblah/d3-countries-scatter/countries.csv' from origin 'null' has been blocked by CORS policy: Cross origin requests are only supported for protocol schemes: http, data, chrome, chrome-extension, chrome-untrusted, https.
```

This web page is trying to read the file `countries.csv`, but your browser isn't letting it happen. This is because if your browser let web pages read files all over your computer all the time, it'd probably get tricked into sending passwords and stuff to scammers and other enemies of yours! So the browser just says *no*.

To make this work, we need to make our computer a **web server**.

### Step 3: Open `index.html` and succeed

Instead of opening `index.html` directly in your browser, open it in VS Code. Then look at the bottom right-hand corner of your VS Code window, down by the blue (or purple) bar. You'll see some text that says **Go Live**. 

Click that text.

Tada! Magically, a new browser window will open pointed at `127.0.0.1/index.html`, with a beaaaautiful scatterplot graphic on it. We've tricked your computer into serving up the data by running a little web server on it.

> `127.0.0.1` or `localhost` is the address/name of your computer. Don't worry, it doesn't touch the internet, it's just on your machine.

### Step 4: Read `index.html`

How does it work? Well, let's read `index.html`. The important pieces are these five lines:

```html
<h1>This is a sample D3 page</h1>
<div id="chart"></div>
<p>Hope you like the chart!</p>
<script src="d3.v7.min.js"></script>
<script src="script.js"></script>
```

The second line – `<div id="chart"></div>` – is the container that the chart is going to be put in. Notice how on the web page your scatterplot exists *between* the title at the top of the page and the paragraph down at the bottom.

If you had used ai2html to create this graphic, instead of an empty div you'd have thousands of lines of Illustrator-export SVG code kicking around in there! One of the reasons D3 is great is that it allows you to put placeholders on the page and fill them in with content later.

The next important line is `<script src="d3.v7.min.js"></script>`. This tells your browser to go grab the `d3.v7.min.js` file and include it on the page, which adds D3's capabilities to your website.

> An alternative would be to use a copy of D3 that's already on the internet, like at [https://cdnjs.cloudflare.com/ajax/libs/d3/7.4.4/d3.min.js](https://cdnjs.cloudflare.com/ajax/libs/d3/7.4.4/d3.min.js). This is called a **CDN**, and... well, it used to speed up pages back in the day, but now it's just kind of a lazy way to have one less file to manage.
 
 The final line is `<script src="script.js"></script>`, which grabs `script.js` and includes the code from it on your page. **This is your code that uses D3.**

### Step 5: Open `script.js`

Now, finally, open up `script.js`. This is your JavaScript code that uses D3 to build that not-quite-amazing graphic you're looking it.

Next up you'll start **reading it** and **editing it** in order to pick up some D3 skills.

