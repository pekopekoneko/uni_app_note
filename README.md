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
