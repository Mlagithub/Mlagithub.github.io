

![MD_LOGO][MDLogo]
<br/>

# **MarkDown** 语法及技巧总结

本文主要总结了 **MarkDown** 的基本语法及使用技巧。

1. 各种语法可以嵌套使用
2. MarkDown 完全兼容 **HTML** 语法，可以直接在 MarkDown 文档中插入 HTML 内容。

> 
目录：
+ 标题 
+ 字体及颜色
   + 加粗
   + 删除线
   + 斜体
   + 字体
   + 颜色
+ 注释
+ 引用
+ 图片
   + MarkDown 语法
   + HTML 调整图片大小及位置
+ 超链接
+ 列表
   + 无序列表
   + 有序列表
+ 表格
+ 代码
   + 单行
   + 多行
+ 流程图
+ 其它
   + 换行
   + 分割线
   + 流程图
+ 参考

<br/>

# 标题

```md
N 级标题：左边加 N 个 #
说明：# 后面要加空格
```
## 二级标题：##
#### 四级标题：####
##### 五级标题：#####

<br/>

# 字体及颜色

## MarkDown 标准 
> **加粗**： 左边加 2 个 \* 

> *斜体*：左右各加 1 个 \* 

>***斜体加粗***： 左右各加 3 个 \* 

>~~删除线~~： 左右各加 2 个 ~~

## HTML 字体设置
```html
<font face="" color=xxx size=[1,2,3,5,6,7]>
your content goes here
</font>
```
```html
<font face="黑体">我是黑体字</font>  
<font face="微软雅黑">我是微软雅黑</font>  
<font face="STCAIYUN">我是华文彩云</font>  
<font color=red>我是红色</font>  
<font color=#008000>我是绿色</font>  
<font color=Blue>我是蓝色</font>  
<font size=5>我是尺寸</font>  
<font face="黑体" color=green size=5>我是黑体，绿色，尺寸为5</font> 
```
<font face="黑体">我是黑体字</font>  
<font face="微软雅黑">我是微软雅黑</font>  
<font face="STCAIYUN">我是华文彩云</font>  
<font color=red>我是红色</font>  
<font color=#008000>我是绿色</font>  
<font color=Blue>我是蓝色</font>  
<font size=5>我是尺寸</font>  
<font face="黑体" color=green size=5>我是黑体，绿色，尺寸为5</font>  


<br/>

# 注释

MarkDown 中的注释有多种实现方法。HTML 支持**多行**、**行中**注释。
MarkDown 仅支持多行，不支持行中，且 ` <> ` 及 `#` 与 `()` 之间至少空要一格。

> HTML 语法：
```html
<!-- your comment goes here
and here -->
```

>MarkDown 语法：
```md
[comment]: <> (your comment goes here
and here)

[comment]: # (your comment goes here
and here)

[//]: <> (your comment goes here
and here)

[//]: # (your comment goes here
and here)
```

<br/>

# 引用
> 这句话现在被引用了, 句子开头使用了：` > `
> > 这是一个嵌套引用，句子开头使用了：`` >> ``
> > > 这是一个嵌套嵌套引用，句子开头使用了：`` >>> ``

>多个 `>` 之间可以有空格  
>引用环境中，每行开头的空格不被显示，缩进需要嵌套引用实现

<br/>

# 图片


## MarkDown 语法添加图片
> 网格图片： `![picture-desc](http://xxx.jpg, "optional title")`  
> 本地图片： `![picture-desc](./figure/a.bmp, "optional title")`  
> base64编码的图片： `![desc](data:image/png,base64,xxx, "optional title")` 其中 `xxx` 为图片的编码值。  
> 
如 `![alvtar](./figures/markdown-ref-1.png)` 显示为：

![alvtar](./figures/markdown-ref-1.png)

## HTML 语法添加图片
```html
<img src="url" width="" height="" title="" alt="">
```
显示原始图片
> `<img src="./figures/markdown-ref-1.png">` ：  
<img src="./figures/markdown-ref-1.png">

调整图片的大小
> `<img src="./figures/markdown-ref-1.png" width="200" height="200">`  
<img src="./figures/markdown-ref-1.png" width="200" height="200">

调整图片的位置
```html
<div align="center">
   <img src="./figures/markdown-ref-1.png" width="200" height="200">
</div>
```
<div align="center">
   <img src="./figures/markdown-ref-1.png" width="200" height="200">
</div>

<br/>

# 超链接

## MarkDown 超链接语法

```md
[your content goes here](hyperlinks goes here)

说明：括号要使用英文字符
```
> [点我访问-ACT项目主页](http://202.197.20.234)  
> [点我访问-本地文件](./figures/c++20_compiler_support.png)  

## HTML 超链接语法
```html
<a href="hyperlinks goes here">
   your content goes here
</a>

说明：<a> 语法还有其它参数可以使用，但并不一定适用于所有解释器。
```
<a href="http://202.197.20.234">
   点我访问-ACT项目主页
</a><br/>

<a href="http://202.197.20.234">
   点我访问-本地文件
</a>

<br/>

# 列表

## 无序列表
```md
[-,+,*] 列表内容
```
> 说明：  
> > 可以混合使用 `-,+,*`  
> > 上下级之间缩进两个及以上空格

+ 使用 `+`  
  - 使用 `-`
- 使用 `-`
  * 使用 `*`
    - 使用 `-`

## 有序列表
```md
[数字.] 列表内容
```
> 每一级别的数字自动编号
1. 数字是 1  
2. 数字是 2 


> 可以自定义第一项的编号值，其它项的值由系统根据第一项的值计算得出
6. 数字是 6  
3. 数字是 3
2. 数字是 2
9. 数字是 9


> 列表间有空行不影响继续编号  
> 故多个列表间不能只有空行，要有其它元素

1. 现在编号值是 1   
2. 现在编号值是 2，从这里空两行，再继续


3. 现在编号值是 1
4. 现在编号值是 2  

> 只能使用 `一个整数.` 这样的形式，  
> 其它形式不是列表，如下所示  

1.1. abc  
1.2. abc  
<br/>

# 表格
```md
表头|表头|表头
---|:--:|---:
内容|内容|内容
内容|内容|内容
```
表头|表头|表头
---|:--:|---:
内容|内容|内容
内容|内容|内容


> 第二行分割表头和内容  
> `-` 有一个就行，为了对齐，多加了几个  
> 文字默认居左  
> `-` 两边加 `:` 表示文字居中  
> `-` 右边加 `:` 表示文字居右  
> 注：原生的语法两边都要用 | 包起来。此处省略  

<br/>

# 代码 

## 单行代码
``` ` ```  代码内容  ``` ` ```  
> 代码内容用一个反引号包起来

## 多行代码 
``` ` ``` ``` ` ``` ``` ` ```xxx  
代码内容  
``` ` ``` ``` ` ``` ``` ` ```
> 代码内容用三个反引号包起来  
> 三个反引号单独占一行  
> xxx 为代码的语言类型，用来进行语法高亮  
> 各解释器支持的代码高亮风格及种类不相同

<br/>

# 其它
1. 换行的两种方法
   > 两个空格加回车换行符键  
   > 使用 html 换行标记 `<br/>` 或者 `<br>`<br/>
2. 分割线
   > 使用三个或三个以上的 `*` 或者 `-` 单独占一行来添加一条分割线，将内容分块。  

   > `***` 显示为：
   ***
   > `---` 显示为：
   ---
3. 流程图
> 各解释器支持情况不同，有的不支持
```flow
st=>start: 开始
op=>operation: My Operation
cond=>condition: Yes or No?
e=>end
st->op->cond
cond(yes)->e
cond(no)->op
&
```

<br/>



[MDLogo]:data:image/jpg;base64,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
