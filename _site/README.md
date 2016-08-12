## Commands I ran for project set-up

* gem install bundler
* mk dir my-test-site
* cd my-test-site
* git init my-test-site
* git checkout -b gh-pages  # Because I want to create a site in github for this project per [Project pages site](https://help.github.com/articles/user-organization-and-project-pages/)
* touch Gemfile
* Open Gemfile in your text editor and add lines below:
	```
	# A Gemfile requires at least one source which tells us where to download the gems.
	source 'https://rubygems.org'

	gem 'jekyll', '3.1.6'

	# Usually we’d have to also specify our plugin gems in _config.yml so Jekyll knows about them. 
	# We can avoid this by putting our plugin gems in a “jekyll_plugins” group which Jekyll includes automatically.
	group :jekyll_plugins do
		gem 'github-pages'
	end	
	```
* bundle install
* git add .
* git commit -m "Created bundler setup for jekyll project creation."
* To create a new Jekyll template site:
	```bundle exec jekyll new . --force```
* Run your Jekyll site locally:
	```bundle exec jekyll serve```



## Keeping your site up to date with the GitHub Pages gem

	Jekyll is an active open source project and is updated frequently. As the GitHub Pages server is updated, the software on your computer may become out of date, resulting in your site appearing different locally from how it looks when published on GitHub. Run either of the below update commands:
```
bundle update github-pages
```
or
```
gem update github-pages
```



## Managing Project Source Branch and gh-pages branch in remote for auto-publishing in GitHub

* `master` branch is the source and `gh-pages` branch for publishing in github
* Every time you make changes to the website source, you'll make the commit to the master branch.
* When you're done making changes to the master branch, you'll push the git subtree (in our case, it's _site sub-directory) to gh-pages for publishing
```
$ git subtree push --prefix _site origin gh-pages
```
* Bingo, your website is published in github.

Note 1: Note in our case there is no local gh-pages branch
Note 2: _site sub-directory is removed from .gitignore list and is being tracked



## Tools Used

* Git and GitHub
* MAMP [Used this initially for playing with Wordpress related sites and ended up using it as a place to store this projects source code under its `htdocs` directory. I know you're shouting expletives!]
* Jekyll
* Bundler
* Botstrapp-sass


## References

* [Setting up your GitHub Pages site locally with Jekyll](https://help.github.com/articles/setting-up-your-github-pages-site-locally-with-jekyll/)
* [Using Bootstrap CSS with Jekyll](http://veithen.github.io/2015/03/26/jekyll-bootstrap.html)
* [My Jekyll Blog Setup with Bootstrap, SASS and Pygments](http://kvurd.com/blog/my-jekyll-blog-setup-bootstrap-sass-pygments/)