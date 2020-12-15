## 什么是webhooks？
webhook也被称为反向API，**他是应用给其他应用提供实时信息的一种方式**，完全由后端推送。信息产生后，webhook会发送给已经注册的应用，使这些应用可以实时获取数据，避免用轮询获取数据。 
*** 
travis CI利用github提供的webhooks，监控仓库的操作，如push，当执行操作时，触发自动化构建任务。
***
同样，我们也可以用自己的服务器来实现自动化部署操作...
1. 在服务器中安装git并配置密钥`ssh-keygen -t rsa -C '邮箱'`，并在github中添加密钥
2. 在服务器clone仓库
3. 添加项目操作文件
4. 配置webhook  
   [github webhooks](https://github.com/7Hua/testBook/settings/hooks)

