
## What is CSS?

**CSS** (short for **Cascading Style Sheets**) is the language used to control the visual presentation and layout of websites. While [[1 - HTML]] defines the content and structure (like headers and paragraphs), CSS tells the browser exactly how that content should look—handling everything from colors and fonts to positioning and animations.


### What is the Meta Viewport element used for?

Is a crucial component in responsive web design.

Gives the browser instruction on how to control the page's dimensions and scaling on different devices.

`<meta name ="viewport" content="width=device-width, initial-scale=1.0">`

The `width=device-width` part tells the browser to set the width of the page to match the screen width of the device. This is essential for creating responsive layouts that adapt to different screen sizes.

The `initial-scale=1.0` sets the initial zoom level when the page is first loaded. A value of 1.0 means that the page is displayed at `100%` zoom, without any scaling.

Normally it's used on the tag `head` of the [[1 - HTML]].






### How do Width and Height work?

You can use with values like pixels(px), percentages(%), viewport units (vw, vh), and more.

If you not specify a width or a height, then the default is set to `auto`. This lets the browser determine the element's width based on its content, parent and display type. For a `div` element, `width: auto;` or `height:auto;` makes it expand to fill the full width of its parent container. 

The `min-width` property specifies the minimum width an element can be. Even if the content inside is smaller, the element won't shrink below this value.

The `min-heigth` specifies the minimum height an element can be. It ensures that the element does not become shorter than the set value.

The `max-width` specifies the maximum width an element can grow to, even if there is enough space for it to be wider.

The `max-height` specifies the maximum height an element can grow to, regardless of the content size.





### What Are the Different Types of CSS Combinators?

CSS combinators are used to define the relationship between selectors in CSS. They help in selecting elements based on their relationship to other elements, which allows for more precise and efficient styling. 

#### Descendant combinator

Is used to target elements matched bu the second selector if they are nested within an ancestor element that matches the fist selector. An ancestor can be a parent element or a parent's parent.

`figure img {
	border: 4px solid  blueviolet;
}`

#### Child combinator 

The child combinator  (`>`) in CSS is used to select elements that are direct children of a specified parent element.

This combinator targets only elements with a specific parent, making your CSS rules more precise and preventing unintended styling of deeper nested elements.

`.cotainer > p {
	color: blue;
}`

#### Next-sibling combinator

The next-sibling combinator (+) in CSS selects an element that immediately follows a specified sibling element. This combinator is useful when you want to apply styles to an element that directly follows another element, allowing for targeted styling based on the element's position relative to its siblings.  

`img + figcaption {
	border: 4px solid black;
}` 
![[Pasted image 20260521220953.png]]


#### Subsequent-sibling combinator 

The subsequent-sibling combinator (~) in CSS selects all siblings of a specified element that come after it. 

Unlike the next-sibling combinator, which targets only the immediately following sibling, the subsequent-sibling combinator can target any siblings that follow the specified element, offering greater flexibility in styling.

`h2 ~ p {
	color: green;
}`

![[Pasted image 20260521221550.png]]





### What Is the Difference Between Inline and Block-Level elements in CSS?

In [[1 - HTML]] and CSS, elements are classified as either inline elements or block-level elements, and this classification dictates how they behave in the document layout.

Block-level elements are elements that take up the full width available to them by default, stretching across the width of their container. 

These elements always start on a new line and push other content to the next line, creating a block of content.

Block-level elements have the CSS property `display: block;` applied by default. This property ensures that the element stretches to fill the container's width and appears on a new line.  

Some common block-level elements are `div` elements, paragraphs, headings, ordered lists, unordered lists, and section elements.

![[Pasted image 20260522181626.png]]

In this example, we have two paragraph elements where the first one has a red border around it.

The two paragraph elements do not share the same line because they are block level elements by default.

So, both paragraph elements will take up the full width of its container, which in this case is the `body` element.

Block-level elements are ideal when you want content to stack vertically, such as paragraphs, sections, or larger blocks of content. They're commonly used to define the layout and structure of a webpage.

Inline elements, unlike block-level elements, only take up as much width as they need and do not start on a new line. These elements flow within the content, allowing text and other inline elements to appear alongside them.

Inline elements have the CSS property `display: inline;` applied by default. This property ensures that the element remains within the flow of the content and does not break onto a new line.

Common inline elements are `span`, `anchor`, and `img` elements.

![[Pasted image 20260522181833.png]]

In this example, we have a `span` element nested inside of a paragraph element. The `span` element has a `red` text color with a `green` border around it so you can see the highlighted word better.






### How Does Inline-Block Work, and How Does It Differ from Inline and Block Elements?

 The `inline-block` property remains in the text flow without starting on a new line.

However, unlike inline elements, you can adjust the width and height of and `inline_block` element, just as you would with block-level elements.

In short, the key difference between `inline` and `inline-block` is that  `inline` elements cannot have their size controlled, whereas `inline-block` elements allow for full control over dimensions while still staying inline with other content.

![[Pasted image 20260522201628.png]]
![[Pasted image 20260522201727.png]]

But if you remove the `display: inline-block;` property, neither the height nor the width will be applied even though you define it clearly:

![[Pasted image 20260522202134.png]]
![[Pasted image 20260522202141.png]]






### What Are Margins and Padding, and How Do They Work?

Margin and padding are essential properties in CSS for creating well-structured, readable, and visually appealing web pages.

Margins control the space outside an element, helping to separate it from other elements and define the layout  structure, while padding controls the space inside an element, improving content readability and aesthetic appeal.

If three values are provided in `margin: ;` or `padding: ;`, the first value applies to the `top` margin, the second value to the `left` and `right` margin, and the third value to the `bottom` margin.

`p {
	margin: 10px 20px 30px;
}`

When using four values, this gives you more control, as you can independently specify each margin value for each side of the target element. The first value targets the `top`, the second value targets the `right`, the third value targets the `bottom`, and the fourth value targets the `left`. 

`p {
	margin: 10px 20px 30px 40px;
}`


## CSS Specificity, the Cascade Algorithm, and Inheritance

### What is CSS Specificity, and the Specificity for inline, internal, and External CSS?

CSS specificity is a fundamental concept that determines which styles are applied to an element when multiple rules could apply.

Understanding specificity helps developers resolve conflicts between different CSS rules and ensures that desired styles are consistently applied.

CSS specificity is calculated based on the type of selectors used. 

The highest specificity is attributed to inline styles, which are applied directly to an element through the style attribute.



