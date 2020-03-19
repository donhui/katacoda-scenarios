#### 启动 Jenkins
使用如下命令启动 Jenkins 容器：

`docker run -d --name jenkins \
    -p 8080:8080 -p 50000:50000 \
    --env JAVA_OPTS="-Djenkins.install.runSetupWizard=false" \
    donhui/jenkins-with-maven:2.204.5`{{execute}}

相关插件（git、pipeline）和工具（Maven）已经预先配置好；
8080 端口用来打开 web dashboard，50000 端口用来和其它 Jenkins agent 通信。

可以通过如下命令查看 Jenkins 容器日志：
`docker logs -f jenkins`{{execute}}

#### 打开 Dashboard

你可以通过下面 URL 打开 Jenkins Dashboard：`https://[[HOST_SUBDOMAIN]]-8080-[[KATACODA_HOST]].environments.katacoda.com/`{{open}}

用户名是：`admin`{{copy}}，密码是：`9YxwvCOUPML8onXF`{{copy}}

Jenkins 可能需要一点时间来完成启动并准备就绪，在接下来的步骤中，您将使用 Dashboard 开始构建 Maven 项目。
