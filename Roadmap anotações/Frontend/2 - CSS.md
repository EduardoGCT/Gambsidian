
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
2. **Source Order (The Last Resort):** If the specificity scores are completely identical, the rule that appears **last (closest to the bottom)** in the CSS processing order wins and overrides previous declarations.
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


