## HTML 空元素
```
没有内容的 HTML 元素被称为空元素。
空元素是在开始标签中关闭的。
*** <br> 就是没有关闭标签的空元素（<br> 标签定义换行）。
```
## HTML 属性
```
常用属性：class,id,style,title
属性一般描述于开始标签
属性总是以名称/值对的形式出现，比如：name="value"。
class 属性可以多用 class=" " （引号里面可以填入多个class属性）
id 属性只能单独设置 id=" "（只能填写一个，多个无效）
```
## HTML 水平线
```
*** <hr> 标签在 HTML 页面中创建水平线。
hr 元素可用于分隔内容。在内容之间添加水平线
```
## HTML 文本格式化标签
```
<b>	定义粗体文本
<em>	定义着重文字
<i>	定义斜体字
<small>	定义小号字
<strong>	定义加重语气
<sub>	定义下标字
<sup>	定义上标字
<ins>	定义插入字
<del>	定义删除字
```
## HTML "计算机输出" 标签
```
<code>	定义计算机代码
<kbd>	定义键盘码
<samp>	定义计算机代码样本
<var>	定义变量
<pre>	定义预格式文本
```
## HTML 引文, 引用, 及标签定义
```
<abbr>	定义缩写
<address>	定义地址
<bdo>	定义文字方向
<blockquote>	定义长的引用
<q>	定义短的引用语
<cite>	定义引用、引证
<dfn>	定义一个定义项目。
```
## HTML 链接 - target 属性
```
使用 target 属性，你可以定义被链接的文档在何处显示。
_blank	在新窗口中打开被链接文档。
_self	默认。在相同的框架中打开被链接文档。
_parent	在父框架集中打开被链接文档。
_top	在整个窗口中打开被链接文档。
framename	在指定的框架中打开被链接文档。
```
## HTML<title>元素不仅可以显示文本，也可以在左侧显示logo等图片。
```
显示时，要将<link>标签放入<head>里。
举例：

<!doctype HTML>
<html>
<head>
<link rel="shortcut icon" href="图片url">
<title>这是一个带图片的标签</title>
</head>
<body>
……
</body>
</html>
```
## 如何使用 style 属性制作一个没有下划线的链接。
```
<a href="//www.runoob.com/" style="text-decoration:none;">访问 runoob.com!</a>
```
## HTML 样式实例 - 字体, 字体颜色 ，字体大小
```
我们可以使用font-family（字体），color（颜色），和font-size（字体大小）属性来定义字体的样式:
```
## HTML 表格
```
表格由 <table> 标签来定义。每个表格均有若干行（由 <tr> 标签定义），每行被分割为若干单元格（由 <td> 标签定义）。字母 td 指表格数据（table data），即数据单元格的内容。数据单元格可以包含文本、图片、列表、段落、表单、水平线、表格等等。

HTML 表格标签
<table>	定义表格
<th>	定义表格的表头
<tr>	定义表格的行
<td>	定义表格单元
<caption>	定义表格标题
<colgroup>	定义表格列的组
<col>	定义用于表格列的属性
<thead>	定义表格的页眉
<tbody>	定义表格的主体
<tfoot>	定义表格的页脚
举例：
<table border="1">
    <tr>    //tr定义行
        <th>Header 1</th>   //th定义表头，第一行第一列定义字段1
        <th>Header 2</th>   //第二行第一列定义字段2
    </tr>
    <tr>
        <td>row 1, cell 1</td> //td定义每行数据
        <td>row 1, cell 2</td>
    </tr>
    <tr>
        <td>row 2, cell 1</td>
        <td>row 2, cell 2</td>
    </tr>
</table>
```
## HTML 列表标签
```
<ol>	定义有序列表
<ul>	定义无序列表
<li>	定义列表项
<dl>	定义列表
<dt>	自定义列表项目
<dd>	定义自定列表项的描述
```
## HTML 表单标签
```
New : HTML5新标签
标签	描述
<form>	定义供用户输入的表单
<input>	定义输入域
<textarea>	定义文本域 (一个多行的输入控件)
<label>	定义了 <input> 元素的标签，一般为输入标题
<fieldset>	定义了一组相关的表单元素，并使用外框包含起来
<legend>	定义了 <fieldset> 元素的标题
<select>	定义了下拉选项列表
<optgroup>	定义选项组
<option>	定义下拉列表中的选项
<button>	定义一个点击按钮
<datalist>New	指定一个预先定义的输入控件选项列表
<keygen>New	定义了表单的密钥对生成器字段
<output>New	定义一个计算结果
```
## HTML字符实体
```
Note: 实体名称对大小写敏感！
	描述	实体名称	实体编号
 	空格	&nbsp;	&#160;
<	小于号	&lt;	&#60;
>	大于号	&gt;	&#62;
&	和号	&amp;	&#38;
"	引号	&quot;	&#34;
'	撇号 	&apos; (IE不支持)	&#39;
￠	分	&cent;	&#162;
£	镑	&pound;	&#163;
¥	人民币/日元	&yen;	&#165;
€	欧元	&euro;	&#8364;
§	小节	&sect;	&#167;
©	版权	&copy;	&#169;
®	注册商标	&reg;	&#174;
™	商标	&trade;	&#8482;
×	乘号	&times;	&#215;
÷	除号	&divide;	&#247;
```