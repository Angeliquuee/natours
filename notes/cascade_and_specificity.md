# Cascade and Specificity
As you know, we use a selector to select one or more HTML elements that we want to style. Then in a declaration block, is where write the actual styles in order to style elements on our page. To do so, we can write one or more declarations in each declaration block. Each declaration consists of a CSS property and its corresponding value which is the value that we assign to a property. This value we assign to a property is called the declared value.

- - - -

![Imgur](https://imgur.com/oju0JEC.png)

- - - -

### Cascade
Process of combining different stylesheets and resolving conflicts between different CSS rules and declarations, when more than one rule applies to a certain element.

A declaration for a certain style property like font size can appear in several stylesheets and also several times inside one single stylesheet. Now CSS can also come from different sources. The most common one is the CSS that we developers write, these declarations that we put in our stylesheets are called the _author declarations_.

Another source can be called the user declarations which is CSS coming from the user. For instance, when the user changes the default font sizes in the browser then that is user CSS. And last but not least, there are default browser declarations. For example, if we put an anchor tag in our HTML for a link and then don’t style it at all, it will usually be rendered with blue text and underlined. That’s called the _user agent CSS_ because it is set by the browser.

Cascade combines all these CSS declarations coming from all of these different sources, but how does it actually resolve conflict when more than one rule applies? Well what it does is to look at the important of selector specificity and to source order conflicting declarations in order to determine which one takes precedence.

**Important (weight) > Specificity > Source Order**

First off the cascade starts by giving the conflicting declarations different importance’s based on where they are declared.

### Importance
1. User `!important`declarations
2. Author `!important` declarations
3. Author declarations
4. User declarations
5. Default browser declarations

Let us take a look at an example. So here we have two rules which both apply to the button class. We have two conflicting declarations about the background color. These are both author declarations, but if you look closely in the first rule the declaration with the background color contains the important keyword and therefore this declaration is more important and takes precedence, as you can see from our list above. And so, we see that our button is indeed blue.

```css
.button {
	font-size: 20px;
	color: white;
	background-color: blue !important;
}

#nav .pull-right .button {
	background-color: green;
}
```

### Specificity
1. Inline styles
2. IDS
3. Classes, pseudo-classes, attribute
4. Elements, pseudo-elements

When we have conflicting declarations with the same importance we calculate their selector specificity based on the priorities listed above. Inline styles have the highest specificity.

Using another example, let us see how they actually calculate specificities.

```css

/* -1- */
.button {
	font-size: 20px;
	color: white;
	background-color: blue;
}

/* -2- */
nav#nav div.pull-right .button {
	background-color: green;
}

/* -3- */
a {
	background-color: purple;
}

/* -4- */
#nav a.button:hover {
	background-color: yellow;
}
```

First off, all these declarations have the same important because they are author declarations .

The specificity is actually not just one number, but one number for each of the four categories that was shown to us before (Inline styles, IDS, classes, pseudo elements and attributes, etc) and for each of these we count the number of occurrences in the selector. Simple as that.

In selector `/* -1- */` we don’t have any inline styles of course because an inline style would have to be written in the HTML which is not the case here, so it’s a zero. We also have no IDS here, so it is again a zero and no elements. But what we do have is… the classes. So it’ll look something like this:

`(0, 0, 1, 0)` Inline, IDS, Classes, Elements.

Great, let’s compare it to the `/* -2- */` selector.

`(0, 1, 2, 2)` Inline, IDS, Classes, Elements.

Okay, but what about `/* -3- */`?

`(0, 0, 0, 1)` Inline, IDS, Classes, Elements.

Now the last one… `/* -4- */`

`(0, 1, 2, 1)` Inline, IDS, Classes, Elements.

Makes sense right? But how do we actually use these numbers to find out which of the selectors applies? We start to look at the numbers from left to right, starting with the most specific category the _inline styles_. If there is a selector with 1 it wins against all of the other selectors because this is the most specific category.

Let’s move on to the IDS. We see that selector two and four have a one here while the others have zero. So, the ones with zero are out of the game, because they are less specific than the selectors two and four. Now since both of these selectors have a 1 in this category we have to move on and check the classes.

They both have a 2 in this category, so it is a tie between them. And finally, we move onto the elements category the selector has a two while the selector four has a one. The selector number two is the most specific out of all. And, so, it will have a background color of green.

Now imagine selector four also had two elements then both selectors two and four would have the exact same specificity, right? So what happens in this case?

### Source Order
The last declaration in the code will override all other declarations and will be applied.

So again, if everything is equal, and if all the declarations selectors have the same specificity then the last CSS declaration written in the code is the one that will apply.

# Overview
* CSS declarations marked with `!important` have the highest priority.
* But, only us `!important` as a last resort. It’s better to use correct specificities - **more maintainable code**!
* Inline styles will always have priority over styles in external stylesheets.
* A selector that contains **1** ID is more specific than one with **1000** classes.
* A selector that contains **1** class is more specific than one with **1000** elements.
* The universal selector `*` has no specificity value `(0, 0, 0, 0)`.
* Rely more on **specificity** than on the **order** of selectors.
* But rely on order when using 3rd-party stylesheets - always put your author stylesheet last.
