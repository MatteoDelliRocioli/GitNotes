# Exclude files from git commands

I've tested it with `add`,`diff`,`show`

```
git add -- . ":(exclude)*<insert the name of the file to exclude here>"
```
