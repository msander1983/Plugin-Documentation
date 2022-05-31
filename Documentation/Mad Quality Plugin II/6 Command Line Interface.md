# Command Line Interface

The **Mad Quality Commander** CLI file `MadQualityCommander.exe` lives in the `C:\...\Flare.app` folder.

To validate all topics and snippets in a folder against a set of rules, use this syntax:
`C:\>”C:\....\Flare.app\MadQualityCommander.exe” ”C:\...\my folder” ”C:\...\my rules.xlsx” ”C:\....\myLog.txt”
`

- To include subdirectories, use the `/i` flag.
- To format the log as XML, use the `/xml`  flag. 
- To use the average score of the broken rules per file as the exit code, use the `/score` flag. 
