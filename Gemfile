source "https://rubygems.org"
# Hello! This is where you manage which Jekyll version is used to run.
# When you want to use a different version, change it below, save the
# file and run `bundle install`. Run Jekyll with `bundle exec`, like so:
#
#     bundle exec jekyll serve
#
# This will help ensure the proper Jekyll version is running.
# Happy Jekylling!
gem "jekyll", "~> 4.0.0"
gem "kramdown-math-katex"
# This is the default theme for new Jekyll sites. You may change this to anything you like.
# 默认主题 可以修改成其他的
gem "minima", "~> 2.5"
# If you want to use GitHub Pages, remove the "gem "jekyll"" above and
# uncomment the line below. To upgrade, run `bundle update github-pages`.
# gem "github-pages", group: :jekyll_plugins
# If you have any plugins, put them here!
# 插件引用
group :jekyll_plugins do
  gem "jekyll-feed", "~> 0.12"
end

# Windows and JRuby does not include zoneinfo files, so bundle the tzinfo-data gem
# and associated library.
install_if -> { RUBY_PLATFORM =~ %r!mingw|mswin|java! } do
  gem "tzinfo", "~> 1.2"
  gem "tzinfo-data"
end

# gem 'my-awesome-jekyll-theme'

# # Performance-booster for watching directories on Windows
# gem "wdm", "~> 0.1.1", :install_if => Gem.win_platform?

# require 'json'
# require 'open-uri'
# versions = JSON.parse(open('https://pages.github.com/versions.json').read)

# gem 'github-pages', versions['github-pages']