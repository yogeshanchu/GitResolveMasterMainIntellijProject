local has Repo ABC and has files.
Commits are already checked in master branch

remote has Repo ABC created after the local repo
has files and default branch is "main"

Master branch was pushed to remote, so it was created as a separate branch.

How to now push master changes to main on remote, delete master. Also take in any changes done on main on remote repo into local repo


#check or checkout master branch
git branch -a
git checkout master
#rename master to main
git -m main
#rename symoblic refs (git HEAD file refs) to main typically automatically done on rename
git symbolic-ref HEAD refs/heads/main
#get all remote online changes from remote (origin) main branch on to local main
git pull --rebase origin main
git push -u origin main
git push https://github.com/yogeshanchu/ABC.git --delete master

#in case your branch was based off master and master was deleted
git branch --unset-upstream
