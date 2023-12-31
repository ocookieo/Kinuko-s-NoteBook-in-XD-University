# Git的初始配置
本文档仅基于Windows系统下的第一次配置，且谨记Unix的哲学是没有消息就是好消息，所以输入指令后没有反应就是成功的表现。
## 姓名和邮箱的设置
直接到官网上下载Git，然后设置全部都点next。

第一次使用之前需要提供用户姓名和邮箱，使用win+cmd键打开windows的命令行
```
git config --global user.name "Your Name"
git config --global user.email "email@example.com"
```
这个设置基于Git是分布式版本控制系统，所以不可避免的需要让电脑提供姓名和邮箱，这里使用的global定义了全局变量，表示这台机器上的所有用户都是使用这个姓名和邮箱，所以建议不要随便乱写。

在设置完后方可在VS Code上使用Git，否则会报错。

## 创建一个版本库
版本库又叫仓库，英文名：**repository**，这个版本库里的文件都可以被git所管理。强烈建议这里所建立的路径里面不要有任何的中文，这将会引起巨大的错误。

在当前目录下创建一个文件，并把路径改成这个文件下，这个文件名为*learngit*
```
mkdir learngit
cd learngit
```
通过git init命令将该目录改成Git可管理的仓库
```
git init
```
## 将文件添加到版本库里
这个文件一定要放在该版本库目录下，或者子目录。

使用Window的用户千万不要使用Windows自带的记事本编辑任何文本文件，建议你下载Visual Studio Code代替记事本。

第一步：使用`git add`命令将文件添加到仓库：
```
git add readme.txt
```
第二步：使用`git commit`命令将文件提交到仓库：
```
git commit -m "wrote a readme file"
```
$ -m $是为这个提交，附加一个说明，方便自己和别人理解阅读，请务必这么做。

git commit命令执行成功后会告诉你，1 file changed：1个文件被改动（我们新添加的readme.txt文件）；2 insertions：插入了两行内容（readme.txt有两行内容）。

### 一次提交多个文件
```
git add file1.txt
git add file2.txt file3.txt
git commit -m "add 3 files."
```

