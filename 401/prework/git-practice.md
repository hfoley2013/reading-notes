# Git Practice

## Reference

* [Learn Git Branching](https://learngitbranching.js.org/)

## Notes

* `HEAD`
  * Symbolic name for the currently checked out commit
    * The commit you are working on top of
  * Taken from the most recent commit from GitHub
* **Detaching Head**
  * Moves the head from once branch to another
* **Relative Commits**
  * Can travel up the commit tree by using `^` operator or specifying the commit hash
* **Branch Forcing**
  `git branch -f main HEAD~3`
  * The `~` operator specifics the number of relative refs to go back
* `git reset`
  * `git reset HEAD~1`
    * Resets the HEAD back 1 commit
* `git revert`
  * Allows us to reverse changes and shares those reversed changes with others
