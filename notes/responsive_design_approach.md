# Responsive Design Strategies
* Start writing CSS for the desktop: large screen;
* Then, media queries shrink design to smaller screens.

Desktop-first -> Mobile-first
Mobile-first -> Desktop-first

* Start writing CSS for mobile devices: small screen;
* Then, media queries expand design to a large desktop screen;
* Forces us to reduce websites and apps to the absolute essentials.

- - - -
### Desktop-first approach

Our spectrum: **0px -> 600px -> 900px -> 1200px -> ∞**
Our initial **desktop-first** code goes here: **∞**
Our initial **mobile-first** code goes here: **0px**

**Maximum** width at which media query still applies.
```css
max-width: 600px;
/* (iswidth <= 600px ?)
```

```css
max-width: 900px;
/* (iswidth <= 900px ?)
```

```css
max-width: 1200px;
/* (iswidth <= 1200px ?)
```

Note: Media queries don’t add any importance or specificity to selectors, so code order matters - **media queries at the end**.

- - - -

### Mobile-first approach

```css
min-width: 600px;
/* (iswidth >= 600px?) */
```

```css
min-width: 900px;
/* (iswidth >= 900px?) */
```

```css
min-width: 1200px;
/* (iswidth >= 1200px?) */
```

- - - -

## Is Mobile-first right for you?

### Pros
* 100% optimized for the mobile experience;
* Reduces websites and apps to the absolute essentials;
* Results in smaller, faster and more efficient products;
* Prioritizes content over aesthetic design, which may be desirable;

### Cons
* The desktop version might feel overly empty and simplistic;
* More difficult and counterintuitive to develop;
* Less creative freedom, making it more difficult to create distinctive products;
* Clients are used to see a desktop version of the site as a prototype;
* Do your users even use the mobile internet? What’s the purpose of your website?

No matter what you do, *always* keep both desktop and mobile in mind.

- - - -

## Selecting our breakpoints: the options
**Bad** Unfortunately, the bad way is the most used way. Designers like to use Apple products to set breakpoints for their screen width. While this is the easiest way, it does come with its problems. First, you are only optimizing for one very specific device, ignoring all the users for other users. Second, and even more important, is that it’s not future-proof. Tomorrow, Apple might change resolutions on all of their resolutions. Then you would have to change all of your media queries, which is pretty tedious.

**Good** In the good way, we look at all the most-used device width on the entire internet and then try to group them in a logical way. And while it’s still not ideal, to use real devices to figure out breakpoint, it’s already a lot better than the first way. Because we’re using a lot of devices, and we’re also using the most popular device width. Plus, we’re not setting breakpoints at one specific width, but between similar device width.

**Perfect** Ignore devices altogether and only look at your content and your design. Ideally, it will work like this. You begin at one size, either mobile or desktop and then start increasing your screen-width or decreasing for desktop first. Then, as soon as the design breaks, which means the design no longer works, then you insert a new breakpoint. So, again, you just place in breakpoints wherever your design starts to look weird and out of place, and don’t think about devices at all.

Without the constraints of pre-defined breakpoints, it’s hard to find the best ones and not to end up with a bunch of them. And that’s why we’re going to use the **good** method for this project. In later projects, we’ll try out the **perfect** way.



