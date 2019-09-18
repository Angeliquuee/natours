# CSS Parsing II
### How CSS Values Are Processed
You may ask, “Why is it important to learn how vh, rem, percentages are calculated?” It is important for many reasons. First because every time you use a unit other than pixels like rem or vh or some other relative unit, you need to know that it will be ultimately converted to pixels and you also need to know how that happens. Also knowing this stuff, will help you predict and control better which property takes which value in the end.

We’re going to be analyzing how the five CSS declarations built a small element. And in particular, how exactly the declared values are processed in six different steps starting from the declared value all the way to the final actual value.

- - - -

![Imgur](https://imgur.com/vxmxrqe.png)

- - - -

![Imgur](https://imgur.com/upWQMRZ.png)

- - - -
# Overview
* Each property has an initial value, used if nothing is declared (and if there is no inheritance - see next lecture)
* Browsers specify a root font-size for each page (usually 16px)
* Percentages and relative values are always converted to pixels
* Percentages are measured relative to their parent’s font-size, if used to specify font-size
* Percentages are measured relative to their parent’s width, if used to specify lengths
* em are measured relative to their parent font-size, if used to specify font-size
* em are measured relative to the current font-size, if used to specify lengths
* rem are always measured relative to the document’s root font-size
* vh and vw are simply measurements of the viewport’s height and width
