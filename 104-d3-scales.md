# Scales in D3

We aren't here to build web pages from scratch and become D3 experts, we're here to *cheat our way to the top!*

## The reason for scales

The most fundamental concept of D3 is something like, **"every row in your dataset gets a visual representation on the page, and the columns of your data are responsible for *how* the visual is displayed."**

For example, in this visualization each row is a country, which gets the visual representation of a circle. The columns shake out like this:

|data attribute|visual attribute|
|---|---|
|life expectancy|x position|
|per-capita GDP|y position|
|continent|color|

This happens through **scales**.

## Breaking down the axis scales

For example, let's look at how the **X and Y axes are built:**

```js
const xPositionScale = d3.scaleLinear().domain([0, 80000]).range([0, width]);
const yPositionScale = d3.scaleLinear().domain([0, 100]).range([height, 0]);
```

The x scale takes an **input** (or domain) between zero and 80,000 and gives back an **output** (or range) between 0 and the width of the graphic. So a country with a GDP of $0 would be all the way on the left and a country with a GDP of $80,000 would be all the way on the right.

The y scale takes an **input** between zero and 100 and gives back an **output** between the height of the graphic and zero. D3 starts counting from the top of the chart, so a country with a life expectancy of zero shows up at the bottom (`height`), while a country with a life expectancy of 100 shows up zero pixels from the top.

**Your mission:** Adjust the y axis so that it is 

## Breaking down the color scale

Now let's look at the **color scale:**

```js
const colorScale = d3.scaleOrdinal().range(d3.schemeAccent);
```

It's a different kind of scale from the last ones - `d3.scaleOrdinal()` as compared to `d3.scaleLinear()`. Ordinal scales are **categories** and linear scales are **numbers**. Since each continent is a category, 

> You can use colors with `scaleLinear`, too! That allows you to ask for something like "translate from data that goes 0 to 100 into a visual that goes beige to red" and if you put in 50 *it gives you some sort of beige-y reddish pink color*. It's amazing.

D3 has like [six hundred kinds of scales](https://github.com/d3/d3-scale) and you'll never understand anything about them from reading the documentation, so don't fret and just live your life copying and pasting for the time being.

The `d3.schemeAccent` part is just a default D3 color scheme. You know how you can always tell an Excel chart because they all use the same colors? It's the same thing with D3. Try changing `d3.schemeAccent` to `d3.schemeCategory10` and you'll maybe recognize hundreds of visualizations you've seen before.

You can find more color schemes [over here](https://github.com/d3/d3-scale-chromatic#api-reference).

And do you have better taste than the D3 overlords? You can also specify your own color scheme by just sending it an array of colors, like this:

```js
const colorScale = d3.scaleOrdinal().range(['#7FDBFF', '#0074D9', '#01FF70', '#001F3F', '#FF4136', '#85144B', '#FF851B']);
```

Find a color scheme that you like!

## A few scale examples

|Code|Usage|Example|
|---|---|---|
|`d3.scaleLinear()`|Relating a number to position or color|0-10 maps to 0->100 (5 -> 50)|
|`d3.scalePoint()`|Spacing out points evenly on an axis|[Cat, dog, beetle] maps to 0->100 (cat -> 0, dog -> 50, beetle -> 100)|
|`d3.scaleBand()`|Spacing out bars evenly on an axis|[Cat, dog, beetle] maps to 0->100 (with 10-pixel bars, cat takes up 0-10, dog 45-55, beetle 90-100)|
|`d3.scaleOrdinal()`|Relating a category to another category| [Republican, Democrat] maps to [red, blue]|
|`d3.scaleSqrt()`|Relating a number to radius of a circle (area)|0-10 maps to 0->100 radius|
