

# Variables and Strings

## Working with Data Types

### What Is Dynamic Typing in JavaScript, and How Does It Differ from Statically Typed Languages?

JavaScript is a dynamically typed language, meaning you don't need to specify the data type of a variable when you declare it. Instead, the type is determined based on the value assigned to the variable while the program is running. This allows you to change the type of a variable throughout the program.

An example:

![[Pasted image 20260525192434.png]]

The flexibility of dynamic typing makes JavaScript more forgiving and easy to work with for quick scripting, but it can also introduce bugs that may be harder to catch, especially as your program grows larger.

In conclusion, JavaScript's dynamic typing allows variables to change types freely, which offers flexibility but can lead to unexpected errors during execution.

Statically typed languages like [[1.a - Java]] require you to specify variable types upfront, which helps catch errors before the program runs but offers less flexibility.

---



### How Does the typeof Operator Work, and What Is the typeof null Bug in JavaScript?

The `typeof` operator in JavaScript is a simple yet powerful tool that lets you see the data type of a variable or value. It always returns a string indicating the type.

![[Pasted image 20260525193156.png]]

Using the `typeof` operator can be especially useful when you're debugging or trying to understand what kind of data you're working with in your code.

However, there's a well-known quirk in JavaScript when it comes to `null`.

![[Pasted image 20260525193416.png]]

In this example, we have a variable called `exampleVariable` and have assigned it the value of `null`. But when we use the `typeof` operator, it returns the string `object`.

This is widely considered a bug in JavaScript, dating back to its early days. The reason for this behavior is rooted in the way JavaScript was originally designed.

When the language was first implemented, values like `null` were represented as a special type of object, leading to this unexpected result.

Unfortunately, this has become a part of the language, and while it's confusing, it's something you'll need to be aware of.

---



# Booleans and Numbers

.