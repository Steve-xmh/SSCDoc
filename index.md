# SteveScratchC Lua API

每个函数都会附上可用最低版本和可用最高版本（SSC）（Ex: 1.0.0+ 2.0.0-）

# 目录

[SSC](#ssc-主函数)

[SSCBlock](#SSCBlock-类)

---

## ssc 主函数

这里存放了 SSC 库自带的函数，可以使用

---

`string ssc.typeof(obj)`

>注意：本函数尚未完成，仍在制作之中

返回 SSC 对象的类型名称，Lua 原生的 `type()` 对于 SSC 自身的对象只能返回 `userdata`

`nil ssc.msgBox(msg,...)`

显示一个信息框

`nil ssc.loadProject(filename)`

>注意：本函数尚未完成，仍在制作之中

打开一个工程

`nil ssc.savdProject(filename)`

>注意：本函数尚未完成，仍在制作之中

保存一个工程

`nil ssc.newProject()`

>注意：本函数尚未完成，仍在制作之中

新建一个工程

`nil ssc.runStep(minTime = 16)`

>注意：本函数尚未完成，仍在制作之中

执行一次程序循环，直到最高耗时结束（默认 1/60 秒）（minTime 单位为毫秒）

## SSCBlock 类

本类用于对模块的单独操作

---

`SSCBlock ssc.block.new(cmdName = "undefined")`

>注意：本函数尚未完成，仍在制作之中

新建一个模块对象，并返回这个对象

`nil ssc.block.setPos(SSCBlock obj, number X = nil, number Y = nil)`

>注意：本函数尚未完成，仍在制作之中

设置模块 obj 的位置，以代码编辑页面左上角为原点，如某坐标参数为 `nil` 则不对其轴坐标更改

`number,number ssc.block.setPos(SSCBlock obj)`

>注意：本函数尚未完成，仍在制作之中

获取模块 obj 的坐标，返回 X 坐标和 Y 坐标

`SSCBlock/string/number/nil ssc.block.setArg(SSCBlock obj, number argPos, SSCBlock/string/number argBlock = nil)`

>注意：本函数尚未完成，仍在制作之中

设置模块 obj 中指定位置的变量槽中的子模块 argBlock，你可以设置 Lua 常量到其中，如果原先已有模块或常量值则返回这个旧值，而模块则会被重新放置到离原模块最近的地方

`nil ssc.block.setFunction(SSCBlock obj, function fun)`

>注意：本函数尚未完成，仍在制作之中

设置模块 obj 的执行函数，你可以使用 Lua 来制作你的自定义模块，这样会导致原模块功能丧失且无法恢复
