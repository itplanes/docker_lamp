# 基于docker的LAMP环境

## 说明
这是一个基于docker的LAMP环境，并利用PowerShell提供在windows下的个性配置集中管理（其中根目录下的"[开始.bat](https://github.com/aogg/docker_lamp/blob/master/%E5%BC%80%E5%A7%8B.bat)"可一步构建docker环境，并可重启所有容器。）



## 使用
- 1、修改[/powerShell/local.ps1](https://github.com/aogg/docker_lamp/blob/master/powerShell/local.ps1)文件，
更多配置设置可在[/powerShell/common.ps1](https://github.com/aogg/docker_lamp/blob/master/powerShell/common.ps1)中
- 2、配置执行文件的环境变量，可查看[/powerShell/command-alias.ps1](https://github.com/aogg/docker_lamp/blob/master/powerShell/command-alias.ps1)文件，其中VBoxManage在virtualbox的bin目录下
- 3、双击"[开始.bat](https://github.com/aogg/docker_lamp/blob/master/%E5%BC%80%E5%A7%8B.bat)"


**注意**
- 1、如果首次运行"[开始.bat](https://github.com/aogg/docker_lamp/blob/master/%E5%BC%80%E5%A7%8B.bat)"并在创建容器时报错，继续双击运行即可。


## 结构说明

**开始.bat**<br />
首次已管理员身份打开，然后以后就直接双击即可（这里管理员和当前用户对于docker-machine是有区别的）


**容器配置**<br />
各容器放在docker文件夹内，对应配置也在容器文件夹的conf文件夹<br />
其中php、nginx的conf文件夹已实现共享，可本地修改并在容器内及时体现出
如：<br />
1、[docker/php/conf/conf/php.ini](https://github.com/aogg/docker_lamp/blob/master/docker/php/conf/conf/php.ini)<br />
2、[docker/php/conf/etc/php-fpm.conf](https://github.com/aogg/docker_lamp/blob/master/docker/php/conf/etc/php-fpm.conf)<br />
3、[docker/nginx/conf/nginx.conf](https://github.com/aogg/docker_lamp/blob/master/docker/nginx/conf/nginx.conf)<br />

其中sources.list是通过COPY过去，所以如要修改必须重新构建所有容器