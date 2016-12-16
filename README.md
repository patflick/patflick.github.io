To build and deploy after changes run the following in the `source` branch:

NOTE: Make sure to first commit all changes in `source`.

```
make deploy
```

which will do the following:

```
bundle exec jekyll build
git stash
git checkout master
cp -rf _site/* ./
rm -rf _site
git add -A .
git commit -m "updates to website"
git push origin master
git checkout source
git stash pop
```
