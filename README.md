# people's spark www


## Contributing

Posts are added to the [`_posts`](./_posts/) directory in
[markdown](https://docs.github.com/en/get-started/writing-on-github/getting-started-with-writing-and-formatting-on-github/basic-writing-and-formatting-syntax).
Follow the other files in that directory as a guide.

Layout / template changes are added or edited in [`_layouts`](./_layouts)

These files will get compiled by github after merging to our main branch. The
static site generator that github uses is
[`jekyll`](https://jekyllrb.com/docs/), in case you want to make bigger changes.

To change the theme of the site you will need to add the gem for the theme
in the [`Gemfile`](Gemfile). The theme is then set in [`_config.yml`](_config.yml)

### Making changes on github

Follow the steps [provided by github to add a using their web
ui.](https://docs.github.com/en/repositories/working-with-files/managing-files/adding-a-file-to-a-repository)**


### Making changes locally

_You probably will need to make a [personal access
token](https://docs.github.com/en/authentication/keeping-your-account-and-data-secure/creating-a-personal-access-token)
for this._

To contribute all you need to do is clone the repo, make your changes,
push a new branch, and make a pull request.

**Note:** if you are not part of the github project then you will need to [fork
the project first.](https://docs.github.com/en/get-started/quickstart/fork-a-repo)

```
git clone git@github.com:peoples-spark<-$CHAPTER if needed>/github.io.git
git checkout -b $POST_BRANCH
# Make your site changes, probably in _posts or _layouts
git push origin $POST_BRANCH:$POST_BRANCH
# Then follow the link git provides you to make a pull request
```

## Develop on Your Computer

To test website changes without pushing them to the live website you can run
`jekyll` locally. Jekyll is the tool that github pages defaults to using to
build website and provides decent docker images.

Local development requires [`docker`](https://www.docker.com/get-started/) or
another container runtime like [`podman`](https://podman.io/getting-started/).

To see live changes as you edit run the docker container in your terminal: 

```
docker run  -v $(pwd):/srv/jekyll:Z -p "4000:4000" -it jekyll/jekyll jekyll serve
```

Open [https://localhost:4000](https://localhost:4000** in your browser to see
the website.

**NOTE:** any changes to [`_config.yml_`](_config.yml_) will require you to
restart the docker container
