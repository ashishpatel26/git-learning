# Git: Zero to Hero

Learning plan. Each phase: concepts, commands to practice, mini-task.

---

## Phase 0 — Setup

- Install Git, run `git --version`
- `git config --global user.name "..."`
- `git config --global user.email "..."`
- `git config --global init.defaultBranch main`
- Learn: working dir vs staging area vs repo (3-tree model)

**Task:** Configure git, verify with `git config --list`.

---

## Phase 1 — Beginner: Local Basics

- `git init`
- `git status`
- `git add <file>` / `git add .`
- `git commit -m "msg"`
- `git log`, `git log --oneline`
- `git diff` (unstaged) vs `git diff --staged`
- `.gitignore`
- `git show <commit>`

**Task:** Create repo, make 5 commits building a small text project (e.g. a README that grows).

---

## Phase 2 — Beginner: Undoing Things

- `git restore <file>` (discard working changes)
- `git restore --staged <file>` (unstage)
- `git commit --amend`
- `git reset --soft/mixed/hard HEAD~1`
- `git revert <commit>`
- Difference: reset (rewrites history) vs revert (adds new commit)

**Task:** Make a bad commit, fix it 3 ways: amend, reset, revert (separate scenarios).

---

## Phase 3 — Intermediate: Branching

- `git branch`, `git branch <name>`
- `git switch <branch>` / `git checkout <branch>`
- `git switch -c <branch>` (create+switch)
- `git merge <branch>` (fast-forward vs 3-way merge)
- Resolving merge conflicts manually
- `git branch -d/-D`
- Branching strategy basics (feature branches)

**Task:** Create 2 branches editing the same line of a file, merge, resolve conflict by hand.

---

## Phase 4 — Intermediate: Remotes

- `git remote add origin <url>`
- `git clone <url>`
- `git push`, `git push -u origin <branch>`
- `git pull` = fetch + merge
- `git fetch` alone
- `git remote -v`
- Push/pull tracking branches

**Task:** Create GitHub repo, push local repo, clone it elsewhere, make change, push/pull sync.

---

## Phase 5 — Intermediate: Collaboration Workflow

- Fork vs clone
- Pull requests (GitHub/GitLab)
- Code review basics via PR
- `git log --graph --oneline --all`
- Handling merge conflicts from PRs
- `.gitignore` templates, `git rm --cached`

**Task:** Open a PR on a personal repo (branch → push → PR → merge on GitHub).

---

## Phase 6 — Advanced: Rewriting History

- `git rebase <branch>` (vs merge)
- Interactive rebase: `git rebase -i HEAD~n` (squash, reword, drop, reorder)
- `git cherry-pick <commit>`
- `git reflog` (recovery net)
- Rebase conflicts, `--continue` / `--abort`
- Golden rule: never rebase shared/public history

**Task:** Squash 4 messy commits into 1 clean commit via interactive rebase. Recover a "lost" commit using reflog.

---

## Phase 7 — Advanced: Inspection & Debugging

- `git blame <file>`
- `git bisect` (binary search for bad commit)
- `git log` filters: `--author`, `--since`, `-p`, `-S"string"` (pickaxe)
- `git stash`, `git stash pop/list/apply/drop`
- `git tag`, annotated vs lightweight tags

**Task:** Use `git bisect` to find a commit that introduced a bug in a small script repo.

---

## Phase 8 — Advanced: Internals

- Git objects: blob, tree, commit, tag
- `.git` directory structure
- `git cat-file -p <hash>`
- How commits form a DAG (content-addressable storage, SHA-1/256)
- `git gc`, `git fsck`
- Refs, HEAD, detached HEAD state

**Task:** Manually inspect `.git/objects`, decode a blob/tree/commit with `git cat-file`.

---

## Phase 9 — Advanced: Multi-repo & Large Projects

- Submodules: `git submodule add/update`
- Subtrees (alternative to submodules)
- Monorepo basics, sparse-checkout
- `git worktree` (multiple working dirs, one repo)
- Large file handling: Git LFS

**Task:** Add a submodule to a repo, update it, understand detached HEAD inside submodule.

---

## Phase 10 — Hero: Workflow Mastery

- Git workflows: GitHub Flow, Git Flow, Trunk-Based Development
- Commit message conventions (Conventional Commits)
- Signing commits (GPG/SSH), `git commit -S`
- Hooks: pre-commit, commit-msg, pre-push (`.git/hooks`, or Husky)
- `git config` aliases for speed
- Rewriting entire history: `git filter-repo` (removing secrets/large files)
- Resolving hard rebase/merge conflict scenarios under pressure

**Task:** Set up a pre-commit hook that blocks commits with a forbidden keyword. Configure 3 custom aliases.

---

## Practice Resources

- learngitbranching.js.org — interactive visual practice (branching/rebase)
- Real repo: contribute to small open-source project (find "good first issue")
- Build a personal project, use full workflow (branches, PRs, rebase, tags, releases)

---

## Progress Checklist

- [ ] Phase 0 — Setup
- [ ] Phase 1 — Local Basics
- [ ] Phase 2 — Undoing Things
- [ ] Phase 3 — Branching
- [ ] Phase 4 — Remotes
- [ ] Phase 5 — Collaboration
- [ ] Phase 6 — Rewriting History
- [ ] Phase 7 — Inspection & Debugging
- [ ] Phase 8 — Internals
- [ ] Phase 9 — Multi-repo
- [ ] Phase 10 — Workflow Mastery
