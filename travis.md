生命周期：
- before_install
- install(默认npm install)
- before_script
- script(默认npm test)
- aftersuccess或者afterfailure
- *before_deploy*
- *deploy* 快捷部署
- *after_deploy*
- after_script

```yml 
        language: node_js
        node_js:
          - "10"

        #指定缓存模块，可选。缓存可加快编译速度。
        cache:
          directories:
            - node_modules

        #准备阶段
        before_install:
          - npm install gitbook-cli -g

        #安装依赖
        install:
          - npm install

        before_script:
          #...

        #指定构建和测试脚本
        script:
          - gitbook install
          - gitbook build
          - cd ./_book
          
        #script成功之后的步骤
        after_success:

        #script失败之后的步骤
        after_failure:
          #...

        #script之后的步骤
        after_script:
          - git init
          - git config user.name "${U}"
          #- git config user.name "${USER_NAME}"
          - git config user.email "${USER_EMAIL}"
          - git add .
          - git commit -m "publish gitbook"
          - git push --force --quiet "https://${ACC_TOKEN}@${GH_REF}" master:${BRANCH}

        #指定要监视的分支，默认为主分支
        branches:
          only:
            - main

        #定义脚本内环境变量，在脚本内可直接使用
        env:
          - U=7hua
```
参数  
- USER_NAME：用户名
- USER_EMAIL：邮箱
- GH_REF：项目地址（注意不要加https）
- BRANCH：发布分支
- ACC_TOKEN：github通行证([github](https://github.com/))

0ba177cdaf0461916ba552c1ed8746708e9c51be
  