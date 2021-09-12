# CLI Command Cheat Sheet for terminal (Mac)

<!-- toc -->

- [Simple Command](#simple-command)
  * [pwd (Print Working Directory)](#pwd-print-working-directory)
  * [ls (List Items)](#ls-list-items)
  * [cd (Change Directory)](#cd-change-directory)
  * [clear](#clear)
  * [Trick](#trick)
    + [Auto Completion](#auto-completion)
- [Creating and Deleting Files](#creating-and-deleting-files)
  * [mkdir (Make Directory)](#mkdir-make-directory)
  * [touch(Create New File)](#touchcreate-new-file)
  * [rm (Remove)](#rm-remove)
  * [rmdir (Remove Directory)](#rmdir-remove-directory)
- [Flags](#flags)
  * [Example:](#example)
    + [Combining command](#combining-command)
  * [Find out what are the flags available](#find-out-what-are-the-flags-available)
  * [rm -r (Remove Non-empty Folder)](#rm--r-remove-non-empty-folder)
- [Copy & Moving Files & Folders](#copy--moving-files--folders)
  * [cp [source path] [target path]](#cp-source-path-target-path)
  * [Copy multiple files with flags `-r`](#copy-multiple-files-with-flags--r)
    + [cp -r [source path] [target path]](#cp--r-source-path-target-path)
  * [mv [source path] [target path]](#mv-source-path-target-path)
  * [rename the filenames with `mv`](#rename-the-filenames-with-mv)
    + [`mv indexs.css index.css`](#mv-indexscss-indexcss)

<!-- tocstop -->

# Simple Command

## pwd (Print Working Directory)
shows the current directory that you are in

## ls (List Items)
list the items which are in the current direcory

## cd (Change Directory)

simply type  
1. `cd` to go back to root folder
2. `cd ..` to go up one hierachy level

##  clear
to make your terminal line looks cleaner, and go back to the top, but when you scroll up the terminal, you can still see the previous commands that you have used.

##  Trick

###  Auto Completion

Type the first letter of the folder that you want to go into, then press `tab`, the terminal will show all the possible folders or auto complete the name of the folder

# Creating and Deleting Files

## mkdir (Make Directory)

example: `mkdir hello` will create a new folder called **hello** in the current directory

## touch(Create New File)

touch command will touch the existing files and change the date when these files were changed the last time, but when the command cannot find the specific file, it will create anew one.  

We are basically misuing this command, but this is a way of creating a new files within your file system. 

example: `touch world.js`

## rm (Remove)

This command delete files permanently, keep this in mind, as you will not be able to restore the file from the bin.

example: `rm world.js`

## rmdir (Remove Directory)

Same as `rm`, this command delete the folder permanently.

And take note that this command delete folder instead of files.

Example: `rmdir hello`

---

**Take Note**  

You cannot remove a folder which contains files within it. You will need to remove the files then only you can delete the folder

---

# Flags

Flags allow users to modify the command and are sometimes called as options. They normally start with a `-` after a command

## Example:

`ls -s` shows the files and the file size

`ls -l` shows print the files exist in the current directory in long format, including time created, creator etc

### Combining command

`ls -ls` shows the files in long format as well as the file size

## Find out what are the flags available

type `man [command]` to find out what are the flags available for a specific command

Example: `man mkdir`

##  rm -r (Remove Non-empty Folder)

With the flag `r`, users can remove the folders which are not empty. However, do take note of this, as it might cause you huge problems when you delete the whole folder with all the data inside.  

**YOU WONT BE ABLE TO RETREIVE BACK THE DELETED DATA**

# Copy & Moving Files & Folders

##  cp [source path] [target path]
This command helps to copy a files into another folder, it requires two path, one for source files another for target folder.

Example: `cp data/index.css copied/`
The above example copied the a file **index.css** from the folder called **data** into another folder called **copied**

##  Copy multiple files with flags `-r`

###  cp -r [source path] [target path]

Example: `cp -r data/ copied/`
The above example will copy all the files in the data folder into the copied folder.  

Take note of the slashes, without the slashes, the command will create a new directory in the copied folder instead. And always remember to type the target source, if not, it will delete the source folder instead

##  mv [source path] [target path] (move files around)

The principle is basically same as copy except that t

his command merely moves the files around instead of copy the files

You can also move the whole folder instead of a single files

##  rename the filenames with `mv`

### `mv indexs.css index.css`

The above command renames the file **indexs.css** into **index.css**