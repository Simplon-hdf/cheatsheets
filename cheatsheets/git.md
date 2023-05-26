**Cheat Sheet Git et Github**

That cheat sheet is about how to create a git project and how to use a simple version of git.

**1) How to start a repository**

**2) Add, Save & Check**

**3) Send, Receive & Remote**

List all remotes & upstreams
```bash
git remote -v
```

Add an *upstream*, from a fork for example
```bash
git remote add upstream https://github.com/[user]/[project].git
```

Pull from *upstream*
```bash
git fetch upstream
git merge upstream <branch>
```
ou
```bash
git pull upstream <branch>
```

**4) Manage branchs**

**5) Remove, Restore & Revert**

**6) Merge & Rebase**

**7) Upstream**

**8) Compare, Diff & Log**

Display diff between staging area and working directory
```bash
git diff --staged
```

RIGHT OUTER JOIN **branch_A** ON **branch_B**
```bash
git log branch_B..branch_A
git diff branch_B...branch_A
```

Show commit logs with paths that moved *(deleted/moved files)*
```bash
git log --stat -M
```

**9) Others : must know**


