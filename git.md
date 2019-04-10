## [Git简易指南](http://www.bootcss.com/p/git-guide/)

### 安装
略

### 创建新仓库
1. 创建新文件夹，打开
2. 执行`git init`

### 检出仓库
1. 创建本地仓库克隆版本`git clone /path/to/repository`
2. 克隆远程服务器仓库`git clone username@host:/path/to/repository`或者`git clone path`

### 将已有仓库连接到某个远程服务器
`git remote add origin <server>`

### 添加与提交
1. 将改动添加到缓存区：`git add <filename>`或者`git add *`
2. 将改动提交到HEAD，但还没到远端仓库：`git commit -m "comment"`
3. 将改动提交到远端仓库：`git push origin master`(其中，master可以换成任何分支)

### 更新本地仓库
`git pull`