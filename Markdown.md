## Markdown Cheatsheet

### Headings
```
# H1
## H2
### H3
#### H4
##### H5
###### H6
```

### Emphasis
```
*italic* or _italic_
**bold**
***bold italic***
~~strikethrough~~
```

### Paragraphs & Line Breaks
```
Line one

Line two (blank line = new paragraph)
Line with break<br>Next line (HTML <br> for hard break)
```

### Lists
- Unordered
```
- Item
* Item
- Item
  - Nested item
```

- Ordered
```
1. First
2. Second
   1. Nested
```

- Task list (GitHub)
```
- [ ] To do
- [x] Done
```

### Links
```
[inline link](https://example.com)
[title link](https://example.com "Title")
<https://example.com>  <!-- autolink -->
[ref link][id]

[id]: https://example.com "Optional title"
```

### Images
```
![alt text](path/to/img.png)
![with title](path/to/img.png "Title")
```

### Code
- Inline
```
Use `code` in a sentence.
```

- Block
````
```language
// code here
```
````

### Blockquotes
```
> Quote
>> Nested quote
```

### Horizontal Rule
```
---
***
___
```

### Tables
```
| Col A | Col B | Col C |
|:----- |:----: | -----:|
| left  | center| right |
| a     | b     | c     |
```

### Escaping
```
\*literal asterisks\*
```

### HTML (when allowed)
```
<sup>sup</sup> <sub>sub</sub> <br>
```

### Footnotes (CommonMark extensions)
```
Here is a footnote reference.[^1]

[^1]: Footnote text.
```

### Definition Lists (some renderers)
```
Term
: Definition
```

### Admonitions (GitHub-style via blockquote)
```
> [!NOTE]
> Useful tip.
```

### Check Renderer Support
- Core spec: headings, emphasis, lists, links, images, code, blockquotes, hr.
- Extensions vary: tables, task lists, footnotes, definition lists, admonitions.
