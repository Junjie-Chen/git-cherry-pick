# git cherry-pick

## What is `git cherry-pick`
Apply the changes from one or more existing commits

## Why is `git cherry-pick`
Grab only one commit that developers need and apply its change sets to the topic(feature) branch without merging in all commits

## How is `git cherry-pick`
* `git cherry-pick d4e8411d09` - Apply the change sets of one commit to the current branch
* `git cherry-pick d4e8411d09..57d290ec44` - Apply all commits in the range to the current branch
* `git cherry-pick --edit` - Modify the commit message
* `git cherry-pick --continue` - Save changes after resolving cherry-picking conflicts
* `git cherry-pick --abort` - Stop the cherry-picking operation

### Useful commands for `git cherry-pick`
* `git diff from-commit to-commit > output.diff` - Send the difference bewtween 2 commits into a file ending in `.diff` that is the standard file extension for diff files
* `git apply output.diff` - Apply changes in a diff patch file to the working directory
* `git format-patch 2e33d..655da` - Export all commits in the range and create individual files for each one of these commits
* `git format-patch 2e33d..655da --stdout > feature.patch` - Output patches as a single file
* `git format-patch master` - Export all commits on the current branch which are not in the `master` branch
* `git format-patch master -o feature` - Put patch files into a directory
* `git format-patch -1 655da` - Export a single commit
* `git am feature/0001-some-name.patch` - Apply a single patch
* `git am feature/*.patch` - Apply all patches in a directory
* `git checkout -b new-feature 8527e7a` - Create a topic branch from a particular commit
* `git checkout -- file` - Undo a change to the previous state

#### Difference between a formatted patch and a diff patch
The commit history is inside the patch and therefore can be transferred when the patch is applied.
