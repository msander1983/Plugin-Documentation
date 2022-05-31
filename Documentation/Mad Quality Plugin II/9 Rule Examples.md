# Rule Examples

To match a variable where the following text node doesn't start with a space:
`xpath:.//MadCap:variable[following-sibling::text()[not(starts-with(.,' '))]]`

To match a variable wher the preceding text node doesn't end with a space:
`xpath:.//MadCap:variable[preceding-sibling::text()[not(matches(.,'.*\s+$'))]]` 

To match a variable with a missing space at either end: 
`xpath:.//MadCap:variable[preceding-sibling::text()[not(matches(.,'.*\s+$'))] or following-sibling::text()[not(starts-with(.,' '))]]`

To find an `<a>` element that's not covered by a condition the contains the text `Online`:
`xpath:.//a[not(ancestor-or-self::*[contains(@MadCap:conditions,"Online")])]`