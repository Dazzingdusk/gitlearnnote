git下载安装以后先需要配置github
1、git config --global user.name "config name"
2、git config --global user.email "email address"

注意这里的参数global是指全局配置，即这个机器的配置，也可以单独的配置每一个仓库。

使用：
git是一个分布式的版本管理软件，因此你可以不需要服务器，而单独的运行在本地，一样可以进行版本的管理。
首先你需要本地建立一个版本仓库，毕竟git不可能帮你直接管理整个文件系统吧，所以你需要给他一个平台让他施展拳脚，
所以这个版本仓库（实际是一目录），就是他施展拳脚的“舞台”了。
在git bash中。一下三步就可以初始化一个仓库：
1、mikdir  仓库名
2、cd  仓库名
3、git init  
执行完上面三步，一个git仓库就配置好了，接下来就是开始使用了。