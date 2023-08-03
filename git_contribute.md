### ***Git GitHub Fork***

> #### Add to Someone Else's Repository

* At the heart of Git is collaboration. However, Git does not allow you to add code to someone else's repository without access rights.

* In these next 3 chapters we will show you how to copy a repository, make changes to it, and suggest those changes be implemented to the original repository.


> #### Fork a Repository

* A ***fork*** is a copy of a repository. This is useful when you want to contribute to someone else's project or start your own project based on theirs.

* ***fork*** is not a command in Git, but something offered in GitHub and other repository hosts. Let's start by logging in to GitHub, and fork our repository:
 * https://github.com/w3schools-test/w3schools-test.github.io

 ![git hub fork img](https://www.w3schools.com/git/img_github_fork.png "Fork Example").

* > Now we have our own copy of w3schools-test.github.io:

![git hub fork example](https://www.w3schools.com/git/img_github_fork_complete.png)

* Now let's look at how we add a local copy of this for us to work with.

### Git Clone from GitHub

#### Clone a Fork from GitHub

* Now we have our own fork, but only on GitHub. We also want a clone on our local Git to keep working on it.

* A clone is a full copy of a repository, including all logging and versions of files.

* Move back to the original repository, and click the green "Code" button to get the URL to clone:

![git clone img](https://www.w3schools.com/git/img_github_clone_url.png)


### Configuring Remotes

> ##### Basically, we have a full copy of a repository, whose origin we are not allowed to make changes to.

> ##### Let's see how the remotes of this Git is set up:

```cmd
git remote -v
origin  https://github.com/w3schools-test/w3schools-test.github.io.git (fetch)
origin  https://github.com/w3schools-test/w3schools-test.github.io.git (push)
```

* We see that origin is set up to the original "w3schools-test" repository, we also want to add our own fork.

> First, we ***rename*** the original ***origin remote*** :

```cmd
git remote rename origin upstream
git remote -v
upstream        https://github.com/w3schools-test/w3schools-test.github.io.git (fetch)
upstream        https://github.com/w3schools-test/w3schools-test.github.io.git (push)
```

> #### Then fetch the ***URL*** of our own ***fork***:
> #### And add that as ***origin***:



![Fetch url of our own fork img](https://www.w3schools.com/git/img_github_clone_fork_url.png)

```cmd
git remote add origin https://github.com/kaijim/w3schools-test.github.io.git
git remote -v
origin  https://github.com/kaijim/w3schools-test.github.io.git (fetch)
origin  https://github.com/kaijim/w3schools-test.github.io.git (push)
upstream        https://github.com/w3schools-test/w3schools-test.github.io.git (fetch)
upstream        https://github.com/w3schools-test/w3schools-test.github.io.git (push)
```

> ### ***Note: According to Git naming conventions, it is recommended to name your own repository origin, and the one you forked for upstream***

* Now we have 2 remotes:
    * ***origin*** - our own ***fork***, where we have read and write access
    * ***upstream*** - the original, where we have read-only access

* Now we are going to make some changes to the code. In the next chapter, we will cover how we suggest those changes to the original repository.


> ### Git GitHub Send Pull Request

##### Push Changes to Our GitHub Fork

* We have made a lot of changes to our local Git.

* Now we push them to our GitHub fork:

* commit the changes:

```cmd
git push origin
Enumerating objects: 8, done.
Counting objects: 100% (8/8), done.
Delta compression using up to 16 threads
Compressing objects: 100% (5/5), done.
Writing objects: 100% (5/5), 393.96 KiB | 32.83 MiB/s, done.
Total 5 (delta 0), reused 0 (delta 0), pack-reused 0
To https://github.com/kaijim/w3schools-test.github.io.git
   facaeae..ebb1a5c  master -> master
```

> * Go to GitHub, and we see that the repository has a new commit. And we can send a Pull Request to the original repository:

![send pull request](https://www.w3schools.com/git/img_github_fork_pull_request.png)

> ### Click that and create a pull request:

![Create pull request](https://www.w3schools.com/git/img_github_fork_create_pull_request.png)

> #### Remember to add an explanation for the administrators.

![Description write](https://www.w3schools.com/git/img_github_fork_create_pull_request_comment.png)

> ### Pull Request is sent:

![pull request is send now](https://www.w3schools.com/git/img_github_fork_pull_request_sent.png)

> ### Approving Pull Requests

* Now any member with access can see the Pull Request when they see the original repository:

![Approve pull request](https://www.w3schools.com/git/img_github_new_pull_request.png)

> #### And they can see the proposed changes:

![proposed changes](https://www.w3schools.com/git/img_github_pull_requests_overview.png)

### ***Comment on the changes and merge:***

![commment and merge](https://www.w3schools.com/git/img_github_pull_request_merge.png)

> ### Confirm:

![confirm merge](https://www.w3schools.com/git/img_github_pull_request_confirm_merge.png)


> ### And changes have been ***merged*** with ***master:***

![all done now](https://www.w3schools.com/git/img_github_pull_request_merged.png)



