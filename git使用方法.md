# 如何使用git实现对代码的基本管理？

# ---本文的操作示例是基于github的，gitee等其他平台类似，不做赘述 

# 说明：本文只针对满足日常的基本操作，面向对象是大学新生，还有一些其他的命令和高级的操作没有涉及，望见谅！
- - -
# 目录
* ## part 1: git的基本配置
* ## part 2: git的基本命令
* ## part 3: 什么是分支branch，如何使用
* ## part 4: 内容补充
- - -


## part 1：git的基本配置

### [git的安装教程请点我](https://www.bilibili.com/video/BV1vM4m1Q7hC/?spm_id_from=333.337.search-card.all.click&vd_source=822e86b53dab98632ef279a46d2536db)

### [视频中的镜像源地址请点我](https://mirrors.tuna.tsinghua.edu.cn/)

### 说明：在git的代码推送(push)和代码拉取(pull)的时候会弹出git登陆界面要求登录github

在完成登陆后请使用以下命令保存git的登录信息
```
git config --global credential.helper store
```

删除本地git凭证，下次push的时候需要重新登录
```
git credential-cache exit
```

### 补充说明：在后续的代码推送操作时如果网络无法连接github建议使用ssh，[请点我查看如何配置ssh](https://www.bilibili.com/video/BV1fK4y1q7kp/?spm_id_from=333.999.0.0&vd_source=822e86b53dab98632ef279a46d2536db)

视频中ssh配置的一些说明
cmd打开控制台，输入以下代码生成密钥
```
ssh-keygen -t ed25519 -C "你的邮箱"
```
三次回车，直到生成密钥视图

### git的配置命令（cmd回车直接配置即可）
### 注意：以下的配置只是起标识作用，作用是在代码的管理过程中知道作者的来源
```
配置用户名：git config --global user.name "自己起一个名字"

配置邮箱：git config --global user.email "填写你的邮箱"
```

### 查看配置命令
```
git config --global user.name

git config --global user.email
```

- - -

## part 2：git的基本命令

### 准备工作
* ### 在github上创建一个仓库repository
* ### 完成了git的基本配置和上述的准备工作
* ### 在本地新建一个文件夹并新建一个txt文件作为测试使用，右键文件夹点击`git bash here`

### 1. 初始化
```
git init
```

### 2. 添加文件到本地暂存区（就是要上传的文件）
添加全部文件
```
git add .
```
添加单个文件：
```
git add 文件名
```

### 补充：查看文件状态
```
git status
```

### 3.提交更改
```
git commit -m "first commit"
```
双引号内的内容是对本次文件提交的描述，这里是第一次提交可以像上述一样描述，下一次提交如果更改了某系内容可以修改双引号内的内容进行说明
```
示例
git commit -m "本次添加了xxx文件"
```

### 4.设置远程仓库（建议都使用ssh地址，不会受到网络限制，推送速度快）
```
git remote add origin (你的仓库https地址)
```
如果网络无法连接，采用ssh
```
git remote add origin (你的仓库ssh地址)
```
### 如何重新设置远程仓库地址，用set-url（例如：github---->gitee）
```
git remote set-url origin (你的仓库地址)
```

### 如何记忆两种地址
1. **https**地址:https://github.com/（你的github用户名）/（你的仓库名称）.git
2. **ssh**地址:git@github.com:（你的github用户名）/（你的仓库名称）.git

区别在于ssh的地址中github.com后面是冒号“ ：”

### 5.push代码
```
git push -u origin main
```
说明：origin后的main是分支名称，可被替换，详见后面的branch分支的使用

### 6.下一次更新代码
```
git add .
git commit -m "填写更改的描述"
git remote add origin （仓库地址）
git push origin main
```

### 如果出现了冲突，本地和仓库的内容不一致出现版本冲突，即命令行出现reject红色报错
```
git pull origin main --allow-unrelated-histories
```
### 这个时候会进入Git 合并过程中的编辑器
运用如下命令输入后回车退出
```
:wq
```
### 再次推送即可
```
git push origin main
```

### 如果push的时候显示Everything up-to-date表示没有差异，文件一直，并没有更更改内容

### 采用如下代码强制合并，谨慎使用，可能会丢失某些文件
```
git push origin main --force
```

- - -

## part 3：什么是分支branch，如何使用
### branch分支就是提供多人合作编写代码的载体，可以理解为一个branch就是一个合作者，有不同的合作者也就是多个分支，以下介绍一下基本用法

### 查看分支，当前分支会有一个  *  在前,同时分支名变绿
```
git branch
```

### 1.创建新的分支
```
git branch (分支名)
```

### 2.删除分支
```
git branch -d (分支名)
```

### 3.切换到某个分支
```
git checkout (分支名)
```

### 补充：创建并切换到该分支
```
git branch -b （分支名）
```

### 4.切换到分支后的操作和前面相同，不同的是push之后仓库会收到pull request的请求，由仓库主人审核是否合并到主分支main，即是否把分支更改的内容与源代码进行合并更新，作为仓库的最新版本代码


### 注意提交的时候是当前状况下的分支名称
```
git push origin (切换到的分支名称)
```
### 5.在本地直接进行分支合并，仓库中无需再审核

* ### 首先切换到分支完成更改并push
用如下命令切换到**主分支**
```
git checkout main
```
* ### 然后使用如下命令选择需要合并的分支
```
git merge (分支名)
```

- - -

## part 4：内容补充

### 1.查看日志(就是更改和提交的信息)
```
git log
```

### 2.查看仓库地址
```
git remote -v
```

### 3.回退到某一个版本并复制代码到本地
### 首先查看日志，选择需要的版本，复制哈希值（需要的版本日志中的由数字和字母组成一段字符串，颜色是黄色的）

* ### 1. 切换到需要的版本，算作一个分支
```
git checkout （需要的版本日志中的哈希值）
```
* ### 2. 复制当前版本文件到本地
### 这里以windows系统复制到桌面为例
```
cp -r . /c/Users/jackson/Desktop/backup-folder
```
### 说明：jackson是我的用户名，替换成自己的，backup-folder是一个文件夹，如果再桌面没有创建会自动创建并把需求版本的所有文件放在本文件夹

### 4.比较不同版本的差异
```
git diff （旧版本的哈希值） （新版本的哈希值）
```

- - -
## 最后补充一下：如果刚开始使用git不习惯或者不好上手，可以使用github desktop上传文件，可以实现再软件中远程搭建仓库，在桌面会生成一个含有git文件的文件夹，文件夹名称就是远程仓库的名称，之后每一次更新内容的时候就把**所有**文件拖入该文件夹，删除之前文件夹中的所有内容，在软件中进行推送即可，相当于直接覆盖之前的文件实现了更新


## 关于github desktop的下载和汉化教程可以上网自行查阅

## 本文到这就结束了，感谢您的阅读，因作者水平有限，如有错误请指正，如有其他建议和分享请给我留言！！！:smile: