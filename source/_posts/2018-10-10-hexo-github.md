---
title: hexo+github
date: 2018-10-10 15:20:28
tags:
---
# hexo + github
***
## softs
- node.js
- git bash
***
## steps
1. install hexo-cli
   - npm install -g hexo-cli
2. initialize (through git bash)
   - mkdir hexo ; cd hexo
   - hexo init .
   - npm install 
   - npm install hexo-deployer-git --save
3. generate ssh-key from local (through git bash)
   - cd ~; ssh-keygen -t rsa -P ''
   - cat .ssh/id.rsa.pub
   - copy the content to github (SSH and GPG keys)
   - git config --global git config --global user.email "serenityc@live.cn"
   - test ssh connection (ssh -T git@github.com)
4. add a new repository (github)
   - **the repository name** must be *serenityc1.github.io*
5. modify the GitHub Pages (from github repository settings)
6. edit hexo _config.yaml 
   - modify title,author,timezone,etc.
   - modify new_post_name
```
		new_post_name: :year-:month-:day-:title.md
```
   - modify deploy
``` 
        deploy:
          type: git
          repository: git@github.com:SERENITYC1/serenityc1.github.io.git
          branch: master
```
7. hexo g;hexo d
***
## access the website
```
		https://serenityc1.github.io/
```
***
## push a new article
1. method 1
   - hexo new 'article title'
   - edit the hexo/source/_posts/2018-10-10-xxx.md
   - hexo g
   - hexo d
2. method 2
   - cp your new xxx.d to  hexo/source/_posts/2018-10-11-xxx.md
   - on the top,add
```
		---
		title: xxx
		date: 2018-10-11 10:11:28
		tags:
		---	
```
   - hexo g
   - hexo d