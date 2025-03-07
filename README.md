## 从 GHCR 拉取镜像
1. 登录 GHCR `echo $GHCR_PASSWORD | docker login ghcr.io -u $GHCR_USERNAME --password-stdin`
这里 $GHCR_USERNAME 是你的 GitHub 用户名，而 $GHCR_PASSWORD 可以是你的个人访问令牌（PAT），该令牌需要有适当的权限来读取私有仓库或访问公共仓库。
2. 拉取镜像 `docker pull ghcr.io/your-github-username/myimage:latest`
将 your-github-username 替换为你的实际 GitHub 用户名或组织名，myimage 替换为你推送的具体镜像名称，latest 替换为你想要拉取的具体标签。

## 推送到阿里云容器镜像服务
1. 登录阿里云Docker Registry
$ docker login --username=[myusername] registry.cn-shanghai.aliyuncs.com
用于登录的用户名为阿里云账号全名，密码为开通服务时设置的密码
2. 从Registry中拉取镜像
$ docker pull registry.cn-shanghai.aliyuncs.com/[myusername]/[myimage]:[镜像版本号]
3. 将镜像推送到Registry
$ docker login --username=[myusername] registry.cn-shanghai.aliyuncs.com
$ docker tag [ImageId] registry.cn-shanghai.aliyuncs.com/[myimage]:[镜像版本号]
$ docker push registry.cn-shanghai.aliyuncs.com/[mynamespace]/[myimage]:[镜像版本号]
