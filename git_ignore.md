### Git Ignore and .gitignore

#### Git Ignore

* When sharing your code with others, there are often files or parts of your project, you do not want to share.
* Examples
    * log files
    * temporary files
    * hidden files
    * personal files
    * etc.

* Git can specify which files or parts of your project should be ignored by Git using a .gitignore file.

* Git will not track files and folders specified in .gitignore. However, the .gitignore file itself IS tracked by Git.

> ### Create .gitignore
* To create a .gitignore file, go to the root of your local Git, and create it:

```cmd
touch .gitignore
```

* Now open the file using a text editor.

* We are just going to add two simple rules:

    * Ignore any files with the .log extension
    * Ignore everything in any directory named temp

### Example

```cmd
# ignore ALL .log files
*.log

# ignore ALL files in ANY directory named temp
temp/
```

### >> Now all .log files and anything in temp folders will be ignored by Git.


#### Note: In this case, we use a single .gitignore which applies to the entire repository.

### It is also possible to have additional .gitignore files in subdirectories. These only apply to files or folders within that directory.


> Rules for .gitignore
* Check the rules

> ### Local and Personal Git Ignore Rules

* It is also possible to ignore files or folders but not show it in the distributed .gitignore file.

* These kinds of ignores are specified in the .git/info/exclude file. It works the same way as .gitignore but are not shown to anyone else.



