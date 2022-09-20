# Git Intro

Source: [Git Tutorial: A Comprehensive Guide](https://blog.udemy.com/git-tutorial-a-comprehensive-guide/)

## Notes

### What is Git?

***Snapshots***

* Git is a Distributed Version Control System (DVCS)
* Creates a snapshot of a file every time you save it (*commit*)

***Local Operations***

* Git allows you to work via local resources, meaning you can continue to code even when not online or connected via a VPN
* Committed files can be uploaded to an online repository via the *push* command once connectivity is reestablished

***Track Changes***

* Git automatically tracks every single change that is made to a file or directory
* It will auto-detect if there is file corruption or loss of information during upload

***Loss of Data***

* Git reduces teh likelihood of data loss by via accidental deletion or due to transmission loss

***States***

* Modified
  * File has been changed, but not committed to the database
* Staged
  * File has been flagged for commitment in the next snapshot (`git add`)
* Committed
  * Data is securely stored in a local database (`git commit`)

![Life Cycle of a File](https://blog.udemy.com/wp-content/uploads/2015/08/image006.png)

### Basic Git Commands

* Getting a File's Status

``` git
$ git status
```

* Tracking & Staging New Files

``` git
$ git add filename (for a single file)
$ git add * (for all files in a repository)
$ git add . (for all files in a directory)
```

* Committing a File

``` git
$ git commit -m "comments on change" (this commits the current file)
$ git commit -a (commits all changes made to tracked files)
```

* Pushing Changes to Online Repository

``` git
$ git push origin master (will push to the master branch on repository on GitHub)
```

* Stashing Changes

  Used when you are not ready to commit changes, but do not want to lose them

``` git
$ git stash (temporarily removes changes and hides them, giving you a clean working directory)

$ git stash apply (retrieves hidden changes)
```

### Remote Repositories

* Cloning Repositories

``` git
$ git clone https://github.com/YOUR-USERNAME/YOUR-REPOSITORY
(this will make a local copy of your Git repository)
```