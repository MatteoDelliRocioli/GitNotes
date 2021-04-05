# `Embrace the CLI power`

<b>NB: </b><br>
- <b>All the commands here displayed must be run in the path where you have cloned your repo</b><br>
- <b>Angle brackets mean that the inner text must be replaced to the text which suits best for your case</b><br>
- <b>The following commands have to be used after a `git fetch` and `git pull` to be accurate</b>
---

## `Want to know where and when a specific file has been modified in the entire repo?` <br>
Type:
> git log --all -- <path/to/file>

A little variant to this can be appling time ranges
> git log --all --since="<2 months ago>" --until="<2 weeks ago>" -- <path/to/file> 

<br>

The previous command output should be something like:

```shell
commit e484800536e5fsdaffsdaf4230095e3fsdafb37e
Author: Matteo Delli Rocioli <myEmail@email.com>
Date:   Fri Dec 4 15:02:13 2020 +0100

    Issue #1: A meaningful commit message

commit e484800536e5fsdaffsdafrwerfs5344230095e3
Author: Matteo Delli Rocioli <myEmail@email.com>
Date:   Thu Jul 30 15:33:12 2020 +0200

    Issue #1: WIP: A meaningful commit message
```
That output can be used for at least two more checks:

1. What changes did a particular commit bring?
2. Which branches have the newly found commit in their history?

For the first case,
## `The changes brought by a particular commit can be seen typing:`
> git show <`commit-complete-hash`> <path/to/file>

<br>

For the latter case, 
## `To find the branches that have a specified commit type:`
> git branch --all --contains <`commit-complete-hash`>
