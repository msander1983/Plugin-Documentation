# Markdown Plugin (Deprecated)

This plugin has been deprecated and is replaced by [[Markdown Plugin II]].

The plugin is based on the CommonMark specification. For more information, see the [CommonMark specification](https://spec.commonmark.org/).

## Command Line Interface (KaizenCommander.exe )

### To import Markdown files from one folder to another:

```
KaizenCommander -md -import "C:\...\from-folder" "C:\...\to-folder"
```

### To convert all Markdown files to topics and snippets in a folder (-s to include sub-folders):

```
KaizenCommander -md -syncmd "C:\...\myFolder"
```

### To convert all topics and snippets to markdown files in a folder (-s to include sub-folders):

```
KaizenCommander -md -synctopics "C:\...\myFolder"
```

## Import a Markdown file to Flare

To convert a markdown file to a Flare topic:

1. Click **Import file**.
2. Select the .md file.
3. Save the .html file.

## Import an entire folder of Markdown files to Flare 

1. Click **Import folder**.
2. Select the folder with the Markdown files. 
3. Select the destination folder in your Flare project. 

The .md files from the selected folder are now converted  to topics and copied into your Flare project along with any linked  images. 

## Convert all topics in your project to Markdown files 

1. Click **Convert all topics to Markdown files in a folder**.
2. Select the folder with the Markdown files. 

The .md files from the selected folder are now converted to topics in the same folder. 

## Convert all Markdown files in your project to Flare topic files

1. Click **Convert all Markdown files to topics in folder**
2. Select the folder with the topic files. 

The topic files from the selected folder are now converted to Markdown files in the same folder. 

## Convert a topic file to a TOC file (Experimental)

For this to work, the topic file must contain a bullet list with relative links to .md files. 

1. Open a topic and click Convert topic to TOC. 

The selected topic is converted to a TOC file. 