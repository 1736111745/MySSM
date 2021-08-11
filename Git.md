# Git

- 版本控制工具

### 一.入门

#### 1.安装

##### 1.下载地址

按ctrl+鼠标左键单击[下载地址](http://git-scm.com/downloads)

##### 2.安装包安装步骤

1. <img src="图片\Git安装\Git安装1.png" alt="Git安装1" style="zoom:50%;" />

2. 选择安装路径

<img src="图片\Git安装\Git安装2.png" alt="Git安装2" style="zoom:50%;" />

3. <img src="图片\Git安装\Git安装3.png" alt="Git安装3" style="zoom:50%;" />

4. 之后一路Next

##### 3.初始化仓库

1. 新建文件夹

   - 也就是本地仓库

   - 例: D:\project\MyGit
   - <img src="图片\Git安装\Git初始化1.png" alt="Git初始化1" style="zoom:50%;" />

2. 进入新建的文件夹，打开Git命令控制台
   - <img src="图片\Git安装\Git初始化2.png" alt="Git初始化2" style="zoom:50%;" />

3. 使用Git命令设置Git本地仓库用户信息
   - <img src="图片\Git安装\Git初始化3.png" alt="Git初始化3" style="zoom:67%;" />

4. 使用Git命令初始化本地仓库
   - <img src="图片\Git安装\Git初始化4.png" alt="Git初始化4" style="zoom:50%;" />

5. 从远程仓库克隆项目到本地
   - 先获得远程仓库项目地址<img src="图片\Git安装\Git初始化5-1.png" alt="Git初始化5-1" style="zoom:50%;" />
   - 然后使用Git命令从远程仓库将项目克隆到本地
   - <img src="图片\Git安装\Git初始化5-2.png" alt="Git初始化5-2" style="zoom:50%;" />

#### 2.基本的Git命令

##### 1.Git基本概念

- **版本库**：前面看到的.git隐藏文件夹就是版本库，版本库中存储了很多配置信息，日志信息和文件版本信息等

- **工作目录**`工作区`：包含.git文件夹的目录就是工作目录（例：MyGit）主要用于存放开发的代码

- **暂存区**：.git文件夹中有很多文件，其中一个index文件就是暂存区，也可以叫做stage，暂存区是一个临时保存修改文件的地方

- **Git工作目录**下的**文件**存在两种**状态**：
  - untracked:未跟踪（未被纳入版本控制）
  - tracked:已跟踪（被纳入版本控制）
    - Unmodified：未修改状态
    - Modified:已修改状态
    - Staged:已暂存状态

##### 2.本地仓库操作

<img src="图片\Git安装\Git基本命令1.png" alt="Git基本命令1" style="zoom:80%;" />

- **git status** ：查看文件状态
  - 查看的是工作目录、暂存区、版本库三者是否做到统一

- <img src="图片\Git安装\Git基本命令查看文件状态.png" alt="Git基本命令查看文件状态" style="zoom:67%;" />

- **git add**：将工作目录文件 `提交/添加` 到 暂存区
  - git add 文件名

- <img src="图片\Git安装\Git基本命令添加文件到暂存区.png" alt="Git基本命令添加文件到暂存区" style="zoom:67%;" />

- **git reset**:将暂存区的文件`取消暂存`
  - git reset 文件名

- <img src="图片\Git安装\Git基本命令取消文件暂存.png" alt="Git基本命令取消文件暂存" style="zoom:67%;" />

- **git commit** ：将文件从暂存区`提交到版本库`
  - git commit 文件名 -m "日志说明" 文件名

- <img src="图片\Git安装\Git基本命令提交文件到版本库.png" alt="Git基本命令提交文件到版本库" style="zoom:67%;" />

- **git rm**:删除文件
  - git rm 文件名

> git rm命令，首先删除的是工作目录的文件，并不影响版本库，如果要同步，则需要提交改变到版本库

> 使用命令 git commit -m "delete 文件名"

- <img src="图片\Git安装\Git基本命令删除文件并同步到版本库.png" alt="Git基本命令删除文件并同步到版本库" style="zoom:67%;" />

- **.gitignore**:忽略需要添加和提交的文件
  1. 首先再工作目录创建文件名为.gitignore的文件（名字是固定的不能任意命名）
  2. 其次按照需求和语法，在.gitignore文件内编辑语句，添加需要忽略的文件
     - *.a ：忽略所有后缀名为a的文件
     - ！lib.a：即使忽略所有后缀名为a的文件，也不忽略lib.a文件
     - /todo:只忽略工作目录中todo文件夹下的文件，不忽略todo文件夹下，子文件夹下的文件
     - build/：忽略工作目录中build文件夹下的所有文件及目录
     - doc/*.txt:忽略工作目录中doc文件夹下的所有后缀名为txt的文件
     - doc/* * / *.pdf:忽略工作目录中doc文件件下的所有目录及子目录中后缀为pdf的文件

- <img src="图片\Git安装\Git基本命令忽略需要添加和提交的文件.png" alt="Git基本命令忽略需要添加和提交的文件" style="zoom:67%;" />

- **git log** :查看日志
  - git log 
  - 按q退出日志

- <img src="图片\Git安装\Git基本命令查看日志.png" alt="Git基本命令查看日志" style="zoom:67%;" />

##### 3.远程仓库操作

- **git remote**:查看关联的远程仓库
  - 
- <img src="图片\Git安装\Git基本命令查看远程数据库.png" alt="Git基本命令查看远程数据库" style="zoom:67%;" />
-  **git clone** :克隆远程仓库
  - git clone 远程仓库地址
- <img src="图片\Git安装\Git基本命令克隆远程仓库.png" alt="Git基本命令克隆远程仓库" style="zoom:67%;" />
- **git remote add** :添加/关联一个远程仓库
  - git remote add 自定义远程仓库别名 远程仓库地址
- <img src="图片\Git安装\Git基本命令关联远程仓库.png" alt="Git基本命令关联远程仓库" style="zoom:67%;" />
- **git remote rm**:移除一个关联的远程仓库
  - git remote rm 要移除的远程仓库别名
- <img src="图片\Git安装\Git基本命令移除关联的远程仓库.png" alt="Git基本命令移除关联的远程仓库" style="zoom:67%;" />
- **git fetch**:从远程仓库抓取最新版本到本地版本库，不会自动合并（不会自动加载到工作目录）
  - **git fetch** 远程仓库别名 远程仓库分支名
  - 合并版本库中最新版本远程仓库文件到本地工作目录： **git merge**  远程仓库别名/分支名
- <img src="图片\Git安装\Git基本命令抓取远程仓库最新版本.png" alt="Git基本命令抓取远程仓库最新版本" style="zoom:67%;" />
- **git pull** :从远程仓库拉取最新版本到本地版本库并合并到本地工作目录
  - **git pull** 远程仓库别名 远程仓库分支名 
  - 如果报：fatal: refusing to merge unrelated histories 错误 
  - 使用 **git pull** 远程仓库别名 远程仓库分支名 --allow-unrelated-histories 命令即可

- <img src="图片\Git安装\Git基本命令拉取远程仓库.png" alt="Git基本命令拉取远程仓库" style="zoom:67%;" />

- git push :将本地工作目录推送到远程仓库
  - git push 远程仓库别名 远程仓库分支名

- <img src="图片\Git安装\Git基本命令推送到远程仓库.png" alt="Git基本命令推送到远程仓库" style="zoom:50%;" />

##### 4.Git分支

- **git branch**:查看分支
  - git branch:查看本地所有分支
  - git branch -r:查看所有远程分支
  - git branch -a:查看本地和远程所有分支

- <img src="图片\Git安装\Git基本命令查看分支.png" alt="Git基本命令查看分支" style="zoom:50%;" />

- git branch git:创建分支
  - git branch 需要创建的分支名

- <img src="图片\Git安装\Git基本命令创建分支.png" alt="Git基本命令创建分支" style="zoom:50%;" />

- git checkout:切换分支
  - git checkout 需要切换的分支名

- <img src="图片\Git安装\Git基本命令切换分支.png" alt="Git基本命令切换分支" style="zoom:50%;" />

- git branch:删除分支
  - git branch -d :删除本地分支
  - 如果从远程拉取了分支，本地又修改了该分支内的文件（本地和远程不一致）,此时要删除需要使用以下命令
  - git branch -D:强制删除本地分支

- <img src="图片\Git安装\Git基本命令删除本地分支.png" alt="Git基本命令删除本地分支" style="zoom:50%;" />

- git push:推送本地分支到远程仓库
  - git push 远程仓库别名 要推送的本地分支名

- <img src="图片\Git安装\Git基本命令推送分支到远程仓库.png" alt="Git基本命令推送分支到远程仓库" style="zoom:50%;" />

- git merge :合并分支
  - git merge 要被合并的分支名

- <img src="图片\Git安装\Git基本命令合并分支.png" alt="Git基本命令合并分支" style="zoom:50%;" />

##### 5.Git标签

- git tag :查看标签
  - git tag :列出所有标签
  - git show 标签名：查看标签信息

- <img src="图片\Git安装\Git基本命令查看标签.png" alt="Git基本命令查看标签" style="zoom:50%;" />

- git tag :添加标签
  - git tag 要创建的标签名

- <img src="图片\Git安装\Git基本命令添加标签.png" alt="Git基本命令添加标签" style="zoom:50%;" />

- git tag :删除标签
  - git tag -d 要删除的标签名
  - git push origin :refs/tags/要删除的标签名
