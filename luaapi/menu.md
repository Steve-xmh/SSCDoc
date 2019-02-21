# SteveScratchC Lua API

[目录](../index.md#目录)

```lua
print("Hello SteveScratchC!")
wait(1)
print("And hello Lua!")
```

为了方便外置模块开发者制作属于自己的模块，或者是自己的插件， SteveScratchC 嵌入了 Lua 5.3 来辅助 SteveScratchC 的执行，减轻模块开发负担。

## 为什么选择 Lua ？

最主要的是这个是原作者唯一接触过的脚本语言，嵌入简单，都是 C 语言。对于这个脚本语言，语法简单，轻便小巧，速度快，所以采用了它。

## 为什么不使用 LuaJIT ？

LuaJIT 从 2.1.0 Beta3 开始就弃坑到了现在，其语法停留在 Lua 5.1 。虽然 LuaJIT 的运行速度非常迅速，但是在 SteveScratchC 中只用作辅助开发，不用做主要语言，且有部分语法和库与官方版本不符，为了保证代码稳定性和功能性，所以选择了官方版本。
说句题外话，最近我在 Github 发现了一个配套了 JIT 功能的 Lua 5.3 二次开发 [Ravi](https://github.com/dibyendumajumdar/ravi) ，虽然提供了 JIT 功能但是却还有部分缺陷，这里就不再叙述了。

## API 目录

以下为在 Lua 语言中可用的 API ，其中以 `_G` 为首的表按树表的形式列出，如需方便可以使用 `Ctrl + F` 使用浏览器查询功能查询函数。
为了更加好的发挥 Lua 的对象化特性，许多 C 结构在 Lua 中以 `userdata` 的形式出现，通过 `metatable` 来实现对象操纵，为了识别这些特殊对象，您需要使用 `typeof(对象)` 来查询对象类型名称。

- [`_G` 全局函数](_G.md#_G)
    - **变量**
        - `_SSCVER` SteveScratchC 版本号
        - [`ssc` SteveScratchC 主函数库]()
            - **函数**
                - `msgBox()` 显示信息框
    - **函数**
        - `wait(sec)` 等待/让出线程
        


