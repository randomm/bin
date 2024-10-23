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
