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
