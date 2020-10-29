## 数据类型
```
JavaScript 中有八种基本的数据类型（译注：前七种为基本数据类型，也称为原始类型，而 object 为复杂数据类型）。

number 用于任何类型的数字：整数或浮点数，在 ±253 范围内的整数。
bigint 用于任意长度的整数。
string 用于字符串：一个字符串可以包含 0 个或多个字符，所以没有单独的单字符类型。
boolean 用于 true 和 false。
null 用于未知的值 —— 只有一个 null 值的独立类型。
undefined 用于未定义的值 —— 只有一个 undefined 值的独立类型。
symbol 用于唯一的标识符。
object 用于更复杂的数据结构。
```
```
反引号将包装在 ${...} 中的表达式嵌入到了字符串。
eg:
let name = "Ilya";
// 表达式为数字 1
alert( `hello ${1}` ); // hello 1
// 表达式是一个字符串 "name"
alert( `hello ${"name"}` ); // hello name
// 表达式是一个变量，嵌入进去了。
alert( `hello ${name}` ); // hello Ilya
```
## 弹窗
```
与用户交互的 3 个浏览器的特定函数：

alert
显示信息。
prompt
显示信息要求用户输入文本。点击确定返回文本，点击取消或按下 Esc 键返回 null。
confirm
显示信息等待用户点击确定或取消。点击确定返回 true，点击取消或按下 Esc 键返回 false。

这些方法都是模态的：它们暂停脚本的执行，并且不允许用户与该页面的其余部分进行交互，直到窗口被解除。
```
## 数据类型转换
```
对 undefined 进行数字型转换时，输出结果为 NaN，而非 0。
对 "0" 和只有空格的字符串（比如：" "）进行布尔型转换时，输出结果为 true。
```
## 数组方法
```
添加/删除元素：
push(...items) —— 向尾端添加元素，
pop() —— 从尾端提取一个元素，
shift() —— 从首端提取一个元素，
unshift(...items) —— 向首端添加元素，
splice(pos, deleteCount, ...items) —— 从 index 开始删除 deleteCount 个元素，并在当前位置插入 items。
slice(start, end) —— 创建一个新数组，将从位置 start 到位置 end（但不包括 end）的元素复制进去。
concat(...items) —— 返回一个新数组：复制当前数组的所有元素，并向其中添加 items。如果 items 中的任意一项是一个数组，那么就取其元素。

搜索元素：
indexOf/lastIndexOf(item, pos) —— 从位置 pos 开始搜索 item，搜索到则返回该项的索引，否则返回 -1。
includes(value) —— 如果数组有 value，则返回 true，否则返回 false。
find/filter(func) —— 通过 func 过滤元素，返回使 func 返回 true 的第一个值/所有值。
findIndex 和 find 类似，但返回索引而不是值。

遍历元素：
forEach(func) —— 对每个元素都调用 func，不返回任何内容。
转换数组：
map(func) —— 根据对每个元素调用 func 的结果创建一个新数组。
sort(func) —— 对数组进行原位（in-place）排序，然后返回它。
reverse() —— 原位（in-place）反转数组，然后返回它。
split/join —— 将字符串转换为数组并返回。
reduce(func, initial) —— 通过对每个元素调用 func 计算数组上的单个值，并在调用之间传递中间结果。

其他：
Array.isArray(arr) 检查 arr 是否是一个数组。
arr.some(fn)/arr.every(fn) 检查数组。
与 map 类似，对数组的每个元素调用函数 fn。如果任何/所有结果为 true，则返回 true，否则返回 false。
arr.fill(value, start, end) —— 从索引 start 到 end，用重复的 value 填充数组。
arr.copyWithin(target, start, end) —— 将从位置 start 到 end 的所有元素复制到 自身 的 target 位置（覆盖现有元素）。
```
## var let const 区别（变量提升问题）
```
https://www.cnblogs.com/jing-tian/p/11073168.html
具名函数有变量提升，函数表达式不能变量提升
    const divDom = $('demo');//不会报错,具名函数自动变量提升到最前面
    console.log(divDom);
    function $(id){
        return document.getElementById(id);
    }
    
    const tableDom = _$('demo')//会报错，函数表达式不会变量提升，必须先声明后使用
    const _$ = function (id){
        return document.getElementById(id);
    }
```
