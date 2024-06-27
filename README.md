# ~/bin/

This repository contains personal scripts for various tasks. These scripts are intended for personal use and can be added to the `~/bin` directory for easy execution.

## Scripts

### compare_branches

A script to compare two Git branches and display the differences regardless of commit history (it uses git cherry in the background), including whether commits are merge commits and providing clickable links to the commits on GitHub. On Mac OS (iTerm2 at least) use command+click.

#### Usage

Clone repo and add the folder to your PATH. Then it is easy as pie:

```bash
cd to_repo_folder
compare_branches [-v] <branch1> <branch2>
```
