# CSS Architecture, Components, and BEM
We want code that is…

* Clean
* Modular
* Reusable
* Ready for growth

To make it easier for us to add features to our webpage app. We need to take important decisions concerning our HTML and CSS right from the beginning of the project.

We need a good strategy and mindset. There is a mindset that Jonas provides for us and that is called the think, build, and architect mindset.

**Think** about the layout of your webpage or web app before writing code

**Build** your layout in HTML and CSS with a consistent structure for naming classes

**Architect** create a logical architecture for your CSS with files and folders

## Think
Starting with the **thinking** side, there is a thing called _component-driven design_ which is used all across software development.

In CSS, we try to divide our modular components. What are these components, exactly? Well, they are the building blocks to construct our interfaces. So we can basically think of our interface as a collection of components held together by the overall layout of the page. Probably the most important thing about components is that they should be re-usable across a project, and between different projects. They also should be independent, allowing us to use them anywhere on the page.

### Component-driven design
* Modular building blocks that make up interfaces
* Held together by the layout of the page
* Re-usable across a project, and between different projects (to speed up development)
* Independent, allowing us to use them anywhere on the page

As a side note, this component-driven design strategy is similar to Brad Frost’s super popular atomic design philosophy. According to atomic design, the smallest units on a page are atoms, which together form molecules, which combine together to form organisms. And these organisms can be seen as our components in some situations.

## Build
It is important to have a consistent strategy and a structure for naming our classes. BEM stands for Block Element Modifier. Here is a small example of what BEM code looks like:

```css
.block {}
.block__element {}
.block__element-modifier {}
```


* **BLOCK**: standalone component that is meaningful on its own.
* **ELEMENT**: part of a block that has no standalone meaning.
* **MODIFIER**: a different version of a block or an element.

## Architect
Next up is architect which is the last part of our strategy. This means that we need to create a logical folder and file structure for our CSS to live in. There is a thing called a 7-1 Pattern introduced by Hugo Giraudel.

The 7-1 Pattern is extremely simple. We will have 7 different folders for partial Sass files, and 1 main Sass file to import all other files into a compiled CSS stylesheet. When we say Sass it could just mean any CSS pre-processor because all of them give us the allowance to implement this pattern.

The 7 folders are base folders:
* **base/** - basic product definitions
* **components/** - a file for each component
* **layout/** - defining an overall layout
* **pages/** - styles for specific projects
* **themes/** - different visual themes
* **abstracts/** - code that doesn’t output any CSS like variables or mix-ins
* **vendors/** - third party CSS
