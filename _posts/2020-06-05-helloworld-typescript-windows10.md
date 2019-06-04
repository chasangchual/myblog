---
title: Gettting started TypeScript in Windows 10 sub system
date: 2019-06-04T15:34:30-04:00
categories:
  - Web front-end
tags:
  - web
  - typescript
  - react
---

## Add a New User
### (1) add user
```
# adduser [username]
```
### (2) add the new user into sudoers
open ```/etc/sudoers``` and add ```[username]  ALL=(ALL:ALL) ALL``` in the # User privilege specification section
### (3) update ```apt-get```
```
sudo apt update && sudo apt -y upgrade && sudo apt autoremove
```

## Install nodejs with nvm (node version manager)
https://yoember.com/nodejs/the-best-way-to-install-node-js/

### (1) install nvm (https://github.com/nvm-sh/nvm)
```
curl -o- https://raw.githubusercontent.com/nvm-sh/nvm/v0.34.0/install.sh | bash
```
Then start a new Ubuntu terminal
### (2) install nodej
```
sangchual@DESKTOP-NQFH4UO:~$ nvm list
            N/A
iojs -> N/A (default)
node -> stable (-> N/A) (default)
unstable -> N/A (default)
sangchual@DESKTOP-NQFH4UO:~$ nvm ls-remote
        v0.1.14
        v0.1.15
        …
        v12.0.0
        v12.1.0
        v12.2.0
```
```
sangchual@DESKTOP-NQFH4UO:~$ nvm install 12.2.0
Downloading and installing node v12.2.0...
Downloading https://nodejs.org/dist/v12.2.0/node-v12.2.0-linux-x64.tar.xz...
#################################################################################################################### 100.0%
Computing checksum with sha256sum
Checksums matched!
Now using node v12.2.0 (npm v6.9.0)
Creating default alias: default -> 12.2.0 (-> v12.2.0)
sangchual@DESKTOP-NQFH4UO:~$ nvm use 12.2.0
Now using node v12.2.0 (npm v6.9.0)
sangchual@DESKTOP-NQFH4UO:~$ nvm alias default 12.2.0
default -> 12.2.0 (-> v12.2.0)
sangchual@DESKTOP-NQFH4UO:~$ node -v
v12.2.0
```
### (2) install npm (node package manager)
```
sangchual@DESKTOP-NQFH4UO:~$ npm install -g npm
/home/sangchual/.nvm/versions/node/v12.2.0/bin/npm -> /home/sangchual/.nvm/versions/node/v12.2.0/lib/node_modules/npm/bin/npm-cli.js
/home/sangchual/.nvm/versions/node/v12.2.0/bin/npx -> /home/sangchual/.nvm/versions/node/v12.2.0/lib/node_modules/npm/bin/npx-cli.js
+ npm@6.9.0
updated 1 package in 106.21s
sangchual@DESKTOP-NQFH4UO:~$ npm -v
6.9.0
```
### (3) increases the amount of inotify watche
One more thing! Don’t forget to run the following command, which increases the amount of inotify watches.
```
sangchual@DESKTOP-NQFH4UO:~$ echo fs.inotify.max_user_watches=524288 | sudo tee -a /etc/sysctl.conf && sudo sysctl -p
[sudo] password for sangchual:
fs.inotify.max_user_watches=524288
fs.inotify.max_user_watches = 5
```

## Create a TypeScript HelloWorld project
```
npx create-react-app helloworld-ts --typescript 
```