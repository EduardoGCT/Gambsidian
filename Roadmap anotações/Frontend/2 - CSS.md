
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



---


