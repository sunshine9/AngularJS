## AngularJS 简介
##### AngularJS 扩展了HTML
```html
<div ng-app=""> // ng-app 指令定义了一个AngularJS应用程序
    <p>姓名：<input type="text" ng-model="name"></p> // ng-model 把元素值(如输入域的值)绑定到应用程序
    <p ng-bind="name"></p> // ng-bind 把应用程序数据绑定到HTML视图
</div>

<script src="http://apps.bdimg.com/libs/angular.js/1.3.9/angular.min.js"></script>
```
##### AngularJS表达式
```html
<p>我的第一个表达式：{{ 5 + 5 }}</p>
// AngularJS表达式写在双大括号内，可以包含文字、运算符和变量
// 数字、对象、数组、字符串
```

##### AngularJS应用
```html
<div ng-app="myApp" ng-controller="myCtrl">
名：<input type="text" ng-model="firstName"><br>
姓：<input type="text" ng-model="lastName"><br>
姓名：{{firstName + " " + lastName}}
</div>
<script>
var app = angular..moudle('myApp', []);
app.controller('myCtrl',function($scope){
    $scope.firstName = "John";
    $scopr.lastName = "Doe";
})
</script>

// ng-app 定义了应用，ng-controller 定义了控制器

```

##### AngularJs指令
```html
// ng-app 初始化一个AngularJS应用程序
// ng-init 初始化应用程序数据
// ng-model 把元素值(如输入域的值)绑定到应用程序
// ng-bind 绑定数据
// {{}}数据绑定
// ng-reapeat 重复HTML元素
<div ng-app="" ng-init="names=['Jani','Hege','Kai']">
    <p>使用 ng -repeat 来循环数组</p>
    <ul>
        <li ng-repeat="x in names">
        {{ x }}
    </ul>
</div>
```


































