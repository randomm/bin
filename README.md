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

### docker_prune

A script to safely prune all unused Docker data, including images, containers, volumes, and networks. It checks if Docker is installed, prompts the user for confirmation before proceeding, and logs the output to a timestamped log file for future reference. After pruning, it displays detailed Docker disk usage information.

#### Usage

Clone the repository and add the folder to your `PATH`. Then run:

```bash
docker_prune
```

**Steps performed by the script:**

- **Checks if Docker is installed.**
- **Prompts you to confirm the pruning action.**
- **Prunes all unused Docker data using `docker system prune -a --volumes -f`.**
- **Logs the output to a file named `docker_prune_YYYYMMDD_HHMMSS.log`.**
- **Displays Docker disk usage after pruning.**

**Note:** This action cannot be undone. Ensure that you want to remove all unused Docker data before proceeding.

### cleanup_caches

A script to help clear various development-related caches on your system. It supports cleaning caches for multiple package managers and development tools including Poetry, Homebrew, pip, pipenv, Yarn, npm, and Cypress. The script shows the current cache sizes and prompts for confirmation before clearing each cache.

#### Requirements

- **Operating System**: macOS (uses macOS-specific paths like `~/Library/Caches`)
- **Shell**: zsh (script is written as a zsh script)
- **Package Managers**: None required, script checks for presence of each tool

#### Usage

Clone the repository and add the folder to your `PATH`. Then run:

```bash
cleanup_caches
```

**Supported Caches:**

- **Poetry** - Clears Poetry's PyPI cache (`~/Library/Caches/pypoetry`)
- **Homebrew** - Runs `brew cleanup` to remove old versions
- **pip** - Purges pip's package cache
- **pipenv** - Removes virtualenv environments (`~/.local/share/virtualenvs`)
- **Yarn** - Cleans Yarn's global cache (`~/Library/Caches/Yarn`)
- **npm** - Clears npm's package cache (`~/.npm`)
- **Cypress** - Removes Cypress cache directory (`~/Library/Caches/Cypress`)

**Note:** The script will:
- Check if each tool is installed and skip those that aren't present
- Show the current cache size for each tool
- Ask for confirmation before clearing each cache
- Skip empty caches automatically
- Only work on macOS systems due to path dependencies
