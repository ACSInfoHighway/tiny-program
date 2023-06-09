# Golang入门教程

`Golang`是Google 2009年发布的开源编程语言，其主要目标是“兼具 Python 等动态语言的开发速度和 C/C++ 等编译型语言的性能与安全性”。

Go语言有时候被描述为“C 类似语言”，或者是“21 世纪的C语言”。Go从C语言继承了相似的表达式语法、控制流结构、基础数据类型、调用参数传值、指针等很多思想，还有C语言一直所看中的编译后机器码的运行效率以及和现有操作系统的无缝适配。Go语言的用途众多，可以进行网络编程、系统编程、并发编程、分布式编程。

## 安装Golang环境

1. 从[Golang官网](https://go.dev/dl/)获取go(`go1.17.7.linux-amd64.tar.gz`)语言安装包

```sh
wget https://go.dev/dl/go1.17.7.linux-amd64.tar.gz
```

2. 然后根据[安装文档](https://go.dev/doc/install)进行安装，执行go version返回如下表示安装成功。

```sh
czh@vm:~$ go version
go version go1.17.7 linux/amd64
```

*思考: 执行`go env`返回如下，其中`GOPATH`,`GOROOT`等变量作用是什么？如何进行设置？  *

```sh
czh@vm:~$ go env
GO111MODULE=""  
GOARCH="amd64"  
GOBIN=""  
GOCACHE="/home/czh/.cache/go-build"  
GOENV="/home/czh/.config/go/env"  
GOEXE=""  
GOEXPERIMENT=""  
GOFLAGS=""  
GOHOSTARCH="amd64"  
GOHOSTOS="linux"  
GOINSECURE=""  
GOMODCACHE="/home/czh/go/pkg/mod"  
GONOPROXY=""  
GONOSUMDB=""  
GOOS="linux"  
GOPATH="/home/czh/go"  
GOPRIVATE=""  
GOPROXY="https://proxy.golang.org,direct"  
GOROOT="/usr/local/go"  
GOSUMDB="sum.golang.org"  
GOTMPDIR=""  
GOTOOLDIR="/usr/local/go/pkg/tool/linux_amd64"  
GOVCS=""  
GOVERSION="go1.17.7"  
GCCGO="gccgo"  
AR="ar"  
CC="gcc"  
CXX="g++"  
CGO_ENABLED="1"  
GOMOD="/dev/null"  
CGO_CFLAGS="-g -O2"  
CGO_CPPFLAGS=""  
CGO_CXXFLAGS="-g -O2"  
CGO_FFLAGS="-g -O2"  
CGO_LDFLAGS="-g -O2"  
PKG_CONFIG="pkg-config"  
GOGCCFLAGS="-fPIC -m64 -pthread -fno-caret-diagnostics -Qunused-arguments -fmessage-length=0 -fdebug-prefix-map=/tmp/go-build396602306=/tmp/go-build -gno-record-gcc-switches"
```

## Go hello-world

执行如下命令创建`hello-world`工程目录：

```go
$ mkdir hello
$ cd hello
```

创建`hello.go`文件，代码如下：

```go
package main

import "fmt"

func main() {
    fmt.Println("Hello, World!")
}
```
> `main()`与c语言中的`main`函数租用一致，是整个程序的入口。

编译运行程序：
```
$ go run .
Hello, World!
```
> 思考：`go run .`与`go build`有什么区别？

## Go入门

关于`go`基本语法和进阶知识这里不再赘述，在网上有很多非常好的文档可以参考，`STFW`：

* [Go Tutorial Doc](https://go.dev/doc/tutorial/)
* [Go Playground](https://go.dev/play/)
* [A Go Tour](https://go.dev/tour/welcome/1)
* [Go语言圣经(中文版)](https://books.studygolang.com/gopl-zh/)

在实践和练习中熟悉go吧。

如果希望获得使用go设计模式上的指引，请浏览这些原则：

[Go Proverb](https://go-proverbs.github.io)

如果你对其他编程语言有一定的了解，可以参阅Gao Sion对Go语言较细节的学习[GoDetail](sec05_Go_details.md)。

否则可以直接看[下面的部分](sec06_Explore_more.md)

学习一门编程语言通常步骤如下：

- 学习语言基础，可以使用语言之间对比学习方法，具体来说包括以下内容：
    - 原生数据类型、数据结构及基本方法
    - 语法规范：
        - 变量声明/定义/使用
        - 运算符
        - 控制结构
        - 函数
- 掌握自动化编译工具，掌握调试方法
- 学习编程模式及语言特性，如面向对象/面向过程
- 理解产业界使用经验和标准模式
- 实践，在使用中学习官方库和第三方库的使用