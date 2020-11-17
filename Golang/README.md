# Golang 学习笔记
## 目录
- [数据类型](../Golang/数据类型.md)
- [常用标准库](../Golang/常用标准库.md)
- 网络编程

## 配置 Go SDK（待完善）
本文档用在 `Windows 10` 环境下的 `Go` 环境配置。

### go get
`go get` 命令被用于安装包及其依赖。如果加上 `-u` 参数，代表强制软件包为最新版本；如果是 `-d` 参数，则可以跳过编译和安装的步骤，只是将存储库克隆到 `$GOPATH` 中。

```Go
go get -u github.com/gin-gonic/gin //安装 Gin 包
```
### go build & go install

`go install` 用于编译包和依赖，当没有指定参数时，表示编译或安装当前目录的所有包。

### 清除缓存

当开启 `GO111MODULE=on` 后，下载的模块内容会缓存在 `$GOPATH/pkg/mod` 目录中，如果要清除模块中的缓存，可用以下命令：

```Go
go clean --modcache
```
