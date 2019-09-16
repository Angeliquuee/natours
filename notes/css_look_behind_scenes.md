# How CSS Works: A Quick Look Behind The Scenes
### What happens to CSS when we load up a webpage?
A bunch of stuff happens behind the scenes of the internet, until the browser can start loading the website we requested. Things like HTTP request, finding out the right domain name service, etc.

We’re not interested in that though. We’re going to be focusing more on what is happening under the hood in the browser on a computer where the user opens the page.

So, our starting point is when the browser initially started to load the HTML file it then takes the loaded HTML code and then parses it which basically means it decodes our file line by line.

From this process the browser loads up the Document Object Model, or DOM, which basically describes the entire web document, basically like a family tree, with parents, children, and siblings elements. So, this DOM is where the entire decoded HTML is stored.

Now, as the browser parses the HTML, it also finds the style sheets included in the HTML head, and it starts loading them as well. And just like the HTML, the CSS is also parsed. But the parsing of CSS is a bit more complex.

During the CSS parsing phase, there are two main steps:
1. Resolve conflicting CSS declarations (cascade)
2. Process final CSS values

First off, conflicting CSS declarations are resolved through a process known as the cascade. The second step in CSS parsing, is to process final CSS values. For instance, converting a margin defined in percentage units to pixels. Imagine that we defined the left margin as 50%, but that 50% on a smartphone is completely different than a 50% on a large screen, right?

And that’s why these percentages and other relatives units can only be calculated on the user’s device in the parsing phase.

The final CSS is also stored in a tree-like structure called the CSS Object Model, or CSSOM, it’s similar to the DOM. And, so, now that we have both the HTML and CSS parsed and stored, these together form the so-called Render Tree. And with that, we finally have everything that we need to render the page.

Now, in order to actually render the page, the browser uses something called the Visual Formatting Model. This algorithm calculates and uses a bunch of stuff that you already know about like: the box model, floats, and positioning.

After all of these steps, we have the final rendered website.

---

![Imgur](https://imgur.com/ves8O0G.png)
