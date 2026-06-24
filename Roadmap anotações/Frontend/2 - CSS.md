
# Basic CSS
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

When comparing **Inline**, **Internal**, and **External** CSS, the default hierarchy depends heavily on proximity and location weight:

1. **Inline CSS** `(1, 0, 0, 0)` ➔ **Highest Priority**
   - Applied directly to an element via the `style` attribute (e.g., `<p style="color: red;">`).
   - Overrides any internal or external stylesheet rules (unless `!important` is used).
1. **Internal CSS** ➔ **Medium Priority (Contextual)**
   - Defined within `<style>` tags inside the `<head>` section of an HTML document.
   - *Note:* It shares the same inherent selector-based rules as External CSS, but often overrides external styles purely due to **Source Order** (typically placed after external `<link>` tags).
3. **External CSS** ➔ **Lowest Priority (Contextual)**
   - Written in a separate `.css` file and linked using the `<link>` element.
   - Provides the best code maintainability but can be easily overridden by internal and inline styles.

Specificity is represented as a four-part weight vector: **`(Inline, ID, Class, Type)`**

| Selector Level | Weight Category | Specificity Value | Examples / Description |
| :--- | :--- | :--- | :--- |
| **Level 1** | **Inline Style** | `(1, 0, 0, 0)` | Written directly inside the HTML tag attribute. |
| **Level 2** | **ID Selectors** | `(0, 1, 0, 0)` | Targets unique structural elements (e.g., `#header`, `#submit-btn`). |
| **Level 3** | **Class, Attributes & Pseudo-classes** | `(0, 0, 1, 0)` | Targets reusable blocks (e.g., `.btn`, `[type="text"]`, `:hover`). |
| **Level 4** | **Element Type & Pseudo-elements** | `(0, 0, 0, 1)` | Targets raw HTML tags (e.g., `p`, `div`, `h1`, `::before`). |

When multiple matching selectors possess conflicting definitions, the Cascade Algorithm filters and resolves them using these subsequent tie-breakers:

1. **Specificity Score:** The selector with the highest weight vector wins (e.g., `(0, 1, 0, 0)` beats `(0, 0, 2, 5)`).
2. **Source Order (The Last Resort):** If the specificity scores are completely identical, the rule that appears **last (closest to the bottom)** in the CSS processing order wins and overrides previous declarations...

---



### What Is the Universal Selector, and What Is Its Specificity?

The universal selector (`*`) is a special type of CSS selector that matches any element in the document.

It is often used to apply a style to all elements os the page, which can be useful for resetting or normalizing styles across different browsers.

The universal selector can be used to select all elements within a specific context or globally across the entire document. 

An example of using the universal selector for setting the `margin` and `padding` for the entire HTML document:
![[Pasted image 20260525173248.png]]
![[Pasted image 20260525173313.png]]


The universal selector has the lowest specificity value of any selector. Ir contributes 0 to all parts of the specificity value (0, 0, 0, 0).

This means that any other selector, including type selectors, class selectors, and inline styles, will override the styles set by the universal selector.

---


### What Is the Specificity for Type Selectors? 

Type selectors, also known as element selectors, target elements based on their tag name. 

These selectors are fundamental in CSS and allow you to apply styles to all instances of a specific HTML element. 

Type selectors are straightforward to use and are written simply as the tag name of the element you want to style.
![[Pasted image 20260525182321.png]]

Type selectors have a relatively low specificity compared to other selectors. The specificity value for a type selector is `(0, 0, 0, 1)`.

---



### What Is the specificity for Class Selectors?

Class selectors are a key part of a CSS, allowing developers to target multiple elements with the same class attribute and apply consistent styling.

![[Pasted image 20260525182836.png]]
![[Pasted image 20260525182840.png]]

The specificity value for a class selector is `(0, 0, 1, 0)`. This means that class selectors can override type selectors, but they can be overridden by ID selectors and inline styles.

Class selectors can be combined with other selectors to create more specific rules. 

![[Pasted image 20260525182955.png]]
![[Pasted image 20260525183002.png]]

---


### What Is the Specificity for ID Selectors?

ID selectors are among the most powerful selectors in CSS, allowing developers to apply styles to a specific elements with unique identifiers.

This makes them highly effective for targeting individual elements that need unique styling. 

ID selectors are defined by a hash (`#`) followed by the ID name. They should be unique within an HTML document, meaning no two elements should share the same ID.

![[Pasted image 20260525183711.png]]
![[Pasted image 20260525183722.png]]

---

ID selectors have a very high specificity, higher than type selectors and class selectors, but lower than inline styles. The specificity value for an ID selector is `(0, 1, 0, 0)`.

This means that ID selectors can override class selectors and type selectors but can be overridden by inline styles.

---



### What Is the important Keyword, and What Are the Best Practices for Using It?

The `!important` keyword in CSS is used to give a style rule the highest priority, allowing it to override any other declarations for a property. 

When used, it forces the browser to apply the specified style, regardless of the specificity of other selectors.

![[Pasted image 20260525184609.png]]

---
The `!important` keyword in CSS is used to give a style rule the highest priority, effectively overriding other declarations, including those with higher specificity and inline styles.

However, the `!important` keyword does not change the specificity of the CSS selector itself. It simply ensures that the rule with `!important` is applied, even if there are other conflicting rules with higher specificity.

Another appropriate use case for the `!important` keyword is to override styles from third-party libraries or frameworks when you do not have control over the original CSS.

However, overusing the `!important` keyword can lead to difficulties in maintaining and debugging your CSS, as it breaks the natural cascading of styles and can lead to unintended consequences.

So, it is best to use the `!important` keyword sparingly.

---



### How Does the Cascade Algorithm Work at a High Level?

The Cascade algorithm is the process the browser uses to decide which CSS rules to apply when there are multiple styles targeting the same element. It ensures that the most appropriate styles are used, based on a set of well-defined rules.

The process begins with **relevance**. The browser first filters all the CSS rules to find those that actually apply to the element in question. This includes matching selectors and considering media queries that might be in effect.

A media query is a CSS technique used to apply styles based on the characteristics of the device or viewport, such as its width, height, or orientation.

Next, the algorithm considers **origin and importance**. CSS can come from different sources: the browser’s default styles (user-agent), styles set by the user, and styles written by the author (you).

Following the consideration of origin, the algorithm then evaluates the importance of each rule, giving priority to rules marked with `!important`, which override other rules regardless of their source.

After filtering by origin and importance, the algorithm looks at **specificity**. When two rules from the same origin and importance level apply, the rule with the higher specificity will be applied.

Specificity is a measure of how targeted a selector is, with more specific selectors taking precedence over more general ones.

Finally, if everything else is equal, the **order of appearance** comes into play. When two rules have the same specificity, the one that appears last in the CSS will be applied.

This is why the order in which you write your styles can sometimes affect the outcome.



---



### How Does Inheritance Work with CSS at a High Level?

Inheritance is a key concept in CSS that determines how styles are passed down from parent elements to their child elements. 

Just like in the real world, where children often inherit traits from their parents, in CSS, certain properties can be inherited by child elements from their parent elements.

This allows for a more efficient way to apply consistent styling across an entire document. 

In CSS, not all properties are inherited by default. For example, properties like `color`, `font-family`, and `line-height` are inherited. This means that if you set the text color on a parent element, all of its child elements will inherit that color unless you specifically override it.

---



## Styling Lists and Links

### How Do You Space List items Using margin or line-height

Margins and line-height are essential for spacing list items to enhance readability and visual appeal.

Margins ca be used to create space between list items bu applying margin properties to the `li` elements. This method allows you to control the spacing outside each list item, effectively increasing or decreasing the gap between them. 

![[Pasted image 20260527120638.png]]
![[Pasted image 20260527120709.png]]

The `line-height` property adjusts the vertical spacing between lines of text within a single list item. 

While it primarily affects the spacing between lines of text within each item, it can also indirectly influence the overall spacing between list items if the items contain only a single line of text.

If list items have multiple lines of text, the `line-height` will affect the spacing between those lines, but it does not directly adjust the spacing between separate list items themselves.

To control the spacing between individual list items, you would use `margin` or `padding` properties instead.

![[Pasted image 20260527121605.png]]



---



### How Do the Different list-style Properties Work?

In CSS, the `list-style` property is used to control the appearance of lists on a webpage.

The `list-style` property is actually a shorthand for three other properties:

- `list-style-type`
- `list-style-position`
- `list-style-image`

The `list-style-type` property allows you to define the type of bullet point or number used in a list.

For unordered lists, you can choose from several bullet styles, such as discs, circles, or squares.

For ordered lists, you can use different numbering systems, like decimal, Roman numeral, or even alphabetical characters. 

`list-style-type`:
![[Pasted image 20260527122312.png]]

`list-style-position`:
![[Pasted image 20260527122341.png]]

`list-style-image`:
![[Pasted image 20260527122405.png]]

You can combine the three properties into a single `list-style` shorthand property.

The order of the values in the shorthand doesn't matter, but all three can be specified together. 

%% <ul style="list-style: square inside url('https://cdn.freecodecamp.org/curriculum/cat-photo-app/relaxing-cat.jpg');">

<li>Item 1</li>

<li>Item 2</li>

<li>Item 3</li>

</ul> %%



---



### Why Are Default Link Styles Important for Usability on the web?

Default link styles play a crucial role in enhancing usability and accessibility on the web. 

These styles, typically blue for unvisited links and purple for visited links, have become a standard that users have come to expect and rely on when navigating websites. 

The primary purpose of default link styles is to provide clear visual cues that help users distinguish between interactive and non-interactive elements on a webpage.

This distinction is fundamental to creating an intuitive and user-friendly browsing experience. 

![[Pasted image 20260527123610.png]]

These styles serve several important functions.

Firstly, the blue color for unvisited links stands out against most background colors and text, making links easily identifiable. This contrast is crucial for users to quickly scan a page and find navigational elements or important information.

The underline further emphasizes that the text is clickable, providing an additional visual cue. This is particularly helpful for users who may be colorblind or have difficulty distinguishing colors. 

The change in color for visited links (typically to purple) helps users keep track of where they've been. This feature is invaluable for navigation large websites or conducting research, as it prevents users from inadvertently revisiting the same pages. 

It's also important to consider the different states of links. In addition to the default and visited states, links typically have hover and active states:
![[Pasted image 20260527124536.png]]



---



### How Do You Styles the Different Link States?

There are different states of a link, including `link, visited, hover, focus` and `active`.
These states are important for helping users recognize links and providing clear feedback after interactions, which improves both usability and accessibility.

Styling these different link states is crucial for usability and accessibility, as it provides visual cues about the current state of the link. This helps users understand which links they have visited, which link they are interacting with, and what will happen when they click.

Additionally, clear link states enhance the overall user experience by providing immediate feedback on user interactions, reducing confusion and improving the site's navigability.

These states can be styled using something called `pseudo-classes` in CSS.

A pseudo-class is a keyword added to a selector that specifies a special state of the selected element.

For example, `:hover` can change a button's color when the user's pointer hovers over it, while `:visited` can change the color of a link that has already been visited.

The syntax of a `pseudo-class` looks something like this where `A` is the selector and `:B` is the `pseudo-class`:

![[Pasted image 20260527125422.png]]

The `:link` pseudo-class styles unvisited links, indicating that they are clickable.
![[Pasted image 20260527125549.png]]

`:visited` links that gabe already been visited or clicked.
![[Pasted image 20260527125640.png]]

`:hover` changes the link's style when the user hovers over it.
![[Pasted image 20260527125719.png]]

`:focus` adds styles around the link when it is focused, such as when navigating with a keyboard, or enhancing accessibility.

Here an example using the `outline` property to apply a solid orange outline.
![[Pasted image 20260527125850.png]]

`:active` changes the link styles while the link is being clicked.
![[Pasted image 20260527125942.png]]

.

---



## Working with Backgrounds and Borders

### How Do Background Image Size, Repeat, Position and Attachment Work?

When working with background images in CSS, you have several properties at your disposal to control how these images are displayed. 

The main properties we'll focus on are `background-size`, `background-repeat`, `background-position`, and `background-attachment`. 

```
<style>
	body{
		background-image: url("https://cdn.freecodecamp.org/curriculum/cat-photo-app/relaxing-cat.jpg");
	}
</style>
```

If you want to set the size for the background image, you can use the `background-size` property.

You can use `contain` to scale the image as large as possible without cropping or stretching.

```
<style>

body {

background-image: url("https://cdn.freecodecamp.org/curriculum/cat-photo-app/relaxing-cat.jpg");

background-size: contain;

min-height: 100px;

}

</style>
```

If we change the `background-size` property to use the `cover` value, then the background image will scale to cover the entire `body` element while maintaining its aspect ratio.

```
<style>

body {

background-image: url("https://cdn.freecodecamp.org/curriculum/cat-photo-app/relaxing-cat.jpg");

background-size: cover;

min-height: 100px;

}

</style>
```

In the previous examples, you probably noticed that the background image would continuously repeat.

By default, background images repeat both horizontally and vertically to fill the entire element. However, you can control this behavior.

You can use the `background-repeat` property with the value set to `no-repeat`.

```
<style>

body {

background-image: url("https://cdn.freecodecamp.org/curriculum/cat-photo-app/relaxing-cat.jpg");

background-size: contain;

background-repeat: no-repeat;

min-height: 100px;

}

</style>
```

with the `background-size` set to ` contain` and the `background-repeat` set to `no-repeat`, the image will no longer repeat on the screen.

If you wanted to repeat the background image horizontally, you can use the `repeat-x` value for the `background-repeat` property.

```
<style>

body {

background-image: url("https://cdn.freecodecamp.org/curriculum/cat-photo-app/relaxing-cat.jpg");

background-size: contain;

background-repeat: repeat-x;

min-height: 100px;

}

</style>
```

And to set the background image vertically, you can use the `repeat-y`.

The `background-position` property allows you to set where in the element the background image appears. You can use keywords like `top, bottom, left, right and center`, or specific pixel or percentage values.

```
<style>

body {

background-image: url("https://cdn.freecodecamp.org/curriculum/cat-photo-app/relaxing-cat.jpg");

background-size: contain;

background-repeat: no-repeat;

background-position: center top;

min-height: 100px;

}

</style>
```

Lastly, `background-attachment` determines whether the background image scrolls with the content or remains fixed when the page is scrolled.

The main values are `scroll`(default), where the background image scrolls with the content, and `fixed`, where the background image stays in the same position on the screen,

```
<style>

body {

background-image: url("https://cdn.freecodecamp.org/curriculum/cat-photo-app/relaxing-cat.jpg");

background-position: center top;

background-attachment: fixed;

}

</style>
```

If you wanted to combine a few of the properties into one line, you can do that by using the shorthand ` background` property.

```
<style>

body {

background: center top fixed

url("https://cdn.freecodecamp.org/curriculum/cat-photo-app/relaxing-cat.jpg");

}

</style>
```



---



### What is a Background Gradient, and How Does It Work?

A background gradient in CSS is a smooth transition between two or more colors that can be applied to the background of an element. Gradients allow you to create visually appealing backgrounds without needing images. 

There are two main types of gradients: linear gradients and radial gradients.

A linear gradient transitions colors along a straight line. You can define the direction and the colors involved.

```css
background: linear-gradient(direction, color-stop1, color-stop2, ...);
```

The direction specifies the direction of the gradient. It can be an angle (such as `45deg`), a keyword (such as `to right, to bottom`), or a side/corner.

`color-stop` specifies the colors and positions where the gradient transitions occur.

```html
<html>
<style>
.linear-gradient{

background: linear-gradient(to right, red, yellow);

height: 40px;

}
</style>
<body>
<div class="linear-gradient"></div>
</body>
</html>
```

This CSS creates a linear gradient that transitions from `red` on the `left` to `yellow` on the `right`. The gradient is applied to an element with a height of `40%` of the viewport height. You'll learn more about `vh` units in a future lesson.


Another type of gradient would be the `radial` gradient.

A radial gradient transitions colors radiating from an origin (usually the center) outward in a circular or elliptical shape.

```css 
background: radial-gradient(shape size at position, color-stop1, color-stop2, ...)
```

On the syntax, the `shape` specifies the shape of gradient which could be `circle` or `ellipse`.

The `size` determines the size of the gradient's ending shape which could be `closest-side`, `closest-corner`, `farthest-side` or `farthest-corner`.

`position` determines the position of the gradient's center which could be specified using keywords (such as `center`, `top left`, `bottom right`) or precise values (such as `50% 50%`, `10px 20px`).

Lastly, color stops are a list of colors that the gradient transitions through. Each color stop can optionally include a position value (percentage or length) indicating where the color should be placed.

![[Pasted image 20260603151342.png]]

The `closest-side` keyword makes the gradient's ending shape fit the closest side of the element. The gradient is applied to an element with a height of `60%` of the viewport height.



---



### What Are Some Accessibility Considerations for Backgrounds?

In web design, backgrounds play a vital role in defining the overall look and fell of a webpage.

However, when designing with backgrounds, it's crucial to consider accessibility to ensure your content is usable and readable by all users, including those with visual impairments.

One of the primary accessibility concerns related to backgrounds is ensuring that there is sufficient contrast between the background and the text.

Without adequate contrast, users with visual impairments, including those with low vision or color blindness, may struggle to read the content on your page.

Contrast refers to the difference in lightness or darkness between two colors. Sufficient contrast between the background color and the text color is essential for readability.

The Web Content Accessibility Guidelines (WCAG) recommend a minimum contrast ratio of 4.5:1 for normal text and 3:1 for large text.

Another consideration is avoiding placing text over busy or complex backgrounds, such as images or gradients with multiple colors. Busy backgrounds can make it hard to distinguish the text from the background, regardless of the contrast.

When designing backgrounds, avoid using color as the sole means of conveying information. For example, using just color to indicate an error or success message (such as red for error or green for success) can be problematic for users with color blindness.

In addition to color, you should use symbols or text to convey information. For example, alongside a red error message, you could use an icon or bold text to make it clear that there’s an error.

Though less common, background audio or videos can also affect accessibility.

Background music or auto-playing videos can be distracting for some users, particularly those with cognitive disabilities. If you include background audio, always provide a way for users to mute or pause the audio.

---



### What Are the Different Ways You Can ADD Borders Around Images?

In CSS, there are several ways to add borders around images, each offering different styling options and levels of control.

Let's explore some of the most common and versatile methods.

The most straightforward way to add a border to an image is by using the `border` property. This property is a shorthand that allows you to set the width, style, and color of the border all at once.

```css
img {

border: 2px solid red;

}
```

This CSS rule adds a 2-pixel wide, solid red border around all `img` elements. You can adjust the width, style (such as `dashed`, `dotted`, or `double`), and color to suit your design needs.

If you need more control over individual sides of the border, you can use the specific border properties for each side:

```css
img {

border-top: 10px solid red;

border-right: 10px dashed green;

border-bottom: 10px dotted blue;

border-left: 10px double purple;

}
```

This allows you to create unique border styles for each side of the image.

Another way to create a border effect is by using the `outline` property. While similar to border, outline doesn't affect the element's dimensions or layout:

```css
img {

outline: 3px solid gold;

}
```

This creates a gold outline around the image without changing its size or position.

If you want to create rounded corners on your border, you can use the `border-radius` property in conjunction with border:

```css
img {

border: 2px solid black;

border-radius: 10px;

}
```



---



# Design

## User Interface Design

### What Are Common Design Terms to Help You Communicate with Designers?

#### Layout:

Layout is how the visual elements are arranged on a page or screen to communicate a message. These elements may include text, images, and white space. The layout is like the blueprint of a design. Designers must consider the placement, size, and hierarchy of each element.



---



#### Composition:

Composition is the art of arranging elements to create a harmonious design. I determines how elements like images, text, and shapes relate to each other and contribute to the design in an artistic way. While layout mostly focuses on the placement of the elements, composition also considers the artistic impact that this placement will have in the overall design.



---



#### Balance:

Balance is how the visual weight is distributed within a composition . Designers aim to create an equilibrium through  symmetrical or asymmetrical arrangements. A balanced design feels harmonious.

---



#### Hierarchy:

Hierarchy establishes the order of importance of the elements in a design. It's about making sure the most important information is noticed  first. You can implement a visual hierarchy with size, color, contrast, alignment, white space, and ever typography.

---



#### Contrast:

Contrast is helpful for guiding user attention to what you want to emphasize. You can do this through variations in color, size, shape, texture, or any other visual characteristic. Strong contrast is also helpful for improving readability.

--- 



#### White space:

White Space, also known as "negative space", is the empty space in a design. It's the area surrounding the elements. You might be surprised to know that white space is not necessarily white. Actually, it can be space in any color or texture. Its purpose is to improve the readability and enhance the visual hierarchy of a design.

---



### What Is the Importance of Good Visual Hierarchy in Design?

Visual hierarchy refers to the way you layout and display the content of your page to guide the viewer's attention.

A strong hierarchy can provide a clear path for the eye to follow, ensuring that the information you convey is consumed in the order that you intended.

Let's consider a basic page layout in which the HTML for the page is semantically correct, but the styling applied does not create a strong visual hierarchy.

![[Pasted image 20260616134253.png]]

If the font size isn't distinct, there is no visible indication of the document flow, although things are separated by headings.

To create a visual hierarchy, you should apply different font sizes to the heading tiers. You could also use something like a "callout box" to highlight a specific section.

![[Pasted image 20260616134402.png]]

Visual hierarchy can also help increase your user conversion. For example, you can take advantage of the callout box to further draw attention to a Call to Action (CTA) button.

![[Pasted image 20260616134438.png]]



---



### How Does Scale work in Design?

The "scale" of something refers to its size.

When you're looking at scaling in your web design, you're looking at the size relationships between different elements, and how these elements might adapt to different screen sizes.

Using the correct scale for your elements plays an important role in visual hierarchy. Larger elements will draw more attention, which can guide your users through the content in the way that you want.

For example, the visual separation between a heading and a paragraph draws your reader’s attention, but the scale should be appropriate to get an eye-catching text that pulls your reader to that section.

![[Pasted image 20260616134714.png]]



---



### How Does Alignment Work in Design?

When you are designing web pages, it is important to create cohesive and visually appealing designs. One way to achieve this is through the use of alignment.

Alignment is the process of arranging text and images in a way that creates a visual connection between elements.

It helps to create a sense of order and organization on the page, making it easier for users to navigate and understand the content.

There are several types of alignment you can use, but the basic ones are:

- left alignment
- center alignment
- right alignment
- justified alignment
- vertical alignment

Left, right, and center alignments are all subtypes of horizontal alignment, while vertical alignment is used to align elements along a vertical axis.

Let's take a closer look at each type of alignment and how you can use them in your designs.

Left alignment is commonly used with text where each element is aligned to the left margin. Aligning all of the headings and paragraphs on a web page to the left margin makes it easier for the user to read and follow the content.

![[Pasted image 20260616134945.png]]

The opposite of left alignment is right alignment, where each element is aligned to the right margin. This is often used on websites to display additional content like promotional banners or advertisements.

![[Pasted image 20260616135002.png]]


Vertical alignment can be used, for example, for a contact form on a website. Aligning all of the form inputs like the name, email, and message fields along a vertical axis makes it easier for the user to fill out the form.

![[Pasted image 20260616135040.png]]



---



### What Is the Importance of Whitespace in Design?

White space refers to any type of space around elements like images, text, and buttons. White space is important in design because it helps to create a balance between the elements on the page.

Let's take a look at some examples of how white space can be used effectively in design.

For example, let's consider a call-to-action (CTA) button. CTAs are used to encourage users to take a specific action like signing up for a newsletter or making a purchase.

On the freeCodeCamp homepage, the CTA button is visually separated from other elements. The image below shows this button, with a certain amount of space around it.

![Call-to-action button on the freeCodeCamp homepage with yellow background and black text reading: Get started (it's free). The button is centered on its own line with ample white space above and below.](https://cdn.freecodecamp.org/curriculum/lecture-transcripts/what-is-the-importance-of-whitespace-in-design-1.png)

By using white space effectively, we can help to make a CTA button more prominent and encourage users to click on it.

Now let's take a closer look at the different types of white space.

This first example uses both macro and active white space. Macro white space is the space between larger elements like images, text blocks, and buttons.

Active white space is the space that is intentionally created to help guide the user's eye and draw attention to certain elements on the page.

In contrast to active white space, there is also passive white space. Passive white space is the space that is left over after all the elements on a page have been placed.

Another type of whitespace would be micro white space. This is the space between individual characters in a line of text.

The image below shows the Frequently Asked Questions section on the freeCodeCamp homepage, where this spacing allows you to read each question and answer easily.

![The Frequently Asked Questions section on the freeCodeCamp homepage, with text spaced sufficiently between each letter.](https://cdn.freecodecamp.org/curriculum/lecture-transcripts/what-is-the-importance-of-whitespace-in-design-2.png)

Micro white space is important because it helps to improve readability and legibility, making it easier for users to scan and understand the content.

When designing your web pages, you always want to be mindful of the law of proximity. This law states that elements that are close together are perceived as being related, while elements that are far apart are perceived as being unrelated.

You can use white space to help group related elements together and help navigate users through the content on your page.

---



### What Are Best Practices for Working with Images in Your Designs?

The first thing to consider is creating responsive images. Responsive images are images that scale to fit the size of the screen they are being viewed on. This is important because it ensures that your images look good on all devices, from desktops to mobile phones.

`
<html>
<style>

body {

font-family: sans-serif;

padding: 20px;

background-color: #fefefe;

color: #333;

text-align: center;

}

  

img {

max-width: 100%;

height: auto;

border-radius: 8px;

}

  

p {

font-size: 16px;

max-width: 600px;

margin: 20px auto;

line-height: 1.6;

}

</style>

  

<h1>Responsive Cat Image</h1>

  

<img

src="https://cdn.freecodecamp.org/curriculum/cat-photo-app/cats.jpg"

alt="Two cats peacefully sleeping together."

/>

  

<p>

This image automatically scales based on the screen size. Whether you're viewing on a desktop or a mobile phone,

it adjusts its size without losing proportions, making the design clean and user-friendly on all devices.

</p>
</html>`
Another thing to consider is the resolution for images. Higher quality images with better resolution have more pixels per inch. Pixels are small squares that make up an image.

Pixels per inch, or PPI, is the number of pixels in one inch of an image. The higher the PPI, the better the image quality.

You want to make sure that your images are high quality and look good on all devices. This means that you should use high resolution images that are optimized for the web.

Another thing to consider is the size of your images and how they fit within the spaces in the layout. You want to make sure that your images are the right size and are not too large or too small.

Using large images that are meant to fit in smaller spaces in the design can slow down your website and make it harder for users to load your site. You want to make sure that your images are the right size and are optimized for the web.

When it comes to image placement, you want to think about balance, hierarchy, and alignment to help ensure your images are optimized for the web.

Balance is the distribution of visual weight in a design. You want to make sure there is a good balance between text and images on the site so it creates a harmonious design

`
<html>
<style>

body {

font-family: sans-serif;

margin: 0;

padding: 40px 20px;

background-color: #f9f9f9;

color: #333;

}

  

.container {

display: flex;

flex-wrap: wrap;

align-items: center;

justify-content: space-between;

gap: 30px;

max-width: 1000px;

margin: 0 auto;

}

  

.text {

flex: 1 1 400px;

}

  

.text h2 {

font-size: 28px;

margin-bottom: 10px;

}

  

.text p {

font-size: 16px;

line-height: 1.6;

}

  

.image {

flex: 1 1 400px;

}

  

.image img {

width: 100%;

height: auto;

border-radius: 8px;

}

</style>

  

<div class="container">

<div class="text">

<h2>Balanced Layout</h2>

<p>

Balance is essential in web design. By evenly distributing visual weight—such as pairing this block of text

with a complementary image—you create a layout that feels calm, structured, and easy to navigate.

</p>

</div>

  

<div class="image">

<img src="https://cdn.freecodecamp.org/curriculum/cat-photo-app/cats.jpg" alt="Two cats peacefully sleeping together.">

</div>

</div>
</html>
`



---



### What is Progressive Enhancement?

Progressive enhancement is a design approach that ensures all users, regardless of browser or device, can access the essential content and functionality of an application.

It focuses on delivering a core experience that works for everyone, while offering extra features and improvements to users with more advanced browsers or better internet connections.

The progressive enhancement approach lives by these core principles:

- All core content and basic functionality should be accessible on all browsers
- All advanced layouts should be provided through external CSS stylesheets
- All advanced functionality should be provided through external JavaScript files
- A user's browser preferences should be respected

Using a progressive enhancement approach makes your applications more accessible because all core content and functionality should not be blocked in unsupported environments.

In terms of speed, a progressive enhancement approach can also help improve the performance of your applications.

Those users that are working with slower internet connection speeds will still be able to access the content because the browser will download the necessary resources first.

When it comes to SEO, progressive enhancement can also help improve the visibility of your applications.

Search engines will be able to crawl the content of your applications because the core content is available in the initial HTML response.

While some have criticized this approach deeming that it is not always realistic for applications that rely heavily on JavaScript for their functionality, it is still a good practice to follow when building applications.

---



## User-Centered Design


### What Is User-Centered Design?

User-centered design is a web development approach that prioritizes the end user, from their needs to their preferences and limitations. The goal of user-centered design is to craft a web page that is intuitive, efficient to use, and pleasing for your users to interact with.

One of the first aspects of user-centered design is considering your target demographics. For example, if your intended user-base is younger, you might leverage more flashy eye-catching designs that grab their attention immediately. For an older audience, you might focus more on clear and streamlined designs without distractions.

Another aspect to consider is the goal of your end users. For example, if you're building an e-commerce page for your products, you probably don't want to advertise someone else's products on your page. But if you're building a personal blog, you might include advertisement elements to generate revenue from passive readers.

User behavior is an important factor as well. You'll want to leverage an analytics tool, like Google Analytics, to measure how your users engage with your pages. This can reveal areas where users might be getting "stuck" and leaving your page, or opportunities to improve the overall interaction flow.

A key to user-centered design is to actually involve your users. Providing a feedback channel where they can share their experiences and pain points with your site allows you to capture vital information and iterate further to improve. Ultimately, user-centered design means you need to put the user at the forefront of your decision making, whether that's through research or direct feedback.

---



### What Are User Requirements, User Research, and Testing?

User research is the systematic study of the people who use your product. The goal is to measure user needs, behaviors, and pain points.

User research comes in many forms. Perhaps one of the most common is the Net Promoter Score, or NPS. The NPS measures how likely your users are to recommend your product to a friend. NPS is measured through a survey offered at key milestones along the user's journey, such as after 7 days, 30 days, and 90 days. NPS is measured on a scale of 0 to 10, with 9 and 10 indicating an active promoter of your site.

Another research vector is an exit interview. This is a survey you show to your users when they cancel a subscription or delete an account. Data from this survey can give you insight into the factors causing user churn, so you can address them.

User testing, on the other hand, refers to the practice of capturing data from users as they interface with your application. For example, a video game going through beta testing is a form of user testing. One you might run into as a web developer is A/B testing. A/B testing involves shipping a new feature to a randomly selected subset of your user base. You can then leverage analytics data to determine if the feature is beneficial.

Finally, user requirements refer to the stories or rubric that your application needs to follow. This can inform the development process. User requirements might be defined by user research, or industry standards. They can even be defined by stakeholder input.

These requirements may be functional, meaning they dictate how your application should work, or non-functional, meaning they define how your application should behave. User requirements are not static, either. The information from both user testing and user research can impact the requirements, and they will change as your user base changes.

Understanding the difference is essential for collecting the most accurate data so you can deliver the best experience for your end users.

---



### What Are Best Practices for Designing a Dark Mode Feature?

The first consideration is the avoidance of saturated colors in dark mode. Saturated colors are colors that are bright and intense. For example, a bright magenta button against a dark gray background can be too intense and cause eye strain. Instead, you should use desaturated colors in dark mode. Desaturated colors are colors that are less intense, have a lower saturation level, and more comfortable to look at in dark mode. To see the previews, you will need to enable the interactive editor.

![[Pasted image 20260616142814.png]]

Another consideration with dark mode is the use of pure black backgrounds with white text. While this high contrast can be effective, it can also be too harsh on the eyes. Instead, consider using a dark gray background with light gray text for a softer contrast. Text will be easier on the eyes and more comfortable to read in dark mode.

![[Pasted image 20260616142932.png]]

Another consideration is the use of dark mode with the site's brand identity. A brand identity is a set of visual elements that represent a brand, such as the logo, colors, and typography. When implementing dark mode, you should consider how the dark mode feature is consistent with your brand's colors and style. It is fine to have the brand icon and buttons at full saturation, while the surrounding elements are desaturated.

In general, when it comes to design, you always want to be mindful of the user experience and contrast levels. Dark mode is no exception, and by following these best practices, you can create a dark mode feature that is effective and user-friendly.

---



### What Are Best Practices for Designing Breadcrumbs?

When it comes to web design, there are many types of navigational aids you can use. Examples include top navigation bars, sidebars, and footers. But if your site is on the more complex side with deeper levels of navigation, you might want to consider using breadcrumbs.

Breadcrumbs are a navigation aid that shows the user where they are in the site's hierarchy. Here is an example of what breadcrumbs look like for a mock-up electronics website:

**Home / Electronics / Phones / Smartphone XYZ**

In most websites, breadcrumbs are displayed at the top of the page, showing the user the path they took to get to the current page. Starting from the `Homepage`, the user navigated to the `Electronics` category, then to the `Phones` category, and finally to the `Smartphone XYZ` product. You have probably interacted with breadcrumbs on a website as you were searching for a product or specific piece of information.

The use of breadcrumbs is helpful because it can help users understand where they are in the site's hierarchy and how to navigate back to the previous pages. This is especially useful when a user has come from a search result or an external link and needs to understand the context of the page they are on.

When it comes to designing breadcrumbs, there are a few considerations to keep in mind. The first is to decide on what the separator will be. The separator is the character that separates the different levels of the hierarchy. Common separators include the greater than sign (`>`), right angle quotation marks (`»`) ,and the forward slash (`/`).

The second consideration is the placement of the breadcrumbs. Breadcrumbs are typically placed at the top of the page, either above or below the main navigation bar. Users shouldn't have to struggle to find the breadcrumbs, so make sure they are visible and easy to locate.



---



### What Are Best Practices for Designing Cards?

The first consideration for card design should be simplicity. You don't want your cards to be visually cluttered or display too much information. For example, if a card design is visually cluttered, there will be too much information for the user to process all at once.

Here is an example of a cluttered card design:

![[Pasted image 20260616143740.png]]

Having less information and good spacing between items on the card makes it easier for the user to process the information, and allows for multiple cards on the page.

![[Pasted image 20260616143844.png]]


Another thing to consider is where the user can click on the card. Some card designs will have a single button, making it obvious where the user can click. Other card designs will have the entire card clickable. When the user hovers over any part of the card, the card will change color or have a shadow effect to indicate that the card is clickable. Whatever design you choose, it needs to be consistent throughout your site and easy for the user to understand.

![[Pasted image 20260616143934.png]]




---



### What Are Best Practices for Designing Infinite Scrolls?

 Infinite scrolling is a design pattern that loads more content as the user scrolls 
 down the page. Oftentimes, this is used on social media sites like Twitter. For 
 example, if you are logged in and want to see more tweets, you can scroll down 
 and more tweets will load.

```js
window.addEventListener('scroll', () => {

if (window.innerHeight + window.scrollY >= document.body.offsetHeight) {

loadMorePosts();

}

});

  

function loadMorePosts() {

const container = document.querySelector('.infinite-scroll');

for (let i = 0; i < 3; i++) {

const post = document.createElement('div');

post.className = 'post';

post.textContent = `Post ${container.children.length + 1}`;

container.appendChild(post);

}

}
```

Infinite scrolling is also used as a substitute for pagination. Pagination is a design pattern that breaks up content into pages. This is often used when there is a lot of content to display. An example of pagination is when you search for something on Google and you see the search results on multiple pages. With pagination, you have to click on a button to go to the next page. With infinite scrolling, you just keep scrolling down and more content will load.

```js
let currentPage = 1;

const postsPerPage = 3;

const totalPosts = 50;

const totalPages = Math.ceil(totalPosts / postsPerPage);

const container = document.querySelector('.pagination');

const prevButton = document.querySelector('.prev');

const nextButton = document.querySelector('.next');

  

function renderPosts() {

container.innerHTML = '';

const start = (currentPage - 1) * postsPerPage;

const end = start + postsPerPage;

for (let i = start; i < end && i < totalPosts; i++) {

const post = document.createElement('div');

post.className = 'post';

post.textContent = `Post ${i + 1}`;

container.appendChild(post);

}

prevButton.disabled = currentPage === 1;

nextButton.disabled = currentPage === totalPages;

}

  

prevButton.addEventListener('click', () => {

if (currentPage > 1) {

currentPage--;

renderPosts();

}

});

  

nextButton.addEventListener('click', () => {

if (currentPage < totalPages) {

currentPage++;

renderPosts();

}

});

  

renderPosts();
```

As you incorporate infinite scrolling into your design, there are a few best practices to keep in mind. The first consideration is to provide a "Load More" button that loads the next set of results when the user clicks on it. This is a good way to give the user control over when they want to see more content.

Another consideration would be to add a "Back" button. This gives users the ability to go back to the previous page without having to scroll all the way back up. This creates a better user experience and gives them more control over their browsing experience.

Sometimes you will see designs with a "Back to the top" button which leads users back to the top of the page of results. Another consideration is to provide a loading indicator. Users should have a clear indication that more content is being loaded; otherwise, they might think that the page is broken.

One of the last considerations would be to keep the footer accessible to the user. If the footer contains important information, then it should be accessible to the user at all times.

In conclusion, infinite scrolling is a great way to display content on your website. However, you should keep in mind the best practices when designing your infinite scroll so that you can provide the best user experience possible.

---



### What Are Best Practices for Designing Modal Dialogs?

What is a modal? It's the type of pop-up that a website might show you on top of their content. HTML has a `dialog` element that you can use to create modals.

The content behind a modal is usually dimmed. This helps the user visually focus on the area you want them to interact with – in this case, the modal.

It's always a good idea to allow the user to click outside of the modal to close it.

![[Pasted image 20260616145304.png]]

```js
const dialog = document.querySelector('dialog');

const closeButton = dialog.querySelector('button:last-of-type');

const openModalButton = document.getElementById('open-modal');

  

closeButton.addEventListener('click', () => {

dialog.close();

});

  

openModalButton.addEventListener('click', () => {

dialog.showModal();

});

  

// Close the modal when clicking outside of it

dialog.addEventListener('click', (event) => {

const rect = dialog.getBoundingClientRect();

const isInDialog = (

event.clientX >= rect.left &&

event.clientX <= rect.right &&

event.clientY >= rect.top &&

event.clientY <= rect.bottom

);

if (!isInDialog) {

dialog.close();

}

});
```

You'll often see very prominent buttons on modals. These are called CTAs, or call-to-action. You want these to be easily identifiable since the purpose of interrupting the user's flow with a modal is to prompt them to take a specific action.

Modals should also have a close button. While you may really want the user to click on your CTAs, it's important to give them an option to back out of the modal and resume whatever they were previously doing.

![[Pasted image 20260616145429.png]]

```css
.cta {

background-color: #007BFF;

color: white;

border: none;

padding: 10px 20px;

border-radius: 4px;

cursor: pointer;

}

  

.close {

background-color: transparent;

color: #007BFF;

border: none;

padding: 10px 20px;

cursor: pointer;

}
```



---



### What Are Best Practices for Progress Indication on Forms, Registration, and Setup?

Progress indication is a way to show users how far they are in a process. It can be used in forms, registration, and setup processes. The goal is to help users understand where they are in the process and how much more they need to do.

For example, you can use a progress indication bar to show users what is left to do when filling forms. You don't want to create a situation where the user needs to fill out a lengthy form and they don't know how many more steps they need to complete. Transparency is key so the user knows whether they have enough time to sit down and complete the form or if they need to come back later.

![[Pasted image 20260616145755.png]]


When designing a progress indication section, there are a few best practices to keep in mind. The first consideration is to keep it simple. You don't want to overwhelm the user with too much information where they get frustrated and leave the site.

The second consideration is to make it possible to go back to previous steps. This is important because users may want to go back and check their previous answers or make changes.

Another consideration is to make the progress indication section easy to find. If the user can't find it, they won't know how far they are in the process.

The last consideration is to have clear section titles, percentages, or steps. If you just have a progress bar with no context, the user won't know what it means.

![[Pasted image 20260616145920.png]]



---



### What Are Best Practices for Designing Shopping Carts?

The first design consideration is making sure the shopping cart is visible to users at all times. Most shopping cart designs will have the cart displayed in the upper right hand corner of the page. Users should see the number of items in their cart displayed next to the cart icon, and be able to click on the cart to see more details about the items they are purchasing.

Another consideration is providing a clear way for users to update the quantity of items in their cart. This can be done by providing a quantity input field next to each item in the cart. Users can easily update the quantity of an item by changing the number in the input field.

You should also provide a "Remove" button next to each item in the cart. This allows users to easily remove items from their cart. You don't want to make it difficult for users to remove items from their cart, as this can lead to frustration and abandoned carts.

Another consideration is the shopping cart icon itself. The icon should be something easily recognizable for all users. A common icon is a shopping cart with a handle and wheels. Other icons might be a shopping bag or a basket. But you don't want to choose an icon that is too abstract or difficult to understand.

When the user wants to review the total in their cart, they should be able to easily find the total cost of all items in the cart. This should be displayed prominently on the page, so users don't have to search for it.

![[Pasted image 20260616154815.png]]

Finally, you should provide a clear call-to-action button for users to proceed to checkout. This button should be prominently displayed on the page, so users don't have to search for it.

You don't want to have too many buttons on the page, as this can lead to confusion. The call-to-action button should be the most prominent button on the page, so users know exactly what to do next. You should use the brand's primary color for the button, so it stands out from the rest of the page.

---



### What Is Progressive Disclosure?

A progressive disclosure is a design pattern used to only show users relevant content based on their current activity and hide the rest. This is done to reduce cognitive load and make the user experience more intuitive.

![[Pasted image 20260616155006.png]]

![[Pasted image 20260616155013.png]]




---



### What Is Deferred and Lazy Registration?

Lazy registration is a UI design pattern that allows users to browse and interact with your application without having to register. A good example of this would be an e-commerce site. Users should be able to browse through the products and add a few items to their cart. Then, if they are interested in purchasing, they will need to register.

The reason is that users need to see the value your site offers before they are willing to provide their information and register. When designing your applications, users should be able to see the value and feel like the application is safe to provide their information. Otherwise, they will not be willing to register and you will lose potential customers.

You will need to make sure to communicate that the user's sensitive data will be protected and secure. In later modules, we will discuss how to secure your application and protect your user's data.

Another good example of lazy registration would be YouTube. YouTube is a video sharing platform with millions of videos on everything from tech, pop culture, and gaming. If you visit YouTube, users can watch as many videos as they like without needing to sign in or register. However, if they want to like, comment, or subscribe to a channel, they will need to register.

If the user likes the content they are watching or wants to participate in the conversations, then they will be more willing to register. Lazy registration is a useful design pattern that allows users to see the value of your application before they are willing to provide their information.

The next time you are designing an application, consider using lazy registration to increase user engagement and retention.

---



## Common Design Tools


### What Are Design Briefs and How Do Developers Work with Them?

When it comes to designing new features or applications, a good first step would be to create a design brief.

A design brief is a document that outlines the objectives, goals, and requirements of a project. It is a roadmap that guides the design process and ensures that the final product meets the needs of the client.

Usually the client will write the design brief and it will serve as a working draft. Sometimes, the designer might write one and consult with the client to make sure it meets their needs.

There are a few key elements that should be included in a design brief.

The first element is the overview of the project and business. This overview should include the company's details, mission, values, unique selling points, and products or services.

The next key element should be to document the goals and objectives for the project. This should include the purpose of the project, and the desired outcomes.

Examples of goals include increasing traffic to a site or increasing the number of monthly page visits by X percent.

Another key element would be the target audience. The design brief should include information about the target demographics, interests, and needs of the audience.

You should also include information about the competition and how the project will differentiate itself from the competition.

Another key element would be the project scope. This should include the deliverables, timeline, and budget. The deliverables should include a list of all the items that will be produced as part of the project, such as mockups, and final designs.

Without clearly defining project scope, things can get out of hand and go over budget. So, it's best to be as detailed as possible about what is expected to be delivered and by when.

One of the challenging aspects about project design is the timescale and budget. It is important to be realistic about what can be achieved within the given timeframe and budget. So, having a design brief that outlines these constraints is important.

Once all of these details have been discussed and documented, the design brief should be reviewed and approved by all stakeholders before the project begins. At that point, the designers can get started with their work.

So, what is the developer's role in all of this? The developer's role is to take the designs, understand the project requirements, and turn them into a working product.

This involves writing code, testing, and debugging the application to ensure that it meets the requirements outlined in the design brief.

Oftentimes, developers will work in teams where the work is split up between multiple developers.

There will also usually be a project manager who will be responsible for coordinating the work and making sure that the project stays on track.

So, while you might not be involved in the design and initial decision-making process as a developer, it is still important to understand the design brief and how it will impact your work.

---



### What Are Some Common Tools Developers Should Know About That Are Used by Designers in the Industry?

Design is the foundation of every enterprise-level web application. That's why designers and developers work closely to create user-focused interfaces that are visually appealing and functional.

Because of this, developers should be familiar with common design tools to make the most of what designers offer. Most of these design tools excel in vector-based design and prototyping.

Vector-based design involves creating digital art using mathematical formulas to define lines, shapes, and colors. Prototyping, on the other hand, refers to the process of creating an interactive model of a product or user interface.

Let's talk about some common design tools developers should know about.

Figma is one of the most common and essential design tools that developers should know. This cloud-based tool specializes in User Interface and User Experience (UI/UX) design. It enables design and development teams to collaborate from anywhere, offering built-in features such as:

- Vector-based design
- Automatic layout
- Commenting and feedback system
- Version history
- Real-time collaboration
- Design systems, and more.

To get started with Figma, you can use the web-based interface or download the desktop app for your computer. It has a generous free tier, so you can get a lot done without paying for the pro version.

Sketch is another essential design tool that developers should be familiar with. Like Figma, it is vector-based and primarily used for UI/UX design.

Sketch is popular for its intuitive interface and simplicity, making it ideal for developers who want to quickly create prototypes. It's also widely used by designers for tasks like creating UIs, icons, and web layouts.

The main constraints with Sketch are its lack of a cloud-based interface and its availability only on macOS.

Adobe XD is another vector-based design and prototyping tool for UI/UX design, known for its seamless integration with other Adobe apps like Photoshop, Illustrator, and After Effects.

This integration makes workflows such as interactive prototyping and animations more efficient.

Adobe XD is available for both Windows and macOS and includes a cloud-based interface. For the best experience, however, you should use the app directly.

Another design tool worth mentioning is Canva. You can use Canva to create a wide range of visual content, including posters, cover photos, presentations, short videos, and more. Its user-friendly and simple design makes it ideal for beginners.

Additionally, Canva offers a rich library of templates, images, and design elements that make it easy to create professional-looking designs.

Beyond these features, Canva supports web interface design and allows for collaboration with teammates. The platform is available on the web, desktop, Android, and iOS app.

Other popular design tools developers should know are Framer, InVision, Adobe Photoshop, Adobe Illustrator, and Miro.

---



# Absolute and Relative Units

## Working with Relative and Absolute Units

### What Are Absolute Units in CSS, and When Should You Use Them? 

There are two types of units you can use to define these properties: relative units and absolute units. 

Absolute length units are of fixed length and are not relative to anything else. Relative means that the length is relative to something else, like the size of the screen or the size of the parent element.

The most common absolute unit is pixel (px). Pixels are a fixed-size unit of measurement in CSS, providing precise control over dimensions. This menas that 1 px is always equal to 1/96th of an inch.

It is important to note that while 1 px is standardized as 1/96th of an inch for the purposes of CSS layout, the actual physical size of a pixel may differ depending on the display.

Generally you will use pixels where you need precise control over element dimensions, spacing, and layout. Sometimes you might use pixels for margins, padding, and borders.

Remember that margin is the space outside of the box. So, in this example, the box will have a margin of `10px` on all sides.

Other types of absolute units include the following:

- The `in` (inches) unit, which is equal to 96 px
- The `cm` (centimeters) unit, which is equal to 25.2/64 of an inch
- The `mm` (millimeters) unit, which is equal to 1/10th of a centimeter
- The `q` (quarter-millimeters) unit, which is equal to 1/40th of a centimeter
- The `pc` (picas) unit, which is equal to 1/6th of an inch
- The `pt` (points) unit, which is equal to 1/72th of an inch

Most of these units will be used for print and not for screens.

---



### What Are Percentages in CSS, and When Should You Use Them?

Percents in CSS are relative units that allow you to define sizes, dimensions, and other properties as a proportion of their parent element. When you use a percentage value, you're essentially saying, "make this X% of its container."

For example, if you set `width: 50%;` on an element, it will occupy half the width of its parent container. This makes percentages incredibly useful for creating responsive designs that adapt to different screen sizes.

![[Pasted image 20260624153142.png]]

Percentages are ideal for creating fluid layouts that adjust to various screen sizes. For instance, setting a container to `width: 80%;` ensures it takes up 80% of its parent's width, regardless of the device.

![[Pasted image 20260624154023.png]]

Using percentages for flexible images is another common practice. By applying `max-width: 100%;` to images, you allow them to scale down on smaller screens while maintaining their aspect ratio.

![[Pasted image 20260624155625.png]]

While less common, percentages can also be used for font sizes to create scalable typography. For example, `font-size: 120%` would make the text 20% larger than its parent's font size.
![[Pasted image 20260624155907.png]]

Percentages can be particulary handy for vertical centering. Here's an example of how you might use percentages with the `transform` property to center an element vertically. 

This example positions the element 50% from the top of its container, then uses `transform` to move it back up by half its own height, effectively centering it vertically.

Remember, percentages are always relative to something. For horizontal properties like `width`, they're relative to the parent's width. For vertical properties like `height`, they're usually relative to the parent's height (if specified).

However, be cautious when nesting elements with percentage-based dimensions, as this can lead to unexpected results. Also, keep in mind that percentage-based heights can be tricky if the parent doesn't have a defined height.

---



### What Are ems and rems in CSS, and When Should You Use Them?

`em` units are relative to the font size of the element. If you are using ems for the `font-size` property, the size of the text will be relative to the font size of the parent element.

To better understand how this works, let's take a look at an example:
![[Pasted image 20260624162624.png]]

For the HTML, we have a paragraph and a `div` element. The paragraph element has a class of `para`, and the `div` element has a class of `blue-box`.

For the `para` class, we set the `font-size` to `20px` and the `margin-bottom` to `1.5em`. This means that the margin will be 1.5 times the font size of the paragraph element. `1.5em` results in 30 pixels of margin at the bottom of the paragraph. We have also set a `border` of `2px solid red` so you can see the margins better.

For the `blue-box` class, we set the background color to `blue`, the text color to `white`, and the `padding` to `10px` on all four sides.

From the example, there'll be a clear space between the bottom of the paragraph element and the blue box.

So what happens if we remove the `font-size` property from the `para` class?

Well, the bottom margin will be relative to the font size of the parent element. In this case, the parent element is the body element, which has a default font size of `16px`.

Good use cases for `em`s would be when you are working with modular components like buttons or cards. By using `em` units, you can ensure that all aspects of the component (such as padding, margin, and borders) scale proportionally with the font size, keeping consistent proportions.

So, up until this point, we have been setting the font size for an element using pixels. But that does present some challenges for users.

Inside your browser settings, you can control the default font size.

For those with visual impairments, they may increase the font size to make it easier to read. But if you are setting pixels for the font sizes in your web designs, the text will not scale proportionally with the rest of the content.

One way to address this issue is to use `rem` units for typography. A `rem` unit is relative to the font size of the root element, which is the `html` element.

By default, the font size of the `html` element is `16px`. If the user increases the font size in their browser settings, the font size of the `html` element will increase, and all rem units will scale proportionally.
![[Pasted image 20260624163524.png]]

By setting the font size to `1.2rem`, the font size of the paragraph element will be 1.2 times the font size of the root element. If the user hasn't changed the default font size, the font size of the paragraph element will be `19.2px` because it is 1.2 times `16px`.

So when should you use `rem` units? `rem` units are preferred over pixels for typography because they scale proportionally with the user's browser settings. This makes your content more accessible to users with visual impairments.

`rem` units can also help maintain consistent spacing and layout across different elements.

---



### What Are vh and vw Units, and When Should You Use Them?

`vh and vw` are viewport-relative units that allow you to size elements based on the dimension of the browser window. These units are particularly useful for creating responsive designs that adapt to different screen sizes. 

`vh` stands for "viewport height," and `1vh` is equal to 1% of the viewport's width.

This means that if you set an element's height to `100vh`, it will occupy the full height of the viewport, regardless of the actual pixel dimensions of the device. 

These units are especially handy when you want to create full-screen layouts or elements that maintain a specific proportion of the screen.

For example, you might want to use them to create a hero section that always fills the entire screen.
![[Pasted image 20260624164353.png]]

This CSS ensures that the hero section will always be exactly the size of the viewport, regardless of the device's screen size.

`vh` and `vw` units can also be used for typography to create responsive text sizes.

One of the advantages of `vh` and `vw` units is that they respond to changes in the viewport size in real-time. This means that if a user resizes their browser window, elements sized with these units will adjust accordingly without needing to reload the page. However, it's important to use these units judiciously. Setting font sizes solely with `vw` units, for example, can lead to text becoming too small on narrow screens or too large on wide screens.

Another consideration is that on mobile devices, the viewport height can change when the browser's address bar appears or disappears, which can cause unexpected layout shifts if you're using `vh` units extensively.

In summary, `vh` and `vw` units are powerful tools for creating responsive layouts and elements that adapt to the viewport size. They're particularly useful for full-screen sections, maintaining aspect ratios, and creating smoothly scaling designs. However, they should be used thoughtfully and often in combination with other CSS techniques to ensure the best user experience across all devices.

---



### What is the calc() Function, and How Does It Work?

With the `calc()` function, you can perform calculations directly within your stylesheets to determine property values dynamically. This means that you can create flexible and responsive user interfaces by calculating dimensions based on the viewport size or other elements.

In the world of programming, when we run the task performed by a function, we say that we "call" the function. The values that we pass into the function are known as arguments.

Like you can see in the code below, to call a function, you write its name followed by the arguments within parentheses, separated by commas. There shouldn't be a space between the name of the function and the opening parenthesis:

```css 
function(argument1, argument2, argument3) 
```

A function may only need one value to know what to do. In that case, it will only take one argument. That's what happens with the `calc()` function. It takes one argument because it needs to know what to calculate.

For this, you pass something called an expression as an argument. An expression is a combination of values and operators that produces a result.

This is how you can call the `calc()` function. You write the name calc, followed by parentheses, and within the parentheses, you write the expression:

```css
calc(expression)
```

The expression is evaluated to calculate the final result. "Evaluated" just means that the values and operators are converted into a single value behind the scenes. The result is assigned to the CSS property where the calculation is being made.

You can perform calculations on values that represent length, angle, time, percentages, numbers, and colors. You can also combine different units like pixels, percentages, and ems.

With numbers, all the values in the expression, also called the operands, must have their corresponding units, like `px`, `em`, and percentage (`%`). Depending on the operator, different operands may have different units.

You can use the addition (`+`), subtraction (`-`), multiplication (`*`), and division (`/`) operators in the expression.

If there are multiple operands and operators, `calc()` will follow the standard operator precedence rule. You can also add parentheses to establish the order of the operations if needed.

In the example below, you can see a `div` with the text `Hello, World!`.

Using the CSS type selector for selecting the `div`, you can style it with white text and a dark blue background:

![[Pasted image 20260624165625.png]]



---


