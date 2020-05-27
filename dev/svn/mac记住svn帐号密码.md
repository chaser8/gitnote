1、查看 主目录下：~/.subversion/config 文件，找到“store-auth-creds = no”这句，看前面是否有#号注释符。 
如果没有，则或者加上#号，或者将no改为yes。

2、查看 主目录下： ~/.subversion/auth/的目录权限，当前用户是否具有可写权限。 
   查看 主目录下： ~/.subversion/auth/svn.simple/ 目录下是否存在文件。存在的话，看文件权限是否可写。 
   不可写的，改成可写权限。
需要让用户属于本机用户

chmod -R user 