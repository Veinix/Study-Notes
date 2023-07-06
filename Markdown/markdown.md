# Markdown Notes

## What is markdown?

Markdown is a lightweight markup language for creating formatted text using a plain-text editor. John Gruber created Markdown in 2004 as a markup language that is appealing to human readers in its source code form. Markdown is widely used in blogging, instant messaging, online forums, collaborative software, documentation pages, and readme files.

The initial description of Markdown contained ambiguities and raised unanswered questions, causing implementations to both intentionally and accidentally diverge from the original version. This was addressed in 2014, when long-standing Markdown contributors released CommonMark, an unambiguous specification and test suite for Markdown.

Its key design goal was readability, that the language be readable as-is, without looking like it has been marked up with tags or formatting instructions, unlike text formatted with 'heavier' markup languages, such as Rich Text Format (RTF), HTML, or even wikitext (each of which have obvious in-line tags and formatting instructions which can make the text more difficult for humans to read). [^1]  

[Sources and More info](#sources)

---

## Topics

* [Standardization and Variants](#standardization-and-variants)

* [Basic Syntax](#basic-syntax)  

* [Extended Syntax](#extended-syntax)  

* [Custom Styling](#custom-styling)

---

## Standardization and Variants

There have been many attempts to standardize Markdown.

![xkcd 927](https://imgs.xkcd.com/comics/standards.png)

This document follows CommonMark's spec [^2] [^3]  by using the markdownlint extension [^4]  

Websites like Bitbucket, Diaspora, GitHub, OpenStreetMap, Reddit, SourceForge, and Stack Exchange use variants of Markdown to facilitate discussion between users.

Depending on implementation, basic inline HTML tags may be supported. For example: Italic text may be implemented by `_underscores_` and/or `*single-asterisks*`.

You can read about the different variants in the wikipedia page

---

## Basic Syntax  

Nearly all Markdown applications support the basic syntax outlined in the original Markdown design document. There are minor variations and discrepancies between Markdown processors — those are noted inline wherever possible.[^5]  

* [Heading](#heading)

* [Bold](#bold)

* [Italic](#italic)

* [Blockquote](#blockquote)

* [Ordered List](#ordered-list)

* [Unordered List](#unordered-list)

* [Code](#code)

* [Horizontal Rule](#horizontal-rule)

* [Link](#link)

* [Image](#image)  

### Heading

**Markdown** | **HTML** |
---------|----------|---------
 ``# Heading level 1`` | ``<h1>Heading level 1</h1>``
 ``## Heading level 2`` | ``<h2>Heading level 1</h2>``
 ``### Heading level 3`` | ``<h3>Heading level 1</h3>``
 ``#### Heading level 4`` | ``<h4>Heading level 1</h4>``
 ``##### Heading level 5`` | ``<h5>Heading level 1</h5>``
 ``###### Heading level 6`` | ``<h6>Heading level 1</h6>``
 ``####### Heading level 7`` | ``<h7>Heading level 1</h7>``

### Bold

### Italic

### Blockquote

### Ordered List

### Unordered List

### Code

### Horizontal Rule

### Link

### Image

## Extended Syntax

These elements extend the basic syntax by adding additional features. Not all Markdown applications support extended syntax elements. You’ll need to check whether or not the lightweight markup language your application is using supports the extended syntax elements you want to use. If it doesn’t, it may still be possible to enable extensions in your Markdown processor. [^6]

* Table

* Fenced Code Block

* Footnote

* Heading ID

* Definition List

* Strikethrough

* Task List

* Emoji

* Highlight

* Subscript

* Superscript

### Admonition

Nesting supported (by indent) admonition, the following shows a danger admonition nested by a note admonition.

!!! note Note

    This is the **note** admonition body

    !!! danger Danger Title

        This is the **danger** admonition body

## Custom Styling

---

## Sources

[Markdown Guide - MD Cheat Sheet](https://www.markdownguide.org/cheat-sheet/)

[VSCode Docs - Markdown](https://vscode-docs.readthedocs.io/en/latest/languages/markdown/)

[Visual Studio Code Docs - Markdown](https://code.visualstudio.com/docs/languages/markdown)

[Github - Writing with Markdown](https://docs.github.com/en/get-started/writing-on-github/getting-started-with-writing-and-formatting-on-github/quickstart-for-writing-on-github)

[^1]: ["Markdown".](https://en.wikipedia.org/wiki/Markdown) Wikipedia

[^2]: ["CommonMark Spec".](https://spec.commonmark.org/) CommonMark

[^3]: ["CommonMark".](https://commonmark.org/) CommonMark

[^4]: Anson, David [markdownlint repo.](https://github.com/DavidAnson/markdownlint) Github

[^5]: ["Basic Syntax"](https://www.markdownguide.org/basic-syntax) Markdown Guide

[^6]: ["Extended Syntax"](https://www.markdownguide.org/extended-syntax/) Markdown Guide
