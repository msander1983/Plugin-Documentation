# Kaizen Plugin

The Kaizen Plugin is a collection of tools that will help you work more efficiently with specific problems in Flare.

Here's a webinar about the plugin: [How to Increase Your Productivity in MadCap Flare with the Kaizen Plugin](https://www.madcapsoftware.com/webinars/how-to-increase-productivity-madcap-flare-kaizen-plugin/).

See the [[Kaizen Plugin Release Notes]]. 

## Replace tags using REGEX

With the **Advanced Tag Replacer** you can search and replace any tag, attribute or set of attributes in your Flare project.

To replace tags or tag attributes in your project:

1.  Open the **Advanced Tag Replacer** from the **Cleanup** tab.
2.  Enter your search text in the **Search for** field.
3.  To get a list of the existing tags in your project, click **Search tags**.
4.  Select the tags you'd like to process.
5.  Select the action (replace, unbind, delete, or wrap)
6.  Select or enter the replacement tag.
7.  To replace the tags in your project, click **Execute**.

The tags have now been replaced. To undo - click **Undo**.

## Import micro content from Excel

To import micro content from Excel:

1.  Create an Excel file with two columns. The first column contains the micro content phrase, and the second columns contains the micro content text.
2.  Click Import > Import Micro Content from Excel, select the Excel file and click OK.

The micro content file opens.

## Split a topic and create a TOC

Splitting a topic file is a quick and easy way to create a new manual from a single topic file. You can split a topic files by H1-H4.

To split a topic file into separate topic files based on the heading level, and generate a corresponding TOC-file:

1.  Open the relevant topic.
2.  Click Split by H1 to split by heading level 1, etc.

The topic files and the corresponding TOC are created.

## Import a Markdown file to Flare

The plugin only supports the CommonMark specification. For more information, see [CommonMark specification](https://spec.commonmark.org/0.28/).

To import and convert entire folders, or all Markdown files in an open Flare project - you can get the [[Markdown Plugin II]].

To convert a markdown file to a Flare topic:

1.  Click **Import Markdown file**.
2.  Select the .md file.
3.  Save the .html file.

## Replace tags in a topic

You can only replace tags based on its class attribute, all other attributes will remain the same. For example, if you select to replace

```
<b class="Apples"></b>
```

with

```
<span class="Bananas"></span>
```

any b-element with the class element set to "Apples" will be replaced, but will retain its other attributes. For example,

```
<b class="Apples" id="Golden Delicious"></b>
```

would become

```
<span class="Bananas" id="Golden Delicious"></span>
```

1.  Click **Replace tags in topic**.
2.  Select the tag you want to replace.
3.  Select the tag you'd like to use instead.
4.  Select the approriate setting
    -   To replace one tag with another, select **Replace tags**.
    -   To unbind the tag, and only keep its content, select **Unbind tags**.
    -   To delete tag tag and its contents, select **Delete tags and content**.
5.  Click **Execute**.

If you want to undo the changes before you close the window, click **Undo**.

## Replace tags in a folder

You can only replace tags based on its class attribute, all other attributes will remain the same. For example, if you select to replace

```
<b class="Apples"></b>
```

with

```
<span class="Bananas"></span>
```

any b-element with the class element set to "Apples" will be replaced, but will retain its other attributes. For example,

```
<b class="Apples" id="Golden Delicious"></b>
```

would become

```
<span class="Bananas" id="Golden Delicious"></span>
```

1.  Click **Replace tags in folder**.
2.  Select the appropriate folder.
3.  To include all sub-folders, select **Include sub-folders**.
4.  Select the tag you want to replace.
5.  Select the tag you'd like to use instead.
6.  Select the approriate setting
    -   To replace one tag with another, select **Replace tags**.
    -   To unbind the tag, and only keep its content, select **Unbind tags**.
    -   To delete tag tag and its contents, select **Delete tags and content**.
7.  Click **Execute**. A backup-file is created on your desktop.

If you want to undo the changes before you close the window, click **Undo**.

## Create a WordCloud from your project, or a folder

To create a Word Cloud from the most used words in your project, or from the topic files in any folder (including sub-folders) - click any of the **WordCloud from...** button.

## Farm Glossary Terms from your project

To extract potential glossary candidates from your current project,

1.  Click **Farm Glossary Terms**. The Term Farmer window appears.
2.  Edit the list of terms, and optionally, add explanations.
3.  Click **Create Glossary** to create a new .flglo file and add to your project.

## Creating topics from CSV or Excel files

With the **Topic Creator** tools you can create topics, snippets, or other XML files from a different data sources. This lets you maintain data in, for example, Excel, and then create the topics using a template file.

### Set up a template file

You can set up a template in any valid XML-file, for example, topic files (.htm), snippet files (.flsnp), or even target files (.fltar).

### Set up a template that creates one file per line

1.  Create a new file in Flare.
    
2.  Open the file in, e.g. Notepad++.
    
3.  Use the headers from your data file where you want to import the data. For example, if your Excel file has two columns, **Title** and **Description** - you could set up a template like this:
```html
	<?xml version="1.0" encoding="utf-8"?>
	<html>
		<body>
			<h1>[[Title]]</h1>
			<p>[[Description]]</p>
		</body>
	</html>
```

### Sample CSV data
```csv
Title;Description
Title A;Description A
Title B;Description B
```

### Templates with repeating patterns

If your data is hierarchical, for example like this,

| Title | Data A |  Data B | Data C | 
| --- | --- | --- | --- | 
| Lorem A | Lorem 1 | Lorem 2 | Lorem 3 |
| Lorem A | Lorem 1.1 | Lorem 2.1 | Lorem 3.1 | 
| Lorem A | Lorem 1.2 | Lorem 2.2 | Lorem 3.2 |

, you can set up a template with a repeating pattern, where the headers inside the `<div class="repeat" >` are repeated while the other headers stay the same. The example would result in two files each containing a table.

```html
	<?xml version="1.0" encoding="utf-8"?>
	<html>
		<body>
			<h1><[[Title]]/h2>
			<div class="repeat">
				<table>
					<th>
						<td>Data A</td>
						<td>Data B</td>
						<td>Data C</td>
					</th>
					<tr>
						<td>[[Data A]]</td>
						<td>[[Data B]]</td>
						<td>[[Data C]]</td>
					</tr>
				</table>
			</div>
		</body>
	</html>
```

### Import data from a CSV file

Note that the CSV file must have a header row.

1.  Click **Data Import (CSV)**.
2.  Select the path to the CSV file.
3.  Select the path to the template file.
4.  Select the folder where you want the output files.
5.  To overwrite any existing files, select the **Overwrite files** checkbox.
6.  To generate the files, click **Execute**.

### Sample CSV data

Title;Description
Title A;Description A
Title B;Description B

### Import data from an Excel file

Note that the Excel file must have a header row.

1.  Click **Data Import (Excel)**.
2.  Select the path to the Excel file.
3.  Select the path to the template file.
4.  Select the folder where you want the output files.
5.  To overwrite any existing files, select the **Overwrite files** checkbox.
6.  To generate the files, click **Execute**.

## Add a To-Do note to a topic

To add a To-Do note to a topic, insert an annotation, and write

```
	TODO: This is my task.
```

To view all the To-Do Notes in a project, click the **To-Do Notes** button.

To insert an annotation, do this:

1.  Select some text
2.  Open the **Review** tab
3.  Click **Insert Annotation**.