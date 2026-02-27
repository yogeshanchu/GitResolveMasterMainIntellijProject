Readme.md original

This repo is just a test to resolve the master vs main branch issue in Git. 
Github creates the default branch as main, whereas intellij / git adds master as the default branch. This means you cannot really merge these two as they are different orgin commit histories. i.e. one is not branched off from the other

The step missing on the internet is that you need to checkout the main branch after you have deleted the master (step 3 below). And then rebase your local branch onto origin / main

git branch -m master main
git push -u origin main
git push origin --delete master
