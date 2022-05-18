# Observable

Once upon a time there was a beautiful website called [bl.ocks](https://bl.ocks.org/). Since nothing gold can last, the twin spectres of Monetization and Walled Gardens swooped in, and bl.ocks was replaced by its modern-day equivalent [Observable](https://observablehq.com/).

In a positive sense, Observable is like Jupyter notebook for JavaScript (and especially for data visualization!). It's a great place to experiment with tools and techniques, and absolutely the number one location for finding interesting interactives that the community is playing around with. 

Extracting content *out of* Observable to put onto your website is another story, but... we can talk about that later!

> Don't worry if you can't remember whether there's an `e` in there or not, I can never keep it straight.

## Using Observable

While Jupyter is more or less "we split Python up into little boxes," Observable has a bit of a learning curve and the skills you learn aren't directly transferrable to vanilla JavaScript. But hey, it's hella useful for plenty of things, so give it a shot.

If you'd like to try to learn D3 through Observable tutorials (the current recommended method according to d3js.org), you can [follow these tutorials here](https://observablehq.com/@d3/learn-d3).

Spoiler alert, I don't think they're great. It's like 50% D3, 50% Observable, so it's kind of an awkward mix.

You can learn about Observable as a *platform by itself*, too, through [these tutorials here](https://observablehq.com/tutorials). They're still focused on data viz, but they use [Observable Plot](https://observablehq.com/@observablehq/plot), which is an alternative visualization library that's part of the Observable platform.

Observable Plot easier to use than D3 but is just a part of Observable, so while it's maybe good for exploration and light prototyping it's probably not worth much of an investment.

## Learning D3 using Observable the cheating way

The best thing about Observable is that you don't need to run any servers, don't need to set up your VS Code environment, don't need to write anything from scratch or debug strange errors for sixteen hours. It's all *right there* and *very simple* once you get past the insanity of breaking everything into oddly-interrelated boxes all around the page.

My recommendation is selfish, and it is [visit this Observable](https://observablehq.com/@jsoma/countries-csv). You're going to customize it!

Click the `...` button on the top right, then "Fork...". This will create your own copy of it! Now go through these exercises to figure out how D3 and Observable work:

1. Make the circles a little bit bigger.
2. Play around with the "Maximum age" and "Minimum age" sliders to see how it changes the visualization. Can you find where the sliders connect to the graphic? (Hot tip, it's in the scale!)
4. Add another slider that adjusts the radius of the circles.
5. Add another slider that adjusts the *opacity* of the circles. (Hot tip, you'll need to change another `attr` called `opacity` that may or may not range from zero to one).
3. Add new sliders for both minimum and maximum GDP, and make them change the x axis in the same way that the age sliders change the y axis.

## Exporting and embedding

When your graphic is set up in a way you like, you'll think **I love this, let's pop it onto my own website!**

## .......

Copy it into your document

Why? Export and look at what you get back.
