Reece's blog source

This blog is currently implemented with hugo and the clarity theme.


## Notes

### Setup

*Approximately* like this:

```
sudo snap install hugo --channel=extended/stable
hugo new site blog
cd blog
git init
git add .
git commit -am initial

git submodule add https://github.com/chipzoller/hugo-clarity themes/hugo-clarity
cp -a themes/hugo-clarity/exampleSite/* .
git add .
git commit -am "added clarity theme with default content"
```

I also converted toml to yaml because I find toml to be an
unworthwhile change.

Then, I had a bunch of junk content, converted approximately like
`pandoc -f rst -t markdown $f -o ${f%.rst}.md`.


Also, hugo puts content in `public/`, so I created reece.github.io,
then (from memory):

```
git clone git@github.com:reece/reece.github.io.git public
cd public
touch .nojekyll
git com -am "add .nojekyll" 
git push
cd ..
git submodule add git@github.com:reece/reece.github.io.git public
git com -m "added github pages repo at public/" public
```


# Links

* https://medium.com/@asishrs/automate-your-github-pages-deployment-using-hugo-and-actions-518b959a51f9

* https://gohugo.io/hosting-and-deployment/hosting-on-github/
