# CSS Parsing III
```css
.parent {
  font-size: 20px;
  line-height: 150%;
}

.child {
  font-size: 25px;
}
```

These notes are going to be about inheritance in CSS. Inheritance is a way of propagating property values from parent elements to their children. We have a simple example shown above and we’re going to be determining what the line-height of the child element will be.

We remember that from the previous lecture that each and every CSS property must have a value. Even if neither we, the developer nor the browser specifies it. In that case, there’s no cascaded value.

So when processing a property for a certain element, such as line-height, the first question that the CSS engine asks is if there is a cascaded value. And if so, that’s the value that is used. Now if there is no cascaded value, then the next question is if the property can be inherited and that depends on each property. There are some properties that are inherited and others are not. In the case of line-height that property gets inherited. You can check to see if you look up the line-height property specification from documentation. So if a property is inherited, then the value of that property becomes the computed value of its parent element.

It’s very important to note that the property that gets inherited is not simply the 150%, but the computed value. In this case, that’s 150% of 20 pixels, which is 30 pixels. So the line-height, the child element, will also be 30 pixels, not 150% of the 25 pixel font size.

So again, it’s not simply the declared value that passed, but the computer value. Now if it’s a property that isn’t inherited.. like for example, padding, then the specified value will become the initial value which is also specific to each property. In the case of padding, that’s just zero pixels.

- - - -

![Imgur](https://i.imgur.com/tKMjGRt.png)

- - - -

## Inheritance: What You Need To Know
* Inheritance passes the values for some specific properties from parents to children - **more maintainable code**
* Properties related to text are inherited: `font-family`, `font-size`, `color`, etc.
* Inheritance of a property only works if no one declares a value for that property
* The `inherit` keyword forces inheritance on a certain property
* The `initial` keyword resets a property to its initial value
