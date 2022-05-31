# Mad Quality Plugin (Deprecated)

The Mad Quality Plugin is based on the Schematron  standard, which is a rule-based validation language for making  assertions about the presence or absence of patterns in XML trees. It is a structural schema language expressed in XML using a small number of  elements and XPath.

You can use the Mad Quality plugin e.g. for business validation, quality control/assurance, house-style-rules checking.

Schematron is  simple language with only five important elements:

![[schematron-diagram.png]]    

| A **Schema**, which is the root element of a validation file |
| ------------------------------------------------------------ |
| A number of **Pattern** elements - in turn grouping together a set of rules |
| A number of **Rule** elements - setting the context for the validation (e.g. all Paragraphs, or Headings, etc.) |
| A set of **Assert** - each with an XPath test - reporting whenever the test is negative. Assertions are used for making sure a topic conforms to a set of rules - a tells you  when the rules are broken |
| A set of **Report** elements -  each with an XPath test - reporting whenever the test is positive.  Reports are used for telling you when a rule is broken. A Report is an  up-side-down Assertion |

## Release notes

| Date       | Version | What's new?                                                  |
| ---------- | ------- | ------------------------------------------------------------ |
| 2021-05-13 | 		   | Silent mode enabled for the installer |
| 2021-03-16 | 		   | Updated help call URL. |
| 2020-10-22 |         | The last column in the Rule Browser now word wraps.          |
| 2020-04-03 |         | To improve usability - the Rule Browser no longer displays the full file name. |
| 2019/05/31 |         | Updates to the help call.                                    |
| 2020-05-06 |         | Updated installer so that it works with Flare 2020.          |

## Sample rules

### Report empty paragraphs

This sample rule tells you when there is an empty paragraph in a topic:

```xml
<schema xmlns="https://purl.oclc.org/dsdl/schematron">
 	</pattern>
		<pattern id="empty-paragraph">
		<rule context="//p">
			<report test="string-join(text(),'')='&#160;'">
				Empty paragraph.
			</report>
			<report test="string-join(text(),'')=''">
				Empty paragraph.
			</report>
		</rule>
	</pattern>
</schema>   
```

### Find consecutive lists

This rule finds sibling ul- and ol- elements that should potentially be merged.

```xml
<pattern id="consecutive-ul-ol">
	<rule context="//ul/following-sibling::*[1][self::ul]|//ol/following-sibling::*[1][self::ol]">
		<report>Two consecutive lists were found. Merge them.</report>
	</rule>
</pattern>
```

### Keyword in heading

This rule tells you when a heading has a Keyword

```xml
<pattern id="keyword in heading">
	<rule context="/html/body/*[self::h1 or self::h2 or self::h3]">
		<report test="count(//MadCap:keyword) &gt; 0">Index keyword in heading.</report>
	</rule>
</pattern>
```

### Local styling

This pattern finds occurences of local styling.

```xml
<pattern id="local-styling">
	<rule context="//*[not(name()='table') and @style]">
		<report>
			This element appears to have local styling. 
		</report>
	</rule>
</pattern>
```

## How can I use the plugin?

### Setting up a new rule

To set up a new rule:

1. Create a new text-file in e.g. Notepad or Notepad++.
2. Create the Schematron-based XML structure, e.g.

```
<pattern id="local-styling">
	<rule context="//*[not(name()='table') and @style]">
		<report>
			This element appears to have local styling. 
		</report>
	</rule>
</pattern>
```

1. Save it in the **C:...\Flare.app\Plugins\Mad Quality Plugin** folder with the ".xml" extension.

## Where can I learn more about XPath and Schematron?

- For information about the Schematron standard, see [https://schematron.com/](http://schematron.com/).
- For information about XPath, see https://en.wikipedia.org/wiki/XPath.
- To test XPath-statements, you can use [https://www.xpathtester.com/xpath](http://www.xpathtester.com/xpath)