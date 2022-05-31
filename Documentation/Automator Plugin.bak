# Automator Plugin

With the Automator plugin, you can build your very own MadCap Flare plugin to automate the things you do over and over again, saving you both time and energy in the process.

To learn how SimCorp uses the Automator plugin see the MadCap webinar: [The Power of MadCap Flare Supports Large-scale Documentation and Fuels SimCorp's Continuous Delivery of 450k+ Help Topics](https://www.madcapsoftware.com/webinars/the-power-of-madcap-flare-supports-large-scale-documentation-and-fuels-simcorps-continuous-delivery-of-450k-help-topics/)

## Release notes

| Date | What's new? |
| --- | --- |
| 2021-03-16 | Updated help call URL. |
| 2020-04-12 | Corrected a bug where the \[%root%\] variable returned the root path with "" at the end - causing python scripts to fail. |
| 2020-05-06 | Updated installer so that it works with Flare 2020.|
| 2019-05-31 | First release.| 
## Build your first plugin using the Automator

To create a plugin button that opens the current topic in Notepad, follow these steps:

1.  Click **Set up automations** on the **Automator** tab. The **Automator Settings** window appears.
2.  Set **Tab** to **My Plugin**.
3.  Set **Group** to **Notepad**.
4.  Set **Path** to **C:\\windows\\notepad.exe**
5.  Set **Arguments** to **"\[%topic%\]"**
6.  Set **Icon** to **face**.
7.  Set **Label** to **Open in Notepad**.
8.  Set **Tool tip** to **Opens the current file in Notepad**.
9.  Click **Save**.
10.  **Close** the settings window and restart Flare.
   
Your Flare ribbon now has a tab called **My Plugin**... go check it out!

## Examples

The tables provides a few examples of automations you can create. For more complex workflows, I recommend you use .BAT files, Power Shell scripts, or even Python scripts.

| Tab       | Group             | Path                                                         | Arguments                                                    | Icon          | Label                 | Tool tip                                                     |
| --------- | ----------------- | ------------------------------------------------------------ | ------------------------------------------------------------ | ------------- | --------------------- | ------------------------------------------------------------ |
| My Plugin | Browser shortcuts | https://www.google.com                                       |                                                              | stars         | Google                | Opens google.com in your browser.                            |
| My Plugin | Text editors      | C:\Program Files (x86)\Notepad++\Notepad++.exe               | "[%topic%]"                                                  | code          | Open in Notepad++     | Opens the current topic (or other file) in Notepad++ for editing. |
| My Plugin | MadBuild          | C:\Program Files\MadCap Software\MadCap Flare 14\Flare.app\madbuild.exe | -project "C:\Users\Mattias\Improvementsoft AB\SampleProject\SampleProject.flprj" -batch "NewBatchTarget" | build         | Build batch target    | Builds the target using madbuild.exe.                        |
| My Plugin | Pandoc            | C:\Users\Mattias\AppData\Local\Pandoc\pandoc.exe             | "[%topic%]" -o "[%desktop%]\REPLACE([%topicFileName%], .htm, .docx)" | import_export | Convert to Word       | Converts the current topic to a Word document and saves in on your desktop. |
| My Plugin | Pandoc            | C:\Users\Mattias\AppData\Local\Pandoc\pandoc.exe             | "[%topic%]" -o "[%desktop%]\INPUT(Enter file name)"          | import_export | Convert to any format | Converts the current topic to another format, depending on the file name suffix, e.g. .md or .docx. |

## Argument variables

To integrate your automations with Flare, you can use special argument variables to your scripts or executable files.

**NOTE**: To ensure that spaces in file paths are handled properly you should wrap the variables in double quotation marks, e.g. "\[%topic%\]".

| Variable          | Value                                                        |
| ----------------- | ------------------------------------------------------------ |
| `[%topic%]`         | The path to the currently open (and in focus) topic (or other file). For example:                            c:\My projects\Mattias\Content\Topic A.htm |
| `[%root%]`          | The path to the root folder of the Flare project (the folder with the .flprj file). For example:                             c:\My projects\Mattias\Content\Topic A.htm |
| `[%topicFileName%]` | The file name of the currently open topic. For example: Topic A.htm |
| `[%content%]`       | The path to the /Content/ folder, for example:                            c:\My projects\Mattias\Content\ |
| `[%flprj%]`         | The path to the Flare project (.flprj) file.                 |
| `[%desktop%]`       | The path to you desktop folder. For example:                            C:\users\mattias\desktop |

## Custom argument functions

To make your automations even more powerful - you can use the following functions in the **Arguments** field.

To ensure that spaces in file paths are handled properly you should wrap the functions in double quotation marks, e.g. "INFILE()".

| Function                                  | Description                                                  |
| ----------------------------------------- | ------------------------------------------------------------ |
| `REPLACE(This is my text, text, dog)`       | Replaces the word "text" with "dog" in the string "This is my text" - resulting in a string that reads "This is my dog". |
| `INPUT(This is a title)`                    | Prompts you to enter text or value when you  run your automation. For example, INPUT(Please enter your name) would  ask you for your name, and then replace the entire **INPUT(This is a title)** element with your name. |
| `SELECT(Option 1, Option 2, Option 3)`      | Asks you to select an option from a list item box.           |
| `INFILE()`                                  | Asks you to select a file from your computer.                |
| `MULTISELECT(Option 1, Option 2, Option 3)` | Asks you to select one or more options. The result is a list separated by ";", for exampel: **Option 1;Option 2; Option 3**. |
| `OUTFILE() `                                | Asks you to select a save-file.                              |
| `FOLDER()`                           | Asks you to select a folder.                                 |
| `CLIPBOARD()`                               | Gets the content from your clipboard.                        |
| `SELECTION()`                               | Gets the selected text from your topic (if any).             |
