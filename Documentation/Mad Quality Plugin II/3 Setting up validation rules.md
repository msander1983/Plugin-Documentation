# Setting up validation rules

For examples of rules, see [[5 Examples]].

For a list of supported CSS syntax, see [[4 CSS Syntax]].

For instructions on how to install the plugin, see [[2 Install the Mad Quality Plugin]].
        
> Setting up rules requires Microsoft Excel, or a software that can edit .xlsx files. 

A rule consists of these parts:

**Name**
- The name of the rule, for example "MS-20210417104127".

**Enabled**
- A TRUE/FALSE setting to enable or disable a rule

**Description**
- A description of the rule and its source, for example "[https://docs.microsoft.com/en-us/style-guide/acronyms](https://docs.microsoft.com/en-us/style-guide/acronyms)"

**Message**
- A message to present to the writer when a rule is broken, for example "Avoid using acronyms in a title or heading."
	- You can add `%s` and `%t` to your message to include regular expression matches. For example, for a rule with the `Word` function with the parameter `checkbox:check box`, the message could be `Don't say '%s', say '%t'` and it would then display this to the writer: `Don't say 'checkbox', say 'check box'`.

**Type**
- The type determines whether to **assert** or **report** the presence of a pattern.    

**Context**
- The CSS-based context to apply the rule in, for example, to apply it to all paragraph elements, the context would be `p`.

> It is possible to use XPath in the context. For example `.//p` to match all paragraphs.

**Function**
- The function of the rule. Each function, except the **None** function takes one or more parameters, set in the **Parameters** field. 
	- **None**. The rule just asserts or reports the presence of the context element, for example `p > h1` to find a heading wrapped in a paragraph tag.
	- **Regex**. The rule checks for the match of a regular expression in the text value of an element. All inline elements are unbound, so `<p>Lorem <b>ipsum</b> dolor</p>` becomes `Lorem ipsum dolor`.
		- To develop and test regular expressions, I recommend a site called [RegEx Pal](https://www.regexpal.com/).
	- **RawRegex**. The rule matches the text of the entire tag, for example :`<p>Lorem ipsum <MadCap:variable/> dolor</p>` instead of just the text value.
	- **Word**. The rule checks for the presence of a single word in the context element. For example `checkbox` would match elements with that word.  Optionally - you can suggest an alternative to the matches word, by adding a colon and the replacement word, for example `checkbox:check box`. This provides a suggestion for replacement to the writer
	- **ListOfWords**. This rule works like the **Word** rule, but on a list of words. For example `checkbox,intelligent`, or, to suggest replacements: `checkbox:check box,intelligent:smart`.
	- **Readability**. Matches elements with a readability score lower than the parameter value you set, for example `60`.
	- **FileNameRegex**. Matches the file name based on a regular expression. For example, you can set up a rule to ensure that file names don't have spaces, or only have lower-case letters. 
	
	> Both the **Word** and **ListOfWords** functions can include REGEX in the left hand side of the parameter. 
	
**IgnoreCase**
- A TRUE/FALSE option. For rules based on regular expressions this setting determines whether to ignore the letter-case of the matching text. 

**Parameters**
- The parameters for the different functions. 

**Score**
- A penalty score to apply when a rule is broken. Use this to let writers know how serious a broken rule is.

**FileFilters**
- This is a comma-separated wildcard based text that lets you assign rules to different file types, or files with a specfic prefix. For example `*.htm,*.html,*.flsnp` matches topics and snippets in Flare. 




 