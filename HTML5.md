# HTML Barebones Guide

## Document
- \<!DOCTYPE html> — HTML5 doctype.
- \<html lang="en"> … \</html> — Root element.
- \<head> … \</head> — Metadata.
- \<meta charset="utf-8"> — Character encoding.
- \<meta name="viewport" content="width=device-width, initial-scale=1"> — Responsive viewport.
- \<title> … \</title> — Page title.
- \<link rel="stylesheet" href="styles.css"> — External CSS.
- \<script src="app.js" defer></script> — External JS.
- \<base href="/" target="_blank"> — Base URL/target for relative links.

## Structure & Sections
- \<body> … \</body> — Page content.
- \<header> … \</header> — Top banner/site header.
- \<nav> … \</nav> — Major navigation.
- \<main> … \</main> — Main content (one per page).
- \<section> … \</section> — Thematic grouping with heading.
- \<article> … \</article> — Self-contained content.
- \<aside> … \</aside> — Side content/related info.
- \<footer> … \</footer> — Footer info.
- \<div> … \</div> — Generic block container.
- \<span> … \</span> — Generic inline container.

## Headings & Text
- \<h1> … \</h1> to <h6> … </h6> — Headings.
- \<p> … \</p> — Paragraph.
- \<br> — Line break.
- \<hr> — Thematic break.
- \<strong> … \</strong> — Important text.
- \<em> … \</em> — Emphasis.
- \<b> … \</b> — Stylistic bold.
- \<i> … \</i> — Stylistic italic.
- \<u> … \</u> — Stylistic underline.
- \<small> … \</small> — Small print.
- \<mark> … \</mark> — Highlighted.
- \<sup> … \</sup> — Superscript.
- \<sub> … \</sub> — Subscript.
- \<abbr title="…"> … \</abbr> — Abbreviation.
- \<cite> … \</cite> — Work title citation.
- \<blockquote> … \</blockquote> — Block quote.
- \<q> … \</q> — Inline quote.
- \<code> … \</code> — Inline code.
- \<pre> … \</pre> — Preformatted text.
- \<kbd> … \</kbd> — User input.
- \<samp> … \</samp> — Sample output.
- \<var> … \</var> — Variable.
- \<time datetime="…"> … \</time> — Machine-readable time.
- \<data value="…"> … \</data> — Machine-readable value.
- \<!-- comment --> — Comment.

## Links & Media
- \<a href="URL"> … \</a> — Hyperlink.
- \<img src="…" alt="…"> — Image.
- \<figure> … \</figure> — Self-contained media.
- \<figcaption> … \</figcaption> — Media caption.
- \<audio controls src="…"> — Audio.
- \<video controls src="…"> — Video.
- \<source src="…" type="…"> — Media source.
- \<track kind="captions" src="…" srclang="…"> — Media text track.
- \<picture> … \</picture> — Responsive images.
- \<iframe src="…"> … \</iframe> — Inline frame.
- \<embed src="…" type="…"> — Embedded content.
- \<object data="…" type="…"> — Embedded resource.
- \<canvas> … \</canvas> — Scriptable drawing area.
- \<svg> … \</svg> — Vector graphics.

## Lists
- \<ul> … \</ul> — Unordered list.
- \<ol> … \</ol> — Ordered list.
- \<li> … \</li> — List item.
- \<dl> … \</dl> — Description list.
- \<dt> … \</dt> — Term.
- \<dd> … \</dd> — Description.

## Tables
- \<table> … \</table> — Table.
- \<caption> … \</caption> — Table title.
- \<thead> … \</thead> — Header row group.
- \<tbody> … \</tbody> — Body rows.
- \<tfoot> … \</tfoot> — Footer rows.
- \<tr> … \</tr> — Table row.
- \<th scope="col|row"> … \</th> — Header cell.
- \<td> … \</td> — Data cell.
- \<colgroup> … \</colgroup> — Column group.
- \<col span="…"> — Column properties.

## Forms
- \<form action="…" method="get|post"> … \</form> — Form.
- \<label for="id"> … \</label> — Control label.
- \<input type="text|email|password|checkbox|radio|number|date|file|hidden|submit|reset|button|range|search|tel|url|color|datetime-local|time|month|week"> — Input control.
- \<textarea rows="…" cols="…"> … \</textarea> — Multiline text.
- \<select> … \</select> — Dropdown.
- \<option value="…"> … \</option> — Option.
- \<optgroup label="…"> … \</optgroup> — Option group.
- \<button type="button|submit|reset"> … \</button> — Button.
- \<fieldset> … \</fieldset> — Group controls.
- \<legend> … \</legend> — Fieldset caption.
- \<datalist id="…"> \<option value="…"> — Suggestions list.
- \<output for="…"> … \</output> — Calculation result.
- \<progress value="…" max="…"> — Progress bar.
- \<meter value="…" min="…" max="…"> — Scalar measurement.

## Metadata & Misc
- \<style> … </style> — Internal CSS.
- \<link rel="icon" href="…"> — Favicon.
- \<meta name="description" content="…"> — Description.
- \<meta name="keywords" content="…"> — Keywords (legacy).
- \<meta http-equiv="refresh" content="5;url=…"> — Redirect/refresh.
- \<details> … \</details> — Disclosure widget.
- \<summary> … \</summary> — Summary for details.
- \<dialog open> … \</dialog> — Modal/dialog.
- \<template> … \</template> — Inert HTML fragment.
- \<slot> … \</slot> — Web components slot.

## Global Attributes (common)
- id, class, style, title
- lang, dir
- hidden
- tabindex
- draggable
- contenteditable
- aria-* (accessibility)
- data-* (custom data)

## Minimal Boilerplate
\<!DOCTYPE html><br />
\<html lang="en"><br />
\<head><br />
&nbsp;&nbsp;\<meta charset="utf-8"><br />
&nbsp;&nbsp;\<meta name="viewport" content="width=device-width, initial-scale=1"><br />
&nbsp;&nbsp;\<title>Title</title><br />
\</head><br />
\<body><br />
&nbsp;&nbsp;\<main><br />
&nbsp;&nbsp;&nbsp;&nbsp;\<h1>Hello\</h1><br />
&nbsp;&nbsp;&nbsp;&nbsp;\<p>World\</p><br />
&nbsp;&nbsp;&nbsp;&nbsp;\</main><br />
\</body><br />
\</html>
