# Markdown Style Guide

> A Bullshit-Free Approach to Markdown

## Table of Contents

1. [Accessibility](#accessibility)
1. [Headings](#headings)

## Accessibility

### Images

Images should have an alt tag that accurately describes the content of the image.
([`no-alt-text`](https://github.com/DavidAnson/markdownlint/blob/HEAD/doc/Rules.md#md045))

> **Why?** For users that have trouble seeing and use a screen reader, images must have alt tags in
> order to accommodate for those users.

<!-- prettier-ignore-start -->
```markdown
<!-- Good -->
![Alternate text](image.jpg)
<!-- Bad -->
![](image.jpg)
```
<!-- prettier-ignore-end -->

## Code Blocks

### Language

Code blocks should be marked with their appropriate language.
([`fenced-code-language`](https://github.com/DavidAnson/markdownlint/blob/HEAD/doc/Rules.md#md040),
[`proper-names`](https://github.com/DavidAnson/markdownlint/blob/HEAD/doc/Rules.md#md044))

> **Why?** For proper syntax highlighting the language should be specified in each code block.

<!-- prettier-ignore-start -->
````markdown
<!-- Good -->
```markdown
```

<!-- Bad -->
```
```
````
<!-- prettier-ignore-end -->

### Style

Code blocks should be written with the fenced style (```) rather than the indented style, and have
blank lines around the block.
([`code-block-style`](https://github.com/DavidAnson/markdownlint/blob/HEAD/doc/Rules.md#md046),
[`blanks-around-fences`](https://github.com/DavidAnson/markdownlint/blob/HEAD/doc/Rules.md#md031))

> **Why?** You already (in theory) have spaces and tabs in your code. We think it makes more sense
> to not add any additional tabbing in, as that can mess up copy / pasting.

<!-- prettier-ignore-start -->

````markdown
<!-- Good -->
```JavaScript
console.log('Hi, this is JavScript!);
```

<!-- Bad -->
    # Some markdown code


# Some content
```JavaScript
console.log('Hi, this is JavScript!);
```
## Some more content
<!-- prettier-ignore-end -->
````

## Document

### End of File

Every file should end with a blank line.
([`single-trailing-newline`](https://github.com/DavidAnson/markdownlint/blob/HEAD/doc/Rules.md#md047))

> **Why?** It makes your Git diffs look a lot nicer, and keeps compatibility for some older tools.

<!-- prettier-ignore-start -->
```markdown
<!-- Good -->
The last line before the end of file

End of the file

<!-- Bad -->
The last line before the end of file
End of the file
```
<!-- prettier-ignore-end -->

### Inline HTML

Besides comments, there should be no inline HTML in your markdown document.

**Why?** Some markdown renderers don't support HTML.
([`no-inline-html`](https://github.com/DavidAnson/markdownlint/blob/HEAD/doc/Rules.md#md033))

<!-- prettier-ignore-start -->
````markdown
<!-- Good -->
```html
<h1>This is some html</h1>
```

<!-- Bad -->
<h1>This is some html</h1>
````
<!-- prettier-ignore-end -->

### Line Length

Lines should have a maximum length of 100 characters.
([`line-length`](https://github.com/DavidAnson/markdownlint/blob/HEAD/doc/Rules.md#md013))

> **Why?** As monitors become higher resolution, an 80 character "standard" limit is becoming
> obsolete. We think that 100 is plenty, and doesn't mess up your file's formatting too much.

<!-- markdownlint-disable line-length -->
<!-- prettier-ignore-start -->
```markdown
<!-- Good -->
Lorem ipsum dolor sit amet, consectetur adipiscing elit. Duis a nisl venenatis, maximus lorem ac,
sodales ipsum posuere.

<!-- Bad -->
Lorem ipsum dolor sit amet, consectetur adipiscing elit. Duis a nisl venenatis, maximus lorem ac, sodales ipsum posuere.
```
<!-- prettier-ignore-end -->

<!-- markdownlint-enable line-length -->

### Tabbing

Documents should only use spaces, not tabs.
([`no-hard-tabs`](https://github.com/DavidAnson/markdownlint/blob/HEAD/doc/Rules.md#md010))

> **Why?** Kienle Holdings decided on spaces over tabs for our entire codebase. This is 100%
> opinion-based.

<!-- markdownlint-disable no-hard-tabs -->
<!-- prettier-ignore-start -->
```markdown
<!-- Good -->
  * This list starts with a space

<!-- Bad -->
	* This list starts with a tab
```
<!-- prettier-ignore-end -->

<!-- markdownlint-enable no-hard-tabs -->

## Headings

### Content

Headers cannot have the same content as another header if they're on the same hierarchal level in
the document.
([`no-duplicate-heading`](https://github.com/DavidAnson/markdownlint/blob/HEAD/doc/Rules.md#md024),
[`siblings_only`](https://github.com/DavidAnson/markdownlint/blob/HEAD/doc/Rules.md#md024))

> **Why?** Headings on the same level with the same name can realistically be combined under one
> heading. In cases such as change logs, you may want to reuse headers, thus allowing them to be the
> same if they're on a different level.

<!-- prettier-ignore-start -->
```markdown
<!-- Good -->
# Heading
## Sub header
### Another Heading
## Sub header

<!-- Bad -->
# Heading
## Sub header
# Heading
## Sub header
```
<!-- prettier-ignore-end -->

### Hierarchy

Headings should always be in order (i.e. no h3 right after a h1, or h4 after a h6). Additionally,
there should be no more than one h1 per document.
([`required-headings`](https://github.com/DavidAnson/markdownlint/blob/HEAD/doc/Rules.md#md043),
[`heading-increment`](https://github.com/DavidAnson/markdownlint/blob/HEAD/doc/Rules.md#md001),
[`single-title`](https://github.com/DavidAnson/markdownlint/blob/HEAD/doc/Rules.md#md025))

> **Why?** For automatic documentation systems that use heading navigation, it's important that
> everything is in the right order.

<!-- prettier-ignore-start -->
```markdown
<!-- Good -->
# Heading 1
## Heading 2

<!-- Bad -->
# Heading 1
### Heading 3
```
<!-- prettier-ignore-end -->

### Position

Headings should always start on the left.
([`heading-start-left`](https://github.com/DavidAnson/markdownlint/blob/HEAD/doc/Rules.md#md023))

> **Why?** Headings that don't start on the left won't be parsed as headings by Markdown.

<!-- prettier-ignore-start -->
```markdown
<!-- Good -->
# Heading

<!-- Bad -->
  # Incorrect Heading
```
<!-- prettier-ignore-end -->

### Style

Headings should be written only in open ATX style, not closed ATX or Setext. Additionally, headings
should have one space between the heading definition and the text, as well as surrounded by a blank
line on each side
([`heading-style`](https://github.com/DavidAnson/markdownlint/blob/HEAD/doc/Rules.md#md001),
[`no-missing-space-atx`](https://github.com/DavidAnson/markdownlint/blob/HEAD/doc/Rules.md#md018),
[`no-multiple-space-atx`](https://github.com/DavidAnson/markdownlint/blob/HEAD/doc/Rules.md#md019),
[`blanks-around-headings`](https://github.com/DavidAnson/markdownlint/blob/HEAD/doc/Rules.md#md022))

> **Why?** We think that ATX is more verbose and easier to maintain than Setext. Other stylistic
> rules are also used to ensure that headings are rendered correctly.

<!-- prettier-ignore-start -->
```markdown
<!-- Good -->
# Heading
## Another heading

<!-- Bad -->
# Incorrect Heading #
Another Incorrect Heading
=========================
##  An incorrect heading in ATX
#Nope, not a valid header
There should be a space between this and the heading
## A correct heading
There should be a space between this and the heading
```
<!-- prettier-ignore-end -->

## Hyperlinks

### Content

Links should always point to a valid URL or heading.
([`no-empty-links`](https://github.com/DavidAnson/markdownlint/blob/HEAD/doc/Rules.md#md042))

> **Why?** Clicking on a link and not having it go anywhere breaks the user's expectation of how
> links work.

<!-- prettier-ignore-start -->
```markdown
<!-- Good -->
[Kienle Holdings](https://kienle.holdings)
[Some Fragment](#fragment)

<!-- Bad -->
[An empty link]()
[An empty fragment](#)
```
<!-- prettier-ignore-end -->

### Style

Links should only be enclosed in properly formatted link elements, and never in plain text.
([`no-bare-urls`](https://github.com/DavidAnson/markdownlint/blob/HEAD/doc/Rules.md#md034),
[`no-space-in-links`](https://github.com/DavidAnson/markdownlint/blob/HEAD/doc/Rules.md#md039),
[`no-reversed-links`](https://github.com/DavidAnson/markdownlint/blob/HEAD/doc/Rules.md#md011))

> **Why?** Depending on what parser the user is using to read Markdown, plain text links may not be
> clickable. Wrapping your links in the appropriate tag ensures that they function as expected,
> regardless of what software the end user is using. Additionally, if your link is formatted
> incorrectly, the markdown parser might not interpret it as expected.

<!-- prettier-ignore-start -->
```markdown
<!-- Good -->

[Kienle Holdings](https://kienle.holdings)
<https://kienle.holdings>

<!-- Bad -->
https://kienle.holdings
(https://kienle.holdings)[Kienle Holdings]
[ Kienle Holdings ](https://kienle.holdings)
```
<!-- prettier-ignore-end -->
