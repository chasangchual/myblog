---
title: "Steps to create a blog on GitHub Pages with jekyll"
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
   ![git for windows install](assets/images/git_for_windows/install_screen.png)
## 1.2 install Ruby
  - download [Ruby+Devkit 2.6.3-1 (x64)](https://rubyinstaller.org/downloads/) and execute to install
   ![git for windows install](assets/images/ruby/install_screen.png)
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
~~~
> gem install bundler
~~~
![git for windows install](assets/images/ruby/install_bundler.png)

# Prepare jekyll 
## 1. install jekyll gems
## 1. create a jekyll site

# Work With GitHub Repository

# Change jekyll Theme

# Customize Theme 