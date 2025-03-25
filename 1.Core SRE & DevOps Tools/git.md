# 🧱 Section A: Git

## ✅ 1. Introduction

Git is a distributed version control system (VCS) designed to handle everything from small to very large projects with speed and efficiency. It allows multiple developers to collaborate on code in a non-linear workflow. Git is the backbone of modern software development and a foundational tool for DevOps and SRE practices.

---

## ✅ 2. Key Components

- **Repository** – A project folder initialized with Git tracking.
- **Commit** – A snapshot of staged changes.
- **Branch** – A separate line of development.
- **Merge** – Integrates changes from one branch to another.
- **Remote** – A version of the project hosted on another system (e.g., GitHub, GitLab).
- **Index (Staging Area)** – Where changes are prepared before committing.
- **HEAD** – Pointer to the current branch reference.

---

## ✅ 3. Common Commands

| Command | Description |
|---------|-------------|
| `git init` | Initialize a new Git repository. |
| `git clone <url>` | Clone a repository from a remote. |
| `git status` | Show the working tree status. |
| `git add <file>` | Stage changes for commit. |
| `git commit -m "msg"` | Commit staged changes. |
| `git log` | View commit history. |
| `git diff` | Show changes between commits or working directory. |
| `git branch` | List, create, or delete branches. |
| `git checkout <branch>` | Switch branches or restore files. |
| `git merge <branch>` | Merge a branch into the current one. |
| `git pull` | Fetch and integrate from remote. |
| `git push` | Upload local commits to remote. |

---

## ✅ 4. Pros & Cons

### ✅ Pros:
- Distributed and highly available
- Branching and merging are fast and reliable
- Powerful tooling and integrations (GitHub, GitLab, Bitbucket)
- Large community and support ecosystem
- Enables CI/CD pipelines and GitOps

### ❌ Cons:
- Can be confusing for beginners (merge conflicts, rebases)
- Complex workflows can lead to mistakes if not documented
- History rewriting can be dangerous in shared branches

---

✅ Git is essential for collaboration, automation, and version tracking in SRE, DevOps, and software engineering environments.

# 🧱 Section B: Git Interview Prep – Basic Questions (40)

This section covers 40 basic Git interview questions with answers and examples. These help build foundational understanding of Git concepts and commands.

---

### ✅ 1. What is Git?
Git is a distributed version control system used to track changes in source code and coordinate work among developers.

---

### ✅ 2. What is the difference between Git and GitHub?
- **Git** is the version control system.
- **GitHub** is a hosting service for Git repositories with collaboration features.

---

### ✅ 3. How do you initialize a Git repository?
```bash
$ git init
```

---

### ✅ 4. How do you clone a remote Git repository?
```bash
$ git clone https://github.com/user/repo.git
```

---

### ✅ 5. How do you check the status of your working directory?
```bash
$ git status
```

---

### ✅ 6. How do you stage a file for commit?
```bash
$ git add filename.txt
```

---

### ✅ 7. How do you commit changes?
```bash
$ git commit -m "Initial commit"
```

---

### ✅ 8. How do you check the commit history?
```bash
$ git log
```

---

### ✅ 9. How do you view a list of branches?
```bash
$ git branch
```

---

### ✅ 10. How do you create a new branch?
```bash
$ git branch feature-x
```

---

### ✅ 11. How do you switch to another branch?
```bash
$ git checkout feature-x
```

---

### ✅ 12. How do you create and switch to a new branch at once?
```bash
$ git checkout -b new-feature
```

---

### ✅ 13. How do you delete a local branch?
```bash
$ git branch -d feature-x
```

---

### ✅ 14. How do you merge a branch?
```bash
$ git merge feature-x
```

---

### ✅ 15. How do you view changes made but not staged?
```bash
$ git diff
```

---

### ✅ 16. How do you view changes that have been staged?
```bash
$ git diff --cached
```

---

### ✅ 17. How do you undo changes in a file (unstaged)?
```bash
$ git checkout -- filename.txt
```

---

### ✅ 18. How do you remove a file from staging?
```bash
$ git reset filename.txt
```

---

### ✅ 19. How do you remove a file from the repository?
```bash
$ git rm filename.txt
```

---

### ✅ 20. How do you rename a file?
```bash
$ git mv old.txt new.txt
```

---

### ✅ 21. How do you fetch changes from a remote repository?
```bash
$ git fetch origin
```

---

### ✅ 22. How do you pull changes and merge?
```bash
$ git pull
```

---

### ✅ 23. How do you push changes to a remote repository?
```bash
$ git push origin main
```

---

### ✅ 24. What is the HEAD in Git?
It is a pointer to the current branch reference.

---

### ✅ 25. How do you view the remote URL?
```bash
$ git remote -v
```

---

### ✅ 26. How do you add a new remote?
```bash
$ git remote add origin https://github.com/user/repo.git
```

---

### ✅ 27. How do you remove a remote?
```bash
$ git remote remove origin
```

---

### ✅ 28. What is a conflict in Git?
Occurs when merging branches with incompatible changes to the same file.

---

### ✅ 29. How do you resolve a merge conflict?
- Manually edit the file
- Stage changes: `git add`
- Complete merge: `git commit`

---

### ✅ 30. How do you check the commit difference between branches?
```bash
$ git log branch1..branch2
```

---

### ✅ 31. How do you stash changes?
```bash
$ git stash
```

---

### ✅ 32. How do you apply the latest stash?
```bash
$ git stash apply
```

---

### ✅ 33. How do you list stashed changes?
```bash
$ git stash list
```

---

### ✅ 34. How do you delete all stashes?
```bash
$ git stash clear
```

---

### ✅ 35. How do you reinitialize a Git repo without losing files?
```bash
$ rm -rf .git
$ git init
```

---

### ✅ 36. How do you tag a commit?
```bash
$ git tag v1.0.0
```

---

### ✅ 37. How do you push tags?
```bash
$ git push origin --tags
```

---

### ✅ 38. How do you remove a tag?
```bash
$ git tag -d v1.0.0
```

---

### ✅ 39. How do you undo the last commit?
```bash
$ git reset --soft HEAD~1
```

---

### ✅ 40. How do you check who modified a line in a file?
```bash
$ git blame filename.txt
```

---

✅ Next: Intermediate Git Questions  
Let me know when you're ready!

# 🧱 Section B: Git Interview Prep – Intermediate Questions (40)

This section covers 40 intermediate Git interview questions with explanations and real-world usage examples.

---

### ✅ 1. What is the difference between `git fetch` and `git pull`?
- `git fetch`: downloads new data from remote but doesn’t merge.
- `git pull`: fetches and merges changes in one step.

---

### ✅ 2. How do you configure Git with username and email?
```bash
$ git config --global user.name "Your Name"
$ git config --global user.email "your@example.com"
```

---

### ✅ 3. What is a detached HEAD?
When `HEAD` points to a specific commit instead of a branch.

---

### ✅ 4. How do you undo a commit that has already been pushed?
- Use `git revert` to create a new commit that undoes the changes:
```bash
$ git revert <commit>
```

---

### ✅ 5. What is the difference between `git reset` and `git revert`?
- `git reset`: moves HEAD and can remove commits.
- `git revert`: creates a new commit to reverse changes.

---

### ✅ 6. How do you squash commits?
```bash
$ git rebase -i HEAD~3
```

---

### ✅ 7. How do you edit a commit message after committing?
```bash
$ git commit --amend
```

---

### ✅ 8. How do you see the commit graph?
```bash
$ git log --oneline --graph --all
```

---

### ✅ 9. How do you cherry-pick a commit?
```bash
$ git cherry-pick <commit_hash>
```

---

### ✅ 10. How do you compare two branches?
```bash
$ git diff branch1..branch2
```

---

### ✅ 11. What’s the difference between `origin` and `upstream`?
- `origin`: the default remote repository.
- `upstream`: typically used to track the original repo in forks.

---

### ✅ 12. How do you set a remote tracking branch?
```bash
$ git branch --set-upstream-to=origin/main
```

---

### ✅ 13. What is `git clean` used for?
Removes untracked files and directories.
```bash
$ git clean -fd
```

---

### ✅ 14. What is a `.gitignore` file?
A file that lists patterns of files/directories Git should ignore.

---

### ✅ 15. How do you ignore file permission changes in Git?
```bash
$ git config core.fileMode false
```

---

### ✅ 16. How do you rename a branch?
```bash
$ git branch -m old-name new-name
```

---

### ✅ 17. How do you delete a remote branch?
```bash
$ git push origin --delete branch-name
```

---

### ✅ 18. How do you configure Git aliases?
```bash
$ git config --global alias.co checkout
```

---

### ✅ 19. What’s the difference between `HEAD`, `origin/HEAD`, and `FETCH_HEAD`?
- `HEAD`: current branch
- `origin/HEAD`: default remote branch
- `FETCH_HEAD`: last fetched branch reference

---

### ✅ 20. How do you list files in a specific commit?
```bash
$ git ls-tree --name-only -r <commit_hash>
```

---

### ✅ 21. How do you revert a file to a previous commit?
```bash
$ git checkout <commit_hash> -- file.txt
```

---

### ✅ 22. How do you unstage all files?
```bash
$ git reset
```

---

### ✅ 23. How do you remove all local branches that have been deleted remotely?
```bash
$ git fetch -p
```

---

### ✅ 24. How do you check which branch you’re on?
```bash
$ git branch --show-current
```

---

### ✅ 25. How do you make a Git repo bare?
```bash
$ git init --bare
```

---

### ✅ 26. What is the staging area in Git?
A space where changes are collected before committing.

---

### ✅ 27. How do you list all tags?
```bash
$ git tag
```

---

### ✅ 28. How do you check changes in a specific commit?
```bash
$ git show <commit_hash>
```

---

### ✅ 29. What is a fast-forward merge?
A merge where the current branch can move forward without needing a new commit.

---

### ✅ 30. How do you prevent fast-forward merges?
```bash
$ git merge --no-ff <branch>
```

---

### ✅ 31. What is the reflog?
Shows the history of where HEAD and branch references have been.

```bash
$ git reflog
```

---

### ✅ 32. How do you recover a deleted branch?
```bash
$ git reflog
$ git checkout -b branch-name <commit_hash>
```

---

### ✅ 33. How do you configure Git to cache credentials?
```bash
$ git config --global credential.helper cache
```

---

### ✅ 34. How do you archive a Git repository?
```bash
$ git archive --format=zip HEAD > repo.zip
```

---

### ✅ 35. How do you make a shallow clone?
```bash
$ git clone --depth=1 <repo>
```

---

### ✅ 36. How do you revert a merge commit?
```bash
$ git revert -m 1 <merge_commit_hash>
```

---

### ✅ 37. How do you check the size of your Git repo?
```bash
$ git count-objects -vH
```

---

### ✅ 38. What is the difference between `tracked` and `untracked` files?
- Tracked: files added to Git and monitored for changes.
- Untracked: files in the working directory not added to Git.

---

### ✅ 39. How do you work with submodules?
```bash
$ git submodule add <repo>
$ git submodule update --init
```

---

### ✅ 40. How do you view configuration settings?
```bash
$ git config --list
```

---

✅ Next: Advanced Git Questions  
Let me know when you're ready!

# 🧱 Section B: Git Interview Prep – Advanced Questions (40)

This section presents 40 advanced Git interview questions focused on real-world Git internals, workflows, and troubleshooting techniques for experienced engineers.

---

### ✅ 1. What is the difference between `git reset`, `git checkout`, and `git revert`?
- `reset`: moves HEAD and optionally modifies index and working tree
- `checkout`: switches branches or restores files
- `revert`: creates a new commit to undo changes

---

### ✅ 2. How does Git store data internally?
Git stores content as snapshots, not diffs. Each file is saved as a blob in a content-addressable filesystem.

---

### ✅ 3. What are Git objects?
Four main types: `blob`, `tree`, `commit`, and `tag`.

---

### ✅ 4. What is a Git hook?
Custom scripts triggered by specific Git events like `pre-commit`, `pre-push`, etc.

---

### ✅ 5. How do you enforce commit message format?
Use a `commit-msg` hook to validate messages.

---

### ✅ 6. What’s the purpose of the `index` in Git?
The staging area – a middle ground between the working directory and the repository.

---

### ✅ 7. How can you bisect a bug in Git?
```bash
$ git bisect start
$ git bisect bad
$ git bisect good <commit>
```

---

### ✅ 8. How do you use Git in CI/CD pipelines?
Automate builds, tests, and deployments using Git commit/merge triggers and hooks.

---

### ✅ 9. How do you sign commits or tags?
```bash
$ git commit -S -m "Signed commit"
$ git tag -s v1.0 -m "Signed tag"
```

---

### ✅ 10. What is Git rerere?
Records how you resolved a conflict and reuses it in future.

---

### ✅ 11. How can you reduce Git repository size?
- Use `git gc`
- Remove large files
- Use `.gitignore` and `.git/info/exclude`

---

### ✅ 12. What is the `ORIG_HEAD`?
Reference to the previous HEAD before dangerous operations like merge or rebase.

---

### ✅ 13. What’s the difference between annotated and lightweight tags?
- Annotated: stored as full Git objects with metadata
- Lightweight: just a pointer to a commit

---

### ✅ 14. How do you undo a `git rebase`?
Use:
```bash
$ git reflog
$ git reset --hard <previous_commit>
```

---

### ✅ 15. How do you keep forks in sync with upstream?
```bash
$ git remote add upstream <url>
$ git fetch upstream
$ git rebase upstream/main
```

---

### ✅ 16. How do you detect and clean orphaned objects?
```bash
$ git fsck --full
$ git prune
```

---

### ✅ 17. What is `git filter-branch` used for?
Rewriting Git history, including removing sensitive data.

---

### ✅ 18. What is BFG Repo-Cleaner?
A faster alternative to `git filter-branch` for rewriting Git history.

---

### ✅ 19. How do you recover lost commits?
Use `reflog` to find and reset to them.

---

### ✅ 20. What are shallow clones and why use them?
Clones with limited history. Use `--depth` to speed up cloning large repos.

---

### ✅ 21. What is `git worktree`?
Allows multiple working directories attached to the same repo.

---

### ✅ 22. How can you detect and avoid merge conflicts early?
Use:
```bash
$ git fetch
$ git merge-base HEAD origin/main
$ git diff <merge-base> HEAD
```

---

### ✅ 23. How do you protect a branch in GitHub/GitLab?
Enable branch protection rules: no force pushes, require PRs, signed commits, etc.

---

### ✅ 24. What is a rebase interactive (`-i`) used for?
- Rewriting commit history
- Squashing, rewording, reordering commits

---

### ✅ 25. How do you preserve merges when rebasing?
Use:
```bash
$ git rebase --preserve-merges
```

---

### ✅ 26. What is `subtree` in Git?
A way to include and manage a subproject within a repository.

---

### ✅ 27. How do you migrate a repository with full history?
```bash
$ git clone --mirror
```

---

### ✅ 28. What is the `HEAD~1`, `HEAD^`, `HEAD@{1}` syntax?
- `HEAD~1`: first parent
- `HEAD^`: parent (same as ~1)
- `HEAD@{1}`: reflog entry 1 step ago

---

### ✅ 29. How do you rename a Git tag?
```bash
$ git tag new-tag old-tag
$ git tag -d old-tag
$ git push origin :refs/tags/old-tag
$ git push origin new-tag
```

---

### ✅ 30. What is Git submodule and how is it different from subtree?
Submodule is a pointer to an external repo. Subtree actually copies the code into your project.

---

### ✅ 31. How do you fix a broken rebase?
```bash
$ git rebase --abort
```

---

### ✅ 32. What is `git fsck`?
Verifies integrity of Git objects.

---

### ✅ 33. How do you stash untracked files?
```bash
$ git stash -u
```

---

### ✅ 34. What is `GIT_DIR` and `GIT_WORK_TREE`?
Environment variables to separate the `.git` folder and working directory.

---

### ✅ 35. How do you automate Git operations in scripts?
Use silent flags like `-q` and handle errors using exit codes and `set -e`.

---

### ✅ 36. What is the difference between `git show` and `git log`?
- `git show`: details of one commit
- `git log`: history view

---

### ✅ 37. What is `git blame` used for?
Shows line-by-line authorship of a file.

---

### ✅ 38. How do you inspect the content of a Git object?
```bash
$ git cat-file -p <object_hash>
```

---

### ✅ 39. How do you backup a Git repository?
Use `git bundle`:
```bash
$ git bundle create repo.bundle --all
```

---

### ✅ 40. How do you run a dry-run of a Git command?
Use `--dry-run` flag, e.g.:
```bash
$ git clean -fd --dry-run
```

---

✅ Next: Git Scenario-Based Questions  
Let me know when you're ready!

# 🧱 Section B: Git Interview Prep – Scenario-Based Questions (25)

This section presents 25 real-world Git scenarios, including practical challenges and solutions typically encountered by DevOps engineers, SREs, and developers.

---

### ✅ 1. You accidentally committed sensitive data. What do you do?
Use `git filter-branch` or BFG Repo-Cleaner to remove it from history, then force push and invalidate the compromised credentials.

---

### ✅ 2. You need to submit a feature branch but squash all commits. How?
```bash
$ git rebase -i main
# Mark all but the first commit as 'squash'
$ git push --force
```

---

### ✅ 3. You want to rebase a long-lived branch without losing changes. Steps?
- Commit or stash your work
- Run:
```bash
$ git fetch origin
$ git rebase origin/main
```
- Resolve conflicts, test, then push with `--force-with-lease`.

---

### ✅ 4. You pushed to the wrong branch. How do you fix it?
```bash
$ git checkout correct-branch
$ git cherry-pick <bad_commit>
$ git push origin correct-branch
$ git reset --hard HEAD~1
$ git push origin wrong-branch --force
```

---

### ✅ 5. A colleague deleted a branch with unmerged work. Recovery?
```bash
$ git reflog
$ git checkout -b recovered-branch <commit_hash>
```

---

### ✅ 6. You merged the wrong feature into `main`. Undo?
```bash
$ git revert -m 1 <merge_commit>
```

---

### ✅ 7. You cloned a large repo and want to reduce size. What to do?
Use a shallow clone:
```bash
$ git clone --depth=1 <repo>
```

---

### ✅ 8. A build fails after a merge. How do you debug?
- Use `git log` and `git diff` to find changes
- Use `git bisect` to isolate the breaking commit

---

### ✅ 9. You want to see who introduced a bug in a file. What do you use?
```bash
$ git blame app.py
```

---

### ✅ 10. You have multiple local branches no longer in use. Clean them?
```bash
$ git branch --merged main
$ git branch -d <old-branches>
```

---

### ✅ 11. You stashed changes and your system crashed. Recover?
```bash
$ git stash list
$ git stash apply stash@{0}
```

---

### ✅ 12. A tag was created on the wrong commit. Fix?
```bash
$ git tag -d v1.0
$ git tag v1.0 <correct_commit>
$ git push --force origin v1.0
```

---

### ✅ 13. Remote changes conflict with your local commits. What now?
```bash
$ git pull --rebase
```
Resolve conflicts and continue rebase.

---

### ✅ 14. You want to contribute to an open-source repo. How?
- Fork → Clone → Create branch → Commit → Push → Pull Request

---

### ✅ 15. You want to sync your fork with upstream.
```bash
$ git remote add upstream <url>
$ git fetch upstream
$ git rebase upstream/main
```

---

### ✅ 16. You need to submit a patch without pushing to remote.
```bash
$ git format-patch -1
```

---

### ✅ 17. You accidentally committed debug logs. Remove them?
- Add to `.gitignore`
- Remove from cache:
```bash
$ git rm --cached debug.log
```

---

### ✅ 18. You want to apply a single file from another branch.
```bash
$ git checkout other-branch -- path/to/file
```

---

### ✅ 19. How do you test a pre-commit hook?
Run the script manually or use:
```bash
$ git commit --allow-empty
```

---

### ✅ 20. You want to track a remote branch you didn’t have before.
```bash
$ git checkout -t origin/feature-xyz
```

---

### ✅ 21. A CI/CD job fails on pull request due to history rewrite. What next?
- Use `git pull --rebase`
- Rebase your PR branch on top of `main`

---

### ✅ 22. You want to quickly view commit history of a file.
```bash
$ git log --oneline path/to/file
```

---

### ✅ 23. Git is prompting for username/password. Use SSH instead?
- Generate SSH key
- Add it to GitHub/GitLab
- Change remote:
```bash
$ git remote set-url origin git@github.com:user/repo.git
```

---

### ✅ 24. You pushed WIP commits and want to clean history. How?
```bash
$ git rebase -i origin/main
# Squash or fixup commits, then force push
```

---

### ✅ 25. Git merge conflict keeps recurring. How do you resolve permanently?
Enable rerere:
```bash
$ git config --global rerere.enabled true
```

---

✅ Next: Section C – Best Practices & Considerations for Git

# 🧱 Section C: Git – Best Practices & Considerations

This section outlines best practices for using Git effectively and safely in team environments, especially relevant for DevOps, SREs, and developers managing production-grade infrastructure or codebases.

---

## ✅ 1. General Best Practices

- **Commit often** with meaningful messages.
- **Use feature branches** for new work instead of committing directly to `main`.
- **Keep branches short-lived** to reduce merge conflicts.
- **Use `.gitignore` wisely** to prevent committing temporary or sensitive files.
- **Don’t commit secrets or credentials**. Use environment variables or secret managers.

---

## ✅ 2. Commit Message Guidelines

- Follow a standard format:
  ```
  <type>(<scope>): <short description>
  
  [Optional body: detailed explanation]
  ```
- Use types like `feat`, `fix`, `chore`, `refactor`, `docs`, `test`.
- Keep the summary line under 50 characters.

---

## ✅ 3. Merging & Rebasing

- Prefer **fast-forward merges** for simple changes.
- Use **merge commits** for feature integration and clarity in history.
- **Avoid rebasing shared branches**.
- **Squash commits** for clean history before merging PRs.

---

## ✅ 4. Collaboration & Remotes

- **Pull before you push** to minimize conflicts.
- **Review code before merging** using Pull Requests or Merge Requests.
- **Use protected branches** to enforce quality checks like CI/CD and reviews.
- **Sync your fork regularly** with upstream repositories.

---

## ✅ 5. Large Repositories & Performance

- Use **shallow clones** for CI/CD if full history isn’t needed.
- Run `git gc` and `git prune` periodically.
- Avoid tracking large binary files; use Git LFS if necessary.

---

## ✅ 6. Safety & Recovery

- Enable `git rerere` to help with repeated conflict resolution.
- Use `reflog` to recover lost commits or branches.
- Test history-rewriting commands (`reset`, `rebase`, `filter-branch`) in non-production environments.

---

## ✅ 7. Automation & Hooks

- Leverage **Git hooks** to enforce commit message format, run linters/tests, or validate files.
- Use `pre-push` hooks to prevent pushing broken or large code.

---

## ✅ 8. Tagging & Releases

- Use **annotated tags** for production releases:
  ```bash
  git tag -a v1.0 -m "Release 1.0"
  ```
- Push tags explicitly:
  ```bash
  git push origin --tags
  ```

---

## ✅ 9. Working in Teams

- Establish a **branching strategy** (Git Flow, GitHub Flow, trunk-based).
- Enforce **CI/CD pipelines** on every merge/push.
- Document your Git workflow for onboarding and collaboration.

---

## ✅ 10. Security & Compliance

- Never store secrets in Git. Use `.gitignore` and secret scanners.
- Periodically audit repos for sensitive data using tools like `git-secrets`.
- Consider signed commits and tags (`git commit -S`, `git tag -s`) for trust and verification.

---

✅ These practices help ensure Git usage is secure, efficient, and team-friendly.
