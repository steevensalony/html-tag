# Matching HTML Tag

This is a tutorial that shows how to use regular expressions for matching HTML tags. This tutorial will show how each regex component of an HTML tag are used. 

## Summary

Regualar expressions (regex) can be used to match and manipulate HTML tags.

Here is an example code for an HTML Tag:

`/^<([a-z]+)([^<]+)*(?:>(.*)<\/\1>|\s+\/>)$/`

## Table of Contents

- [Matching HTML Tag](#matching-html-tag)
  - [Summary](#summary)
  - [Table of Contents](#table-of-contents)
  - [Regex Components](#regex-components)
    - [Anchors](#anchors)
    - [Quantifiers](#quantifiers)
    - [OR Operator](#or-operator)
    - [Character Classes](#character-classes)
    - [Flags](#flags)
    - [Grouping and Capturing](#grouping-and-capturing)
  - [Author](#author)

## Regex Components

### Anchors

Anchors in regex are used to match specific positions within a string. In the context of HTML tags, you can use anchors to match tags based on their position within the string. There are a couple common ones:

Start of Line Anchor `^`, This anchor matches the start of a line. In the case of HTML tags, you can use it to match tags that appear at the beginning of a line or the start of the HTML document. For example, `^<p>` would match a `<p>` tag that appears at the start of a line.

End of Line Anchor `$`, This anchor matches the end of a line. It can be used to match tags that appear at the end of a line or the end of the HTML document. For example, `</p>$` would match a closing `</p>` tag that appears at the end of a line.

Here’s an example that combines both anchors to match a paragraph tag that appears at the beginning of a line and ends at the end of the same line: `^<p>.*<\/p>$`.

### Quantifiers

Quantifiers in regex are used to specify the number of times a preceding element should occur. In the context of HTML tags, quantifiers can be useful for matching tags with varying numbers of attributes or content. Some examples would include:

Asterisk `*`, This quantifier matches zero or more occurrences of the preceding element. For example, `<a.*>` would match `<a>`.

Plus `+`, This quantifier matches one or more occurrences of the preceding element. For example, `<h1>.+</h1>` would match `<h1>Heading</h1>`.

Question mark `?`, This quantifier matches zero or one occurrence of the preceding element. For example, `<img src=".+?" />` would match `<img src="image.jpg" />` or `<img />`.

Curly braces `{n}`, This quantifier matches exactly n occurrences of the preceding element. For example, `<td colspan="{2}">` would match `<td colspan="2">`.

### OR Operator

The OR operator in regex allows you to match either one pattern or another. In the context of HTML tags, the OR operator can be useful when you want to match multiple tags or variations of a tag. Here’s how you can use the OR operator in regex:

Pipe symbol `|`, The pipe symbol acts as the OR operator in regex. It allows you to specify alternative patterns. For example, `<h1|h2>` would match either `<h1>` or `<h2>` tags.

### Character Classes

Character classes in regex allow you to specify a set of characters that you want to match. In the context of HTML tags, character classes can be used to match specific tag names or attributes.

To match specific tag names, you can use a character class with the desired letters. For example, `[a-zA-Z]+` would match one or more lowercase or uppercase letters, allowing you to match tag names like `<div>`, `<p>`, `<span>`, etc.

### Flags

Flags in regex are optional modifiers that can be added to the pattern to change the behavior of the regular expression matching. In the context of HTML tags, flags can be used to make the regex case-insensitive or to match across multiple lines. Here are two commonly used flags in regex:

Case Insensitive Flag `(i)`: The `i` flag makes the pattern case-insensitive, allowing it to match both uppercase and lowercase characters. For example, `/pattern/i` would match `<div>`, `<DIV>`, `<Div>`, and so on.

Multiline Flag `(m)`: The `m` flag allows the pattern to match across multiple lines. This is useful when dealing with HTML that spans multiple lines. For example, `/<p>.+<\/p>/m` would match `<p>Content</p>` even if it’s on separate lines.

### Grouping and Capturing

Grouping and capturing in regex allow you to group parts of a pattern together and capture the matched content for further use. In the context of HTML tags, grouping and capturing can be used to extract specific parts of a tag or to apply operations to specific portions of the tag. Here’s how you can use grouping and capturing in regex for HTML tags:

Parentheses for Grouping: You can use parentheses `()` to group parts of a pattern together. For example, `(<a href=".+">)` would match the opening `<a>` tag with its href attribute.

Capturing Groups: When using parentheses, the content matched by the grouped pattern is captured and can be referred to later. These captured groups are assigned a number, starting from 1. For example, `(<a href=".+">)(.+)(<\/a>)` would capture the entire `<a>` tag in group 1, the content between the opening and closing tags in group 2, and the closing `</a>` tag in group 3.


## Author

This was written by [Steeven](https://github.com/steevensalony)
