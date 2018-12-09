# Sass-Perch 🐦`=+=` Simple, Expressive CSS Flexbox Layouts

## Huh?
Sass-Perch is a really easy-to-learn sass mixin that grabs all of the essentials of flexbox and turns it into a single visual expression. 

## Why?
If you're like me and use flexbox a lot, you'll be writing the same rules over and over again( ie `display: flex;` `flex-flow: row nowrap;` `justify-content: flex-start; align-items: center;`. Also, for a layout system, flexbox isn't _at all_ visual. While scanning a set of CSS rules, it's sometimes difficult to tell what layout will result from a set of flexbox rules without jumping back into the browser. And lastly, flexbox kind of sucks at making decent responsive grids. Why is it so hard to make a grid with equal-width columns on it, with spacing inbetween each item??? #$%$#

## When should I use Sass-Perch?
In almost any case that you find yourself using flexbox, _or_ put more straightforward, when you need a single-axis layout, or you need a wrapping equal-column grid.

## How?
Sass-Perch is easily invoked using `@include perch($expression)` on a parent element. Let's walk through an example to get used to the syntax:

Say we have a post on our website:
```
<div class="news">
  <img src="..." />
  <h2>Wow this is a great article</h2>
  <p>This is a description of this great article.</p>
</div>
```

Which outputs a pretty predictable set of block elements:
![boring](http://nickraleigh.com/wp-content/uploads/2018/12/1.jpg)

Next, we need to figure out if we want to use a layout on a *row* or on a *column*.

**Setting the flex-direction to row is accomplished by setting the first three characters to: `('---')`**
**Setting the flex-direction to column is accomplished by setting the first three characters to: `('===')`**

Setting the first three characters will always be our starting point when we make a new layout.
![basic perch](http://nickraleigh.com/wp-content/uploads/2018/12/2.jpg)

Now what? We align and justify our items on our flexbox, using the three characters we started on. Use the diagram below to help you understand how this works. Basically, we'll be focusing in on character(s) that will tell our flexbox more information about our layout:
![diagram](http://nickraleigh.com/wp-content/uploads/2018/12/3.jpg)
note: on the space-around setting, we add an additional fourth charachter.

We then replace the selected character(s) with one of three options:
- `^` - Think of this as an 'up-arrow'
- `_` - Use as a 'down-arrow'
- `+` - Think 'centered'.

### Row Examples:
Here's a few examples:
- `^--` - Outputs `display: flex; justify-content: flex-start; align-items: flex-start;`
- `-+-` - Outputs `display: flex; justify-content: center; align-items: center;`
- `_-_` - Outputs `display: flex; justify-content: space-between; align-items: flex-end`.

We'll cover columns' behavior below.

Here's where I think this mixin shines: even if the examples above didn't make sense, and you don't fully understand flexbox, visually looking at these expressions will give you an idea of what to expect on the front end. Let's look at the examples above again, and just comment on *what they look like*

- `^--` - A thing on the far left that points upwards (that's exactly where our flex items will go!)
- `-+-` - A thing in the middle (Whoa!)
- `_-_` - Two things pointing downwards with a space inbetween them (Wow!)

## Colum Examples:
We use the `=` character when composing a flexbox with a flex-direction of column. Columns are a bit tricky since they are not horizontal, and don't have as easy of a solution, at first. To overcome this, while looking at a column expression with Sass-Perch, you need to *rotate* the expression 90 degrees with your brain software (🙈💿) to understand it:

![diagram](http://nickraleigh.com/wp-content/uploads/2018/12/4.jpg)

When we do this, our characters that set the flexbox also change:
- `^` - Now is a 'right-arrow'
- `_` - Now is a 'left-arrow'
- `+` - Stays the same.

Let's go through the examples from the diagram above:
- `^==` (after we rotate) we have a character on top (`justify-content: flex-start`), pointing to the right (`align-items: flex-end`).
- `=+=` (after we rotate) we have a centered(+) item (`jusfity-content: center`) situated in the middle (`align-items: center`).
- `_=_=` (after we rotate) we have four characters (`justify-content: space-around`), and the two characters point to the left (`align-items: flex-start)`.

This may seem a little odd at first, but with some practice, will become quite easy to read.

