# Git使用问题整理




** fatal: in unpopulated submodule XXX

若是直接从 github 中下载到对应的项目，直接放到自己的版本控制中，在提交就会报此错误 fatal: in unpopulated submodule.

*即使删除了.git 文件也是没用的。*

解决办法:

#+BEGIN_SRC sh
git rm -rf --cached
git add .
#+END_SRC

** GitHub Actions Workflow

*** refusing to allow an OAuth App to create or update workflow {0} without workflow scope

因为 OAuth 的应用没有指定 workflow 范围，所以无法推送带有更新 workflow 的分支。

*** refusing to allow a Personal Access Token to create or update workflow

GitHub Personal Access Tokens 页面,生成一个新的 Token。特别注意在生成的时候要 =勾选 workflow=.

在 Windows 凭据管理器(控制面板\所有控制面板项\凭据管理器)中，找到 GitHub 的几个凭据，然后编辑：

- git:https://github.com
- git:https://usernaem.com

推送的时候如果要求你输入账号密码，输入那个 Token 作为密码即可。

- [[https://blog.walterlv.com/post/github-push-failed-without-workflow-scope.html][包含 GitHub Actions Workflow 的分支无法推送]]

  
** error: server certificate verification failed.
CAfile: /etc/ssl/certs/ca-certificates.crt CRLfile: none

证书校验有问题,解决方法是加一个环境变量;

- linux
  =export GIT_SSL_NO_VERIFY=1=
- windows
  =set GIT_SSL_NO_VERIFY 1=

之后 =git config --global http.sslVerify false=

