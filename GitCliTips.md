# Exclude files from git commands

I've tested it with `add`,`diff`,`show`

```
git add -- . ":(exclude)*<insert the name of the file to exclude here>"
```
or

```
git add -- . ":!*<insert the name of the file to exclude here>"
```
--- 

# Find out what commits have you done since a certain date

```
git log  --shortstat --author="Matteo Delli Rocioli" --since="06 May, 2021" --graph --decorate 
```
---

# Make git to temporarly and locally forget about a file change

```
git update-index --assume-unchanged <file-path>
```

and to undo:

```
git update-index --no-assume-unchanged <file-path>
```

---

# Git log only current branch commits

```
git log  --graph --abbrev-commit --decorate  --first-parent
```

> ## Filter current branch commits by author

> ```
> git log  --graph --abbrev-commit --decorate  --first-parent --author="matteo"
> ```

---

# Find string in your commits of a particular branch

- First find the hashes of the commits in where you want to look for the string

```
git log  --graph --abbrev-commit --decorate  --first-parent <your-branch> --author="matteo"
```

- The second step is to use those commit hashes to limit the scope of the string search

```
git show <commit-hash-first-commit>..<commit-hash-last-commit> | grep -C10 "<string-pattern-to-search>"
```

---

# How to count the number of commits since you branched out from main

```
git rev-list --count main..your-branch
```

---

# How to selectively add the signature to remotely pushed commits

```
git rebase -i origin/main # to select which commits to modify among all the commits since branching out from the main branch
# replace the 'pick' word with 'edit' for the commits you need to modify
```

```
git commit --amend --no-edit -S # to apply the signature without changing the commit message, the signature must have already been configured
```

```
git rebase --continue # to continue to the next commit
```

```
git push origin <your-branch-name> --force # to re-write the remote branch history with your signed commits. Please bear in mind that this step is especially delicate as ->
# you want to make sure you are the only one working on that branch and/or the other team members are aligned with what you want to do: everything that was pushed before will not ->
# exist anymore
```
