
## Git Magic 

###### Tutorial by Ben Lynn

### Saving State - restore the pristine version 
About to attempt something drastic? Before you do, take a snapshot of all files in the current directory with: 
`git add . `, `git commit -m "my first back up"`, 
if the drastic edits go awry, restore the pristine version with `git reset --hard`. 
To save the state again: 
`git commit -a -m "another backup`

