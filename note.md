##linux 部分常用指令
ls -l
ll
ls -al

-rw-r--r-- 1 Administrator 197121 0 十月  8 10:46 mynote.txt
-   表示是文件  d表示是目录
r read  w write  x exec 可执行
rw-
r--
r--

cat  文件名  就能显示文件内容

rm 文件名/文件夹名  删除文件/目录下的所有文件
rm -rf *.js 循环删除

touch  创建文件

mkdir  创建文件夹

cp  文件的复制


cp -R 源目录名   新目录名  创建一个新目录 并将源目录下的文件全部复制扫新目录下
cp  源文件名    新文件名  复制新文件


mv  文件名/文件夹  路径    将文件/文件夹移动到目标路径  移动后源文件就没有了 就在新文件夹下

grep 内容  文件名 在某个文件中搜索字符串

git config --list 查看git的配置信息
history   查看敲过的命令


##git使用流程
git init
git clone  克隆远程仓库的文件
git status 查看文件状态
git add  文件名
git add -A  添加全部文件
git commit -m"init project"

git 配置别名  对当前账户配置
git config --global alias.st status =>  git status   等价于  git st

git log 看提交日志

 git remote -v  查看远程查库的地址
  origin  远程仓库的地址

github 账号密码  dingchaolin/wei391519

添加远程仓库地址
git remote add origin https://github.com/dingchaolin/gitReact.git
返回结果：
origin  https://github.com/dingchaolin/gitReact.git (fetch)
origin  https://github.com/dingchaolin/gitReact.git (push)

将commit的文件推送到远程仓库：
git push origin master

生成public key：
ssh-keygen -t rsa -C "18810042351@163.com"

查看public key:
cat ~/.ssh/id_rsa.pub
ssh-rsa AAAAB3NzaC1yc2EAAAADAQABAAABAQDmTkwJb7IlRkgyGLImUFKHjrFbz1SyN/eYa316Ab078WbmL4MGAoN2cyXv+prgSg1Ecsq3n5XfBUGRPicwIqjBbXh8HZjolTyh5rf0xGkx4LPao+iMtjGObeFHMWi5/TjT3VMXLvKiWeH1SSfCMqEE0J42kPntLalv7+G4eHII4a26h8laea2jOHf1xn8WvbdqFS25FIRoM18WqSK5God5WVcnZMBFJnKWwSrCkATR+6GwUgFa/Dl3T6nxm+/D+TvLPfxJg5boT2OY/lyJR9G3o9br07t5Z36l3+7QuLsIo4PqhkhtxRNAiFgItRQGC7voCtcNqvruLF/eJ+DX6R8L 18810042351@163.com

githbu设置公钥：
头像-settings-SSH and GPG keys - New SSH key

当提交拒绝的时候 需要本地的代码和远程的代码同步：
git pull origin master
##重要问题

各种操作的时候 比如pull，push等等 一定要进入相应的目录内
比如 这个远程仓库的名是gitReact 操作的时候一定要进入gitReact
中进行操作


解决分支，删除本地相应的文件能解决分支冲突问题

当修改了文件之后：
如果想要保存 就git add
不想保存就 git checkout -- <file> 撤销本地的修改

#删除远程仓库地址
git remote rm origin






