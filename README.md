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

> **Why?** Headings on the same level with the same name can realistically be combined under one
> heading. In cases such as change logs, you may want to reuse headers, thus allowing them to be the
> same if they're on a different level.

### Hierarchy

Headings should always be in order (i.e. no h3 right after a h1, or h4 after a h6).
([`required-headings`](https://github.com/DavidAnson/markdownlint/blob/HEAD/doc/Rules.md#md043))

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

Headings should be written only in open ATX style, not closed ATX or Setext.
([`heading-style`](https://github.com/DavidAnson/markdownlint/blob/HEAD/doc/Rules.md#md001))

> **Why?** We think that ATX is more verbose and easier to maintain than Setext.

<!-- prettier-ignore-start -->
```markdown
<!-- Good -->
# Heading

<!-- Bad -->
# Incorrect Heading #

Another Incorrect Heading
=========================
```
<!-- prettier-ignore-end -->

---

**[:arrow_up: Back to Top](#table-of-contents)**
