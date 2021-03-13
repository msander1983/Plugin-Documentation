# Setting up validation rules

For examples of rules, see [[Sample Rules]].

For a list of supported CSS syntax, see [[CSS Syntax]].

For instructions on how to install the plugin, see [[Install the Mad Quality Plugin]].

>  To set up rules you need Microsoft Excel installed, or another software that can edit Microsoft Excel files. 

To set up a new set of rules:
1. Click **New set of rules**.
2. Enter a name for the new set of rules. Excel opens. 
3. For each new rule
	1. Enter a **Name** and a **Description**.
	2. Enter the **Message** that is showed to users when a rule is broken.
	3. Select the rule **Type**
		- If you select **Report** the rule is broken when the **Context** + **Test** CSS is found in a topic.
		- If you select **Assert** the rule is broken when the **Context** + **Test** CSS is missing from a topic.
	4. Select the rule **Language**. This can be either **CSS** or **XPath**.
		![[XPath Note]]
	5. Enter the **Context** and **Test** CSS or XPath. For more information, see [[CSS Syntax]].
	6. Enter a score for the rule. This is used for calculating an average score of all broken rules in a topic or project and you can use this to track the quality score of your documentation set over time. 





