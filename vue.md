## 选择器
```
* id选择器
el:'#app'
* 类选择器
el:'.app'
```
## 数据绑定
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