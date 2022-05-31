# Release Notes

## 1.0.29 (2022-05-09)
- New FEATURES:
	- You can now run ad-hoc CSS searches to find elements matching a certain CSS expression. Just click the **Search (CSS)** button and enter your query.
	- To quickly validate the XHTML of all topics - you can click the "Validate XML" button. 
- BUG fixes: 
	- Fixed cosmetic issue in the preview window. 
	- Corrected bug in the RawRegex function that would prevent you from using the MadCap-namespace in your REGEX expressions. 

## 1.0.28 (2022-03-17)
- Removed a dependency on Google prettyprint.
- Made sure non-breaking spaces show up in the HTML preview.
- The CSV file now shows the actual word from the rule instead of just "%s" or "%t".
- The MS-20210413120632 rule was updated to avoid a sentence being flagged as having no closing punctuation when it in fact did, only there was a space after the punctuation. 
**NOTE:** Changes to rules only apply to newly created rule sets. 
- Bug fix: If a TOC entry linked to a specific bookmark in a file - that file would not be scanned.

## 1.0.27 (2022-03-08)
- A bug fix to the filter functionality. 

## 1.0.26 (2022-03-01)
- Extended bug reporting via email.
- Fixed a bug in the .ignore-functionality. 
- If you write an xpath statement that returns an XNode that is not an XElement - that would not be supported. Now it is, in the sense that if the match is a non XElement XNode - the parent XElement is returned.
- Added a rule to the default rule set to find images without ALT texts (https://www.w3.org/WAI/WCAG21/quickref/#non-text-content)

## 1.0.25 (2021-12-06)
- Fixed a problem where files in /Project/Users/.../Backups were included in the scan. 
- Changed the timeout limit from 10 seconds to 15 seconds for individual rules.
- Added support for REGEX matching with attributes, e.g. `[class %= \bMyWord\b]`.
- New dialog when there are no broken rules. 
- Enabled XML log mode for the MadQualityCommander using the `/xml` flag. 
- Folders are now shown in the rule violation window.
- Performance improvements. 
- Filtering of the broken rules with free text.
- You can now ignore files by creating an `.mqignore` file with the appropriate file name pattern. Works like .gitignore. 
- Fixed a problem with the license validator. 

## 1.0.24 (2021-11-10)
- Fixed License key problem. 

## 1.0.23 (2021-11-03)
- A correction to the REGEX of the MS-20210413120609 rule. 
- Bug fix: `MadCap:concept` is now properly converted. 
- Updated the license terms, making them less restrictive. 

## 1.0.22 (2021-10-30)
- Fixed a bug where REGEX expressions would sometimes not register properly. 
- Changed the REGEX of MS-20210413120633 to avoid false positives. 
- Fixed a bug where `MadCap:concept` was not properly converted to XPath.
- Fixed a bug where a REGEX to detect a space at the start of an element did not work if the element started with a variable, or other element. 
- Performance improvements. 
- Change in MS-20210413120548 to ensure that "millimeters" and "centimeters" are matched. 
- Fixed a bug where the RawRegex function would not work when e.g. a h1 element had a MadCap:variable as it's first child element.
- The ":empty" selector now also includes non-breaking spaces. 
- Added a new function: RegexInline, which will keep any inline HTML-elements in the matched element. For example `<h1>Lorem <span>ipsum</span></h1>` becomes `Lorem <span>ipsum</span>` rather than just `Lorem ipsum`.

## 1.0.21 (2021-07-23)
- You can now use XPath statements for the context by prefixing the context with "xpath:". The XPath statements must return an element node. Attribute or text nodes are currently not supported. 
- Topics no longer time out at 90 seconds. This prevents long topics from timing out, but means that scanning the entire project takes longer. 
- Various bug fixes. 

## 1.0.20 (2021-05-26)
- Corrected spelling errors. 
- Fixed issue with licensing. 

## 1.0.19 (2021-05-22)
- Enabled silent mode on the installer (/S).
- Added option to link to rule file in remote location, for example on a network drive or on the web. 
- Added Google Developer Style Guide rules. 
- Corrections to the template rule set. 
- The results window now automatically closes when you process another rule set. 
- You can now process any Flare XML file, e.g. .fltar, .fltoc etc. 

## 1.0.18
- Bug fix: When a topic contains an image that is linked to the web - the plugin crashed.

## 1.0.17
- Fixed a bug that caused the RawRegex function to fail.

## 1.0.16
- Removed the "annotate element" function.
- Added timout for rules (10 seconds), and for files (30 seconds).

## 1.0.15
- Bug fixes in the default rules. 
- Validation of all the default rules. 
- Added "RawRegex" function to match the entire element text, e.g. `<p>My element</br><p>` instead of `My element`.
- Corrected bug for Assert type rules.

## 1.0.14
- Disabled the write good rules by default.
- Corrected the bug that prevented the "Word" & "ListOfWord" functions to process topics accurately. 
- Corrected the "index is out of bounds" bug. 
- Changed the MS-20210413120543 rule from "Regex" to "ListOfWords" to make it work :)

## 1.0.13
- The rule template is now added as the default rule set.
- The FileNameRegex did previously not work when combining rule type Assert with a context and a regex pattern. Now it does. 

## 1.0.12
- Updated GUI texts. 
- Fallback validation to prevent "FILE ERROR" and XPATH errors. 
- Fixed a bug where the first row of the rules spreadsheet wasn't converted.

## 1.0.11
- Performance improvements. The plugin is now significantly faster.

## 1.0.10
- Added a hard-coded context called "Text", which is p, td:not(:has(p)), li:not(:has(p)).
- It's no longer possible to add a rule from an http-location using the GUI. You can however, add the link to a .rule file that you manually add to the folder with the xlsx files. 
- Added "scan a random topic".
- Updated the internal CSS to XPath engine to support a wider range of CSS syntax. 

## 1.0.9
- Performance enhancements. 

## 1.0.8
- If a REGEX based rule times out at over 9 seconds - it will disabled while running the remaining quality check. 
- There's now an automatic 14 day free trial when you install the plugin.

## 1.0.7
- Corrected a bug that prevented the "FileNameRegex" function from working. 
- Added more default rules based on the "Write Good" rules. 
- Activated all rules again.
- Added a tab for each category of rules so that you can copy & paste them into the first tab to activate them.
- Extended trial.
- Various rule changes. 

## 1.0.6
- Corrected the en/em-dash rule. The previous REGEX expression took too long to process. 
- Added a box with the message in the results window. If the description or message has a link, you can click it to open in your browser. 
- Files are now processed in parallel to make the processing faster. 
- Added a progress bar for each individual file so that you can see the progress. 
- Disabled some of the more processor intensive rules in the default template. Added tabs for structural rules and MS manual of style. 
- CANCEL => Cancel

## 1.0.5
- The "IgnoreCase" setting was ignored, but isn't anymore.
- Added feature to use rules at other location, e.g. "G:\my Rule.xlsx" or "https://www.github.com/.../rules.xlsx".
- Added button to open the folders with the rules, for easy import/export. 
- Corrected bugs in the rule sets. 
- Corrected resize bug in the results window.

## 1.0.4
- The results window no longer stays on top.
- The processing modal window no longer stays on top while processing. 

## 1.0.3
- Regular expressions now operate on strings without taking inline tags into consideration. 
- Added Microsoft Manual of Style rules to the template. 
- Added progress bar and cancel button.

## 1.0.2
- Regular expressions now operate on an elements string value with tags replaced rather than the element value, which would exclude content in e.g. span tags in paragraphs. 

## 1.0.1
- Bug fixes