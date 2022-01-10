# WindowsPowerShellTricks
Some useful windows power shell functions


Add prefix to file name :

dir | Rename-Item -NewName {"A_" + $_.Name}

Replace space to uncerscore in file name : 

dir | Rename-Item –NewName { $_.Name –replace “ “,”_” }

Rename file name to TitleCase style : 

dir | Rename-Item -NewName {(Get-Culture).TextInfo.ToTitleCase($_.Name)}

Rename all files in subfolders to TitleCase :

Get-ChildItem -Recurse | Rename-Item -NewName {(Get-Culture).TextInfo.ToTitleCase($_.Name)}
