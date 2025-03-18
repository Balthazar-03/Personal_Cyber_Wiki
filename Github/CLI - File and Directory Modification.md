---
aliases:
  - mkdir
  - touch
  - rm
  - cp
  - mv
---
### Commands:
- Mkdir
- Touch
- RM
- CP
- MV
----
Source: https://gist.github.com/bradtraversy/cc180de0edee05075a6139e42d5f28ce
Date: 28-02-2025
Commands:

----
## mkdir
#### Syntax: mkdir {dirname}
Mkdir, or make directory, creates a directory with the given name, at the given location.

## touch
#### Syntax: touch {filename}
Creates a file with the given name, location and extension.
tools like [[Nano]] or [[Vim]] can also create files, but are more limited in scope, leaving this tool mostly for niche situations.
## rm
#### Syntax: rm -tag {dirname}

| Tag | Effect                                                               |
| --- | -------------------------------------------------------------------- |
| -i  | remove the file, but ask for permission                              |
| -r  | removes the directory.                                               |
| -rf | removes the directory and all its contents. Can remove system files. |
| ./* | Removes everything in the current folder.                            |
rm, or remove, by default removes the given file. It can also be said to remove anything it encounters using the flags mentioned above.

Be carefull when using rf, as it can remove all system files leaving your system inoperable and forcing you to reinstall everything.

## cp
#### Syntax: cp {filename} {dirname}

Cp, or copy, copies the targeted file to the given location. I think it can also copy directories and their contents.

## mv
#### Syntax: mv {filename/dirname} {filename/dirname} -tag

Mv, or move has 2 methods of using it.
1. It can move the selected file or directory to the given location.
2. It can rename the given file or folder.