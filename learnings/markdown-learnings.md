# Markdown Learnings

John Gruber created Markdown and an area of his website is still the original
source of truth for Markdown: https://daringfireball.net/projects/markdown/.
As of July 2018, it listed one download: Markdown 1.0.1 (18 KB) — 17 Dec 2004.

Markdown requires Perl 5.6.0 or later along with a standard Perl library module,
Digest::MD5.

By default, Markdown produces XHTML output which means `<br />` style for tags
without any elements.
To generate HTML4-style `<br>` tags, use the `--html4tags` option.

John Gruber gives these credits:
  * Aaron Swartz deserves a tremendous amount of credit for his feedback on the
    design of Markdown’s formatting syntax.
  * Aaron’s html2text is a very handy (and free) utility for turning HTML into
    Markdown-formatted plain text: http://www.aaronsw.com/2002/html2text/.
  * Nathaniel Irons, Dan Benjamin, Daniel Bogan, and Jason Perkins also deserve
    thanks for their feedback.
  * Michel Fortin ported Markdown to PHP; a splendid port, highly recommended.

## GitHub's Markdown

Getting started with writing and formatting on GitHub<br>
https://help.github.com/articles/markdown-basics<br>
redirects to<br>
https://help.github.com/articles/getting-started-with-writing-and-formatting-on-github/<br>
This page just links to two other pages listed below.

About writing and formatting on GitHub<br>
https://help.github.com/articles/about-writing-and-formatting-on-github/<br>
GitHub extended the original Markdown syntax to create GitHub Flavored Markdown.
GitHub combines GitHub Flavored Markdown with a few unique writing features, e.g.
mentioning people and teams, referencing issues and pull requests, and emoji.

Basic writing and formatting syntax<br>
https://help.github.com/articles/basic-writing-and-formatting-syntax/<br>
This is the reference for the basic syntax of GitHub Flavored Markdown and
GitHub-specific features.

Creating and highlighting code blocks<br>
https://help.github.com/articles/creating-and-highlighting-code-blocks/<br>
This provides a little more detail on the syntax of code blocks.

# Markdown Playground

# Heading 1

## Heading 2

### Heading 3

This is a paragraph that continues on to
the second line.

Backticks are used for `code`.

HTML `<br>` tag is used to add line-break.<br>
Otherwise normal contiguous lines form a single paragraph.

Empty line indicates the end of a paragraph.

Asterisks are used for bulleted lists.  Indenting the list items is optional,
but indenting that looks good in plain-text is certainly allowed.

* Item1
* Item2
* Item3

These are the items written in style that looks nice in plain-text.
  * Item1 is short.
  * Item2
  that goes to the second line.
  * Item3
    that goes on the second line that is indented properly.
