# Git本地仓库

git init 命令将此目录变成Git可以管理的仓库

Windows自带的记事本最好不要编辑文件，原因是Microsoft开发记事本的团队使用了一个非常弱智的行为来保存UTF-8编码的文件，他们自作聪明地在每个文件开头添加了0xefbbbf（十六进制）的字符。建议下载Visual Studio Code代替记事本，不但功能强大，而且免费！

git add filename
git commit -m “描述文字” 把文件提交仓库
git status查看状态
git diff filename 查看不同，显示的格式正是Unix通用的diff格式\*\*

git log 查看历史记录

如果嫌输出信息太多，看得眼花缭乱的，可以试试加上--pretty=oneline参数
即 git log --prety=oneline

git reset --hard HEAD^ 回退一个版本（需要commit之后）

┌────┐
│HEAD│
└────┘
│
└──▶ ○ append GPL
│
○ add distributed
│
○ wrote a readme file

┌────┐
│HEAD│
└────┘
│
│    ○ append GPL
│    │
└──▶ ○ add distributed
│
○ wrote a readme file

git reflog （记录每一次命令）

Git缓冲区概念 -廖雪峰
<https://www.liaoxuefeng.com/wiki/896043488029600/897271968352576>

git checkout --filename 可以丢弃工作区的修改

git reset HEAD \<file> 可以把暂存区的修改撤销掉

git rm filename删除文件（后面还需要commit一下）

# 连接Github远程仓库

1.  在用户主目录下，看看有没有.ssh文件，如果没有创建SSH Key:
ssh-keygen -t rsa -C "youremail@example.com"：
2.  登陆GitHub，打开“Account settings”，“SSH Keys”页面。然后，点“Add SSH Key”，填上任意Title，在Key文本框里粘贴id_rsa.pub文件的内容。


git remote add origin git@github.com:自己的GitHub网址

$ git push -u origin master 将本地库的所有内容推送到远程库上

然后，只要本地做了提交，就可以通过命令:
git push origin master 把本地master分支的最新修改推送至Github




