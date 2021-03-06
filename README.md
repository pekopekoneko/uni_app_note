# notebook for uniapp

## class 1

pages 是用来存放页面的文件夹

utils 放的是一些工具类

app.js 是项目入口

app.json 是项目配置

app.wxss 是全局的样式表



### app.js

onLaunch 是小程序完成初始化的时候会触发onlaunch

onShow 是小程序启动或者从后台进入前台会触发onshow

onHide 是小程序从前台进入后台触发的


### app.json

配置文件，每一个页面都需要在pages变量里注册

### 页面

index 是一个代称

index.js 是页面的业务逻辑

index.json 是页面的配置

index.wxml 是页面的模板

index.wxss 是页面的样式


### index.js

必须通过page来指定初始化的数据

也拥有app.js一样的一些基础的生命周期函数

onUnload 是页面卸载的函数

onReady 是页面初次渲染完成

onPullDownRefresh 是用户下拉动作的函数

onReachBottom 是用户上拉触底事件

onShareAppMessage 是用户分享的函数

### 数据绑定

在 index.js中page中的data可以绑定数据
显示就是{{variable_name}}

使用this.setData(Object)

Object格式就类似于{name:"李四"}

### 条件判断

wx:if="{{is_ok}}"

### 列表渲染

比如有 ages:[12,13,14,15]

wx:for="{{ages}}" {{item}}

item 是当前变量的项目的默认值

index 是当前下标的默认值 会根据指针位置输出 0,1,2,3这种位置数据

以下两句也可以成功的输出age的全部元素

wx:for-item="age" {{age}}

wx:for-index="ids" {{ids}}

## class 2

### uni-app 规范

页面遵循vue单文件组件规范

<template>
  <view>
    ....
  </view>
</template>

<script>
  ....
</script>

<style>
  ....
</style>

组件标签靠近小程序规范

更多地使用view image text标签

接口能力靠近微信小程序规范

数据绑定同vue规范

建议使用flex布局进行开发

### uni-app特色

条件编译

app端的nvue开发

其内置了wix引擎，可以使用wix和uni-app的组件

html 5+

### uni-app知识点

自定义组件、基础组件

uni-app API

路由

生命周期

语法（布局样式）

## class 3

### 开发环境

HbuilderX

他对于uni-app有较好的支持度

其他的开发软件可能会有不支持的插件

vue-cli的方式运行项目

### 创建模板

给定的 vue create -p dcloudio/uni-preset-vue test-uniapp

连接不上，故从github上直接下载了下来

可以通过如下的命令展开配置

vue create -p D:\Desktop\uni-preset-vue test

(我将这个文件放在如上位置了)

但不如用hbuilderx直接创建

上述的东西在npm编译过程中会出问题

## class 4

### 模板语法

不建议使用 data:{},因为它会保留上次的值，不会被初始化

所以把data作为一个函数return，每次都会新生成数据

### 数据绑定

v-bind:class="classname"

动态修改类，v-bind可以删掉，只留下:

v-on:click="open"

open放在method里面（附属的函数）

接受点击事件,v-on可以使用@替代

### 动态数据绑定

uni中this可以指带本组件

### 条件判断

v-if="true"就渲染

{{show?'uni-app':'vue}}这句话的意思是show如果是true，就会显示uni-app，否则显示vue

### 列表渲染

v-for="item in arr"就是arr中的每个item

index是下标别名

v-for="(item,index) in arr"   {{(index+1)+' '+ item}} 可以输出序号和数组中的东西

### 基础组件

view相当于div

text相当于span

这些东西建议去dcloud官网去看

<"button" type="default" @click="input>点击</button>

<input type="text" value="value"/>

### 自定义组件

import btn from '@/components/btn/btn.vue'引入组件

同时在export default中也要把btn放入components中

props接收标签属性，要定义type和default值

this.$emit是自定义的事件


### 基础api

官方文档有不同的解释

### 条件编译

<!-- #ifdef APP-PLUS||H5 -->

xxxxx

<!-- #endif -->

这种情况下只会在app端编译出中间的组件，其反义为ifndef

### 页面布局

style中使用page可以定义全局(取代了body)

rpx是自适应的宽度

可以在style中通过@import './index.css'的形式引入样式表
  
要注意flex的应用

### 生命周期

app.vue中定义了应用的生命周期

onlaunch初始化时仅触发一次

onshow应用启动或者后台返回时触发

onhide切入后台触发的

#### 对于页面的生命周期

onready监听页面初次渲染完成

onload监听页面加载

#### 组件也有生命周期
