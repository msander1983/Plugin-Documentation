# Setting up validation rules

For examples of rules, see [[Example Rules]].

For a list of supported CSS syntax, see [[CSS Syntax]].

For instructions on how to install the plugin, see [[Install the Mad Quality Plugin]].

>  To set up rules you need Microsoft Excel installed, or another software that can edit Microsoft Excel files. 

        
## Rule components 
**Name**: The name of the rule.
**Description**: The description of the rule.
**Message**: The message that shows when a rule is violated.
> For some functions, you can use `%s` and `%t` to include data from the broken rule in the message, for example a word. 

**Type**: The validation type. 
- Select **Assert** to assert the existence.
- Select **Report** to report the existence. 
**Context**: The CSS context of the rule. For more information, see [[CSS Syntax]].

**Function**
 - Select **Word** to find a specific word
 - Select **ListOfWords** to find any of the words in the list, e.g. `checkbox,banana`.

**IgnoreCase**: Select **TRUE** to ensure that the regular expression ignores case. 

**Parameters**: The parameters of the selected function. See [[Functions]] for details about each function. 

**Score**: A penalty score for rule violations. 

**FileFilters**: Use wildcards to determine which file types or file name patterns should be processed. For example `*.htm,*.flsnp` or `My*.htm`.




 