## Development Process at Robotic Eyes

### Source Code Management

All our work is source controlled using the Git source code management system.
We have the following rules for working with repositories:

* We only allow squash merge or rebase commits (linear history)
* Merge commits are not allowed
* Every work needs to undergo a review using Github's **pull request** feature
* At least one reviewer needs to be assigned who need to approve the work

#### Branches

GIT offers a convenient way to work with branches. Each feature which
should be developed will result in a new branch where the developers can
finish up the feature completely. Once being done, the code is getting
merged into the master branch after being approved by at least one peer reviewer.

### Implement a new feature

This is the procedure which is suggested to implement a new feature.

#### File an issue on Github

1. Create a new issue for the repository you are working on. Use a short title, and if necessary also add a description with screenshots.
1. If the feature will be implemented by yourself, directly assign the issue to yourself.
1. If not, do not assign the issue. This will be done by the repository lead.

#### Prepare your local machine

1. If you haven't already cloned the repository (only needs to be done once), get a local copy by `git clone <repository link>`.
1. Make sure that your get the latest version of the master branch by
    * `git checkout master`
    * `git pull -r`
1. Create a new branch for your issue
    * `git checkout -b name_of_new_branch`
    * It is good practice to name the branch in the following format `issueID_shorttitle`, e.g. `42_question_to_everything_fix`

#### Work on your feature

1. Perform your work on your machine in your branch.
1. Make regular commits to store your local work.
1. You can also backup your work by pushing your branch to Github
    * `git push --set-upstream origin branch_name`
    * The `--set-upstream` only needs to be set once for registering the branch with your remote repository
1. Once you are done, you just need to make sure to push your latest work to your remote branch.

#### Get back to Github

1. Open up Github and create a new **pull request** for your repository.
1. Assign at least one reviewer.
1. Also make sure that your refer to your issue in the description of the pull request by writing `resolves #issueID`.
   This automatically closes the issue once the branch is merged into master (e.g. `resolves #42`).
1. If the reviewer requests changes, update your code in the same branch. There is no need to file another pull request,
   the old one is still valid and can be used.
1. After the pull request is approved, make sure to merge, and to delete the working branch on Github.

### General notes and best practices

* Make sure that merge commits are disabled for your repository.
* Make one reviewer mandatory for your repository.
* Reviewers are getting notified automatically via email by Github, no need to send an extra email.
* Perform squash merges for pull request, so all working commits are squashed into one commit in the master branch.
* Keep pull requests short.
* Do not implement multiple features/issues within one branch if they are not dependent of each other.
