HTML Coding Standards
=====================

HTML Coding Standards you must conform to when writing HTML in Web Marketing ROI projects.

### Tools for simplifying checking HTML coding standards

To make easier the process of checking HTML-based files for validation, we have several tools that check for some but not all of our required coding standards.

These are:

* W3C Validation (https://validator.w3.org/)
* htmlcs (https://github.com/ecomfe/htmlcs with our rule-set https://github.com/webmarketingroi/html-coding-standards/blob/master/wmroi_htmlcsrc)

## Table of contents

- [Write valid HTML](#write-valid-html)
- [Document encoding](#document-encoding)
- [DOCTYPE](#doctype)
- [Do not add unnecessary whitespace](#do-not-add-unnecessary-whitespace)
- [Avoid hacking the language](#avoid-hacking-the-language)
- [Lowercase names](#lowercase-names)
- [Closing tags](#closing-tags)
- [Nested elements](#nested-elements)
- [Attribute values](#attribute-values)
- [Indentation](#indentation)
- [Never use tabs](#never-use-tabs)
- [Avoid putting multiple elements on one line](#avoid-putting-multiple-elements-on-one-line)
- [Double quotation marks](#double-quotation-marks)
- [Do not use multiple stylesheets when one would do](#do-not-use-multiple-stylesheets-when-one-would-do)
- [Always have a META description](#always-have-a-meta-description)
- [Always have a favicon](#always-have-a-favicon)
- [Reducing markup](#reducing-markup)
- [Line endings](#line-endings)
- [Encoding and charset](#encoding-and-charset)
- [Special characters](#special-characters)
- [Images](#images)
- [Images prefixes](#images-prefixes)
- [HTML anchors](#html-anchors)
- [Comments](#comments)
- [Avoid mixing languages](#avoid-mixing-languages)
- [Accessibility](#accessibility)
- [Attaching CSS and JavaScript files](#attaching-css-and-javascript-files)
- [References](#references)
- [License](#license)

## Write valid HTML

All HTML code must be valid and well formed. You must validate it against the HTML specification. Always use HTML5 (unless specifically instructed otherwise). 

The purpose of defining the formatting and style rules (with the usage of ‘coding standards’) is to improve collaboration, code quality and readability. Tools are free to obfuscate, minify, and compile as long as the general code quality is maintained.

With the correct adherence to coding standards, it should be almost indistinguishable which member of the team wrote what part of the code-base – in other words, it should look largely “uniform” and “consistent” in style in all projects. Remember: Working code (or mark-up) is not the same thing as good code.

### Document encoding

Make sure your editor uses UTF-8 as character encoding, without a byte order mark. Specify the encoding in HTML templates and documents via `<meta charset="utf-8">`. Do not specify the encoding of style sheets as these assume UTF-8. [More can be read about this here](https://www.w3.org/International/tutorials/tutorial-char-enc/). Avoid using `<meta http-equiv="Content-Type" content="text/html; charset=UTF-8">` which still technically works but is somewhat obsolete in HTML5.

### DOCTYPE

You must use the HTML5 Document Type Definition. Consider this to be case-sensitive and it should always be the very first line of any HTML document (i.e.: not a line-break or similar).

```html
<!-- Correct -->
<!DOCTYPE html>

<!-- Wrong -->
<!doctype html>
```

This DOCTYPE must always be the first line in the .html file. The following is incorrect:

```html
<!-- Wrong -->

<!DOCTYPE html>
```

We also recommend against capitalising ‘html’. The following (whilst still technically adhering to the HTML specification is bad style):

```html
<!-- Wrong -->
<!DOCTYPE HTML>
```

### Do not add unnecessary whitespace

Avoid adding unnecessary white-space where-ever possible.

```html
<!-- Correct -->
<h3>Privacy Policy</h3>

<!-- Wrong -->
<h3>Privacy Policy </h3>
```

This applies equally to elements such as `strong` as it does `h3`.

```html
<!-- Correct -->
<strong>Use of your personal information</strong>

<!-- Wrong -->
<strong>Use of your personal information </strong>
```

### Avoid hacking the language

Each element has an intended meaning. For example, ‘h1’ is intended to be a ‘top-level heading’. ‘h2’ is intended to be a ‘second level’ heading.

If your second-level heading has been styled to be larger than your top-level heading – you probably need to rethink your approach.

```html
<!-- Wrong -->
<h2>Main Website Headline</h2>

<h3>Bigger Headline</h3>

<!-- Correct -->
<h1>Main Website Headline</h1>

<h2>Second-Level Heading</h2>
```

Another example of "hacking" the language might be using something like `<small>` (which, according to [W3.org](https://www.w3.org/TR/html-markup/small.html#small), is *supposed* to be used for '*[representing] so-called "fine print" or "small print", such as legal disclaimers and caveats*' where the CSS is overwritten so `<small>` is no longer actually small:

```html
<!-- Wrong -->
<h1>Heading Line One<small>Second Heading Line That Is Actually The Same Size</small></h1>
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

Self-closing tags such as `<br />` are XHTML and not HTML5. Do not use them.

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

Use indentation with 2 spaces for code indentation. [Never use tabs](#never-use-tabs).

Use indentation consistently to enhance the readability of the code.

When elements carry over more than one line of code, indent the contents of elements between the start tag and the end tag. This will make it easy to see where the element begins and ends.

Example:

```html
<div class="container">
  <header class="header">
    <h1>Site Name</h1>
  </header>
  
  <nav class="navigation">
  	<ul>
      <li><a href="#">Link</a></li>
      <li><a href="#">Link</a></li>
      <li><a href="#">Link</a></li>
      <li><a href="#">Link</a></li>
      <li><a href="#">Link</a></li>
  	</ul>
  </nav>
</div>
```

## Never use tabs

Never use tabs. A tab could be a different number of columns depending on your environment or text editor, but a space is always one column. Always use spaces instead. This improves readability across a variety of operating systems and text editors.

## Avoid putting multiple elements on one line

In [Google HTML/CSS Style Guide](https://google.github.io/styleguide/htmlcssguide.xml#General_Formatting), Google writes:

>  Use a new line for every block, list, or table element, and indent every such child element.

Putting multiple (especially ‘block-level’) elements on one line is bad form.

```html
<!-- Correct -->
<p>Paragraph 1</p>

<p>Paragraph 2</p>

<!-- Wrong -->
<p>Paragraph 1</p> <p>Paragraph 2</p>
```

```html
<!-- Correct -->
<ul>
  <li>Line item 1</li>
  <li>Line item 2</li>
  <li>Line item 3</li>
</ul>

<!-- Wrong -->
<ul>
  <li>Line item 1</li><li>Line item 2</li>
  <li>Line item 3</li>
</ul>
```

This means that a human being (other programmer/collaborator) can more quickly read what the intended meaning of this code is (two separate paragraphs to be each interpreted individually – most likely with some spacing between them).

## Double quotation marks

Avoid using single quotation marks, electing to always use double quotation marks.

```html
<!-- Correct -->
<link rel=”stylesheet” href=”style.css”>

<!-- Wrong -->
<link rel='stylesheet' href='style.css'>
```

## Do not use multiple stylesheets when one would do

For landing pages, they should always have only a maximum of one style-sheet. For large sites, there could be a case for more than one – but think long and hard before having multiple style-sheets.

```html
<!-- Correct -->
<link rel="stylesheet" href="assets/css/style.css">

<!-- Wrong -->
<link rel="stylesheet" href="assets/css/normalize.css">
<link rel="stylesheet" href="assets/css/global.css">
<link rel="stylesheet" href="assets/css/style.css">
<link rel="stylesheet" href="assets/css/tablet.css">
<link rel="stylesheet" href="assets/css/mobile.css">
```

## Always have a META description

Always include a META description element such as:

```html
<meta name="description" content="...">
```

The contents of the “content” should be between 150 characters and 160 characters.

## Always have a favicon

Always include a ‘favicon’ such as below:

```html
<link rel="shortcut icon” href="favicon.ico">
```

## Reducing markup

As elegantly expressed in [Code Guide by @mdo](http://codeguide.co/#html-reducing-markup):

> Whenever possible, avoid superfluous parent elements when writing HTML. Many times this requires iteration and refactoring, but produces less HTML.

The example provided:

```html
<!-- Not so great -->
<span class="avatar">
  <img src="...">
</span>

<!-- Better -->
<img class="avatar" src="...">
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

Generally, avoid the usage of them altogether. If HTML is well written – in most cases, HTML comments are unnecessary (since well-written HTML is typically easy to read).

If you find yourself wanting to add HTML comments – ask yourself whether they are absolutely necessary and generally avoid.

In exceptional cases where you think they may benefit readability or comprehensive of a code-block, use them, but make to always follow the format of `<!-- Clear comment -->` on a separate line preceding the difficult to understand HTML.

## Avoid mixing languages

Including a server-side language like PHP into your HTML files or vice versa tends to get messy fast. Don't do it. By doing so, it makes maintainability of the HTML more difficult for front-end developers who do not have server-side programming experience. It also hurts readability and often has an unnecessary (obfuscation)[https://en.wikipedia.org/wiki/Obfuscation] effect.

It may "seem" and feel like it's easier than simply putting the same HTML in a few different files, but it's actually an anti-pattern and something to avoid. It is a poor 'seperation of concerns' and anti-pattern.

MVC-based frameworks are one thing, but don't do this things like:

````html
<!-- Some HTML -->
<?php if (!empty($SIMPLE_MODAL_SCRIPT) && isset($SIMPLE_MODAL_SCRIPT)){ ?><script src="<?=$SIMPLE_MODAL_SCRIPT?>" type="text/javascript"></script><? } ?>
<!-- Some HTML -->
````

... or ...

````html
<!-- Some HTML -->
<?php
if (preg_match("/some-url-pattern/i", $_SERVER['REQUEST_URI'])) {
    $select_display = "style='display:none;'";
    $is_show = false;
} else {
    $select_display = "";
    $is_show = true;
}
?>
<!-- Some HTML -->
````

Both of these cases could have been written equally well in pure HTML without the unnecessary usage of server-side PHP. In the case of the JavaScript-based include - why not simply have that line appear in .html files where that JavaScript file is included? Unless you have, maybe, thousands of pages - maintainability of this should not be an issue (and it is then easy to remove it on pages where it is not required if you are, for example, optimising the load speed of a particular page or similar).

If you *do* have thousands of pages, instead - ask yourself - shouldn't I be using some sort of content management system or MVC framework here?

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

## References

* Google HTML/CSS Style Guide (https://google.github.io/styleguide/htmlcssguide.xml)
* RFC2119 (https://tools.ietf.org/html/rfc2119) – Used to clearly define the usage of the
words ‘MUST’, ‘MUST NOT’, ‘SHOULD’ and ‘SHOULD NOT’.
* Code Guide by @mdo (http://codeguide.co/)
* Web Marketing ROI’s htmlcs ruleset (https://github.com/webmarketingroi/html-coding-standards/blob/master/wmroi_htmlcsrc)

## License

[![](http://i.creativecommons.org/l/by/4.0/88x31.png)](http://creativecommons.org/licenses/by/4.0/)

This work is licensed under a [Creative Commons Attribution 4.0 International License](http://creativecommons.org/licenses/by/4.0/).
