---
layout: post
title: golang 开发笔记
category: go
tags: go
keywords: go
description: go
---

一般建议package的名称和目录名保持一致

go get -u 参数可以自动更新包，而且当go get的时候会自动获取该包依赖的其他第三方包

如果是普通包，当你执行go build之后，它不会产生任何文件。如果你需要在$GOPATH/pkg下生成相应的文件，那就得执行go install。

如果是main包，当你执行go build之后，它就会在当前目录下生成一个可执行文件。如果你需要在$GOPATH/bin下生成相应的文件，需要执行go install，或者使用go build -o 路径/a.exe。

如果某个项目文件夹下有多个文件，而你只想编译某个文件，就可在go build之后加上文件名，例如go build a.go；go build命令默认会编译当前目录下的所有go文件。

你也可以指定编译输出的文件名。我们可以指定go build -o astaxie.exe，默认情况是你的package名(非main包)，或者是第一个源文件的文件名(main包)。

var vname1, vname2, vname3 type= v1, v2, v3

vname1, vname2, vname3 := v1, v2, v3
:= 这个符号直接取代了var和type,这种形式叫做简短声明。不过它有一个限制，那就是它只能用在函数内部；在函数外部使用则会无法编译通过，所以一般用var方式来定义全局变量。

Go对于已声明但未使用的变量会在编译阶段报错，比如下面的代码就会产生一个错误：声明了i但未使用。
```bash
package main

func main() {
	var i int
}
```

> _（下划线）是个特殊的变量名，任何赋予它的值都会被丢弃。在这个例子中，我们将值35赋予b，并同时丢弃34：
```bash
_, b := 34, 35
```

常量
所谓常量，也就是在程序编译阶段就确定下来的值，而程序在运行时无法改变该值。在Go程序中，常量可定义为数值、布尔值或字符串等类型。

它的语法如下：

const constantName = value
//如果需要，也可以明确指定常量的类型：
const Pi float32 = 3.1415926

Go 常量和一般程序语言不同的是，可以指定相当多的小数位数(例如200位)， 若指定給float32自动缩短为32bit，指定给float64自动缩短为64bit