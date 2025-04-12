# PyHTML Enhanced

PyHTML Enhanced is a library for generating HTML documents using a simple and learnable syntax. It is inspired by (and similar to) [Cenk Altı's PyHTML library](https://github.com/cenkalti/pyhtml), but with improved documentation and type safety.

The library has been used by hundreds of students in
[UNSW's COMP1010 course](https://www.handbook.unsw.edu.au/undergraduate/courses/2024/COMP1010), allowing them to create advanced and dynamic websites in Python.

## Key features

* An [online demo](https://comp1010unsw.github.io/pyhtml-demo/) built using Svelte and Pyodide.
* Full IDE support, including type-safety and documentation for all HTML tags, meaning that the library is accessible and intuitive, even for students with no prior programming experience.
* Protection against XSS attacks, with all string content being escaped.
* Many advanced features to allow students to extend their knowledge further.

## Technical details

To make maintenance simple, the library relies heavily on programmatically-generated code for the HTML tags. The list of all current HTML tags, as well as their corresponding documentation is pulled from the Mozilla MDN web documentation, ensuring that the library stays up-to-date with modern web standards.

## Using PyHTML

```py
>>> import pyhtml as p
>>> my_website = p.html(
...     p.head(
...         p.title("Hello, world!"),
...         p.script(src="http://example.com/script.js"),
...     ),
...     p.body(
...         p.h1("Hello, world!"),
...         p.p("This is my amazing website!"),
...     ),
... )
>>> print(str(my_website))
```

This produces the output:

```html
<!DOCTYPE html>
<html>
  <head>
    <title>
      Hello, world!
    </title>
    <script type="text/javascript" src="http://example.com/script.js"></script>
  </head>
  <body>
    <h1>
      Hello, world!
    </h1>
    <p>
      This is my amazing website!
    </p>
  </body>
</html>
```

