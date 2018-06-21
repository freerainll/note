# Git

Git 仓库的版本控制，好处是所有代码发展的历史都会记录下来。我们只要去看代码的每个版本，就可以从中学习到很多东西，知道代码怎么写，知道文档该怎么写。可以举例说明，比如不知道到 MarkDown 中的 TaskList  

## 阮一峰的 Git 教程

阮一峰老师的博客网站，搜索 git 的结果，每个文章质量都很高。

- 常用 Git 命令清单  
  http://www.ruanyifeng.com/blog/2015/12/git-cheat-sheet.html  
- Git 使用规范流程  
  http://www.ruanyifeng.com/blog/2015/08/git-use-process.html  
- Git 远程操作详解  
  http://www.ruanyifeng.com/blog/2014/06/git_remote.html  
- Git 工作流程  
  http://www.ruanyifeng.com/blog/2015/12/git-workflow.html  
- Git 分支管理策略  
  http://www.ruanyifeng.com/blog/2012/07/git.html  
- Git 使用规范  
  http://www.ruanyifeng.com/blog/2015/08/git-use-process.html  
- Commit message 和 Change log 编写指南  
  http://www.ruanyifeng.com/blog/2016/01/commit_message_change_log.html  

## 学习资料

- Git 命令中文版  
  - 网站不错，全是开源方面的资料，平时可以多看看，会有很多简单、有趣的东西  
  - http://www.open-open.com/lib/view/open1401433488824.html  
- 专为设计师写的 github 资料  
  - 可以参考一下吧，职业方向还是有差异的  
  - http://www.ui.cn/detail/20957.html  
- git-it 课程资料  
  - 闯关练习软件的教程文字  
  - http://jlord.us/git-it/index-zhtw.html  
- git 心法（张文细）  
  - 点评：一个简单、明了的博客文章  
  - https://blog.alphacamp.co/2015/01/13/git/  
- 张文细的所有 Git 资料  
  - 点评：带视频，有幻灯片，讲的很到位，可以模仿  
  - 地址：https://ihower.tw/git/  
- git ready  
  http://gitready.com/
- git 命令图解  
  - 点评：配图清楚，比较多，够啰嗦  
  - http://blog.csdn.net/yangwen123/article/details/9084007  
- 猴子都能懂的 Git 入门  
  - 点评：配图还算可以，有点儿卡通幼稚，寓教于乐  
  - http://backlogtool.com/git-guide/cn/intro/intro1_1.html  
- Learn Git  
  - 点评：排版简洁、大方，配图时尚、漂亮，内容专业权威  
  - https://www.atlassian.com/git  

## 资源

- 勋章：http://shields.io/  
- 进度：https://github.com/fehmicansaglam/progressed.io  
- Git 教学软件：onlywei.github.io/explain-git-with-d3/  

## 常见问题

- git 存储凭证  
  http://www.cnblogs.com/volnet/p/git-credentials.html
  $ git config --global credential.helper wincred
  这一行命令搞定，参考网址：https://help.github.com/articles/caching-your-github-password-in-git/

- git 撤销远程仓库的提交  
  http://www.cnblogs.com/chucklu/p/4661149.html

- Git 文件换行问题  
  http://www.cnblogs.com/flying_bat/archive/2013/09/16/3324769.html  

- 如何在 Github 的 pull request 中进行 code review
  参考：
  https://github.com/wangding/Sample/pull/1
  https://github.com/wangding/seIDE/pull/6
  https://github.com/wangding/seIDE/pull/11

- issue 过滤

  ![issue filter.png](http://upload-images.jianshu.io/upload_images/3058932-fbc953aaadb6cdf0.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)

## Git 命令行配置

- 自动记忆凭证  
- 设置快捷键  
- 设置换行检查  

## Git 常用命令

- git 教学演示  

    ```bash
    # 目的命令简单，快捷，可以制造变更
    # 快速制造多个提交，看到版本路线
    # 先看一下命令的效果，然后就不用看了

    touch a
    touch b
    touch c
    
    echo 11 >> a
    echo 22 >> a
    
    git add .

    git commit -m "11"
    
    echo 33 >> a
    git commit -am "33"
    ```

- git rebase 操作  

    ```bash
    # -i 是交互操作
    git rebase -i <SHA>
    
    # 把当前分支在 master 的位置接上
    git rebase master
    ```

- git 基本操作1  

    ```bash
    # add & commit Mothed 1
    git add .
    git commit -m "message"

    #Git 假定所有的改变都是针对同一件事情的，因此它把这些都放在了一个块里。你有如下几个选项：
    #输入 y 来暂存该块
    #输入 n 不暂存
    #输入 e 手工编辑该块
    #输入 d 退出或者转到下一个文件
    #输入 s 来分割该块
    git add -p <file name>

    # add & commit Mothed 2
    git commit -a -m "message"

    # add & commit Mothed 3
    git commit -am "message"
    ```

- git 基本操作2  

    ```bash
    # 改变文件夹的名字：Name -> name
    # 直接运行 git mv Name name，执行不成功，会搞成：Name ->name/Name
    git mv Name tmp
    git mv tmp name
    
    # diff working directory with repos 
    git diff

    # diff staging area with repos
    git diff --cached
    
    # 拿 working directory 和 SHA 比较
    git diff <SHA>

    # ?
    git diff <SHA 1> <SHA 2>
    
    # ?
    git diff --stat <SHA>
    ```

- git ssh 链接

    ```bash
    # diff working directory with repos 
    ssh-Keygen -t rsa -C "your email"

    # 查看用户主目录的 .ssh/ 文件夹中创建的私钥文件（注意备份）
    ls ~/.ssh
    # 目录中两个文件：id_rsa （私钥）  和   id_rsa.pub (公钥)

    # 打印公钥文件内容
    cat ~/.ssh/id_rsa.pub
    # 把文件内容复制到剪贴板中

    # 在 github.com 的 Settings 中找 SSH and GPG keys, new SSH key

    # 利用 SSH 协议来克隆仓库
    git clone git@github.com:wangding/test
    
    # 利用 SSH 协议来添加远程链接
    git remote add origin git@github.com:wangding/test
    ```

- git branch 操作

    ```bash
    # 删除分支 foo 分支，前提 foo 已经合并过
    git branch foo -d

    # 强制删除分支 foo
    git branch foo -D

    # 创建分支 foo
    git branch foo

    # 切换到分支 foo
    git checkout foo

    # 创建分支并同时切换到 foo，一步做到
    git checkout -b foo

    # 修改分支名字
    git branch -m old_name new_name
    git branch -M old_name new_name

    # 列出远程分支
    git branch -r

    # 查看已经合并的分支
    git branch --merged

    # 查看没有合并的分支
    git branch --no-merged

    # 列出远程合并的分支
    git branch -r --merged

    # 取出远程的 foo 分支
    git checkout -t origin/foo

    # 删除远程分支 1
    # <space> 是空格，<remote branch> 是远程分支的名字
    # 把空内容推到远程的分支上，就是删除的意思
    git push origin <space> :<remote branch>

    # 删除远程分支 2
    # 在 github 上可以直接删除分支
    # 在本地 git pull 不能把远程分支的变化反应到本地
    # git pull 和 git fetch 不会清除已经删除的远程分支
    # git branch -r 还可以看到已经删除的远程分支
    # sourceTree 的线图还可以看到已经删除的远程分支
    # 可以执行下面的命令解决问题
    git fetch -p

    # 合并分支
    git merge <branch name>

    # 合并分支，拒绝 fast forward，产生合并 commit
    git merge --no-ff
    ```

- git blame 逐行查看文档

    ```bash
    # 逐行查看 <filename> 的历史
    git blame <filename>

    # 从第 100 行开始查看 10 行
    git blame -L 100,10 <filename>
    ```

- git clean 砍掉 untracked 档案

    ```bash
    # 列出打算要清除的档案
    git clean -n

    # 真正的删除
    git clean -f

    # 连 .gitignore 中忽略的档案也清除
    git clean -x
    ```

- git tag 操作

    ```bash
    # 给当前的 HEAD 指针处贴标签 foo
    git tag foo

    # 给任意的一个提交贴标签 foo
    git tag foo HEAD~4

    # 给当前的 HEAD 指针处贴标签 foo
    git tag foo -m "message"

    # 删除标签 foo
    git tag -d foo

    # 列出标签
    git tag

    # 将所有标签推送到远程仓库中
    git push --tags

    # 将具体某个标签推送到远程仓库中
    git push origin v0.1

    # 拉下来远程仓库的标签
    git pull --tags

    # 删除远程仓库的标签 foo
    git push origin :refs/tags/foo
```

- git stash 操作  

    ```bash
    # 保存进度
    git stash

    # 弹出进度
    git stash pop

    # 查看 stash 列表
    git stash list

    # 删除所有进度
    git stash clear
    ```

- git 其他操作  

    ```bash
    # 查看某个文件的提交记录
    git log <file name>

    # 把 upstream 代表的远程仓库的 master 分支拽到本地
    git pull upstream master

    # 撤销上一个 commit，前提是没有 push 到远程仓库
    git add <something>
    git commit --amend -m "some comment"

    # 弹出 vim 输入多行 message
    git commit

    # 查看 log 日志，并过滤需要的信息
    git log --grep <filter word>
    ```
