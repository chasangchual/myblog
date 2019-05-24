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
gpg: /etc/pacman.d/gnupg/trustdb.gpg: trustdb created
...
--> Installing /usr/share/info/which.info.gz ... done
...
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

* run ```bundle install``` to download jekyll plug-ing gems. It shows jekyll version to install

~~~~
G:\project\github_pages>bundle install
Fetching gem metadata from http://rubygems.org/... done
Resolving dependencies..
Fetching concurrent-ruby 1.1.5
Installing concurrent-ruby 1.1.5
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
Bundle complete! 1 Gemfile dependency, 85 gems now installed.
Use `bundle info [gemname]` to see where a bundled gem is installed.
Post-install message from dnsruby:
...
-------------------------------------------------
Thank you for installing html-pipeline!
You must bundle Filter gem dependencies.
See html-pipeline README.md for more details.
https://github.com/jch/html-pipeline#dependencies
-------------------------------------------------
https://github.com/jch/html-pipeline#dependencies
~~~~

## 2.2 create a jekyll site
* create a jekyll site in myblog directory

~~~~
G:\project\github_pages>bundle exec jekyll new myblog
Running bundle install in G:/project/github_pages/myblog...
  Bundler: Using concurrent-ruby 1.1.5
  ...
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
bundle exec jekyll serve
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

G:\project\github_pages\myblog>git commit -m "initial upload"
[master (root-commit) 8e948fc] initial upload
 7 files changed, 149 insertions(+)
 create mode 100644 .gitignore
 create mode 100644 404.html
...
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

## 2.5 Enable GitHub Pages
- enable GitHub pages for the repository
![enable git pages](/myblog/assets/images/git/enable_github_pages.png)

# 3. Apply minimal-mistakes remote theme
## 3.1 Add remote theme plugin
* wer are going to use jekyll-remote-theme ```https://rubygems.org/search?utf8=%E2%9C%93&query=jekyll-remote-theme```
  * add ````gem 'jekyll-remote-theme', '~> 0.3.1'```` to Gemfile
  * run ````bundle install```` as to download jekyll-remote-theme gem

~~~~
G:\project\github_pages>bundle install
Fetching gem metadata from http://rubygems.org/...............
Fetching gem metadata from http://rubygems.org/..
Resolving dependencies.....
Using concurrent-ruby 1.1.5
...
Using rubyzip 1.2.2
Using jekyll-remote-theme 0.3.1
...
Using terminal-table 1.8.0
Using github-pages 198
Bundle complete! 1 Gemfile dependency, 85 gems now installed.
Use `bundle info [gemname]` to see where a bundled gem is installed.
~~~~

## 3.2 use minimal-mistakes in remote mode
change _config.yml to use minimal-mistakes as remote_theme. and comment ount ````#theme: ... ````

~~~~
remote_theme: mmistakes/minimal-mistakes
~~~~

# 4. Customize Site

## 4.1 clone the mm-github-pages-starter repository

https://github.com/mmistakes/mm-github-pages-starter

~~~~
G:\project\github_pages>git clone https://github.com/mmistakes/mm-github-pages-starter.git
Cloning into 'mm-github-pages-starter'...
remote: Enumerating objects: 67, done.
remote: Total 67 (delta 0), reused 0 (delta 0), pack-reused 67
Unpacking objects: 100% (67/67), done.
~~~~

## 4.2 Copy files

~~~~
mm-github-pages-starter\_data\*
mm-github-pages-starter\_pages\*
mm-github-pages-starter\assets\*
mm-github-pages-starter\_config.yml
~~~~

## 4.3 update _config.yml

~~~~
title: rubust, scalable and measurable software
email: sangchual.cha@gmail.com
description: "Sangchual's blog for sharing stories about software development, quality assuarance and deployment."
twitter_username: username
github_username: chasangchual
minimal_mistakes_skin: "dark"
~~~~

## 4.4 update index.md

~~~~
---
# Feel free to add content and custom Front Matter to this file.
# To modify the layout, see https://jekyllrb.com/docs/themes/#overriding-theme-defaults

layout: posts
author_profile: true
---
~~~~

## 4.5 decrease font size

crate a scss file, ````\assets\css\main.scss```` to overide style.

~~~~
---
# Only the main Sass file needs front matter (the dashes are enough) 
---

@charset "utf-8";

@import "minimal-mistakes/skins/{{ site.minimal_mistakes_skin | default: 'default' }}"; // skin
@import "minimal-mistakes"; // main partials

// https://github.com/mmistakes/minimal-mistakes/issues/1219#issuecomment-326809412
html {
    font-size: 10px; // originally 16px

    @include breakpoint($medium) {
        font-size: 12px; // originally 18px
    }

    @include breakpoint($large) {
        font-size: 14px; // originally 20px
    }

    @include breakpoint($x-large) {
        font-size: 16px; // originally 22px
    }
}

pre {
    line-height: 1.5; // originally 1.8
}
~~~~