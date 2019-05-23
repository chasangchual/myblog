---
title: "Create jekyll based GitHub Pages with the remote theme"
date: 2019-04-18T15:34:30-04:00
categories:
  - blog
tags:
  - Jekyll
  - github
  - pages
  - minimal-mistakes-jekyll
---

# 1. Prerequisites
## 1.1 install git for window
  - download [git for windows](https://git-scm.com/download/win) and execute to install
   ![git for windows install](/myblog/assets/images/git_for_windows/install_screen.png)
## 1.2 install Ruby
  - download [Ruby+Devkit 2.6.3-1 (x64)](https://rubyinstaller.org/downloads/) and execute to install
   ![git for windows install](/myblog/assets/images/ruby/install_screen.png)
  - install MSYS2 base after ruby installed.
    - select ```1 - MSYS2 base installation```. Once completed, just press ENTER.

~~~~
 _____       _           _____           _        _ _         ___
|  __ \     | |         |_   _|         | |      | | |       |__ \
| |__) |   _| |__  _   _  | |  _ __  ___| |_ __ _| | | ___ _ __ ) |
|  _  / | | | '_ \| | | | | | | '_ \/ __| __/ _` | | |/ _ \ '__/ /
| | \ \ |_| | |_) | |_| |_| |_| | | \__ \ || (_| | | |  __/ | / /_
|_|  \_\__,_|_.__/ \__, |_____|_| |_|___/\__\__,_|_|_|\___|_||____|
                    __/ |           _
                   |___/          _|_ _  __   | | o __  _| _     _
                                   | (_) |    |^| | | |(_|(_)\^/_>

   1 - MSYS2 base installation
   2 - MSYS2 system update (optional)
   3 - MSYS2 and MINGW development toolchain

Which components shall be installed? If unsure press ENTER [1,2,3] 1

> sh -lc true
'C:\WINDOWS\system32\drivers\etc\hosts' -> '/etc/hosts'
'C:\WINDOWS\system32\drivers\etc\protocol' -> '/etc/protocols'
'C:\WINDOWS\system32\drivers\etc\services' -> '/etc/services'
'C:\WINDOWS\system32\drivers\etc\networks' -> '/etc/networks'
gpg: /etc/pacman.d/gnupg/trustdb.gpg: trustdb created
gpg: no ultimately trusted keys found
gpg: starting migration from earlier GnuPG versions
...
--> Installing /usr/share/info/sed.info.gz ... done
--> Installing /usr/share/info/tar.info.gz ... done
--> Installing /usr/share/info/texinfo.info.gz ... done
--> Installing /usr/share/info/time.info.gz ... done
--> Installing /usr/share/info/wget.info.gz ... done
--> Installing /usr/share/info/which.info.gz ... done


###################################################################
#                                                                 #
#                                                                 #
#                   C   A   U   T   I   O   N                     #
#                                                                 #
#                  This is first start of MSYS2.                  #
#       You MUST restart shell to apply necessary actions.        #
#                                                                 #
#                                                                 #
###################################################################


MSYS2 seems to be properly installed

   1 - MSYS2 base installation
   2 - MSYS2 system update (optional)
   3 - MSYS2 and MINGW development toolchain

Which components shall be installed? If unsure press ENTER []
~~~~

## 1.3 Install Bundler
Bundler provides a consistent environment for Ruby projects by tracking and installing the exact gems and versions that are needed.

Bundler is an exit from dependency hell, and ensures that the gems you need are present in development, staging, and production. Starting work on a project is as simple as ```bundle install```.
~~~~
gem install bundler
~~~~
![install gem bundler](/myblog/assets/images/ruby/install_bundler.png)

# 2. Prepare jekyll 
## 2.1 install jekyll plugin gems
* Create ```Gemfile``` with below
~~~~
source 'http://rubygems.org'
gem 'github-pages', group: :jekyll_plugins
~~~~
* run ```bundle install``` to download jekyll plug-ing gems
~~~~
G:\project\github_pages>bundle install
Fetching gem metadata from http://rubygems.org/...............
Fetching gem metadata from http://rubygems.org/..
Resolving dependencies....
Fetching concurrent-ruby 1.1.5
Installing concurrent-ruby 1.1.5
Fetching i18n 0.9.5
Installing i18n 0.9.5
Using minitest 5.11.3
Fetching thread_safe 0.3.6
...
Fetching jekyll 3.8.5
Installing jekyll 3.8.5
Fetching jekyll-avatar 0.6.0
Installing jekyll-avatar 0.6.0
Fetching jekyll-coffeescript 1.1.1
Installing jekyll-coffeescript 1.1.1
Fetching jekyll-commonmark 1.3.1
Installing jekyll-commonmark 1.3.1
...
Installing unicode-display_width 1.6.0
Fetching terminal-table 1.8.0
Installing terminal-table 1.8.0
Fetching github-pages 198
Installing github-pages 198
Bundle complete! 1 Gemfile dependency, 85 gems now installed.
Use `bundle info [gemname]` to see where a bundled gem is installed.
Post-install message from dnsruby:
Installing dnsruby...
  For issues and source code: https://github.com/alexdalitz/dnsruby
  For general discussion (please tell us how you use dnsruby): https://groups.google.com/forum/#!forum/dnsruby
Post-install message from sass:

Ruby Sass has reached end-of-life and should no longer be used.

* If you use Sass as a command-line tool, we recommend using Dart Sass, the new
  primary implementation: https://sass-lang.com/install

* If you use Sass as a plug-in for a Ruby web framework, we recommend using the
  sassc gem: https://github.com/sass/sassc-ruby#readme

* For more details, please refer to the Sass blog:
  https://sass-lang.com/blog/posts/7828841

Post-install message from nokogiri:
Nokogiri is built with the packaged libraries: libxml2-2.9.9, libxslt-1.1.33, zlib-1.2.11, libiconv-1.15.
Post-install message from html-pipeline:
-------------------------------------------------
Thank you for installing html-pipeline!
You must bundle Filter gem dependencies.
See html-pipeline README.md for more details.
https://github.com/jch/html-pipeline#dependencies
-------------------------------------------------
~~~~
## 1. create a jekyll site

# Work With GitHub Repository

# Change jekyll Theme

# Customize Theme 