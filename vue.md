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
事件三要素： 
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
## v-show v-if v-bind
```
v-show:控制页面中某个元素是否显示  底层控制为标签display属性
    可以直接通过Boolean值控制元素展示
    <h1 v-show="true">你好</h1>
    可以通过变量控制标签展示和隐藏
    <h1 v-show="isShow">你好</h1>
    data:{
        isShow:true
    }
    可以通过Boolean表达式控制标签展示和隐藏
    <h1 v-show="age >= 30">你好</h1>
    data:{
        age:23
    }
```
```
v-if : 用来控制页面元素是否展示 底层控制是DOM元素(DOM树节点添加和删除)

```
```
v-bind : 用来给页面中标签元素绑定相应的属性   (绑定后的属性值可以动态改变)
<!-- 完整语法 -->
<a v-bind:href="url">...</a>
<img v-bind:src="src">
<!-- 缩写 -->
<a :href="url">...</a>
data:{
    url:" ",
    src:" "
}
```
## v-for
```
v-for: 用来对对象进行遍历（数组也是对象的一种）
/*
v-for遍历对象
*/
<span>{{User.name}}</span>
<span v-for="u in User"> //u:别名 in:关键字  User:对象名
{{u}}  //输出：小白 23
</span>
<span v-for="(key,value,index) in User">
{{index}}:{{key}}:{{value}} //输出：0：name: 小白 ：age: 23
</span>
data:{
    User:{
        name:"小白",
        age:23
    }
}
```
```
/*
v-for遍历数组
*/
<ul>
    <li v-for="a,index in arr">
        {{index}}:{{a}}
        //输出：0：北京校区
                1：天津校区
                2：广东校区
    </li>
</ul>
data:{
    arr:["北京校区","天津校区","广东校区"]
}
```
```
/*
v-for遍历数组中的对象
:key 便于vue内部做重用和排序
*/
<ul>
    <li v-for="user in users" :key="user.id">
        {{user.name}}:{{user.age}}
        //输出：小白：23
                小黑：23
    </li>
</ul>
<ul>
    <li v-for="user,index in users" :key="user.id">
        {{user.name}}:{{user.age}}
        //输出： 0 小白：23
                1 小黑：23
    </li>
</ul>
data:{
    users：[
        {id:"1",name:"小白",age:23},
        {id:"2",name:"小黑",age:23},
    ]
}
```
## v-model双向绑定
```
v-model:用来绑定标签元素的值与vue实例对象中data的数据保持一致，从而实现双向的数据绑定机制
<input type="text" v-model="message"></input>
<span>{{message}}</span>
<input type="button" @click="changeMSG"></input>
data:{
    message:""
}
methods:{
    changeMSG(){
        this.message = "你好呀~"
    }
}
/*
输入框中发生改变时，vue实例中data发生改变，span显示内容也会实时改变
点击button时，data发生改变，输入框内容和span内容也会随之改变
*/
```
```
MVVM架构 双向绑定机制
Model:数据  vue实例中的数据
VM：ViewModel  监听器
View：页面  页面展示的数据

```
## vue-router
```
第一种：在index中创建好router实例，直接在main.js中引入
main.js
..................................
import Vue from 'vue'
import App from './App.vue'
import Router from 'vue-router'
import router from './router/index.js'
Vue.config.productionTip = false

new Vue({
	router,//错误3：此处引入的实例名必须为router，否则会报错
  render: h => h(App),
}).$mount('#app')
....................................
index.js
....................................
import Vue from 'vue'
import Router from 'vue-router'
import HelloWorld from '../components/HelloWorld.vue'
Vue.use(Router)
const router = new Router({
	mode:"history",
	routes:[
		{
			path:'/',
			redirect:HelloWorld
		},
	{
		path:'/HelloWorld',
		name:'HelloWorld',
		component:HelloWorld
	}
	]
})
export default router   //错误1：export default {router}，页面不显示（export default用法出错：https://blog.csdn.net/hsany330/article/details/81001603）
......................................
```
```
第二种：将routes单独引入，在main.js中创建router实例
main.js
..................................
import Vue from 'vue'
import App from './App.vue'
import Router from 'vue-router'
import routes from './router/index.js'
Vue.config.productionTip = false

Vue.use(Router)
const router = new Router({
	mode:"history",
	routes:routes
})

new Vue({
	router,
  render: h => h(App),
}).$mount('#app')
....................................
index.js
....................................
import Vue from 'vue'
import Router from 'vue-router'
import HelloWorld from '../components/HelloWorld.vue'

const routes = [
		{
			path:'/',
			redirect:HelloWorld
		},
	{
		path:'/HelloWorld',
		name:'HelloWorld',
		component:HelloWorld
	}
	]
export default routes  
......................................
APP.vue
......................................
<template>
  <div id="app">
    <img alt="Vue logo" src="./assets/logo.png">
<router-link to="/HelloWorld">你好</router-link>
<router-view ></router-view> //错误2：不写<router-view>，页面不显示
  </div>
</template>

<script>
export default {
  name: 'app',
  components: {},
  created() {
  	console.log(this.$route);
	console.log(this.$router);
  }
}
</script>
...................................................
```