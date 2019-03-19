---
title: Github Page+Hexo搭建个人博客
date: 2019-03-15 11:07:50
tags:
categories: 杂项
---

# 前提

- [GitHub账号](https://github.com/)及相关配置

- [安装Hexo](https://hexo.io/zh-cn/)

# Github

1. 新建项目![](credte repository.png)
2. 在项目设置中查看GitHub Pages的地址 ![](GitHub page site.png)

# Hexo

1. 查看文档进行安装[Node.js](https://nodejs.org/en/)和[Git](https://git-scm.com/)

2. 安装 Hexo

   ```js
   npm install -g hexo-cli
   ```

3. 建站

   ```hexo
   hexo init 项目名
   cd 项目名
   npm install
   ```

4. 如需安装主题，建议去相关主题的GitHub上下载包，复制进项目主题文件夹中，不要克隆

5. 启动服务器查看内容

   ```hexo
   hexo server
   ```

# 将建立的博客与Github Page相关联

1. 在Hexo建立的项目中安装依赖

   ```js
   npm install hexo-deployer-git --save
   ```

2. 打开Hexo建立的项目文件夹下的_config.yml文件，配置如下信息：

   ```text
   url: https://huabinluo.github.io/myNote/   （Github Page地址,涉及样式获取）
   root: /myNote/
   ```

   ```text
   deploy:
    type: git
    repository: https://github.com/HuabinLuo/myNote.git    (Github项目地址)
    branch: master
   ```

3. 执行推送命令

   ```hexo
   hexo generate
   hexo deploy
   ```

# 将项目源文件推送到Github上，方便迁移

1. 将GitHub上的项目克隆到本地

   ```git
   git clone GitHub项目地址
   ```

2. 删除除了.git外的所有文件

3. 将Hexo创建的项目中的所有文件复制进来，安装的依赖文件和使用Hexo命令生成的静态文件可以不用复制

4. 创建分支Hexo

   ```git
   git checkout -b hexo
   ```

5. 将复制过来的文件提交到暂存区

   ```git
   git add --all
   git commit -m "Hexo源文件"
   ```

6. 推送到GitHub

   ```git
   git push --set-upstream origin hexo
   ```

7. 后面在其它电脑使用的时候，直接克隆分支hexo项目，再安装依赖

   ```git
   git clone -b hexo GitHub项目地址
   ```

# 注意项

- 如果Hexo与GitHub Page关联时，推送不成功，请检查git是否有设置用户名和邮箱

  查看用户名和邮箱

  ```git
  git config user.name
  git config user.email
  ```

  设置用户名和邮箱

  ```git
  git config --global user.name "用户名"
  git config --global user.email "邮箱"
  ```

- 如果创建Hexo项目时需要安装主题，请不要使用git clone 安装，否则在源文件推送到GitHub上时，不会推送主题文件，建议下载主题包，复制进Hexo项目主题文件夹中