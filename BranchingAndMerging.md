# Git Branching and Merging #

When working with the npr-android-app code you should create a branch for a feature and someone else should merge it. It's considered bad form to merge your own code and it should be reviewed before it's committed to master.

## Identify or report an issue to the project owner ##
Create a new issue or select an existing issue to address.  It's helpful to inform the project owner that you're working on the issue.

## Starting work ##
When you start work on a feature, create a branch:

```
git checkout -b feature-name
```

## Finishing a feature ##

When it is ready for merging:

  1. Mark the story as "Fixed" in the Issues list
  1. Attach a link to your remote branch with your changes and notify the list. Once the branch has been reviewed and any changes made that are necessary, it is ready to be merged into the master branch.

## Merging a branch and delivering the issue ##

To merge someone's branch:

### Fetch the code ###

```
git fetch
```

### Perform the merge ###

_Make sure you have no unstaged changes before proceeding_

```
git status
```

When merging into master, use a non-fast-forward merge:

```
git checkout master
git reset --hard origin/master
git clean -f
git merge origin/feature-name --no-ff
```

_At this point you may need to fix any merge conflicts._

### Push the code ###

When ready, push to google code:

```
git push origin master
```

### Mark this in the issue ###

Now, very important: Go get the issue tracker and add comment "Commit: ..." with a link to the commit.

Then mark the story as "fixed"

### Cleaning up ###

After the story owner approves the story, you can delete the feature branch.

Deleting a remote branch:

```
git push origin :feature-branch
```