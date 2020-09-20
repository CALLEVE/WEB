数据类型

‘abc’    "abc" 均可



布尔值

true   false



逻辑运算

```javascript
&& 两个都为真，结果为真

|| 一个为真

！  真即真，假即假
```



比较运算符

```javascript
=
==   等于（类型不一样，值一样，也会判断为true）
===  绝对等于（类型一样，值一样，结果为true）
```

JS的一个缺陷，这个于所有的数值都不相等，包括自己

只能通过isNaN（NaN）来判断这个数否是NaN



浮点数

```js
console.log((1/3)===(1-2/3));
```

尽量避免使用浮点数进行运算，存在精度问题

```javascript
console.log(Math.abs(1/3)===(1-2/3));
```



null和undefine

null 空

undefine 未定义的



数据

```javascript
var arr = [1,2,3,e,e,null,undefined];
```



对象

对象是大括号，数组是中括号

每个属性之间使用逗号隔开，最后一个不需要添加

```javascript
var person = {
	name:"wjp",
    age:3,
    tags:['js','java','web','...']
}
```



取对象的值

```javascript

```



## 3.数据类型

### 3.1 字符串

1.正常字符串我们使用 单引号，或者 双引号

2.注意转义字符

```javascript
\'
\n
\t
\u4e2d   \u#### unicode字符
\x41     ascii  字符
```



3.多行字符串编写

```javascript
//tab 上面 esc 下面
 var msg = `das
        dasda
        dada
        dada`

```



4.模板字符串

```javascript
//tab 上面 esc下面
  let name = "qingjiang";
let age = 3;
let msg = `你好呀，${name}`;
```



5.字符串长度

```javascript
str.length
```



6.字符串的可变性、不可变性

![image-20200916204606736](JavaScript.assets/image-20200916204606736.png)

7.大小写转换

```javascript
student.toUpperCase()
student.toLowerCase()
```



### 3.2 数组

Array可以包含任意的数据类型

```javascript
var arr = [1,2,3,4,5,6];
arr[0]
arr[0]=1
```

1.长度

```javascript
arr.length
```

注意：加入给arr.length赋值，数组大小就会发生变化，赋值过小，元素就会丢失



2.indexof，通过元素获取下标索引

```javascript
arr.indexOf(2)
1
```

字符串的“1”和数字 1 是不同的

3.slice（）  截取Array的一部分，返回一个新数组

4.push   pop   

![image-20200916211551311](JavaScript.assets/image-20200916211551311.png)

```javascript
push():压入到尾部
pop():弹出尾部的一个元素
```



5.unshift(),shift() 头部

```javascript
unshift：压入到头部
shift：弹出头部的一个元素
```



6.排序sort()

![image-20200916213008962](JavaScript.assets/image-20200916213008962.png)



7.元素反转

![image-20200916213250133](JavaScript.assets/image-20200916213250133.png)

```javascript
(3) ["A", "B", "C"]
arr.reverse()
(3) ["C", "B", "A"]
```





8.concat()

![image-20200916214101740](JavaScript.assets/image-20200916214101740.png)

注意：concat() 并没有修改数组，只是返回一个新的数组。



9.连接符join

打印拼接数组，使用特定的字符串连接

```javascript
arr
(3) ["C", "B", "A"]
arr.join('-')
"C-B-A"
```



10.多维数组

```javascript
var arr = [[1,2],[3,4],["5","6"]];
undefined
arr[1][1]
4
```



数组：存储数据（如何存，如何取）



### 3.3 对象 

多个键值对的模式

```javascript
var 对象名 = {
    属性名：属性值,
    属性名：属性值
    属性名：属性值
}

```



js中对象，{...}表示一个对象，键值对描述属性 XXX：xxx    均用 , 隔开，最后一个属性不加逗号！

1.对象赋值

```
person.name = "qwerty"
"qwerty"
person.name
"qwerty"
```



2.使用一个不存在的对象属性，不会报错！undefined





3.动态删减属性

```javascript
delete person.name
true
person
{age: 3, email: "2342", score: 0}
```



4.动态添加属性

```javascript
person.sss = "sss"
"sss"
person
{age: 3, email: "2342", score: 0, sss: "sss"}
```



5.判断属性值是否在这个对象中！ xxx in xxx！

```javascript
'age' in  person
true
'toStrig' in person
false
person.toString
ƒ toString() { [native code] }
'toString' in person
true
```



6.判断一个属性是否是这个对象自身拥有的 hasOwnProperty()

```javascript
person.hasOwnProperty('age')
true
person.hasOwnProperty('toString')
false
```



### 3.4  流程控制

if判断

```javascript
var age = 3;
if(age>3){
	alert("haha");
}else{
	alert("kuwa~");
}
```



循环

while循环，避免程序死循环

```javascript
while(age<100){
	age = age +1 ;
	console.log(age)
}

do{
	age = age + 1;
	console.log(age)
}while(age<100)


```



for循环

```javascript
for( let i = 0;i<100; i++){
    console.log(i);
}

```



foreach循环

```javascript
var age = [12,3,11,23,14,15,23,25];

//函数
age.forEach(function(value)){
    concsole.log(value);
}

```



### 3.5  Map和Set

ES6的新特性

Map：格式

```javascript
var mapTest = new Map([["xx",1],["yy",2],["zz",3]]);
```

```javascript
map
Map(3) {"tom" => 100, "jack" => 90, "haha" => 80}
map
Map(3) {"tom" => 100, "jack" => 90, "haha" => 80}
map.set('admin',111)
Map(4) {"tom" => 100, "jack" => 90, "haha" => 80, "admin" => 111}
map.set("admmmmm",111)
Map(5) {"tom" => 100, "jack" => 90, "haha" => 80, "admin" => 111, "admmmmm" => 111}
map
Map(5) {"tom" => 100, "jack" => 90, "haha" => 80, "admin" => 111, "admmmmm" => 111}

map
Map(3) {"tom" => 100, "jack" => 90, "haha" => 80}
map.set("tom", 8888)
Map(3) {"tom" => 8888, "jack" => 90, "haha" => 80}
map.set("sss", 759);
Map(4) {"tom" => 8888, "jack" => 90, "haha" => 80, "sss" => 759}
map.delete("sss")
true
map
Map(3) {"tom" => 8888, "jack" => 90, "haha" => 80}
```



Set:无序不重复的集合

```javascript
set
Set(5) {1, 2, 4, 5, 111}
set.delete(2)
true
set
Set(4) {1, 4, 5, 111}
set.add(999)
Set(5) {1, 4, 5, 111, 999}


Set(4) {1, 2, 4, 111}
set.add(999)
Set(5) {1, 2, 4, 111, 999}
set.delete(2)
true
set
Set(4) {1, 4, 111, 999}
console.log(set.has(111))
VM271:1 true
undefined
```



### 3.6 iterator

遍历map

```javascript
var map = new Map([["tom",1],["jack",2],["jerry",3]]);
for (let x of map){
	console.log(x)
}

var set = new Set([5,6,7]);
for (let y of set){
	console.log(y)
}


(2) ["tom", 1]
(2) ["jack", 2]
(2) ["jerry", 3]
 5
 6
 7
```



## 4.函数

### 4.1  定义函数

> 定义方式一



绝对值函数

```javascript
 function abs(x) {
            if (x>=0){
                return x;
            }else{
                return -x;
            }
        }

abs(5)
5
abs()
NaN

```

return 代表函数结束，返回结果！

如果没有执行return，函数执行完也会返回结果，结果就是undefined



> 定义方式二
>
> ```javascript
>  var abs = function (x) {
>             if (x>=0){
>                 return x;
>             }else{
>                 return -x;
>             }
>         }
> 
> 
>  abs(5)
> 5
> abs(-5)
> 5
> 
> 
> ```



手动抛出异常

```javascript
var abs = function (x) {
            if (typeof x!='number'){
                throw 'Not a Number';
            }
            if (x>=0){
                return x;
            }else{
                return -x;
            }
        }
```



参数问题

>arguments

arguments 是一个js免费赠送的关键字

代表，传递进来的所有参数，是一个数组



问题：arguments包含所有的参数，我们有时候想使用多余的参数来进行附加操，需要排除已有参数



>rest

以前

```java
if(arguments.length>2){
    for(var i=2;i<arguments.length;i++){
        
    }
}

```



ES6引入的新特性，获取处理已经定义的参数之外的所有参数  ...

```javascript
function aaa(a,b,...rest){
    console.log("a=>"+a);
    console.log("b=>"+b);
    console.log(rest);
}


```



### 4.2 变量的作用域

在javascript中，var定义变量实际是存在作用域

假设在函数体中，则在函数体外不可以使用

```javascript
function test(){
	var x = 1;
    x = x + 1;
}
x = x + 2; 
// Uncaught ReferenceError: x is not defined
```



如果在函数内部，使用了相同命名的变量，只要在函数内，就不会冲突

```javascript
        function f1() {
            var x = 1;
            x = x + 1;
        }
        function f2() {
            var x = 1;
            x = x + 1;
        }
```



内部函数可以访问外部函数的成员，反之则不行

```javascript
functtion f1(){
    var x = 1;
    
    //内部函数可以访问外部函数的成员，反之则不行
    function f2(){
        var y = y + 1;
    }
    var z = y + 1;//Uncautch ReferenceError : y is not defined   
}
```





```javascript
        function f1() {
            var x = 1;
            function f2() {
                var x = 'A';
                console.log('inner'+x);// output
            }
            console.log('outer'+x)
            f2();
        }
        f1();
```



假设，内部函数变量和外部函数的变量，重名！

```javascript
function f1() {
            var x = 1;
            function f2() {
                var x = 'A';
                console.log('inner'+x);// output
            }
            console.log('outer'+x)
            f2();
        }
        f1();

```

假设在javascript中函数查找变量从自身函数开始，有内向外 查找，假设外部存在这个同名的函数变量，则内部函数会屏蔽外部函数的变量。



> 提升变量的作用域

```javascript
function test(){
    var x = "x" + y;
    console.log(x);
    var y = ''y;
}

```

结果： y undefined 

说明：js执行引擎，自动提升了y的声明，但是不会提升y的赋值。

建议js内对变量的定义，可以直接放在首行，便于代码维护。



>全局函数

```javascript
// 全局变量
x = 1;

function f(){
    console.log(x);
}

f();
console.log(x);

```



> 全局对象 windows

```javascript
    <script>
        var x = 'xxx';
        window.alert(x);
        var  old_alert = window.alert;
         old_alert(x)
        window.alert = function () {

        };
         // 发现alert() 失效了
        window.alert(123);

        //恢复
        window.alert = old_alert;
        window.alert(354);
    </script>
```

javascript实际上只有一个全局作用域，任何变量（函数同样也可以视为变量），假设没有在函数作用范围内找到，就会向外查找，如果在全局作用域都没有找到，报错`RefnecnceError`

> 规范

由于我们所有的全局变量都会绑定到我们的windows上，如果不同的js文件，使用了相同的全局变量，冲突->如果能够减少冲突？

```javascript
// 唯一全局变量
var kaungApp = {};

// 定义全局变量
kaungApp.name = 'kaungApp';
kaungApp.add = function(a,b){
    return a+b;
}

```

把自己的代码全部放入自己定义的唯一空间名字中，降低全局冲突的问题



> 局部作用域

```javascript
    <script>
        for (var i = 0;i<100;i++){
            console.log(i);
        }
        console.log(i+1);

    </script>
```

ES6  let 关键字，解决局部作用域冲突问题！

```javascript
function aaa(){
    for(let i=0;i<100;i++){
        console.log(i);
    }
	console.log(i+1);
}

```

建议大家都是用` let `去定义局部作用域的变亮



> 常量

在ES6 之前，怎么定义常量，只有用全部大写字母命名的变量就是常量；建议不要修改var



```javascript
var PI = '3.14';

console.log(PI);
PI = '22.2';
console.log(PI);
```

在ES6 引入了常量关键字：`const`



### 4.3 方法

>定义方法

方法就是把函数放在对象的里面，对象只有两个对象：属性和方法

```javascript
    <script>
        var wjp = {
            name:'wjp',
            birth:'2000',
            age:function () {
                var now = new Date().getFullYear();
                return now- this.birth;
            }
        };
	   	//属性
        wjp.name
        //方法，一定要带括号
        wjp.age();
    </script>
```

this是无法指向的，是默认指向调用它的那个对象

>apply

在js中可以控制this指向！



```javascript
<script>
        function getAge(){
            // 今年 - 出生的年
            var now = new Date().getFullYear();
            return now - this.birth;
        }

        // 定义对象的
        var wjp = {
            name:'wjp',
            birth:'2000',
            age:getAge
        };

        var xiaoming = {
            name:'wjp',
            birth:'2000',
            age:getAge
        };

        // 调用的格式，apply(对象名，参数[]);
        // 细节问题， getAge 这个时候他是个对象(不能以方法的格式后面带括号)，调用apply方法，并绑定指定对象的同名方法
        // 这种操作方式，从某种意义上可以进行提炼
        getAge.apply(wjp,[]);

        getAge.apply(xiaoming,[]);


    </script>
```



### 5.对象

>标准对象

```javascript
typeof 123
"number"
typeof '222'
"string"
typeof "2222"
"string"
typeof true
"boolean"
typeof []
"object"
typeof NaN
"number"
typeof {}
"object"
typeof Math.abs
"function"
typeof undefined
"undefined"
```



#### 5.1 时间

```java
        var now = new Date(); //Sat Sep 19 2020 17:28:32 GMT+0800 (中国标准时间)
        now.getFullYear(); // 年
        now.getMonth(); // 月 0-11 月
        now.getDate();  // 日
        now.getDay();   // 星期几
        now.getHours(); // 时
        now.getMinutes(); // 分
        now.getSeconds(); // 秒
        now.getTime(); // 时间戳
```



#### 5.2 Json

json字符串和js对象的转化

```javascript
var user = {
            name:"wjp",
            age:3,
            sex:'男'
        }

// 对象转化为json字符串 {"name":"wjp","age":3,"sex":"男"}
var jsonUser = JSON.stringify(user);

// json 字符串转化为对象，参数json字符串
var  userObj = JSON.parse(jsonUser);

{name: "wjp", age: 3, sex: "男"}
age: 3
name: "wjp"
sex: "男"
__proto__: Object

```



### 6.面向对象

#### 6.1 什么是面向对象

>class 继承

`class`关键字，是在ES6引入的

1.顶一个类，属性，方法

```javascript
// 定义一个学生的类
<script>
        class Student{
            constructor(name) {
                this.name = name;
            }

            hello(){
                alert('hello');
            }
        }
        var xiaoming = new Student("xiaoming");
        var xiaohong = new Student("xiaohong");
    </script>

```



```javascript
console.log(xiaoming)
VM102:1 Student {name: "xiaoming"}
undefined
xiaoming.name
"xiaoming"
xiaohong.name
"xiaohong"
xiaohong.hello
ƒ hello(){
                alert('hello');
            }
xiaohong.hello()
undefined
```



2.继承

```
    <script>
        class Student{
            constructor(name) {
                this.name = name;
            }

            hello(){
                alert('hello');
            }
        }

        class XiaoStudent extends Student{
            constructor(name,gradle) {
                super();
            }

            myGradle(){
                alert("小学生");
            }
        }

        var xiaoming = new Student("xiaoming");
        var xiaohong = new Student("xiaohong");
    </script>
```

本质：查看对象原型

> 原型链

`__proto__`

