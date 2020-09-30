# www.brow.sh
This is the GitHub repository for the main Browsh website. It contains links for the homepage, downloads, documentation, and donation pages.

It's currently a [Jekyll](https://jekyllrb.com/) site.

Note that it receives automatic updates upon every new release of browsh-org/browsh; the updates change the current version number throughout the site.

Contributions welcome.

## Running Site Locally

To run the website locally for development, you will need to have Ruby 2.2.5 or higher and RubyGems installed.

Install Bundler:

`gem install bundler`

Install Jekyll and other dependencies from the Gemfile:

`bundle install` 

Serve the Website:

`bundle exec jekyll serve`

Jekyll’s built-in development server will run the website at http://localhost:4000

Jekyll isn’t officially supported for Windows; for more information on how to install Jekyll for Windows, check out the documentation [here](https://jekyllrb.com/docs/windows/#installation).
