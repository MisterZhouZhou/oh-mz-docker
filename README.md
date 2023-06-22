# 我的docker开发环境
参考FrankFang大佬构建的docker linux开发环境

## 容器功能
内置 git / vim / python3 / zsh / go / node / yarn / pnpm / ruby3 / rails / deno  等命令
给国内用户配置了加速镜像

## 使用方法

### 构建镜像
```shell
  # -t 指定镜像名称, .表示Dockerfile所在目录
  docker build -f Dockerfile -t oh-mz-docker-linux .
```
### 使用示例
https://github.com/MisterZhouZhou/oh-mz-dev

## .devcontainer/devcontainer.json 参考
```json
{
	"name": "OhMyDocker",
	"context": "..",
	"dockerFile": "/path/to/Dockerfile",
	"settings": {},
	"extensions": [],
	"runArgs": [
		//"--network=network1",
		//"--memory=10240m",
		//"--memory-swap=10240m"
		"--dns=114.114.114.114",
		"--privileged",
	],
	"mounts": [
		"source=chezmoi,target=/root/.local/share/chezmoi,type=volume",
		"source=repos,target=/root/repos,type=volume",
		"source=vscode-extensions,target=/root/.vscode-server/extensions,type=volume",
    "source=go-bin,target=/root/go/bin,type=volume",
	],
	"remoteUser": "root",
	"postStartCommand": "/usr/sbin/dockerd & /usr/sbin/sshd -D"
}
```
