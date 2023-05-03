# Advanced git Commands
## List Files in Branch Diff
`git diff --name-only <other-branch-name>`
## Extract Files in Branch Diff
`cp --parents $(git diff --name-only <other-branch-name> [-- <exclusive-folder>]) <existing-directory>`
