# Exporting from and embedding using Observable

When your graphic is set up in a way you like, you'll think **I love this, let's pop it onto my own website!**

To export your visual, click the `...` in the top right-hand corner, then `Export > Download code`. You'll get a `.tgz` file instead of a `.zip`, for god knows what reason, which your computer will hopefully be able to decompress.

Once you get it downloaded, you're welcome to open the folder and use VS Code's Live Server to browse your `index.html` file. It'll look more or less the same as the version on the page.

Take a look at the *code*, though, and you'll see it's less than ideal. The text from the page lives in the JavaScript, the code you wrote isn't nearly as neat as you left it, and it's clearly going to be a pain to work into whatever your website is, much less update it later on!

So what do you do?

## How to use Observable notebooks

Since exporting code isn't the most useful, let's take a look at three other ways you can use observable notebooks

### Observable as a web page

Your first (and easiest) option is **just use the notebook as a web page.** 

It might not live on your portfolio domain, but there are worse things in the world! The Observable site is pleasant-looking, you can drop in text and code and images, and people will know you're Good Enough to use Observable.

### Export an SVG

If you don't need interactivity, **download your graphic as an SVG to clean up in Illustrator**. To the left of your graphic there's a little `⋮` in vertical grey bar. Click it and you'll have the option to download an SVG!

It's a great option if you need to push the graphic through Illustrator to clean it up a bit, and then export the final version with ai2html. I know a lot of people feel D3 is the ultimate tool for interactivity, but it can also be used to lay the groundwork for incredible static visualizations!

### Re-write it manually

Once you've locked down the concept of your visual, you can also just **rebuild your graphic in vanilla D3.** It isn't going to be simple, but with a bit of practice you'll learn what does and doesn't transfer to "normal" D3.

This can be especially useful if you were using Observable as a playground to workshop different approaches to a viz.