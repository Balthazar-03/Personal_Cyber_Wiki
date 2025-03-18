---
aliases:
  - cd
  - ls
  - pwd
  - find
---
### Commands:
- CD
- LS
- PWD
- Find
----
Source: https://gist.github.com/bradtraversy/cc180de0edee05075a6139e42d5f28ce
Date: 28-2-2025

---
## CD
#### Syntax: cd -tag {dirname}

| Flags | Effect                                              |
| ----- | --------------------------------------------------- |
| ~     | Change to Home directory                            |
| ..    | Change to parent directory                          |
| -     | Change to previous directory (using session memory) |
CD is among one of the most universal commands that I know. It is used to change the current operative directory to a different one, thus allowing you to navigate a file system.
GUI Alternatives include [Window's file explorer](https://en.wikipedia.org/wiki/File_Explorer), and [KDE's dolphin](https://apps.kde.org/nl/dolphin/).

## LS
#### Syntax: ls -tag

| Flag | Effect                                             |
| ---- | -------------------------------------------------- |
| -a   | Includes hidden files in list                      |
| -l   | Lists with more information, including permissions |
| -r   | List in reverse order                              |
Ls, or list, reads the given directory's contents, and prints them to the [[CLI (Command-Line Interface)|terminal interface]].
It can be given a file path to read the contents of other directories, though to my knowledge cannot read more than one without more complicated commands.

## PWD
#### Syntax: pwd

Pwd, or print working directory prints the filepath that the [[CLI (Command-Line Interface)|terminal]] is currently working in. It is usefull to keep track of where you are when navigating using CD.

## Find
#### Syntax: find {dirname} -name {filename}

Find is used to find the location of a specific program, script, or file. It can be used to quickly scan for an executable, for a .txt file with the name password among many other things.