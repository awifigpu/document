http://fromwiz.com/share/s/0bqLw11P6APg2N4yAq0vIkJk0DP2FF2otA5x2Q2MGR12h3AU

***

# 项目结构
目录    |                         |说明        
---------------------|----------------------|-------------------
|project_name|                 |  目录， 项目名   
|                        | src             |  目录， 代码目录
|                       |  bin             | 目录，放运行脚本
|                        | data            |  目录，一些数据，比如图片视频   
|                         | models            | 目录，  训练模型数据
|                        | logs              | 目录，    日志目录   
|                       |  conf             | 目录，配置文件目录
|                       |  setup.py            |  python文件，安装、部署、打包的脚本。
|                      |requirements.txt  |  文件，项目依赖说明
|                       |README.md       |  文件， 项目部署，运行，注意事项，配置说明


# 注意

src用到的data，logs，conf，models必须使用相对路径。

有些没用到的文件或者目录可以不加
