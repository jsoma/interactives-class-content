# Welcome to a build system

## Why a build system?

When you're working alone, building every visualization from scratch every single time, it probably makes sense to be an A+ D3 master.

When you work in a place with a bit more stability, things are different! Maybe you produce graphics that are remarkably similar every now and again, for example. In that case it might make sense to have some templates handy.

They don't have to be anything fancy, just a couple line charts, maybe a few styles of bars, all styled up in the right colors. Even though this takes a bit more effort, thought and time to develop up-front, it could really speed up your process later on!

But what if you're on a big team, with a few dozen folks, all working on projects that may or may not be terribly similar? Trying to coordinate can really be painful, especially with something that's as varied and personal as building visualizations.

Instead of everyone murdering each other every single day, you simple update your templates into something that's even fancier. It might go by various names, including a **build system**, **framework**, or **graphics rig**.

## What is a build system?

A "build system" is a pretty generic term in technology, but you can think of it as a series of tools and templates that are all connected together to help produce reproducible, similar-looking end result no matter who is working with them. It can cut out much of the bespoke or personalized nature of developing graphics/project pages and push them closer to an easy-to-use "fill-in-the-blanks."

Most major newsrooms have at least one build system or framework that they operate on - [The Pudding](https://github.com/the-pudding/starter), [Retuers](https://reuters-graphics.github.io/graphics-svelte-components/), [NPR](https://github.com/nprapps/dailygraphics), to name a few. They usually update a bit every few years, if not get replaced outright by total overhauls!

## A build system example

I've put together an example of a simple build system [over here](https://github.com/jsoma/example-svelte-viz-page). It's really simple as far as these things normally go, but it'll get the idea across!

### Svelte

This build system is based on [Svelte](https://svelte.dev/), a web application framework that allows you to build fancy web pages. While there are a million and one ways it's nicer than just using normal HTML, a good example is an ai2html export:

When you use [ai2html](https://www.youtube.com/watch?v=6YkL6TCyxws&list=PLewNEVDy7gq3MSrrO3eMEW8PhGMEVh2X2) to produce a graphic from Illustrator, it creates a handful of graphics along with a `graphics.html` file. In order to put this content into a web page, you need to carefully move the files to the same location as your website, and then cut and paste the contents of your `graphics.html` into your web page.

Since the graphics are often hundreds and hundreds of lines, it can be a real pain! Not to mention all of the manual edits you have to make to create a version that's accessible to screen readers!

But what if instead, you could do something like the code below?

```svelte
<Ai2html name="graphics" description="A scatterplot of various countries"></Ai2html">
```

Turns out _you can do this_, you just need Svelte and a build system to help you. One of your coworkers builds a template (or _component_) that takes in the name of the ai2html file you'd like to embed, and Svelte magically gives you a new HTML tag that does all the heavy lifting for you.

That's only the tip of the surface, but it's pretty great!

### Layer Cake

The build system we've put together also includes some examples of [Layer Cake](https://layercake.graphics/), a graphics framework that can work with Svelte. Instead of writing D3 code from scratch, you might just do something like this:

```svelte
<LayerCake x='gdp_per_capita' y='life_expectancy' data={countries}>
    <Svg>
        <AxisX />
        <AxisY gridlines=false />
        <Scatter opacity='0.5' stroke='black' />
    </Svg>
</LayerCake>
```

And Layer Cake magically puts together a scatterplot with an X and Y axis for you, plotting GDP per capita against life expectancy! You can see a million examples [over on the website](https://layercake.graphics/).

### Why this works

The reason this works is because of *components*, the little baby re-useable templates that you and your coworkers build and improve upon. While you can use the ones from Layer Cake, you can also [use the ones from Reuters Graphics](https://reuters-graphics.github.io/graphics-svelte-components/), or [IBM's design system](https://github.com/carbon-design-system/carbon-components-svelte), or a thousand others! 

You're also welcome to make your own, and customize your way to wonderful personalized glory. For a simple example, take a peek at [this &lt;Title&gt; component](https://github.com/jsoma/example-svelte-viz-page/blob/main/src/routes/_components/Title.svelte), combine it with [how it's used here](https://github.com/jsoma/example-svelte-viz-page/blob/main/src/routes/index.svelte), and [what the final results look like](https://jsoma.github.io/example-svelte-viz-page/).