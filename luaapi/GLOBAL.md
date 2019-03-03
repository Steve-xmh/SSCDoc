# _G

[回到总目录](../index.md#目录)

[回到 API 目录](menu.md#api-目录)

## 简介

_G 为 Lua 语言中的全局变量表，其中所有的量可以通过输入 `_G.name` 获取，由于是全局变量，您也可以直接输入名称来获取内部的变量。

**警告：请不要随意删除 Lua 的原生函数库，否则极有可能会导致 SteveScratchC 的崩溃或者是脚本执行错误！**

下面一个简单的例子用于从全局变量中取出和设置值：

```lua
_G.newVar = "SteveScratchC"
print(_G.newVar) -- SteveScratchC
print(newVar) -- SteveScratchC

local newVar = "SteveScratch"
print(_G.newVar) -- SteveScratchC
print(newVar) -- SteveScratch
-- 注意上方的 newVar，Lua 会默认从当前代码块开始往上寻找变量的值，直至无法查询后查询 _G 中的键值。
```

## 变量

变量名|用途|出现版本
-|-|-
`_SSCVER`|SteveScratchC 版本号，如 `"1.0.0"`|暂无
`ssc`|[SteveScratchC 主函数库](ssc.md#ssc)|AFD v1+

## 函数

函数名|用途|出现版本
-|-|-
`wait([时长/秒])`|让出线程，并等待一定时间后继续执行，空则仅让出线程|AFD v1+

[![知识共享许可协议](https://i.creativecommons.org/l/by-nc-sa/3.0/cn/88x31.png)](http://creativecommons.org/licenses/by-nc-sa/3.0/cn/)
本作品采用[知识共享署名-非商业性使用-相同方式共享 3.0 中国大陆许可协议](http://creativecommons.org/licenses/by-nc-sa/3.0/cn/)进行许可。
