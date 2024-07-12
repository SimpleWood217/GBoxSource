GBoxSource

#介绍
GBox软件源管理系统

#软件架构
基于ThinkPHP5+HTML开发

#安装教程
1.  下载源码包
2.  将源码包上传至服务器
3.  创建数据库
4.  设置PHP版本为7.0-7.2
5.  设置伪静态为ThinkPHP
6.   置运行目录为public
7.  访问域名即可开始安装

#Nginx伪静态
`location ~* (runtime|application)/{
	return 403;
}
location / {
	if (!-e $request_filename){
		rewrite  ^(.*)$  /index.php?s=$1  last;   break;
	}
}`

#Apache伪静态
	<IfModule mod_rewrite.c>
	  Options +FollowSymlinks -Multiviews
	  RewriteEngine On
	  RewriteCond %{REQUEST_FILENAME} !-d
	  RewriteCond %{REQUEST_FILENAME} !-f
	  RewriteRule ^(.*)$ index.php?s=$1 [QSA,PT,L]
	</IfModule>
