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

## Filter current branch commits by author

```
git log  --graph --abbrev-commit --decorate  --first-parent --author="matteo"
```
