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

### remote: Permission to aamir9138/nodejs_vishwas_course.git denied to Aamirmuhammad91. fatal: unable to access 'https://github.com/aamir9138/nodejs_vishwas_course.git/': The requested URL returned error: 403

```
  1) create personal access token
  2) git remote set-url origin https://<personal_Access_Token>@github.com/aamir9138/nodejs_vishwas_course
```
