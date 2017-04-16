1.安装Git：Ctrl + Alt + T使用终端：使用命令
    
    sudo apt-get install git  

2.创建GitHub帐号：登陆git主页： https://github.com/，自己注册一个账号


3.生成ssh key：终端使用命令 
    
    ssh-keygen -t rsa -C "your_email@youremail.com"  

默认在用户文件夹中的 .ssh/id_rsa.pub，（.ssh是隐藏文件夹，需要设置显示隐藏文件夹）复制其中的一串字符。

4.添加SSH key：回到github，进入Account Settings，左边选择SSH Keys，Add SSH Key，title随便填，粘贴你的key。


5.测试ssh key是否成功：使用命令

    ssh -T git@github.com  

如果出现You’ve successfully authenticated, but GitHub does not provide shell access 。这就表示已成功连上github。如果出现“Agent admitted failure to sign using the key.Permission denied (publickey).”这个错误的话，在命令行下执行
[plain] view plain copy
ssh -add  
这样就可以了。

6.配置Git的配置文件，username和email：

    git config --global user.name "your name"   //配置用户名  
    git config --global user.email "your email"    //配置email   

7.在Git上添加一个Repository


8.利用Git从本地上传到GitHub（也就是说在Git上创建了一个空的repository，但是本地的代码并没有push上去）
8.1.进入要所要上传文件的目录输入命令

    git init  

8.2.创建一个本地仓库，使用命令

    git remote add origin git@github.com:yourName/yourRepo.git  

其中youName是你的GitHub的用户名，yourRepo是你要上传到GitHub的仓库
8.3.添加一个文件xxx到本地仓库，使用命令

    git add xxx  

也可以使用

    git add .  

自动判断添加哪些文件
8.4.把这个添加提交到本地的仓库，使用命令

    git commit -m "提交的说明信息”  

通常在“提交的说明信息“中注明此时push的相关信息，例如内容的更新或bug的修复等。
8.5.把本地仓库提交到远程的GitHub仓库，使用命令 

    git push -u origin master  

如果出现错误：无法推送一些引用到 'git@github.com:yourname/xxx.git'提示：更新被拒绝，因为远程版本库包含您本地尚不存在的提交。这通常是因为另外一个版本库已向该引用进行了推送。再次推送前，您可能需要先整合远程变更（如 'git pull ...'）：则使用强行更新 +master:

    git push -u origin +master  

这样就能够把本地仓库的代码push到我们Git上的Repository了～

8.6.如果说我们修改了代码，想再次push上去，此时我们Git上已经有了之前的版本内容了，只需要执行以下的命令就可以了，同样进入所要上传的文件的目录，提交修改：

    git add .   --->   git commit -m "提交的说明信息"   --->   git push -u origin master  


9.从GitHub克隆项目到本地（也就是说可能与别人共同合作一个project，此时别人的Git上已经有代码了，你想把别人的代码”下载“到自己本地（本地没有建立任何项目））
9.1.到Git的仓库右边复制“HTTPS clone url”
9.2.回到要存放的目录下，使用命令 

    git clone https://github.com/PentonBin/Demo.git（例子）  

clone下来之后就能把整个project clone下来了～
9.3.如果本地的版本不是最新的，可以使用命令 

    git fetch origin  

9.4.把更新的内容合并到本地分支，可以使用命令 

    git merge origin/master  

10.Git回滚操作
10.1.先使用

    git log  

查看日志，找到想要回滚的版本:git log
10.2.再使用

    git reset  

回滚到指定版本，如

    git reset –hard 
    4bb7bbc07f4b3792b48a6001bdfcc2b694cd3c81(这一串为commit的值)  


好了，以上就是GitHub的简单使用，推荐一个Git简易使用的web：http://www.bootcss.com/p/git-guide/