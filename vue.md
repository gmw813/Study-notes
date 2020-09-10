## 选择器
```
* id选择器
el:'#app'
* 类选择器
el:'.app'
```
## 数据绑定 v-text和v-html
```
v-text：获取data中数据并以文本形式渲染到指定标签内部 类似js中innerText
{{}}插值方式和v-text区别:
插值方式不会覆盖标签原有内容，v-text会覆盖标签原有内容
   //message:Hello,World
   <span>{{message}}!!!</span>  //输出：Hello,World!!!
   <span v-text="message">!!!</span>  //输出：Hello,World
   <span v-text="message"+"!!!"></span>  //输出：Hello,World!!!
插值方式在网络环境较差时会出现闪烁，v-text可以避免闪烁
```
```
v-html：获取data中数据将数据中含有的html标签先解析再渲染到指定标签内部 类似js中innerHtml
    //message:<a herf="">Hello,World</a>
   <span v-text="message"></span>  //输出:<a herf="">Hello,World</a>
   <span v-html="message"></span>  //输出：Hello,World(带下划线的链接样式)
```
## 绑定事件v-on
```
语法：v-on:事件名="函数名"  或  @事件名="函数名"
 <input type="button" value="点击事件" v-on:click="change">
  <input type="button" value="点击事件" @click="change">
```
```
事件： 
事件源  发生事件DOM元素； 
事件 发生特定的动作； 
监听器  发生特定动作之后的事件处理程序  通常为js中函数；
```
```
事件参数传递：
···
<input type="button" value="点击事件" @click="changeTo(23,'小白')">
···
changeTo(age,name){
  alert(age);
  alert(name);
}
···
```