## Why use git stash?

Git stash is a useful command git offers us to put aside the changes we are currently making on our project.

For example 
1. you are working on a feature branch but your manager calls you because there is a major bug in production env (a bit cathastrophic I know but you get the point :smile:) so you have to quickly change branch before finishing and committing your work
2. you are working on a difficult task and you are trying different strategies to solve the problem thus before trying a new one you want to make sure you can get back on track with the previuos one without committing the changes or having to copy paste the changes in another folder of your system.

In those scenarious `git stash` comes very handy!

## Useful commands

Let's start with the basics: 

### How would you stash your changes?
Use `git stash` in the project path.
That creates a stashed checkpoint in memory of what you where doing.

### But where is it now?

Type `git stash list` to see all the commits you've done. Now you may notice that they already have a name that git automatically creates but what if I tell you that you can call your stash whatever you prefere? So no sooner said than done, you can do that by typing 	`git stash "My stash message"`. 

Used as above though `git stash` only stashes files that are already in the project so if you created a new folder and/or new files you can stash them adding the `-u` option. So a final version of the git stash command can be `git stash -u "My stash message"`.

---

### "Ok mate that's fine but what if I don't remember precisely the changes that I stashed, how can I see them" you could say.

My friend, turns out that there is a simple command for that as well and that is `git stash show 'stash@{<the stash number>}'` for the file names and `git stash show --all 'stash@{<the stash number>}'` to see also the changes in those files. 

The stash number can be seen using the `git stash list` command.

---

### How can I see the contents of a stashed file?

`git show 'stash@{0}:path-to-the-stashed-file-you-want-to-see' > 'path-to-the-file-you-want-to-save-the-contents-in'`

---

### How can I only stash changes from a specific file?

`git stash push -m "<stash-commit-name>" <path-to-file-you-want-to-stash>`

---

I hope you could benefit from this brief guide
