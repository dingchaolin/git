## linux 部分常用指令

- ls -l
- ll
- ls -al

- rw-r--r-- 1 Administrator 197121 0 十月  8 10:46 mynote.txt
-   表示是文件  d表示是目录
- r read  w write  x exec 可执行
- rw-
- r--
- r--

- cat  文件名  就能显示文件内容

- rm 文件名/文件夹名  删除文件/目录下的所有文件
- rm -rf *.js 循环删除

- touch  创建文件

- mkdir  创建文件夹

- cp  文件的复制


-cp -R 源目录名    新目录名  创建一个新目录 并将源目录下的文件全部复制扫新目录下
-cp  源文件名     新文件名  复制新文件


-mv  文件名/文件夹  路径     将文件/文件夹移动到目标路径  移动后源文件就没有了 就在新文件夹下

- grep 内容  文件名 在某个文件中搜索字符串

- git config --list 查看git的配置信息
- history    查看敲过的命令


## git使用流程

- git init
- git clone  克隆远程仓库的文件
- git status 查看文件状态
- git add  文件名
- git add -A  添加全部文件
- git commit -m"init project"

#### git 配置别名  对当前账户配置
- git config --global alias.st status =>  git status    等价于  git st

- git log 看提交日志

- git remote -v  查看远程查库的地址
- origin  远程仓库的地址

#### 添加远程仓库地址
- git remote add origin https://github.com/dingchaolin/gitReact.git
#### 返回结果：
- origin   https://github.com/dingchaolin/gitReact.git (fetch)
- origin   https://github.com/dingchaolin/gitReact.git (push)

#### 将commit的文件推送到远程仓库：
- git push origin master

#### 生成public key：
- ssh-keygen -t rsa -C "18810042351@163.com"

#### 查看public key:
- cat ~/.ssh/id_rsa.pub
- ssh-rsa AAAAB3NzaC1yc2EAAAADAQABAAABAQDmTkwJb7IlRkgyGLImUFKHjrFbz1SyN/eYa316Ab078WbmL4MGAoN2cyXv+prgSg1Ecsq3n5XfBUGRPicwIqjBbXh8HZjolTyh5rf0xGkx4LPao+iMtjGObeFHMWi5/TjT3VMXLvKiWeH1SSfCMqEE0J42kPntLalv7+G4eHII4a26h8laea2jOHf1xn8WvbdqFS25FIRoM18WqSK5God5WVcnZMBFJnKWwSrCkATR+6GwUgFa/Dl3T6nxm+/D+TvLPfxJg5boT2OY/lyJR9G3o9br07t5Z36l3+7QuLsIo4PqhkhtxRNAiFgItRQGC7voCtcNqvruLF/eJ+DX6R8L 18810042351@163.com

#### githbu设置公钥：
- 头像-settings-SSH and GPG keys - New SSH key

#### 当提交拒绝的时候 需要本地的代码和远程的代码同步：
- git pull origin master
##重要问题

- 各种操作的时候 比如pull，push等等 一定要进入相应的目录内
- 比如 这个远程仓库的名是gitReact 操作的时候一定要进入gitReact中进行操作


#### 解决分支，删除本地相应的文件能解决分支冲突问题

- 当修改了文件之后：
- 如果想要保存 就git add
- 不想保存就 git checkout -- node.md 撤销本地的修改
- git checkout -- . 表示当前目录下的所有修改都撤销
#### 强制回退到某一版本号
- git reset --hard e070999eec19cbb8674790a0771e6c9b9f62f734
#### 删除远程仓库地址
- git remote rm origin

#### 查看提交日志
- git log
- commit 5ec726a6d7dd0c216ec465dfabafbaf0384dec4c Author: dingchaolin <18810042351@163.com> Date:   Sat Oct 8 12:44:27 2016 +0800

- commit 后面的就是此次提交的版本号

#### 查看本次提交的做了哪些操作
- git show  版本号
- git show   5ec726a6d7dd0c216ec465dfabafbaf0384dec4c

#### 创建分支
###### 分支：
- master 默认分支
- develop 开发主干分支
- feature 开发的一些分支
- bug 修改bug的分支
- release 上线的分支

#### 切分支
- git branch newbranch 新建一个分支
#### 查看分支
- git branch
#### 新建一个分支并且调转到该分支
- git checkout -b bug
#### 删除一个分支
- git branch -d mybranch
#### 切换到某一分支
- git checkout master
#### 此分支提交
- git commmit -am"提交"
#### 分支合并
- 首先从次分支切换到主分支
- git checkout master
#### 合并
- git merge master bug  (从bug分支合并到master分支)
#### 分支合并过程
- 1.先在次分支执行 git commit -am""
- 2.切换到主分支 git checkout master
- 3.合并 git merge master bug
- 4.拉取主分支 git pull origin master
- 5.合并主分支 git push origin master

### 分支作图形化展示
##### 配置别名
-git config --global alias.lg "log --color --graph --pretty=format:'%Cred%h%Creset -%C(yellow)%d%Creset %s %Cgreen(%cr) %C(bold blue - <%an>%Creset' --abbrev-commit"
- 配置别名之后 git lg 即可
##### 图形化的工具展示
- sourcetree


#### 合并前查看分支的不同
- git diff bug master （bug 指源分支  master 指目标分支）

#### 另一种分支更新方式 代替 git pull
- git fetch origin
- git rebase origin/master

#### 重命名命令
- $ git config --global alias.st status
- $ git config --global alias.ci commit
- $ git config --global alias.co checkout
- $ git config --global alias.br branch
- $ git config --global alias.lg "log --color --graph --pretty=format:'%Cred%h%Creset -%C(yellow)%d%Creset %s %Cgreen(%cr) %C(bold blue)<%an>%Creset' --abbrev-commit"

#### 打标签
- git tag 1.1.1 5ec726a6d7dd0c216ec465dfabafbaf0384dec4c
- 用一个版本号 对应一个版本tag
- git tag 显示版本号

#### 帮助
- git commit --help

#### npm 设置镜像
- npm config set registry http://registry.npm.taobao.org
- npm config set loglevel=http 方便查看下载进度
- npm config set registry https://registry.npmjs.org/
#### npm 其他命令
- npm install gulp -g 全局安装
- npm install gulp --save 添加到依赖中
- --save 和 --save-dev的区别
- --save 版本名和版本号记录在dependencies字段
- --svar-dev 版本名和版本号记录在devDependencies字段
#### 建议
- 项目依赖的模块安装到项目相应的文件中

#### 生成package.json
- npm init  该命令可以生成一个package.json 命令







