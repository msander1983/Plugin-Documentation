# Functions 
## None (or blank)
Select this function when you are just asserting/reporting the existence of a specific element using the **Context** field, e.g. `p > h1` to detect a heading wrapped in a paragraph tag. 
## Regex
Select this function to assert that or report when the context tags' content matches the regular expression in the **Parameters** field. 
## Word
Select this function to match a specific word set in the **Parameters** field. For example `checkbox`.
To propose an alternative word - use the following syntax: `checkbox:check box`.
## ListOfWords
Select this function to match a list of words set in the **Parameters** field. For example `checkbox,banana,apple`.
To propose alternative words - use the following syntax: `checkbox:check box,banana:fruit,apple:fruit`.
## Readability
Select this function to check the readability of the context element(s) using the Flesch Kincaid readability score. Set the **Parameters** field to the lowest acceptable readability value. When you are using the **Readability** function it doesn't matter if you set the rule type to **Assert** or **Report**.
