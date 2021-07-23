# CSS Syntax
The following CSS syntax is supported.

> To use XPath syntax, prefix the `context` value with `xpath:`

## Special tags
- `Text` all p, li (without p), and td (without p) elements. 

## Tag Selectors
- `*` all elements
- `div` all div tags
- `div,p` all divs and paragraphs
- `div p` paragraphs inside divs
- `div > p` all p tags, one level deep in div
- `div + p` p tags immediately after div
- `div ~ p` p tags preceded by div
- `.classname` all elements with class
- `#idname` element with ID
- `div.classname` divs with certain classname
- `div#idname` div with certain ID
- `#idname *` all elements inside `#idname`

## Attribute Selectors
- `a[target]` a tags with the target attribute.
- `a[target="_blank"]` `a` tags where the `target` attribute equals `_blank`
- `[title~="chair"]` title element containing a word
- `[class^="chair"]` class starts with chair
- `[class|="chair"]` class starts with the chair word
- `[class*="chair"]` class contains chair
- `[class$="chair"]` class ends with chair

## Pseudo Selectors/Functions
- `div:empty` element with no children
- `p:first-of-type` first of some type
- `p:last-of-type` last of some type
- `:not(span)` element that's not a span
- `p:first-child` first child of its parent
- `p:last-child` last child of its parent
- `p:nth-child(2)` second child of its parent
- `p:nth-child(3n+1)` nth-child (an + b) formula
- `p:nth-last-child(2)` second child from behind
- `p:nth-of-type(2)` second p of its parent
- `p:nth-last-of-type(2)` ...from behind
- `p:only-of-type` unique of its parent
- `p:only-child` only child of its parent
-  `p:has(br)` element that contains another element
-  `p:contains(text)` element that contains *text*




