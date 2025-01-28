# Jujustsu (`jj`)

## Basic Operations

### Status & Log

`jj status`: show current status of the working copy  
`jj log -r|--revisions <revset>`: show commits of a given revset  
`jj log -r|--revisions ::@`: show all ancestors of the working copy  


### Describing & Creating Commits

`jj describe -m|--message <message> <revset>`: add a description to the working copy  
`jj new <revset> -m|--message <message>`: create a new commit after `<revset>` with the given description  

### Merging Commits

`jj new <revset-1> <revset-2> ...`: create a new commit after listed parents
