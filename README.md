## git 学习笔记


### 创建版本库
```
git init
```
```git init ```命令用于初始化一个git 仓库。
```
 git config --global user.name "Your Name"
 git config --global user.email "email@example.com"
```
设置git账号和邮箱
```
git log
```
该命令显示从最近到最远的提交日志

```
 git reset --hard Head^
```

回退到上一个版本。```Head```指当前版本，```Head^```表示上一个版本。依次类推。往事100个版本写作```Head~100```

```
git reset --hard 3628164(commitId)
```
也可以通过指定Id,回退到特定的提交版本

> ## 工作区和暂存区
> 一般防止代码的文件夹称之为工作区，工作区中有一个```.git```的文件夹,这个不算工作区，而是Git的版本库。
> ```.git```文件夹中包含很多东西，最重要的就是称为state的缓存区和当前分支（默认为```master```分支）
> 把文件添加到版本库分下面两步进行
> 1. git add fileName 将文件修改添加到暂存区
> 2. git commit -m "message" 将暂存区的所有文件修改添加到当前分支
> 上面两步可以通过```git commit -am "message"```这个命令合成一步，但这样并不能将新增文件提交到当前分支

```
git checkout   -- fileName
```
撤销工作区所做的更改，不管是删除还是修改都可以通过该命令“一键还原”
```
git rm fileName
git commit -m "messge"
```
上面两个命令可以提交工作区已经删除的文件。如果是误删除，则可以通过```git checkout -- fileName```还原文件
```
git checkout -b dev
```
```git checkout```命令加上```-b```参数表示创建并切换分支,其相当于下面两条命令
```
git branch dev
git checkout dev
```
```
git branch
```
查看当前分支
