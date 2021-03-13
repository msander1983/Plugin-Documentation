# Sample Rules

### CSS rules

For more information, see [[CSS Syntax]].

| Name | Description | Message | Type | Language | Context | Test | Score | 
|---|---|---|---|---|---|---|---|
|Hard lines breaks||Please avoid hard line breaks in paragraphs|Report|CSS|body|p:has(br)|50|
|Empty paragraphs||Remove empty paragraphs.|Report|CSS|p:empty||75|
|Empty lists||A list must have a list item.|Assert|CSS|ul,ol|:has(li)|100|


### XPath rules

![[XPath Note]]