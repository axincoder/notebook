# 文档内容：git操作的说明

***  工作区(红色, work)----> 暂存区(绿色, stage or index)----->  版本库 ***

1. 配置git用户名和电子邮件  
git config --global user.name jacky  
git config --global user.eamil jacky@qq.com

#查看git配置信息
git config -l

# 创建一个目录，作为git仓库 
mkdir <directory> 
cd <directory> 

# 在当前目录新建一个git仓库
git init
# 或者
git init <directory>


#克隆项目至当前目录
git clone <repo>

#克隆项目至指定目录
git clone <repo>  <direcotry>

# 添加文件到git暂存区(stage index)
git add filename


#将文件由暂存区，添加到版本库
git commit -m "add filename"


#add commit写在一个命令里面
git commit -am "add filename"


#查看工作区，暂存区的状态
# (untracked:表示新增文件，仅仅在工作区)
git status


#删除文件
git rm <filename>
git commit <filename> -m "删除文件filename"


#将本地仓库推到云端仓库
git push 云端仓库地址 marster
#或者先给远程地址设定一个别名，再使用别名来推送
git remote add 别名名称   远程仓库地址
git push 别名名称 marster


#工作区的目录树被重写，被master区的目录树覆盖
git reset HEAD

#将暂存区的文件覆盖工作区(危险操作，工作区将被暂存区覆盖)
git checkout <filename>     #覆盖单个文件
git checkout .              #覆盖整个目录


#将版本库的文件覆盖工作区(危险操作，工作区将被版本库覆盖)
git checkout HEAD <filename>      #覆盖单个文件
git checkout HEAD .             #覆盖整个目录


#查看提交历史记录
git log 
#或
git log --oneline           #简洁版本


#查看指定用户提交的历史记录
git log --author <username>



#本地git仓库，与远程git仓库（如github就是一个典型了远程git仓库）的操作
#因为本地与远程git文件传输是SSH加密的，因此先配置SSH信息
#1、生成SSH KEY
sudo ssh-keygen -t rsa -C "785340449@qq.com"


#2、生成后的公钥在~/.ssh/id_rsa.pub里面,拷贝后配置到github网站上
cat ~/.ssh/id_rsa.pub | pbcopy

#3、测试与github可以连接
ssh -T git@github.com



#Git分支
#分支：意味着从主线中分离出一条支线，在分支上进行开发不影响主线
#1、查看有哪些分支
git branch

#2、创建分支
git branch (branchName)

#3、切换分支
git checkout (branchName)
#或
git checkout -b (branchName)   #创建分支，并切换到新建的分支

#4、合并分支
git merge (branchName)          #将当前分支与branchName分支合并

#5、解决冲突：查看冲突文件后，需要手工解决

#6、删除分支
git branch -d (branchName)




#新建项目如何提交Github
#1、注册一个Github账户

#2、在Github上面创建一个repository

#3、本地创建一个项目

#4、初始化本地项目版本库：
git init

#5、配置远程项目别名: 
git remote add **   https://****.git

#6、同步本地和远程项目: 
git pull --rebase origin master     (别忘记哦)

#7、提交本地项目到远程：
git push -u origin master


#如何首次从github上面获取项目
git clone https://......git      (so easy!)
