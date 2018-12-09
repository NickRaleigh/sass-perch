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
- note: on the space-around setting, we add an additional fourth charachter.
We then replace the character(s) with one of three options:
**`^`, `_`, `+`**
