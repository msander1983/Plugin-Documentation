# Markdown Plugin II

The plugin is based on the CommonMark specification. For more information, see the [CommonMark specification](https://spec.commonmark.org/).

For documentation of the first version of the Markdown plugin, see the [[Markdown Plugin]] documentation.

## Release Notes 

See the [release information](https://github.com/msander1983/MarkdownPluginRelease/releases).

## Import to Flare
* Import a folder with Markdown files to Flare topics.
* Import a folder with Markdown files to Flare snippets.

## Export to Markdown
* Export a Flare topic or snippet to a Markdown file.
* Export a folder of topics and snippets to Markdown files. 

## Convert to Markdown
* Convert the current topic to Markdown.
* Convert a folder of topics and snippets to Markdown.
* Convert all topics and snippets in your Flare project to Markdown.

## Refresh from Markdown
* Overwrite the content of the current topic with the converted content from its corresponding Markdown file.
* Refresh all topics and snippets in a folder from the corresponding Markdown files. 
* Refresh all topics and snippets in your Flare project from Markdown.

> If a topic is called `Topic.htm`, the corresponding Markdown file would be `Topic.md`, and for a snippet called `Snippet.flsnp`, the corresponding Markdown files is `Snippet.flsnp.md`.

## Misc
* Convert a Flare topics to a Flare TOC file (Experimental).

## Markdown Editor
Use the built-in Markdown editor to see what your Markdown is converted to with the plugin. 

### Settings

The settings for converting Markdown to Flare topics are set in a file called `MarkdownSettings.xml`, which is placed either in your Flare project, or in your application data folder in Windows. If a Flare project has a settings file - that file takes precedence over the settings file in the application data folder. 

```xml
<?xml version="1.0" encoding="utf-8" standalone="yes"?>
<Settings>
  <HeaderlessTables>true</HeaderlessTables>
  <ComplexTables>false</ComplexTables>
  <RemoveAttributesOnExport>false</RemoveAttributesOnExport>
  <ConvertXrefs>false</ConvertXrefs>
  <ConvertLocalLinksToXref>false</ConvertLocalLinksToXref>
  <ExportYaml>false</ExportYaml>
  <UseMadCapCodeSnippet>false</UseMadCapCodeSnippet>
  <ConvertedCommentedTags>false</ConvertedCommentedTags>
  <ExportUnsupportedTagsAsComments>false</ExportUnsupportedTagsAsComments>
  <ConvertCommentsToAnnotations>false</ConvertCommentsToAnnotations>
  <CopyImages>true</CopyImages>
</Settings>
```

#### Import settings
- Convert to MadCap Code Snippet
- Convert local links (and #-links) to cross-references
- Convert commented out html tags (`<!--<div>-->`) to HTML
- Convert //comments to MadCap:annotations
- Copy images upon import
- Import tables without adding headers to tables that don't have them.
- Export YAML meta data.
- Convert `[[Wiki links]] `to xrefs (only relevant for folder import).
- Add GitHub repo URL meta data to imported files. /blob/main/ only
- Convert `[block:image]` and `[block:code]` elements to `<img>` and `<code> `respectively.
- Convert #keyword to `<MadCap:keyword term=""keyword""/>`
- Merge adjacent empty table cells in a row.
- Import tables with `<tbody>` and `<thead>`
- Convert #-links to lower case

#### Export settings
- Export HTML elements without attributes to keep the Markdown clean.
- Convert MadCap:xref to regular links on export.
- Export unsupported tags as `<!--<MyTag>-->` comments.
	
### YAML meta data
If a Markdown file contains YAML dat, the YAML tags are converted to meta-tags in Flare. 
* There are a few special cases that are processed differently:
  * **conditions** are converted to the conditions of the topic or snippet.
  * **conditionTagExpression** are converted to the snippet conditions of the topic or snippet. 
  * **fileTags** are converted to file tags for the topic or snippet.

For example,

```yaml
description: Lorem ipsum dolor
keywords: lorem, ipsum, dolor
category: lorem
```
is imported into Flare as 

```html
<meta name="description" content="Lorem ipsum dolor" />
<meta name="keywords" content="lorem, ipsum, dolor" />
<meta name="category" content="lorem" />
```

and this YAML code

```yaml
---
conditions: Default.Mobile,Default.Tablet
conditionTagExpression: include[Default.Mobile], exclude[Default.Tablet]
fileTags: Author.Author1,Author.Author2
---
```

is imported as 

```html
<html xmlns:MadCap="http://www.madcapsoftware.com/Schemas/MadCap.xsd" MadCap:conditions="Default.Mobile,Default.Tablet" 
      MadCap:conditionTagExpression="include[Default.Mobile], exclude[Default.Tablet]" 
      MadCap:snippetVariables="General.VersionNumber:1231231223," MadCap:fileTags="Author.Author1,Author.Author2">
```

## MarkdownCommander.exe CLI

With the MarkdownCommander CLI you can import and export files using the command line. 

To import Markdown files to topics:
```
C:\>MarkdownCommander -import "C:\...\from-folder"" ""C:\...\to-folder"
C:\>MarkdownCommander -import "C:\...\from-folder\myfile.md" "C:\...\to-folder"
C:\>MarkdownCommander -import "C:\...\from-folder\myfile.md" "C:\...\to-folder\myfile.htm"
```
To export topics to Markdown files: 
```
C:\>MarkdownCommander -export "C:\...\from-folder"" ""C:\...\to-folder"
C:\>MarkdownCommander -export "C:\...\from-folder\mytopic.htm" "C:\...\to-folder"
C:\>MarkdownCommander -export "C:\...\from-folder\mytopic.htm" "C:\...\to-folder\mytopic.md"
```
| Flag | Comment | 
| --- | ---|
| /f | Force overwrite |
| /i | Include sub-folders |
| /t | Generate output to console (single file only) |
| /s | Suppress dialogs. |
| `/settings:[file]` | Uses a specific settings file for the Markdown import, e.g. `"/settings:C:\users\mattias\my files\mySettings.xml"` |

To generate a TOC from a folder structure:
	
```
C:\>MarkdownCommander -toc "C:\my folder" "C:\...\myToc.fltoc"
```
	
> If a folder is called "/My Folder/" and has a corresponding Markdown file called "My Folder.md" - that file is used is the parent topic for the node of that folder. Otherwise the folder node will be empty. 
	
## Ignoring files
* To keep files from being imported, you can set up a `.markdownimportignore` file in the source folder.
* To keep files from being exported, you can set up a `.markdownexportignore` file in the source folder.

The syntax is based on wildcards, where
* `*` represents a range of wildcard characters, and 
* `?` represents a single wildcard character

To ensure that the .ignore rules are processed relative to the folder of the .ignore file the line in the ignore file must contain `\`.

### Examples
| Rule | Comment |
| --- | ---- |
| `*\Lorem.md` | Excludes the files called `Lorem.md` in any subfolder to the folder with the rule file | 
| `\Lorem.md` | Excludes the `Lorem.md` file from the folder with the rule file | 
| `*Lorem*`  |  Excludes any file with `Lorem` in its full path. | 
