# Release Notes

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