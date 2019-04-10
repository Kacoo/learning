## Eclipse配置
### 1. lombok插件
下载lombok.jar，命令行用`java -jar lombok.jar`命令打开  
找到Eclipse的安装目录，选中`eclipse.exe`  
点击安装，出现`Successfully`即可（安装速度很快，1s完成）

### 2. Maven配置
1. 下载apache-maven-3.5.2（文件夹）  
2. 编辑系统变量，增加变量名`MAVEN_HOME`，变量值为本地Maven路径，如F:/apache-maven-3.5.2
3. 编辑环境变量，新增`%MAVEN_HOME%\bin`
4. 修改apache-maven-3.5.2/conf/settings.xml，将标签<localRepository>里的路径改成本地MAVEN仓库的路径，如D:/MAVEN/repo  
5. 打开Eclipse，进入Window-Preferences，搜索maven  
Installations中加入本地Maven路径，如F:/apache-maven-3.5.2  
User Settings中，User Settings目录改为本地Maven配置文件路径，如F:/apache-maven-3.5.2\conf\settings.xml；Local Repository目录改为本地仓库路径，如D:/MAVEN/repo  
6. 打开Eclipse，进入Window-Preferences，搜索java
Compiler中Compiler compliance level选择JDK版本，暂时是1.8  

### 3. SVN插件
1. 下载SVN插件包`site-1.10.7`
2. 将其中features目录和plugins目录下的文件拷贝到Eclipse安装目录下的对应文件夹中
3. 重启Eclipse

### 4. JDK设置
百度百科一大堆

### 5. Tomcat配置


### 6.一些问题
1. tomcat项目缺包问题  
右键项目名-Properties-Java Build Path-Libraries-Add External JARs，加入JAR包  
Add Library，加入Tomcat的lib


