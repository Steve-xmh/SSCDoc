# SSCStage

[回到总目录](../index.md#目录)

[回到 API 目录](menu.md#api-目录)

## 简介

`ssc.stage` 提供了对工程舞台和画板的操作函数。

**注意：本版块的内容尚未完成，也许是该板块的内容在软件中没有完成等原因。**

## 变量

变量名|用途|出现版本
-|-|-
暂无

## 函数

函数名|用途|出现版本
-|-|-
`ssc.stage.point(x,y[,r,g,b[,a]])`|在画板上绘制一个点|AFD v3
`ssc.stage.clear()`|清空画板为不透明色|AFD v3

### 详细

`ssc.stage.point(number x, number y[, number r, number g, number b[, number a]])`

在画板上绘制一个点，坐标以像素为单位，且原点位于舞台左上角，颜色值以 rgb 或 rgba 来提供，值限定在 0.0 - 1.0 之间

范例

```lua

ssc.stage.point(50,50,1,0,0) -- 在 x:50 y:50 的位置画一个红点
ssc.stage.point(50,51,0,0,0,0.5) -- 在 x:50 y:51 的位置画一个半透明的黑点

```

