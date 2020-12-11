This is Sky's first git project! :)

# Basic Git Command Line

> This note is made while self-learning web dev from The Odin Project and by watching this [youtube video](xhttps://www.youtube.com/watch?v=HVsySz-h9r4)

### Setup Git

1. Install Git
    1. install through [here](git-scm.com)
2. Check Git version
    1. run `git --version` on your command / terminal
3. Global Configuration
    - run the following command
        1. `git config --user.name "YourName"`
        2. `git config --user.email "YourEmail"`
    - Check those values by
        - `git config --list`

### Need Help

+ `git help <verb>`  or  `git <verb> --help`

- #### Example

    - `git help config`
    - `git add --help`

### Initialize a repository from existing code

1. `ls`
    - to display all __folder__ within that directory
2. `ls -la`
    - to display all __files__ within that directory
3. `cd <directory>`
    - replace `<directory` with the folder you want to initialize your repository
    - Example: `cd Document\GitFolder`
4. `git init`
    - By running this command, you have created a new git directory, and if you run `ls -la` again, you will be able to see a new *.git* folder is displayed! :)

### Before First Commit

1. `git status`
    - to check your commit status and also whether if you have any files that hasn't been committed
2. `touch .gitignore`
    - to create a folder called *.gitignore* so that **Git** will not track on those. You may have some files that contain your own personal details or some codes that is specific to your own Operating System, therefore, you might not want **Git** to trace on those files.
    - *.gitignore* is just a text file. Next, you open this text file using your text editor(VS Code etc), and type in
        > .DS_Store
    
        etc

3. Add all files to Staging Area
    - `git add -A`
    - `git status`
    - Example, adding file one by one
        - `git add .gitignore`
    - use `git status` to check which files that you would want to add to the stage area, then use `git add <fileName>` command to add them.
4. Remove files from Staging Area
    - `git reset <fileNames>`
    - running `git reset`, will remove all the files from your staging area

### Our First Commit

1. `git add -A`
2. `git commit -m "Initia Commit"`
3. `git status`
4. `git log` command will display the commit that you have done

### Cloning a remote repo

- `git clone <url> <where to clone(directory)>`

### Viewing Info about the Remote Repo

- `git remove -v`
- `git branch -a` shows all the branches

## Given a scenario that if you have a file, calc.py, and you have made changes to it

## Pushing changes

### 1. Commit your changes

1. `git diff` shows difference/ changes that you made
2. `git status`
3. `git add -A`
4. `git commit -m "detailed description of you changes"`

### 2. Push to Remote repo

1. `git pull origin main`, if you have a few people working on the same project concurrently, this command is to update your local repo
2. `git push origin main`

## Common workflow

### Create a branch for desired feature

1. `git branch calc-divide`, create a new branch named **calc-divide**
2. run `git branch` to check which branch are you working on
3. `git checkout calc-divide`, change you working branch to the one you just created(calc-divide)

## After you have made the changes, commit them

### Commit them just like [here](#1.-commit-your-changes)

### Then push branch to remote

1. `git push -u origin alc-divide`
2. `git branch -a`

### Merge a branch

1. `git checkout master`, switch to our master branch
2. `git pull origin master`, before you commit any thing to master, always pull down from the master, in case some changes have been made
3. `git branch --merged`, this command will show the branch that have been merge with the master
4. `git merge calc-divide`, merge **calc-divide** into origin
5. `git push origin master`

### Delete a branch

1. `git branch merged`, to double check this branch has been merged with the master branch before you delete it
2. `git branch -d calc-divide`
3. `git branch -a`
4. `git push origin --delete calc-divide`, to delete the **calc-divide** branch from remote repo