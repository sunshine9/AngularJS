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

##### AngularJS控制器
```javascript
var app = angular.moudle('myApp',[]);
app.controller('personCtrl',function($scope){
    $scope.firstName = "John";
    $scope.lastName = "Doe";
    $scope.fullName = function(){
        return $scope.firstName + " " +$scope.lastName; 
    }
})
// 可在外部引用
```

##### AngularJS 过滤器
```javascript
    // curreny 格式化数字为货币格式
    // filter 从数组项中选择一个子集
    // lowercase 格式化字符串为小写
    // orderBy 根据某个表达式排列数组
    // uppercase 格式化字符串为大写
```
currency 过滤器
```html
    <div ng-app="myApp" ng-controller="costCtrl">
        <input type="number" ng-model="quantity" />
        <input type="number" ng-model="price" />
        <p>总价 = {{ (quantity*price) | currency }}</p>
    </div>

    <script>
        var app = angular.module('myApp', []);
        app.controller('costCtrl', function ($scope) {
            $scope.quantity = 1;
            $scope.price = 9.99;
        });
    </script>
```
向指令添加过滤器
```html
    <div ng-app="myApp" ng-controller="namesCtrl">
        <p>循环对象</p>
        <ul>
            <li ng-repeat="x in names | orderBy:'city'">
                {{ x.name +", " + x.city }}
            </li>
        </ul>
    </div>
    <script>
        var app = angular.module('myApp', []);
        app.controller('namesCtrl', function ($scope) {
            $scope.names = [
            {
                name: "zhangsan",
                city: "ShangHai"
            },
            {
                name: "LiSi",
                city: "BeiJing"
            }
            ]
        });
    </script>
```
过滤输入
```html
<div ng-app="myApp" ng-controller="fliterCtrl">
        <input type="text" ng-model="test" />
        <ul>
            <li ng-repeat="x in names | filter:test | orderBy:'city'">
                {{ (x.name | uppercase) +", "+x.city }}
            </li>
        </ul>
    </div>
    <script>
        var app = angular.module('myApp', []);
        app.controller('fliterCtrl', function ($scope) {
            $scope.names = [{
                name: "Wang",
                city: "Chongqing"
            },
            {
                name: "Hong",
                city: "BeiJing"
            },
            {
                name: "Sun",
                city:"Guangzhou"
            }
            ]
        })
    </script>
```



































