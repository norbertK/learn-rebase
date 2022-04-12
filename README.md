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
new feature f2 from f1
f2.123.txt
checkout f1
f1.234.txt
checkout main
m.45.txt

rebase f2 onto main
