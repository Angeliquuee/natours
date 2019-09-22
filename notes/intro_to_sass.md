# What is Sass?
Sass is a CSS preprocessor, an extension of CSS that adds power and elegance to the basic language. CSS gets very messy, very quickly. For each project, having a single CSS file with thousands lines of code gets completely unmanageable after some time.

Sass Source Code -> (Sass Compiler) -> Compiled CSS Code

The way that it works is like this.. instead of writing a CSS file with regular CSS code we write Sass code in Sass files and then we run a compiler that translates that code into regular CSS code as if all we ever did was write regular CSS code in the first place. So, we need to process our Sass code first, and that’s why it is called a CSS preprocessor.

So, what are some features that Sass actually gives us? Here is a quick overview:

* **Variables**: for reusable values such as colors, font-sizes, spacing, etc
* **Nesting**: to nest selectors inside of one another, allowing us to write less code
* **Operators**: for mathematical operations right inside of CSS
* **Partials and imports**: to write CSS in different files and importing them all into one single file
* **Mixins**: to write reusable pieces of CSS code
* **Functions**: similar to mixing, with the difference that they produce a value that can be used
* **Extends**: to make different selectors inherit declarations that are common to all of them
* **Control directives**: for writing complex code using conditionals and loops (not covered in this course)

## Sass syntax vs. SCSS syntax

### Sass syntax
```sass
.navigation
  list-style: none
  float: left

& li
  display: inline-block
  margin-left: 30px
```

### SCSS syntax
```scss
.navigation {
  list-style: none;
  float: left;

& li {
  display: inline-block;
  margin-left: 30px;
 }
}
```

The Sass syntax is indentation sensitive and doesn’t use any semi-colons or curly braces. The SCSS preserves the way that the original CSS syntax looks like.
