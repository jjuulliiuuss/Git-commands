Git-Commands

1)
git branch feature_x
git checkout master
git push -u origin feature_x (unit test)
(if passed) git pull origin master
git merge feature_x
git push origin master
git branch -d feature_x

2)
git cherry-pick (copy commit from one branch to another, e.g. if commit was done in wrong branch,e.g. committed in master, but should have to in feature_x, does not delete that commit in master!)
git checkout file_x (if added, but not committed yet/ resets that file to last commit)
git commit —amend “new description”
git commit —amend (includes new added changes into last commit)
do both only if not yet pushed to remote repo! because it changes the history
git reset —soft target-commit-hash-beginning (current changes remain added, e.g. into staging area)
git reset —mixed target-commit-hash-beginning (current changes into working directory)
git reset —hard (deletes changes, not tracked files get not deleted)
git clean -df (cleans all untracked files)
git checkout target-commit-hash-beginning (,e,g. from the hashes of git reflog, detaches HEAD state. Make a branch from there. To return to master, use git checkout master)
git revert target-commit-hash-beginning (to add a new commit that undo that commit, advantage: it does not change the history, very good if already pushed to remote or others already pulled)


general)
git status
git log
git reflog
git branch -a
git diff (also with two hashes)

3)
stash idea:
when switching from current (e.g. feature_x) branch to another branch (e.g. master) (to check things and not want to save (aka commit) current progress, but also not loose it: Also when you have made changes in one branch and want to carry them over in another branch, just stash and in the target branch> git stash pop
git stash save “message text”
git stash list
git stash apply stash_id (from stash list) (doesn’t get rid of stash though/ still in list then)
git stash pop  > grabs first item in stash list> applies it and drops it from the list
git stash drop stash_id , removes a stash
git stash clear > removes all stashes
 
4)
git add -A (entire working tree, actually default behaviour of git add> git add -A == —all, also with directories
git add -u (adds all of the modified and deleted files, but none of the untracked files -u == —update, also with directories

if in top directory, git add . is the same as git add -A, but if your in one of the folder (e.g. cd folder_x/), than git add . only catches everything down from there. git add -A add all the changes in the working tree, indenpently where one is atm.

