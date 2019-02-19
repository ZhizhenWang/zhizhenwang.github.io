---
layout: post
title: Markdown的语法规则
date: 2019-02-12 23:28:55 +0100
tags: markdown cheatsheet

categories: 技术
---
## 目录
{:.no_toc}
* TOC
{:toc}

这里我们将介绍一下Markdown 的语法规则以及一些栗子(例子)
## 标题
我们用`# title`来表示标题，井号越多，标题越小
```markdown
# 一级标题
## 二级标题
### 三级标题
```
## 段落及换行
为了创建段落，用一个空行来分割一行或多行文字
<table>
    <tr>
      <th>Markdown</th>
      <th>HTML</th>
      <th>Rendered Output</th>
    </tr>
  <tbody>
    <tr>
      <td>
        <code class="language-markdown highlighter-rouge">
          I really like using Markdown.<br><br>

          I think I'll use it to format all of my documents from now on.
        </code>
      </td>
      <td>
        <code><span class="nt">&lt;p&gt;</span>I really like using Markdown.<span class="nt">&lt;/p&gt;</span>
        <br><br>
        <span class="nt">&lt;p&gt;</span>I think I’ll use it to format all of my documents from now on.<span class="nt">&lt;/p&gt;</span>
        </code>
      </td>
      <td>
        <p>I really like using Markdown.</p>

        <p>I think I'll use it to format all of my documents from now on.</p>
      </td>
    </tr>
  </tbody>
</table>

为了创建换行`<br>`，我们在行末附上两个或以上的空格，并加上回车
<table class="table table-bordered">
  <thead class="thead-light">
    <tr>
      <th>Markdown</th>
      <th>HTML</th>
      <th>Rendered Output</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td>
        <code class="highlighter-rouge">
          First line. &nbsp;<br>
          This is the second line.
        </code>
      </td>
      <td>
        <code class="highlighter-rouge">&lt;p&gt;First line.&lt;br&gt;<br>

        This is the second line.&lt;/p&gt;</code>
      </td>
      <td>
        <p>First line.<br>   
        This is the second line.</p>
      </td>
    </tr>
  </tbody>
</table>

## 强调文本
对文本表示强调，可以使用加粗、斜体或者两者都用
### 加粗
用两个星号*或下划线_来包围文本  
如：表示**bold**，可用
```
**bold**
__bold__
```
### 斜体
用一个星号\*或下划线_来包围文本  
如：表示*italic*，可用
```
*italic*
_italic_
```
### 加粗斜体
为了同时用加粗和斜体强调文本，可以用三个星号\*或下划线_来包围文本  
如：表示***very important***，可用
```
***very important***
___very important___
```
## 引用
用`> quote`来表示引用，可以嵌套`>`来表示多层引用
> This quote will change your life.
>> It will reveal the secrets of the universe, and all the wonders of humanity. Don't misuse it.

## 列表
### 有序列表
你可以用任意的数字加点来表示有序列表，数字不一定要求有序，例如：
```markdown
5. First item
8. Second item
3. Third item
5. Fourth item
```
### 无序列表
无序列表可在项目前面加 横线-，星号*或加号+，例如：
```markdown
- First item
- Second item
- Third item
```
## 代码块
来创建代码块，可以用四个空格或者一个Tab来缩进行。另一种方法是用<code>```</code>或者`~~~`来包围代码块，这样就不必缩进行。

用一下代码：
{% highlight markdown %}
```html
<html>
  <head>
  </head>
  <body>
    <p>Hello, World!</p>
  </body>
</html>
```
{% endhighlight %}
来实现
```html
<html>
  <head>
  </head>
  <body>
    <p>Hello, World!</p>
  </body>
</html>
```

## 链接
用 `[an example](http://example.com/)` 来表示内嵌链接 [an example](http://example.com/)
### 添加标题
标题会在鼠标悬浮于链接时显示，如用`[an example](http://example.com/ "Title")`来表示包含标题的链接 [an example](http://example.com/ "Title") 
### 快速转换链接
将URL或者电子邮箱快速的转换成超文本链接，将它们用尖角号包围  
```
<http://www.example.com>  
<mustermann@gmx.com>
```
<http://www.example.com>  
<mustermann@gmx.com>
### 参考样式链接
参考样式链接用两组中括号来表示，括号直接可以有空格。第二中括号内为链接的标签，可包好字母、数字、空格、标点，不区分大小写。
以下三种都能表达同一种参考样式链接

This is [an example][id] reference-style link.
{: .red}

```
This is [an example][id] reference-style link.
This is [an example] [id] reference-style link.
This is [an example][Id] reference-style link.
```
[ID]: http://example.com/  "Optional Title Here"
在文章的任意地方，还必须定义链接标签，标题可用单引号、双引号、括号来包含。
```
[ID]: http://example.com/  "Optional Title Here"
```
参考样式链接的好处为相比与在括号内填写URL，可将链接URL在文章集中某处填写，从而增加源码的连续性和可读性。
{: .green} 
### 隐式链接名
隐式链接名的简写可以让你省略标签，用链接文本代替。
用 `[id][]` 来表示[id][]，即上述定义的标签为ID的链接。

 
## 图片
要添加图片，用`![alt text](URL)`表示   
例如：插入以下图片可以用`![favicon](/assets/favicon/android-chrome-192x192.png)`  
![favicon](/assets/favicon/android-chrome-192x192.png)



## 表格
为了添加表格，可以用三个及以上的短横线`---`来创建表格列标题，用竖线`|`来分割列。
```markdown
|Title 1               | Title 2               |
|--------------------- | --------------------- |
|lorem                 | lorem ipsum           |
|lorem ipsum dolor sit | lorem ipsum dolor sit |
```
当可以用[Markdown 表格生成器](http://www.tablesgenerator.com/markdown_tables)来自动生成表格。

要对齐整列，可以在短横线前后加入冒号来表示，如左对齐`:---`、居中`:---:`、右对齐`---:`

## 杂项
### 转义符
用`\`搭配字符可以输出字符本身

### 删除线
用经过文本中央的水平线表示删除先，像这样~~not needed~~，用两个波浪线`~~`包围文本。

### 水平线
用三个星号`***`、短横线`---`、下划线`___`来创建水平线

### 任务清单
```markdown
- [x] Write the press release
- [ ] Update the website
- [ ] Contact the media
```
- [x] Write the press release
- [ ] Update the website
- [ ] Contact the media

### 脚注
脚注可以用来标注参考文献，用尖角号和标识符`[^1]`来创建脚注引用，标识符可以是数字或字母，不能包含空格和Tab。  
标识符仅仅用来关联 脚注和脚注引用，输出结果时，脚注是以数字递增标号的。  
Here's a simple footnote,[^1] and here's a longer one.[^bignote]

[^1]: This is the first footnote.
[^bignote]: Here's one with multiple paragraphs and code.

    Indent paragraphs to include them in the footnote.
    
    `{ my code }`

    Add as many paragraphs as you like.


### kramdown独有特性
Kramdown是免费的MIT-licensed Ruby库，用来解析和转换Markdown的超集，在Jekyll中支持，可以用于GitHub搭建博客
#### 块属性
可以在段落结尾处加入  
`{: title="title"}` 表示块标题  
`{: .class}` 表示块类型  
`{: #with-an-id}` 表示块标签  
并结合css层叠样式表来赋予各自的样式

#### 自动生成目录
在`_config.yml`中设置
```
markdown: kramdown
```
然后步骤如下：
1. 在你需要的地方写一个有序或无须列表
2. 在列表下面接着写`{:toc}`
3. Jekyll 会替换列表内容为目录标题
就像下面这样：

```markdown
* TOC
{:toc}
```
如果有不需要包含进目录的标题，在标题下加入`{:.no_toc}`
<br><br><br><br><br>