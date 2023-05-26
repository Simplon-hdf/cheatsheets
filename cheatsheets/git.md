**Cheat Sheet Git et Github**

That cheat sheet is about how to create a git project and how to use a simple version of git.

**1) How to start a repository**

**2) Add, Save & Check**

**3) Send, Receive & Remote**

**4) Manage branchs**

**5) Remove, Restore & Revert**

**6) Merge & Rebase**

**7) Upstream**

**8) Others : must know**


-------------------------------------- GIT STASH --------------------------------------

- git stash push -u -m "message" ........... Discard all changes since the last commit.
- git stash ................................ Create a stash without any informations.
- git stash save stashName (obsolete) ...... Save local changes (since last commit) in a stash with a specified name.
- branch nomDeBranch nomDuStash ............ Create a new branch from a specific stash and apply changes to it.
- git stash apply .......................... Apply changes from last stash.
- git stash apply stash@{n} ................ Applies changes to a specific stash without removing it from the list of stashes.
- git stash pop ............................ Applies and removes the last stash.
- git stash pop stash@{n} .................. Applies changes to a specific stash and removing it from the list of stashes.
- git stash list ........................... Show the stash list.
- git stash drop ........................... Delete the last stash.
- git stash drop stash@{n} ................. Remove a particular stash from the stash list.
- git stash show ........................... Show changes in most recent stash.
- git stash show stash@{1} -p .............. Inspect a particular stash.
- git stash clear .......................... Delete all stash.


