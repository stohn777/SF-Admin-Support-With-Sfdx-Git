# Advanced git Commands
## List Files in Branch Diff
`git diff --name-only <other-branch-name>`
## Extract Files in Branch Diff
* Returns the files from the currently checked-out branch.
* Generates `cp` warning for deleted files.
* New files will be included.<br/>
`cp --parents $(git diff --name-only <other-branch-name> [-- <exclusive-folder>]) <existing-directory>`
