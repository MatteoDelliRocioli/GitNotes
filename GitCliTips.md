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
