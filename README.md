# 我的docker开发环境
参考FrankFang大佬构建的docker linux开发环境

## 容器功能
内置 git / vim / python3 / zsh / go / node / yarn / pnpm 等命令
给国内用户配置了加速镜像

## 使用方法

### 构建镜像
```shell
  # -t 指定镜像名称, .表示Dockerfile所在目录
  docker build -f Dockerfile -t oh-mz-docker .
```
