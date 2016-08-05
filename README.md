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

## References
* [Setting up your GitHub Pages site locally with Jekyll](https://help.github.com/articles/setting-up-your-github-pages-site-locally-with-jekyll/)