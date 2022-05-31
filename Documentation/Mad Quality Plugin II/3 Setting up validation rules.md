# Setting up validation rules

For examples of rules, see [[5 Examples]].

For a list of supported CSS syntax, see [[4 CSS Syntax]].

For instructions on how to install the plugin, see [[2 Install the Mad Quality Plugin]].
        
> Setting up rules requires Microsoft Excel, or a software that can edit .xlsx files. 

A rule consists of these parts:

**Name**
- The name of the rule, for example "MS-20210417104127".<br>This string appears in the report and makes it easier to find the rule in the ruleset.

**Enabled**
- Enables (TRUE) or disables (FALSE) the rule.<br>If you disable a rule, the plugin ignores it in the ruleset (does not run it).

**Description**
- A description of the rule and its source.<br>This string appears in the report.<br>For example "[https://docs.microsoft.com/en-us/style-guide/acronyms](https://docs.microsoft.com/en-us/style-guide/acronyms)".

**Message**
- A detailed message about the violation.<br>This string appears in the report.<br>For example "`Avoid using acronyms in a title or heading.`"
	- You can add `%s` and `%t` to your message string to include the Regular Expression matches. For example, for a rule with the `Word` function with the parameter `checkbox:check box`, the message could be `Do not write: '%s'. Write: '%t'.`. The report would show this to the writer: `Do not write: 'checkbox'. Write: 'check box'`.

**Type**
- The type determines whether to **assert** or **report** the presence of a pattern.
	- If you select **Assert**, the report shows a rule violation only if the pattern does **not** appear in your content.<br>For example, to check if H1 appears, enter `h1:nth-of-type(1)` in the **Context** column.<br>This rule would be violated only if a topic / snippet does **not** contain one `<h1>`.
	- If you select **Report**, the report shows a rule violation only if the pattern **does** appear in your content.<br>For example, to check if H-tags contain a `<br />` tag, enter `:header:has(br)` in the **Context** column.<br>This rule would be violated only if a heading tag **contains** a `<br />` tag.

**Context**
- The CSS-based context to apply the rule in. For example, to apply it to all paragraph `<p>` elements, the context would be `p`.<br>I recommend this reference: [MDN CSS selectors](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_Selectors)


> It is possible to use XPath in the context.<br>Examples:<br>- To match all paragraphs, enter: `xpath:.//p`<br>- To match a topic that has the `xml:lang="VALUE"`, enter: `xpath:.//html[@xml:lang]`

**Function**
- The function of the rule. Each function, except the **None** function takes one or more parameters, configured in the **Parameters** column.

	| Function | Description | Clarification / Example |
	| ------------- | --------------------------------------------------------------------- | ----------------------------------------------------- |
	| **None** | The rule just asserts or reports the presence of the context element. | To find a heading wrapped in a paragraph tag, you can configure this Context:<br>`p > h1` |
	| **Regex** | The rule uses the RegEx syntax from the **Parameters** column to check for the pattern match only in the inner text value of an element from the **Context** column.<br>All inline elements are unbound.| The rule analyzes the string<br>`<p>Lorem <b>ipsum</b> dolor</p>`<br>as<br>`Lorem ipsum dolor`. |
	| **RawRegex** | The rule uses the RegEx syntax from the **Parameters** column to check for the pattern match in the entire element from the **Context** column.<br>All inline elements are kept. | The rule analyzes the string<br>`<p>Lorem <b>ipsum</b> dolor</p>`<br>literally as<br>`<p>Lorem <b>ipsum</b> dolor</p>`.<br>For example, to find two adjacent variables with a missing space between them, you can configure:<br>- Context = `p, li`<br>- Parameters = `<\/MadCap:variable><MadCap:variable`<br>For example, to find the `<![CDATA[]]>` tag, you can configure:<br>- Context = `h1, h2, h3, h4, h5, h6, p`<br>- Parameters = `\<!\[CDATA\[` |
	| **RegexInline** | The rule uses the RegEx syntax from the **Parameters** column to check for the pattern match only in the inner text value of an element from the **Context** column.<br>All inline elements are kept. | The rule analyzes the string<br>`<p>Lorem <b>ipsum</b> dolor</p>`<br>as<br>`Lorem <b>ipsum</b> dolor`.<br>Note - Try this function if the **RawRegex** function does not find a match.<br>For example to check if the text in a heading starts with a space, you can configure:<br>- Context = `:header`<br>- Parameters = `^[ ]{1,3}(.+?)`|
	| **Word** | The rule checks for the presence of a single word in the context element.<br>This function supports a RegEx syntax in the left-hand side of the parameter the **Parameters** column. | `checkbox` would match elements with that word.<br>Optionally - you can suggest an alternative to the matched word. Add a colon and the replacement word:<br>`checkbox:check box`.<br>This provides a suggestion for replacement to the writer. |
	| **ListOfWords** | This rule works like the **Word** rule, but on a list of words.<br>This function supports a RegEx syntax in the left-hand side of the parameter the **Parameters** column. | To find content that contains the words `checkbox` or `intelligent`, enter in the **Parameters** column:<br>`checkbox,intelligent`.<br>To also suggest replacement words, enter in the **Parameters** column:<br>`checkbox:check box,intelligent:smart` |
	| **FileNameRegex** | The rule uses the RegEx syntax from the **Parameters** column to check the file names. | To find file names that contain spaces, you can configure:<br>`\s{1,}`<br>To find file names that contain capital letters, you can configure:<br>`[A-Z]` |
	| **Readability** | Matches elements with a readability score lower than the value you configured in the **Parameters** column | `60` |

	
	> To develop and test regular expressions, I recommend these web sites: [RegEx101](https://regex101.com/), [RegEx Pal](https://www.regexpal.com/).
	
**IgnoreCase**
- For rules that contain RegEx in the **Parameters** column, this setting determines whether to ignore (TRUE) or not (FALSE) the letter-case of the matching text. 

**Parameters**
- The parameters for the different functions.<br>For example, a RegEx syntax.<br>See the **Function** section above.

**Score**
- A penalty score to apply when a rule is broken.<br>Use this to let writers know how serious a broken rule is.<br>You decide on the scale and its meaning.

**FileFilters**
- This is a comma-separated wildcard based text that lets you assign rules to different file types, or files with a specfic prefix.<br>For example `*.htm,*.html,*.flsnp` matches topics and snippets. 




 
