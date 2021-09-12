# Basic Git CLI Command

<!-- toc -->

  * [Setup Git](#setup-git)
  * [Need Help](#need-help)
    + [Example](#example)
  * [Initialize a repository from existing code](#initialize-a-repository-from-existing-code)
  * [Before First Commit](#before-first-commit)
  * [Our First Commit](#our-first-commit)
  * [Cloning a remote repo](#cloning-a-remote-repo)
  * [Viewing Info about the Remote Repo](#viewing-info-about-the-remote-repo)
- [Given a scenario that if you have a file, calc.py, and you have made changes to it](#given-a-scenario-that-if-you-have-a-file-calcpy-and-you-have-made-changes-to-it)
- [Pushing changes](#pushing-changes)
  * [1. Commit your changes](#1-commit-your-changes)
  * [2. Push to Remote repo](#2-push-to-remote-repo)
- [Common workflow](#common-workflow)
  * [Create a branch for desired feature](#create-a-branch-for-desired-feature)
- [After you have made the changes, commit them](#after-you-have-made-the-changes-commit-them)
  * [Commit them just like here](#commit-them-just-like-here%23-1-commit-your-changes)
  * [Then push branch to remote](#then-push-branch-to-remote)
  * [Merge a branch](#merge-a-branch)
  * [Delete a branch](#delete-a-branch)

<!-- tocstop -->

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
        or u can just enter the following line into your command `echo ".DS_Store" > .gitignore

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
4. or you can combine first and second step together to be `git checkout -b <calc-divide>`

### Alternative Commands of creating a branch

Use the following command to create a new branch    
`git switch -c new-branch`

#### change to another branch by just `git switch another-branch`

## After you have made the changes, commit them

### Commit them just like [here](#1-commit-your-changes)

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

## To delete files from git

### use the following command: `git rm <filename>`

or 

### Delete manually
1. Delete them in you file explorer / finder,
2. On the command prompt, enter the the following command: `git add .`     
Voila! You wil see your files being deleted not juz from the finder but also from git

## Undo Unstaged Files

Let's say you have a file edited but unstaged, so you remove the changes u made in the file with the following command:    
`git checkout <filename>`

### Alternative with `restore` command

the same result can be achieved by running this command: `git restore <filename>` or simply replace `<filename>` with `.` to remove all the unstaged changes

### Delete unstage files

1. first check which files can be removed by : `git clean -dn`
2. then `git clean -df`, the `f` tag stands for force, you git will force remove the files that are unstage

## Undoing Staged Files

Let's say you have some staged edits and you wanna remove it, we can do it in 2 steps
### With 2 steps
1. Restore to the latest commits by `git restore --staged <filename>`
2. Then `git checkout <filename>`

## Delete Commits with `reset`

### `git reset --soft HEAD~1`

- the `--soft` tag basically mean undo the command `git commit -m "msg"`, the git will go back the HEAD by 1 commit, but the changes will be remained staged
- you can still commit the changes without staging them and with the command `git commit -m "previous commit"`

### Default `reset` command : `git reset HEAD~1`

- after running this command, the changes will be unstaged.
- if you wanna go back 2 commits, just change `HEAD~1` to `HEAD~2` etc

## Deleting branch

### `git branch -D <branch-name>`


 