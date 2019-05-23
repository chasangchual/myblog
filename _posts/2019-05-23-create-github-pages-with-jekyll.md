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

# 2. Install jekyll
## 2.1 download jekyll plugin gems
* create ```Gemfile``` and add two lines below
~~~~
source 'http://rubygems.org'
gem 'github-pages', group: :jekyll_plugins
~~~~
* run ```bundle install``` to download jekyll plug-ing gems. It shows jekyll version to install.
~~~~
G:\project\github_pages>bundle install
Fetching gem metadata from http://rubygems.org/... done
Fetching gem metadata from http://rubygems.org/.. done
Resolving dependencies..
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

Thank you for installing html-pipeline!
You must bundle Filter gem dependencies.
See html-pipeline README.md for more details.
https://github.com/jch/html-pipeline#dependencies

~~~~
## 2.2 create a jekyll site
* create a jekyll site in myblog directory
~~~~
bundle exec jekyll new myblog
~~~~
~~~~
>bundle exec jekyll new myblog
Running bundle install in G:/project/github_pages/myblog...
  Bundler: Using concurrent-ruby 1.1.5
  Bundler: Using i18n 0.9.5
  Bundler: Using minitest 5.11.3
  ...
  Bundler: Using terminal-table 1.8.0
  Bundler: Using github-pages 198
  Bundler: Bundle complete! 1 Gemfile dependency, 85 gems now installed.
  Bundler: Use `bundle info [gemname]` to see where a bundled gem is installed.
New jekyll site installed in G:/project/github_pages/myblog.

G:\project\github_pages>cd myblog

G:\project\github_pages\myblog>dir
 Volume in drive G is Data
 Volume Serial Number is 98B7-C1A5

 Directory of G:\project\github_pages\myblog

2019-05-23  07:57 AM    <DIR>          .
2019-05-23  07:57 AM    <DIR>          ..
2019-05-23  07:57 AM                35 .gitignore
2019-05-23  07:57 AM               398 404.html
2019-05-23  07:57 AM               539 about.md
2019-05-23  07:57 AM             1,069 Gemfile
2019-05-23  07:57 AM               175 index.md
2019-05-23  07:57 AM             1,652 _config.yml
2019-05-23  07:57 AM    <DIR>          _posts
               6 File(s)          3,868 bytes
               3 Dir(s)  96,628,682,752 bytes free

~~~~
* execute jekyll
~~~~
>bundle exec jekyll serve
~~~~
~~~~
G:\project\github_pages\myblog>bundle exec jekyll serve
Configuration file: G:/project/github_pages/myblog/_config.yml
            Source: G:/project/github_pages/myblog
       Destination: G:/project/github_pages/myblog/_site
 Incremental build: disabled. Enable with --incremental
      Generating...
       Jekyll Feed: Generating feed for posts
                    done in 1.164 seconds.
 Auto-regeneration: enabled for 'G:/project/github_pages/myblog'
    Server address: http://127.0.0.1:4000/
  Server running... press ctrl-c to stop.

  Terminate batch job (Y/N)? Y

G:\project\github_pages\myblog>dir
 Volume in drive G is Data
 Volume Serial Number is 98B7-C1A5

 Directory of G:\project\github_pages\myblog

2019-05-23  07:57 AM    <DIR>          .
2019-05-23  07:57 AM    <DIR>          ..
2019-05-23  07:57 AM                35 .gitignore
2019-05-23  07:57 AM    <DIR>          .sass-cache
2019-05-23  07:57 AM               398 404.html
2019-05-23  07:57 AM               539 about.md
2019-05-23  07:57 AM             1,069 Gemfile
2019-05-23  07:57 AM             1,864 Gemfile.lock
2019-05-23  07:57 AM               175 index.md
2019-05-23  07:57 AM             1,652 _config.yml
2019-05-23  07:57 AM    <DIR>          _posts
2019-05-23  07:57 AM    <DIR>          _site
               7 File(s)          5,732 bytes
               5 Dir(s)  96,628,461,568 bytes free
~~~~
## 2.3 create a jekyll site
- create a new GitHub repository for jekyll site
![git for windows install](/myblog/assets/images/git/create_myblog_repository.png)

## 2.4 push local jekyll site to the remote GitHub repository
~~~~
G:\project\github_pages\myblog>git init
Initialized empty Git repository in G:/project/github_pages/myblog/.git/

G:\project\github_pages\myblog>git add .
warning: LF will be replaced by CRLF in .gitignore.
The file will have its original line endings in your working directory.
warning: LF will be replaced by CRLF in 404.html.
The file will have its original line endings in your working directory.
warning: LF will be replaced by CRLF in _config.yml.
The file will have its original line endings in your working directory.
warning: LF will be replaced by CRLF in about.md.
The file will have its original line endings in your working directory.
warning: LF will be replaced by CRLF in index.md.
The file will have its original line endings in your working directory.

G:\project\github_pages\myblog>git commit -m "initial upload"
[master (root-commit) 8e948fc] initial upload
 7 files changed, 149 insertions(+)
 create mode 100644 .gitignore
 create mode 100644 404.html
 create mode 100644 Gemfile
 create mode 100644 _config.yml
 create mode 100644 _posts/2019-05-21-welcome-to-jekyll.markdown
 create mode 100644 about.md
 create mode 100644 index.md

G:\project\github_pages\myblog>git remote add origin https://github.com/chasangchual/myblog.git

G:\project\github_pages\myblog>git push -u origin master
Counting objects: 10, done.
Delta compression using up to 4 threads.
Compressing objects: 100% (9/9), done.
Writing objects: 100% (10/10), 3.24 KiB | 473.00 KiB/s, done.bu
Total 10 (delta 0), reused 0 (delta 0)
To https://github.com/chasangchual/myblog.git
 * [new branch]      master -> master
Branch 'master' set up to track remote branch 'master' from 'origin'.
~~~~

## 2.5 enable GitHub Pages
- enable GitHub pages for the repository
![enable git pages](/myblog/assets/images/git/enable_github_pages.png)


# Work With GitHub Repository

# Change jekyll Theme

# Customize Theme 