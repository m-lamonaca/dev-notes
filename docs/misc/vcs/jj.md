# Jujustsu (`jj`)

## Common Commands

### Status & Log

`jj status`: show current status of the working copy  
`jj log -r|--revisions <revset>`: show commits of a given revset  
`jj log -r|--revisions ::@`: show all ancestors of the working copy  

### Showing Changes

`jj show [<revset>]`: show changes in `<revset>`, compared to its parents  
`jj diff [-f|--from <revset>] [-t|--to <revset>]`: compare file contents between revisions  

### Describing & Creating Commits

`jj describe -m|--message <message> <revset>`: add a description to the working copy  
`jj new <revset> -m|--message <message>`: create a new commit after `<revset>` with the given description  
`jj commit -m|--message <message>`: create and describe a new commit in a single command  

### Deleting Commits

`jj abandon <revset>`: delete the revision `<revset>`  

### Merging Commits

`jj new <revset-1> <revset-2> ...`: create a new commit after listed parents  

### Rebasing Commits

`jj rebase --source <source> --destination <destination>`: rebase `<source>` and descendants onto `<destination>`  
`jj rebase --source <source> --after <destination>`: insert `<source>` and descendants after `<destination>`  
`jj rebase --source <source> --before <destination>`: insert `<source>` and descendants before `<destination>`  

### Squashing & Splitting Commits

`jj squash [-i|--interactive]`: move changes from current revision (`@`) into its parent  
`jj squash -f|--from <source> -t|--to <destination>`: move changes from `<source>` into `<destination>`  

`jj split [-i|--interactive]`: split a revision in two  

### Signing Commits

`jj sign --key <signing-key> -r|--revisions <revset>`: cryptographically sign a revision  

### Managing Bookmarks

`jj bookmark set <bookmark> --to <revset>`: create or update a bookmark to point to a certain commit  
`jj bookmark move <bookmark> --to <revset> [--allow-backwards]`: move bookmark `<bookmark>` to point to `<revset>`  
`jj bookmark create <bookmark> --to <revset>`: create `<bookmark>` pointing to `<revset>`  

## Git Commands

`jj git init --colocate`: init a colocated jj/git repository  
`jj git fetch`: fetch changes from the remote git repository  
`jj git push`: push changes to git  

## Operations

`jj undo [<operation>]`: undo an operation  
`jj operation log`: show list of operations taken  
