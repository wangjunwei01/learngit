#git workflow

## 登陆/注册
* 注册[gitlab](http://10.96.177.116)账号，注册后请联系管理员，管理员会将你加入crossgate开发组中
* 安装git: [official downloads](https://git-scm.com/downloads), 尽量不要使用git gui客户端, 它会隐藏大量有用的信息和操作
* 使用git bash生成ssh key:`ssh-keygen -t rsa -C"your name"`，将public key拷贝到你的剪切板: `cat /c/Users/user_name/.ssh/id_rsa.pub`
* 在[gitlab](http://10.96.177.116)上粘贴你的public key：右上角用户头像 -> settings -> SSH Keys （可以增加多个public keys）

## 创建 crossgate 项目
* 在[crossgate/backend](http://10.96.177.116/crossgate/backend)项目页面，点击Fork按钮，将该项目fork到自己的页面里（点击自己的头像），现在你就拥有了只属于自己的项目拷贝
* clone该项目到本地`git clone git@10.96.177.116:your_page/backend.git`
* clone完成后，使用`git status`检查一下本地git的状态，，默认分支为`dev_PR2`
* 添加remote upstream，`git remote add upstream git@10.96.177.116:crossgate/backend.git`, 该设置用来检查和跟踪主项目的更新

## Daiy Routine - 日常
* 获取主项目更新：`git fetch upstream`
* 合并主项目分支：`git merge upstream/dev_PR1`(或者你需要的分支，经常合并主项目上的更新，以便之后更快的合并到主项目)
* 提交，并关联到JIRA，`git commit -m'CROSSGATE-1024: 这个提交解决了JIRA上编号为1024的问题'`,`git push`，每天**必做**的事情，这样就会更新JIRA上分配给你的任务的状态
* 当一个任务完成可以提交测试的时候，在你的gitlab项目页面，点击“merge request”按钮，向主项目提交merge请求
* 当主管代码review完成，测试完成后，便可以将该merge请求合并到主项目中。

