# Git的使用

## 1、工作流程

==**1. Git仓库**==

==**2. 暂存区**==

==**3. 工作区**==

## 2、指令

1.**git status** ：查看当前文件的状况

2.**git add +文件名** ：将文件从工作区调到暂存区

3.**==git commit-m==+ ”提交描述”**  ：从暂存区到仓库

## 3、初始化一个新的Git仓库

### 1.基本信息设置

1.设置用户名

git config - - global user.name ‘github用户名’

2.设置邮箱

git config - - global user.email ‘github邮箱’

3.查看设置

git config - -list

### 2.初始化新的仓库

1.创建文件夹

2.在文件夹内初始化Git（创建Git仓库）

==用git init命令在指定目录下初始化一个新的Git仓库==

cd +新建文件夹内的文件名进入目录


### 3.向仓库中添加文件

touch 文件名



###  4.修改仓库文件

1. **vi +文件名** ：打开要修改的文件cd

   进入编辑模式：==输入i==进入插入模式，编辑文本

   退出编辑模式：用==ZZ命令==保存并退出

2. cat +文件名：显示修改的内容

3. 将文件从工作区调到暂存区

4. 从暂存区到仓库

### 5.删除文件

第一步：rm -rf +文件名（删除文件）

第二步：git rm +文件名（从Git中删除文件）

第三步：git commit -m+描述

## 4.Git管理远程仓库

### 1.Git克隆操作

目的：将远程仓库（GitHub对应的项目）复制到本地

==指令：git clone + GitHub上复制的链接==

==git push：将本地Git仓库中的提交推送到远程仓库==

**私有项目远程提交的方法**

用指令vi. git/config  将
[remote “origin”]

ur1=https://githhub.com/用户名/仓库名.git
修改为
[remote “origin”]

ur1=https://用户名：密码@githhub.com/用户名/仓库名.git



