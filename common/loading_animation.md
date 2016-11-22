# Loading 动画

### 场景

我们**需要**在所有需要_用户等待_、或者_异步处理_的过程中，增加Loading 动画效果。

![](/assets/2016-11-19_17-33-46.jpg)

需要用到的场景包括：

1. 异步（Ajax）表单提交（如登录、删除记录等）
2. 页面初始化
3. 数据加载（如列表的AJAX翻页）

### 类型

从类型来讲，可以分为全页面的Loading效果覆盖，如下图：

以及，区域性Loading 效果覆盖，如下图：

以及下图：

从场景来看，

**全页面loading效果适合让用户停止一切行为，专心等待的情况，比如页面初始化、客服聊天突然断网等情况。**

**区域性loading给用户的心理暗示为，请等待区域部分的程序处理，同时，您可以干点别的。**

### 实现

可以轻量级、低侵入得实现全屏loading和局部loading方式。

在团队目前的技术储备中，PC端Loading动画最佳的实现方式是Whirl CSS + Angular 1\/2

[Whirl CSS](http://jh3y.github.io/whirl/)是纯CSS3实现Loading动画效果，轻量并且可灵活定制。

只需一行代码，即可实现效果。

```
<div class="whirl duo">
```

实际使用中，配合Angular的ng-class，HTML代码：

```
<div ng-class="{'whirl traditional':isPageLoading}">
```

JS代码：

```
$scope.isPageLoading = true;//显示动画
$http.get(function(){
    $scope.isPageLoading = false; //结束动画
})
```

期待有同学找到更佳的实现效果。

TODO: _移动端的实现总结_

### 其他

用好loading动画，还可以解决表单的重复提交问题。

