.. _gitflow:

Gitflow
=======

Outlines a reasonable git flow when doing development with the team.

Workflow
--------

We use a branching workflow with rebasing to keep the commit log uniform across all our branches:

1. create new branch
2. commit changes to branch & push them to origin
3. rebase regularly onto ``master``
4. force push to overwrite ``origin/new-branch``
5. open pull request

Feature Branches
----------------
Working with creating new branches for features or fixes::

    master~$ git pull -r
    master~$ git checkout -b new-branch
    new-branch~$ # do what you need to make changes to new-branch
    new-branch~$ git add -A    # alternatively you can add specific files
    new-branch~$ git commit -m "a description of some changes to my branch"
    new-branch~$ git push -u origin new-branch   # further changes can be pushed with just 'git push'

Rebasing
--------

Keep commits small and rebase often so that conflicts will be easier to resolve::

    new-branch~$ git fetch
    new-branch~$ git rebase origin/master
    new-branch~$ # resolve conflicts during rebase
    new-branch~$ git push origin new-branch --force   # force push to overwrite origin with rebased version

Pull Requests
-------------

1. When your branch is ready to be reviewed by others you can create a pull request.
2. Make sure you have latest ``master`` branch changes rebased into your working branch
3. Push your branch up to the remote with ``git push origin new-branch``
4. Create a pull request via the Github interface wtih ``master`` as the base branch.
5. Fill out details on what was changed, any setup needed to review/test code, and assign appropriate labels and a person to review.
