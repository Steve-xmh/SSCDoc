# SteveScratchC Lua API

这里是 SteveScratchC 中内嵌语言 Lua 的函数文档，你可以通过已有函数制作插件或自定义模块。

每个函数都会附上可用最低版本和可用最高版本（SSC）（Ex: 1.0.0+ 2.0.0-）

# 目录

[关于 Lua 原生函数部分差异](#关于-Lua-原生函数的部分差异)

[SSC](#SSC-主函数)

[SSCBlock](#SSCBlock-类)

[SSCThread](#SSCThread-类)

---

## 关于 Lua 原生函数的部分差异

在 SteveScratchC 中，由于图形化和用途等缘故 ~~（还有开发者咕咕咕咕咕咕咕）~~ ，部分功能会不能正常运作。

---

1. `io` 库中的文件流 `stdin` `stdout` `stderr` 均无法正常使用，它们只能在调试版本中的命令提示符中输入输出，请不要在正式版本中使用这些文件流，否则会出现一些无法预料的后果！
2. `error` 函数可能无法正常的输出栈回溯信息，可能不能更好的帮助调试，也许通过 `debug.traceback()` 可以获得完整的栈回溯

---

## SSC 主函数

这里存放了 SSC 库自带的函数，可以通过 `ssc.functionName(...)` 来直接使用

---

`string ssc.typeof(obj)`

>注意：本函数尚未完成，仍在制作之中（或许会出现在以后的版本）

返回 SSC 对象的类型名称，Lua 原生的 `type()` 对于 SSC 自身的对象只能返回 `userdata`

`nil ssc.msgBox(msg)`

显示一个信息框，显示时 Lua 程序会等待信息框关闭后继续执行

`string ssc.askBox(msg)`

显示一个询问框，类似“是、否、取消”的信息框，询问询问结束后会返回以下信息：

* `"yes"` 用户按下“是”钮
* `"no"` 用户按下“否”钮
* `"cancel"` 用户按下“取消”钮

`nil ssc.loadProject(filename)`

>注意：本函数尚未完成，仍在制作之中（或许会出现在以后的版本）

打开一个工程

`nil ssc.savdProject(filename)`

>注意：本函数尚未完成，仍在制作之中（或许会出现在以后的版本）

保存一个工程

`nil ssc.newProject()`

>注意：本函数尚未完成，仍在制作之中（或许会出现在以后的版本）

新建一个工程

`nil ssc.runStep(minTime = 16)`

>注意：本函数尚未完成，仍在制作之中（或许会出现在以后的版本）

执行一次程序循环，直到最高耗时结束（默认 1/60 秒左右）（minTime 单位为毫秒）

`table ssc.block`

[SSCBlock](#SSCBlock-类) 所需函数库

---

## SSCBlock 类

SSCBlock 是 SteveScratchC 中解释器的解释基本单位，它用于执行任何挂载到 SSCBlock 的函数，同时指挥 SSCThread 继续执行下一个模块，你可以通过 `ssc.block.functionName(...)` 来操作 SSCBlock 类。

---

`SSCBlock ssc.block.new(cmdName = "undefined")`

>注意：本函数尚未完成，仍在制作之中（或许会出现在以后的版本）

新建一个模块对象，并返回这个对象

`nil ssc.block.setPos(SSCBlock obj, number X = nil, number Y = nil)`

>注意：本函数尚未完成，仍在制作之中（或许会出现在以后的版本）

设置模块 obj 的位置，以代码编辑页面左上角为原点，如某坐标参数为 `nil` 则不对其轴坐标更改

`number,number ssc.block.setPos(SSCBlock obj)`

>注意：本函数尚未完成，仍在制作之中（或许会出现在以后的版本）

获取模块 obj 的坐标，返回 X 坐标和 Y 坐标

`SSCBlock/string/number/nil ssc.block.setArg(SSCBlock obj, number argPos, SSCBlock/string/number argBlock = nil)`

>注意：本函数尚未完成，仍在制作之中（或许会出现在以后的版本）

设置模块 obj 中指定位置的变量槽中的子模块 argBlock，你可以设置 Lua 常量到其中，如果原先已有模块或常量值则返回这个旧值，而模块则会被重新放置到离原模块最近的地方

`nil ssc.block.setFunction(SSCBlock obj, function fun)`

>注意：本函数尚未完成，仍在制作之中（或许会出现在以后的版本）

设置模块 obj 的执行函数，你可以使用 Lua 来制作你的自定义模块，这样会导致原模块功能丧失且无法恢复，如果是 undefined 就当我没说

`boolean ssc.block.setSpec(SSCBlock obj, string spec)`

>注意：本函数尚未完成，仍在制作之中（或许会出现在以后的版本）

设置模块 obj 的规范名称，转换字符将被转换成变量槽方便操作，同时模块的所有子模块将被销毁，具体请参考 Scratch 2.0 规范名称格式，仅可以设置在已经定义了自定义执行函数的模块中，成功返回 `true` ，否则返回 `false`

---
## SSCThread 类

SSCThread 是 SteveScratchC 的模块解释器的重要组成部分，它用于存储一条程序线程的当前状态，并在执行程序循环的时候执行模块和逻辑操作，你可以通过 `ssc.thread.functionName(...)` 来操作 SSCThread 类。

---

`SSCThread ssc.thread.new(SSCBlock block)`

>注意：本函数尚未完成，仍在制作之中（或许会出现在以后的版本）

创建一个线程，并指定第一个模块，且加入到程序循环中。
