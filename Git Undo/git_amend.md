### Git Amend

> #### Git commit --amend

commit --amend is used to modify the most recent commit.

It combines changes in the staging environment with the latest commit, and creates a new commit.

This new commit replaces the latest commit entirely.

#### Git Amend Commit Message

One of the simplest things you can do with --amend is to change a commit message.

Let's update the README.md and commit:


```cmd
git commit -m "Adding plines to reddme"
[master 07c5bc5] Adding plines to reddme
 1 file changed, 3 insertions(+), 1 deletion(-)
```

* Now let's check the log:

```cmd
git log --oneline
07c5bc5 (HEAD -> master) Adding plines to reddme
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

* Oh no! the commit message is full of spelling errors. Embarrassing. Let's amend that:

```cmd

git commit --amend -m "Added lines to README.md"
[master eaa69ce] Added lines to README.md
 Date: Thu Apr 22 12:18:52 2021 +0200
 1 file changed, 3 insertions(+), 1 deletion(-))

```

And re-check the log:

```cmd
git log --oneline
eaa69ce (HEAD -> master) Added lines to README.md
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

We see the previous commit is replaced with our amended one!

> #### Warning: Messing with the commit history of a repository can be dangerous. It is usually ok to make these kinds of changes to your own local repository. However, you should avoid making changes that rewrite history to remote repositories, especially if others are working with them.

### Git Amend Files

Adding files with --amend works the same way as above. Just add them to the staging environment before committing.



