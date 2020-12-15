## Travis CI是什么？
Travis CI是为我们提供持续集成服务的工具，不需要我们自己搭建服务器，只需要连接github，配置好文件，就可以自动帮我们完成构建、测试和发布(*[什么是持续集成?](./持续集成.md)*)。 

## 如何工作？
**Travis CI目前只支持Github**  
程序员往github上推了代码 --> travis检测了到程序员这一行为 -->拉取最新的项目代码到travis --> 在travis的虚拟机中对这个项目进行run build --> 生成静态文件 --> 将静态文件传回给github的可识别目录，供github pages解析渲染。

travis为我们提供了一个node环境，帮我们来做一些重复性工作

## 如何使用？ 
1. 官网关联我们的github和项目 [Travis CI官网](https://travis-ci.com/)  
2. *设置github的[webhooks](webhooks.md)*
3. **配置.travis.yml**
   - 定义了Travis的行为,[YAML](YAML.md)格式的文件
   - 作用：指定Travis的行为，当有新的commit时，Travis就会寻找并执行其中的命令
   - [.travis.yml](travis.md)
4. 获取github域名或者在github pages中关联自己的域名

## GitBook
**基于git制作电子书的工具**
1. 克隆git仓库到本地
2. 编辑电子书
3. npm init -y将license改为创建仓库时的
4. 将写好的.travis.yml文件放在根目录下
5. 创建gh-pages分支，关联到远程，用于展示
6. 在[Travis CI官网](https://travis-ci.com/)配置我们所需要的环境变量

电子书就构建好了，提交测试一下。

## 利用webhook来制作自己的构建工具
**[本地模拟服务器webhooks过程](本地webhook.md)**