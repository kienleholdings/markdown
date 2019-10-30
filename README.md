# Markdown Style Guide

> A Bullshit-Free Approach to Markdown

## Table of Contents

1. [Headings](#headings)

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

# Another Heading

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

**[:arrow_up: Back to Top](#table-of-contents)**
