### Here is the General Guideline for Working in Manymoons

> 1. Start with the latest codebase

```bash
    git checkout master
    git pull origin master
 ```

> 2. Create feature or bugfix branch based of of master branch.
```bash
git checkout -b feature/feature-name
# or
git checkout -b bugfix/issue-to-fix
```

> 3. Work on the code updates and changes locally
* Please try to make commits as often as possible so they're versioned within your branch. Use descriptive comments when adding updates so that the history is readable and easy to follow.

> 4. Create Pull Request against master branch as soon as you make the first commit
* When creating a pull request please summarize the changes being made for this new feature and give it a descriptive title.

> 5. Code review
* When Pull Request is created and you are happy with the change, please assign and ask another developer to review your updates.

> 6. Push feature or bugfix branch to develop
* When the code is approved, it's time to test the feature or bugfix on the actual test environment that is as close to production environment as possible. Merge your branch by switching to develop branch and pushing the desired code. *

```bash
git checkout develop
git merge feature/feature-name
git push

```

7. Merge Pull Request after the QA and approval
* Merge PR using GitHub interface and deploy your updates to production environment.

8. Make sure all changes are deployed and tested on production environment