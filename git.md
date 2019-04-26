## Git简易指南
[指南1](http://www.bootcss.com/p/git-guide/)  
[指南2](http://blog.jobbole.com/53573/)

### 安装
略

### 创建新仓库
1. 创建新文件夹，打开
2. 执行`git init`

### 检出仓库
1. 创建本地仓库克隆版本`git clone /path/to/repository`
2. 克隆远程服务器仓库`git clone username@host:/path/to/repository`或者`git clone path`

### 将已有仓库连接到某个远程服务器，并提交
`git remote add origin https://your_username@bitbucket.org/your_username/repository.git`  
第一次提交`git push -u origin master`  
后面提交只需要`git push`即可

### 添加与提交
1. 将改动添加到缓存区：`git add <filename>`或者`git add *`
2. 将改动提交到HEAD，但还没到远端仓库：`git commit -m "comment"`
3. 将改动提交到远端仓库：`git push origin master/git push`(其中，master可以换成任何分支)

### 更新本地仓库
`git pull origin master`

### 询问状态
`git status`

### 分支操作
#### 创建分支
`git checkout -b new_feature`

#### 查看当前项目下的所有分支
`git branch`