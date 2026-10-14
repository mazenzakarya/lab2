/*What I use*/
 git init => for create local git
 git add . => for stagging
 git commit -m "lab2" => for commiting what we add
  git remote add origin git@github.com:mazenzakarya/lab2.git => to connect local to remote
$ git push origin main=> to push the changes to main
$ git branch dev
$ git branch test
$ git add .=> stagging all files on test branch
$ git commit -m "feat: add files on test" => commit all changes to test branch
$ git push origin test => to push files on test
$ git switch main
$ git merge dev
$ git reset HARD^ => due to mistake by me
$ git merge test
$ git switch main
$ git merge dev
$ git push origin main
$ git switch main
$ git tag -a v1.0.0 -m "Release version 1.0.0" => to add tages
$ git push origin --tags => to push tages to remote
$ git add . => to add files to stage
$ git commit -m "add img to readme"
$ git push origin main => to push images
====================================================
● Tell me how to remove them locally and remotely.
git branch -d test => delete tst branch locally
$ git push origin --delete test => to delete from remote

● Tell me how to checkout another branch without commit
changes
git stash -u
git stash pop

● Tell me how to delete tag locally and remotely.
$ git tag -d  v1.0.0 => delete tag locally
Deleted tag 'v1.0.0' (was 6d830d7)

$ git push origin --delete v1.0.0 => to remove tags from orgin

<img src="src/x4-3.jpeg">