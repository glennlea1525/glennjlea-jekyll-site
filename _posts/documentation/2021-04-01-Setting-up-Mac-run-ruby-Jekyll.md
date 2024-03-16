---
layout: article
title: Setting up a Mac to run Jekyll
description: I had some challenges trying to run Jekyll on my Mac. I thought it best to document how I did it in case it needed to be done again should I buy another Macbook Pro. These set of instructions shows how to get a Jekyll setup on a MAC.
date: '2021-04-01'
categories: documentation
---

# {{ page.title }}

If you had some challenges trying to run Ruby and Jekyll on my Mac, you are not alone. I encountered this problem some time ago. I finally got it running and basically this is how I did it.

## Prerequisites

You need the following:

1. Latest Ruby version.
1. RubyGems
1. Jekyll installed and a project directory created.

## Which Ruby version does you Mac currently have?

According to the Jekyll documentation, you need at least Ruby version 2.5.0 or higher. You can check which version is installed on your MAC by using the following command:

`$ ruby -v`

It could show for example the following version:

`ruby 2.6.5p114 (2019-10-01 revision 67812) [x86_64-darwin17]`

If you don't have Ruby installed on your MAC, then go ahead and install it. You can get plenty of information about installing Ruby at the official Ruby site here: [Installing Ruby](https://www.ruby-lang.org/en/documentation/installation/) This site suggests using Homebrew which is installed by default on macOS. It is quite easy. Just run this command:

`$ brew install ruby`

If you received an error after running this command, you may need to try upgrading Ruby using the following command:

`$ brew upgrade ruby`

This may take a few minutes. You can get more information about updating Ruby on your MAC to the latest version on this page on [The Coding Pad](https://codingpad.maryspad.com/2017/04/29/update-mac-os-x-to-the-current-version-of-ruby/).

We now need to set the path for Ruby. In the following command replace X.X with the first two digits of your Ruby version, which in my case is 2.7

`$ echo 'export PATH="$HOME/.gem/ruby/X.X.0/bin:$PATH"' >> ~/.bash_profile`

where X.X is the Ruby version you found by running ruby -v above

You can get more information about checking the PATH of your Mac at [OSXDaily](https://osxdaily.com/2010/08/31/check-the-path-of-your-mac-with-echo-path/).

Restart the terminal to have the terminal recognize the new Ruby version. Then  re-run the Ruby version command to confirm you have the latest version:

`$ ruby -v`

## Which Gem is your Mac running?

Jekyll requires the use of RubyGems to run packages. Check which version of RubyGems is on your Mac using the following command:

`$ gem -v`

You may need to install RubyGems. Try running the following first to see where, if at all, RubyGems is running on your Mac:

`$ which gem`

If you need to install/update RubyGems, try the following:

`$ gem update --system`

RubyGems should now be installed.

## Installing Bundler

Once you have satisfied the prerequisites, you need to install Bundler which provides a consistent environment for Ruby projects by tracking and installing the exact gems and versions that are needed.

First, check if bundler is already installed on your Mac:

`$ bundler -v`

If you need to install Bundler, simply run the following command in the Jekyll project directory:

`$ cd <jekyll project directory>`

Then run the following command to install bundler:

`$ bundle install`

All the required files will be installed in the project directory and a Gemfile will be created.

You can then check the version of Bundler is the latest using the following command.

`$ bundle update --bundler`

You should see a list of updated Gems installed, then the following:

`$ bundle updated!`

## Now install Jekyll

With Ruby and Bundler installed, you are ready to install Jekyll.

`$ gem install --user-install bundler Jekyll`

This installs Jekyll.

The official Jekyll documentation provides additional installation information:

- [jekyll.com](https://jekyllrb.com/)

Check the gem environment by running:

`$ gem environment`

If the INSTALLATION DIRECTORY still has the old Ruby version in it let's update that to the latest version.

`$ export GEM_HOME=/usr/username/.gem/ruby/2.7.0;`

This updates the INSTALLATION DIRECTORY to 2.7.0

Now let's check the RubyGems environment again by running the following command again:

`$ gem environment`

Run again `bundle install` to ensure you have all the latest gems required by Jekyll:

`$ bundle install`

This will fetch and install the required gems to use bundle

## Run the Jekyll server

Now that you have installed the latest version of Ruby, Bundler and Jekyll, run the Jekyll server.

Note that you need to run this command in the directory of your Jekyll project.

`$ bundler exec jekyll serve`

This will start the Jekyll server and provide an HTTP address for a Jekyll website. Open a browser and enter the Server address shown and a new default Jekyll website will load.

That's it.

## Not quite. I keep getting deprecation errors

After running `bundle exec jekyll serve`, the Jekyll Server ran but I kept getting the following error:

`.rvm/gems/ruby-2.7.0/gems/jekyll-4.0.0/lib/jekyll/tags/include.rb:179: warning: Using the last argument as keyword parameters is deprecated`

Trying to fix that proved problematic. I first tried the following command:

`gem update jekyll`

That didn't work so I then tried the following command:

`sudo bundle update jekyll`

That didn't work as well so I ran this command again:

`bundle install`

That fixed it. Now all I needed to do was run the following command:

`bundle exec jekyll serve`

I have the right version of Jekyll and Bundler. I wasn't sure why I had to do this but it fixed whatever problems Jekyll was annoyed about or maybe it was something Bundler was upset about. Either way, they are both happy and so am I!

I hope you are too.
