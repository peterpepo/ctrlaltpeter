# Git

## Configure user / email
```
git config user.name "<Firstname Lastname>"
git config user.email "user@domain.com"
```

## Force push to overwrite remote
Helpful in case of accidental push to origin followed by ammend on local copy.

Please use with care and make sure, that nobody has pulled the change yet, otherwise it leads to conflicts.

Overwriting history, in general, is considered bad practice.

```
git push origin master --force
```
