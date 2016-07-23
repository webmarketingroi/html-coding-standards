HTML Coding Standards
=====================

HTML Coding Standards you must conform to when writing HTML in Web Marketing ROI projects.

## Table of contents

- [Write valid HTML](#write-valid-html)
- [DOCTYPE](#doctype)
- [Indentation](#indentation)
- [Line endings](#line-endings)
- [Encoding and charset](#encoding-and-charset)
- [Special characters](#special-characters)
- [Images](#images)
- [Images prefixes](#images-prefixes)
- [HTML anchors](#html-anchors)
- [Comments](#comments)
- [Accessibility](#accessibility)
- [Attaching CSS and JavaScript files](#attaching-css-and-javascript-files)
- [License](#license)

## Write valid HTML

All HTML code must be valid and well formed. You must validate it against the HTML specification. Always use HTML5 (unless specifically instructed otherwise). 

The purpose of defining the formatting and style rules (with the usage of ‘coding standards’) is to improve collaboration, code quality and readability. Tools are free to obfuscate, minify, and compile as long as the general code quality is maintained.

With the correct adherence to coding standards, it should be almost indistinguishable which member of the team wrote what part of the code-base – in other words, it should look largely “uniform” and “consistent” in style in all projects. Remember: Working code (or mark-up) is not the same thing as good code.

### DOCTYPE

You must use the HTML5 Document Type Definition. Consider this to be case-sensitive and it should always be the very first line of any HTML document (i.e.: not a line-break or similar).

```html
<!-- Correct -->
<!DOCTYPE html>

<!-- Wrong -->
<!doctype html>
```

### Lowercase names

Element and attribute names must be in all lower case:


```html
<!-- Correct -->
<input name="name" type="text">

<!-- Wrong -->
<input name="name" TYPE="text">
```

### Closing tags

Non-empty elements must have corresponding closing tags.

```html
<h1>My title</h1>
<p>Some text</p>
```

Elements with a single tag, such as `<hr>`, `<br>`, `<input>` and `<img>` must end with `>`:

```html
<br>
<hr>
<img src="john.jpg" alt="John Doe">
```

### Nested elements

Nested elements must be nested appropriately - for example:

```html
<!-- Correct -->
<div>
  <p>Some text</p>
</div>
```

The `<p>` tag and its corresponding closing tag, `</p>`, are both nested inside the `<div>` and `</div>` tags.

If elements overlap they are not properly nested. This is illustrated in the following code:

```html
<!-- Wrong -->
<div>
  <p>Some text</div>
</p>
```

### Attribute values

Attribute values, even numeric attributes should be quoted—for example:

```html
<!-- Correct -->
<input name="age" type="text" size="3">

<!-- Wrong -->
<input name=age type=text size=3>
```

## Indentation

Use indentation with 2 spaces for code indentation. Do not use tabs.

Use indentation consistently to enhance the readability of the code.

When elements carry over more than one line of code, indent the contents of elements between the start tag and the end tag. This will make it easy to see where the element begins and ends.

Example:

```html
<div class="container">
  <header class="header">
    <h1>Site Name<span></span></h1>
  </header>
  <!-- / header -->
  <hr>
  <nav class="navigation">
  	<ul>
      <li><a href="#">Link</a></li>
      <li><a href="#">Link</a></li>
      <li><a href="#">Link</a></li>
      <li><a href="#">Link</a></li>
      <li><a href="#">Link</a></li>
  	</ul>
  </nav>
  <!-- / navigation -->
</div>
<!-- / container -->
```

## Line endings

Format files with \n as the line ending (Unix line endings). Do not use \r\n (Windows line endings) or \r (Apple OS's). 

## Encoding and charset

Set encoding of HTML document and its charset to UTF-8 Normalization Form C (NFC):

```html
<meta charset="utf-8">
```

## Special characters

Encode special characters, for example:

```html
&amp;
&copy;
&raquo;
&gt;
```

## HTML anchors

When you need to link to the section inside a HTML document use ID attribute:

```html
<a href="#section">link</a>
<div id="section"></div>
```

If it isn't possible to use IDs (for example because of ASP.NET platform), use a named anchor:

```html
<a href="#section">link</a>
<a name="section"></a>
```

## Comments

Insert ending comment after closing tag of the HTML section in this format:

```html
<!-- / name-of-class-or-id -->
```

Do not use starting comment.

Examples:

```html
<ol class="accessibility-nav">
  <li><a href="#navigation">Skip to navigation</a></li>
  <li><a href="#content">Skip to content</a></li>
  <li><a href="#sidebar">Skip to sidebar</a></li>
</ol>
<!-- / accessibility-nav -->
 
<p>
  <a href="#" title="Go to homepage"><em>Home</em></a>
</p>
<!-- / breadcrumb -->
```

## Accessibility

Adhere to basic accessibility principles when writing HTML.

### General

- Use h1 - h6 to identify headings - [Read more &raquo;](http://www.w3.org/TR/2008/NOTE-WCAG20-TECHS-20081211/html.html#H4)
- Use structural elements to group links - [Read more &raquo;](http://www.w3.org/TR/2008/NOTE-WCAG20-TECHS-20081211/html.html#H50)
- Provide definitions for abbreviations by using the abbr and acronym elements - [Read more &raquo;](http://www.w3.org/TR/2008/NOTE-WCAG20-TECHS-20081211/html.html#H28)
- Use language attributes on html element to identify the default language of a document - [Read more &raquo;](http://www.w3.org/TR/2008/NOTE-WCAG20-TECHS-20081211/html.html#H57)


### Tables

- Use table markup to present tabular information - [Read more &raquo;](http://www.w3.org/TR/2008/NOTE-WCAG20-TECHS-20081211/html.html#H51)
- Use the scope attribute to associate header cells and data cells in data tables - [Read more &raquo;](http://www.w3.org/TR/2008/NOTE-WCAG20-TECHS-20081211/html.html#H63)
- Use the summary attribute of the table element to give an overview of data tables - [Read more &raquo;](http://www.w3.org/TR/2008/NOTE-WCAG20-TECHS-20081211/html.html#H73)

### Forms

- Provide submit buttons - [Read more &raquo;](http://www.w3.org/TR/2008/NOTE-WCAG20-TECHS-20081211/html.html#H32)
- Use alt attributes on images used as submit buttons - [Read more &raquo;](http://www.w3.org/TR/2008/NOTE-WCAG20-TECHS-20081211/html.html#H36)
- Use label elements to associate text labels with form controls - [Read more &raquo;](http://www.w3.org/TR/2008/NOTE-WCAG20-TECHS-20081211/html.html#H44)
- Use the title attribute to identify form controls when the label element cannot be used - [Read more &raquo;](http://www.w3.org/TR/2008/NOTE-WCAG20-TECHS-20081211/html.html#H65)
- Indicate required form controls - [Read more &raquo;](http://www.w3.org/TR/2008/NOTE-WCAG20-TECHS-20081211/html.html#H90)

### Images

- Use alt attributes on img elements - [Read more &raquo;](http://www.w3.org/TR/2008/NOTE-WCAG20-TECHS-20081211/html.html#H37)
- Use null alt text and no title attribute on img elements for images that Assistive Technology should ignore - [Read more &raquo;](http://www.w3.org/TR/2008/NOTE-WCAG20-TECHS-20081211/html.html#H67)

## License

[![](http://i.creativecommons.org/l/by/4.0/88x31.png)](http://creativecommons.org/licenses/by/4.0/)

This work is licensed under a [Creative Commons Attribution 4.0 International License](http://creativecommons.org/licenses/by/4.0/).
