1、使用git add 命令时出现 warning：LF will be replaced by CRLF in ××××.×× 的解决办法。
出现原因：因为win下换行是（(CR)\r(LF)\n）,而在linux下换行符是\n 。所以这里git会自动的将LF装换成CRLF，因此进行提示。

解决方法：禁用git自动装换就行，主要有一下集中情况：

（1）、如果版本库/项目还没被创建，执行以下操作：
		git config --global core.autocrlf false     //在全局禁用自动转换
（2）、如果版本库/项目已经创建，使用非全局禁用自动转换
		git config core.autocrlf false              //在当前版本库中禁用自动转换
（3）、如果版本库/项目已经创建，在全局禁用自动转换则需要先
	rm -rf .git删除之前创建的.git 文件后添加上面的设置。 
	删除整个.git会把跟远程的链接都断掉，整个git的提交历史/版本库都会被删除！
		
core.autocrlf是git中负责处理line ending的变量，可以设置3个值：true，false，inout。
（1）设置为true【config --global core.autocrlf true】
	当设置成true时，这意味着你在任何时候添加(add)文件到git仓库时，
	git都会视为它是一个文本文件(text file)。它将把CRLF变成LF。
（2）设置为false【config --global core.autocrlf false】
	当设置成false时，line endings将不做转换操作。文本文件保持原来的样子。
（3）设置为input时，添加文件git仓库时，git把CRLF变成LF。
	当有人Check代码时还是lf方式。因此在window操作系统下，不要使用这个设置。

出现上面那个警告的原因是：windows中的换行符为CRLF，而Linux下的换行符为LF（使用Git命令行Git Bash，实际上就是相当于linux环境），
所以在执行git add xxx.xx操作时，会出现这个警告提示！
