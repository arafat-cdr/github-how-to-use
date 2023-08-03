### Git Reset

reset is the command we use when we want to move the repository back to a previous commit, discarding any changes made after that commit.

Step 1: Find the previous commit:

![git reset](https://www.w3schools.com/git/img_reset_part1.gif)

Step 2: Move the repository back to that step:

![git reset stp 2](https://www.w3schools.com/git/img_reset_part2.gif)

After the previous chapter, we have a part in our commit history we could go back to. Let's try and do that with reset.

> ### Git Reset Find Commit in Log
First thing, we need to find the point we want to return to. To do that, we need to go through the log.

To avoid the very long log list, we are going to use the --oneline option, which gives just one line per commit showing:

    * The first seven characters of the commit hash - this is what we need to refer to in our reset command.
    * the commit message


So let's find the point we want to reset to:

```cmd
git log --oneline
e56ba1f (HEAD -> master) Revert "Just a regular update, definitely no accidents here..."
52418f7 Just a regular update, definitely no accidents here...
9a9add8 (origin/master) Added .gitignore
81912ba Corrected spelling error
3fdaa5b Merge pull request #1 from w3schools-test/update-readme
836e5bf (origin/update-readme, update-readme) Updated readme for GitHub Branches
daf4f7c (origin/html-skeleton, html-skeleton) Updated index.html with basic meta
facaeae (gh-page/master) Merge branch 'master' of https://github.com/w3schools-test/hello-world
e7de78f Updated index.html. Resized image
5a04b6f Updated README.md with a line about focus
d29d69f Updated README.md with a line about GitHub
e0b6038 merged with hello-world-images after fixing conflicts
1f1584e added new image
dfa79db updated index.html with emergency fix
0312c55 Added image to Hello World
09f4acd Updated index.html with a new line
221ec6e First release of Hello World!
```

We want to return to the commit: 9a9add8 (origin/master) Added .gitignore, the last one before we started to mess with things.

### Git Reset

We reset our repository back to the specific commit using git reset commithash (commithash being the first 7 characters of the commit hash we found in the log):


```cmd
git reset 9a9add8

```

* Now let's check the log again:


```cmd
git log --oneline
9a9add8 (HEAD -> master, origin/master) Added .gitignore
81912ba Corrected spelling error
3fdaa5b Merge pull request #1 from w3schools-test/update-readme
836e5bf (origin/update-readme, update-readme) Updated readme for GitHub Branches
daf4f7c (origin/html-skeleton, html-skeleton) Updated index.html with basic meta
facaeae (gh-page/master) Merge branch 'master' of https://github.com/w3schools-test/hello-world
e7de78f Updated index.html. Resized image
5a04b6f Updated README.md with a line about focus
d29d69f Updated README.md with a line about GitHub
e0b6038 merged with hello-world-images after fixing conflicts
1f1584e added new image
dfa79db updated index.html with emergency fix
0312c55 Added image to Hello World
09f4acd Updated index.html with a new line
221ec6e First release of Hello World!

```

> #### Warning: Messing with the commit history of a repository can be dangerous. It is usually ok to make these kinds of changes to your own local repository. However, you should avoid making changes that rewrite history to remote repositories, especially if others are working with them.


### Git Undo Reset


* Even though the commits are no longer showing up in the log, it is not removed from Git.

* If you know the commit hash you can reset to it:

```cmd
git reset e56ba1f

```

* Now let's check the log again:

```cmd
git log --oneline
e56ba1f (HEAD -> master) Revert "Just a regular update, definitely no accidents here..."
52418f7 Just a regular update, definitely no accidents here...
9a9add8 (origin/master) Added .gitignore
81912ba Corrected spelling error
3fdaa5b Merge pull request #1 from w3schools-test/update-readme
836e5bf (origin/update-readme, update-readme) Updated readme for GitHub Branches
daf4f7c (origin/html-skeleton, html-skeleton) Updated index.html with basic meta
facaeae (gh-page/master) Merge branch 'master' of https://github.com/w3schools-test/hello-world
e7de78f Updated index.html. Resized image
5a04b6f Updated README.md with a line about focus
d29d69f Updated README.md with a line about GitHub
e0b6038 merged with hello-world-images after fixing conflicts
1f1584e added new image
dfa79db updated index.html with emergency fix
0312c55 Added image to Hello World
09f4acd Updated index.html with a new line
221ec6e First release of Hello World!
```