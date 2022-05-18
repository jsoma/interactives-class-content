# Stealing other peoples' D3 code 

Now that you know how scales work, you're 90% of the way to successfully ~stealing~ borrowing other peoples' code! Let's get to work.

## Changing the data source

**Read through the code and find the place where it specifies the file that's read in**. Yes, you could just name your file `countries.csv` but that... wouldn't be ideal.

Spoiler alert, it's this one:

```js
d3.csv("countries.csv")
  .then(ready)
  .catch(function (error) {
      console.log("Failed with", error)
  })
```

Believe it or not, it's actually all one line! Another way of writing this could be, in theory, like this:

```js
d3.csv("countries.csv").then(ready).catch(function (error) { console.log("Failed with", error) })
```

JavaScript is very forgiving about spacing and newlines and all of that, so starting a new line before `.blahblah` kinds of things is pretty common.

In order to make this baout your own dataset, just change `countries.csv` to be your own file.

## Changing the columns and scales

We already know there are three things that are used in the visualization: life expectancy, GDP per capita, and the continent each country is on. If we scan through the code for words that relate to that, we can pretty quickly find them:

```js
.attr("cx", d => xPositionScale(d.gdp_per_capita))
.attr("cy", d => yPositionScale(d.life_expectancy))
.attr("fill", d => colorScale(d.continent))
```

The first one associated `xPositionScale` with our GDP per capita, the second our `yPositionScale` with the life expectancy, and the final one hooks up `colorScale` with our continent. What if we just... changed the part after the `d.`?

> Narrator: Dear reader, *it would work.*

Of course, you'll also need to adjust the scales to fit your dataset (unless 0-100 on `y` and 0-80000 on `x` makes sense for your data).

But.. there you go! You successfully have stolen a D3 visualization and leveraged it for your own dataset.