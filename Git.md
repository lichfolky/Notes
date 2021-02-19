# GIT

To configure the initial branch name to use in all of your new repositories:

```
  git config --global init.defaultBranch <name>
```

Names commonly chosen instead of 'master' are 'main', 'trunk' and 'development'.
The just-created branch can be renamed via this command:
```
  git branch -m <name>
```

```
  git commit --allow-empty -m "msg"
```

```
echo "# web-cv" >> README.md
git init
git add README.md
git commit -m "first commit"
git branch -M main
git remote add origin https://github.com/lichfolky/web-cv.git
git push -u origin main
```

if already exist
```
git remote add origin https://github.com/lichfolky/web-cv.git
git branch -M main
git push -u origin main
```
