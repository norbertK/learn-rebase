# learn-rebase

trying to understand rebase - finally - perhaps

## looking good

no merge allowed

select feature branch ( git checkout feature )  
git rebase main -i  
git push origin feature --force

pull request

git branch --delete feature  
git branch --delete origin/feature

git branch -r -l  
git fetch -p

## plan

new feature f1 from main
f1.1.txt
commit
new feature f2 from f1
f2.123.txt
commit
checkout f1
f1.234.txt
commit
checkout main
m.45.txt
commit

rebase f2 onto main:
checkout f2
git rebase --onto main f1 f2

soweit so gut - wie kommt das jetzt auf den server?
vscode bietet sync an mit 2up 2down???

> git push origin f2:f2
> To https://github.com/norbertK/learn-rebase.git
> ! [rejected] f2 -> f2 (non-fast-forward)
> error: failed to push some refs to 'https://github.com/norbertK/learn-rebase.git'
> hint: Updates were rejected because the tip of your current branch is behind
> hint: its remote counterpart. Integrate the remote changes (e.g.
> hint: 'git pull ...') before pushing again.
> hint: See the 'Note about fast-forwards' in 'git push --help' for details.

sync geht

f1.1.txt m.45.txt sind jetzt in f2

git rebase main -i  
sync

pull request f2

checkout main
git branch --delete f2
git fetch -p

pull request f1

checkout main
git branch --delete f1
git fetch -p

## plan

new feature feature1 from main
new feature feature2 from main

edit master1.txt in both branches

checkout f1
git rebase main -i  
pull request f1
( der erste ist nur zum Üben, da sich nichts auf main geändert hat, passiert auch nichts )

checkout f2
git rebase main -i  
pull request f2

Auto-merging master1.txt
CONFLICT (content): Merge conflict in master1.txt
error: could not apply 35d9357... feature2
hint: Resolve all conflicts manually, mark them as resolved with
hint: "git add/rm <conflicted_files>", then run "git rebase --continue".
hint: You can instead skip this commit: run "git rebase --skip".
hint: To abort and get back to the state before "git rebase", run "git rebase --abort".
Could not apply 35d9357... feature2

both
git rebase --continue

git branch --delete feature..
