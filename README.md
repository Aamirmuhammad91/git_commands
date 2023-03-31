# git_commands

## How to checkout to a remote branch

```
  git branch -v -a
  // if the remote is not present
  git fetch
  git branch -v -a
  //so if we have a branch remotely but not locally
  git switch -c test origin/test
```

---

## remote: Permission to aamir9138/nodejs_vishwas_course.git denied to Aamirmuhammad91. fatal: unable to access 'https://github.com/aamir9138/nodejs_vishwas_course.git/': The requested URL returned error: 403

```
  1) create personal access token
  2) git remote set-url origin https://<personal_Access_Token>@github.com/aamir9138/nodejs_vishwas_course
```

---

## if we work in one branch and then realize to commit these changes in another branch

```
git checkout <branchname>
// it will say error: Your local changes to the following files would be overwritten by checkout: so we have to stash it
git stash
git checkout <branchname>
git stash apply
git status
// and we have all the changes
```

---

## Reseting to a point to undo

```
git reflog
git reset --hard a03fe6<commit number upto where you want to rollback>
```

---

## create a new branch and switch to it

```
git switch -c mappings
// push to origin
git push origin
```

## gitlab behind 2 commits problem

```
MuhammadA@NB-WXET1730 MINGW64 ~/Desktop/Terminology-service/terminology-system-config (master)
$ git checkout 247-ontology-suggestion-coypu-ontology-add-to-coypu-collection
git pull
git merge origin/master
git push
```

## Removing commits with secret information

### check this link

1. https://docs.github.com/en/authentication/keeping-your-account-and-data-secure/removing-sensitive-data-from-a-repository

2. check this video "https://www.youtube.com/watch?v=liCAFV8Rmbs". The procedure in this videos is as below.

- git filter-branch --force --index-filter "git rm --cached --ignore-unmatch PATH-TO-YOUR-FILE-WITH-SENSITIVE-DATA(here in my case ./secrets.txt)" --prune-empty --tag-name-filter cat -- --all
- echo "secrets.txt" >> .gitignore
- git add .gitignore
- git commit -m "gitignore committed"
- git push origin --force --all
- git push origin --force --tags
