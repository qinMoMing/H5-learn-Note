#JAVASCRIPT

##注意
1. js会自动加分号，故类似for / if / return等语句。。。会是一个坑，后面有东西要连接好。 

##运算符
- 一元 / 二元 / 三元
- 赋值 / 比较 / 算术 / 逻辑 / 位 / 字符串 / 特殊运算符（？：、this、delete、","、typeOf、instanceOf、new、）
##字符串
- 转义字符\用来转义字符串中一些特殊字符
- ES6模板字符串 `${}`
- length
- substring
- toLowerCase / toUpperCase
- indexOf

##数组
通过[]来访问，是有序的，有索引。数组是弱类型的，可包含各种类型。数据的长度是动态的。  
 
创建方式：  
var arr = []; //允许以","结尾。  
var arr = new Array(length);  
var arr = new Array(参数1，参数2，...);  
  
- length
- slice //截取后返回，左闭右开。2参，起止，无止默认尾部。
- push(尾+) / pop(尾-) / shift(头-) / unshift(头+)
- sort //默认转成字符串后按ASCII排序，在元素组上。接收一个函数参数，a小b负。
- reserve //倒转，原数组
- splice //万能方法，从指定索引开始删除若干元素后从该位置插入若干元素，参数有多个。前两个为删除的起始和长度。后面为添加内容。
- concat //连接数组后返回，只拉一次数组。
- join //将数组中的元素用指定的字符串连接起来返回字符串
- delete //是将数组对应值置为undefined,长度不变。

二维数组、稀疏数组  

##Set
一组key的集合，且不重复.ES6新增。

- set / add /delete



##Map
键值对结构，有很快的查找速度。ES6新增。无法使用下标来查找。

- set / get /has /delete 四大方法
- 一个key对应一个值，多次放入会覆盖

##解构赋值
###数组解构
	var [a,b,c]  = ["A","B","C"]
###对象解构
	var {a,b,c} = {a:A,b:B,c:C} 
###默认值
	var [a,c=0] = [1]
	var {a,b,c,d="aaa"} = {a:A,b:B,c:C} 

##循环
- for( ; ; )
- for(let arr in arrs) //包含继承的属性
- while（）do / do () while
- for(let arr of arrs) //
- forEach(function(value,index,this))

##函数
函数声明、函数表达式、Function构造器  
函数声明：function fn(){}  //会前置
函数表达式：（1）var fn = function(){} (2)(function(){})() (3)return function(){}  
Function构造器：new Function() //少用

this的指向问题  
全局、一般、对象函数  
- 用that=this来转移this的指定，使程序易阅读
- 指向调用它的对象
- aplly方法来为this指向 aplly(obj,[arguments])
- call(obj,[arg1],[arg2],...)
- bind(obj)  

函数属性：  
fn.name //函数名   
fn.length //形参个数  
arguments （arguments.callee //函数名） //未传形参的不会绑定，严格模式功能缩减。  
bind与currying，bind与new,new会忽略bind关于this的绑定    

高阶函数：把函数作为参数传入函数的函数 / 把函数作为返回值的函数    


- map(func) arr.map(func) //用func处理arr的每一个数据后返回新的数据，接受一个参数
- reduce(func) //func必须接受两个参数，结果和下一个值。用来递归
- reduceRight
- filter（func） //返回func返回值为true的值组成的数组，func接受3个参数，value，index，array
- sort(function(x,y){-1,1,0}) //直接修改原数组，若x>y返回的是1则是从小到大排列
- some() / every()
- indexOf() / lastIndexOf()

函数若返回一个函数，不会立刻调用，而只是返回了函数的引用，要加上（）后才会调用。而闭包基于这种不立即执行。  
闭包：返回一个函数，函数是内部函数，可以调用外部函数的参数和变量。达到私有函数和私有变量的作用。  

箭头函数：()=>{}  
this的指向，指向定义处的作用域，也就是外层调用者的作用域。而不再是使用时的作用域。


##对象
概念：类是对象的模板，实例是根据类创建的对象。  
JS通过原型链来实现面向对象的编程。  

通过 “.” / ["键值"] 来访问，是{}包含的键值对形式,键值对之间用","隔开。访问属性是原型链的方式。ES6中若键值一样，可只写一个。对象是一种引用类型的变量。键名只能是字符串。无法使用下标来查找。
对象的属性是无序的。    
属性是可以动态添加删除的，每个属性包含writable（可写）、enumerable、configurable（delete可用 标签可否再次修改）、value、get/set。而对象包含proto、class、extensble。  

Object.isExtensible(obj)  
Object.preventExtensions(obj)  
Object.seal(obj)  
Object.isSealed(obj)
Object.freeze(obj)  
Object.isFroze(obj)   


- delete //关键字，删除。表示属性不存在了，prototype属性不能删除
- in //检测是否拥有某一属性,会查找原型链
- hasOwnProperty(property) 
- getPrototypeOf()
- defindeProperty(obj,property,{属性标签及其值})
- getOwnPropertyDescriptor(obj,property)
- propertyIsEnumerable(property)
- getter/setter方法属性 get/set age(){}形式,当原型上有此方式定义的属性时，继承他的对象不能动态的增加相应的属性。要通过defineProperty去修改。


创建对象：  
1、用{}来创建  
2、用构造函数来创建(new)，用构造函数创建的对象原型会指向构造函数。  
3、用Object.creat()在对象中创建已有对象的实例，对其属性进行增删改后返回实例的方式来实现继承    

###标准对象
数据类型的检测  
typeof 检测number / string / boolean / undefined / function  
typeof null / array / object 是object  
typeof NAN 返回Number  
array 用 Array.isArray()检测  
null/undefined没有toString方法    
123..toString() / (123).tostring()才是正确的写法  

instanceOf 基于原型链的检测，不同的windows和iframe不能用instanceOf

object.prototype.toString() 返回字符串 [object type]


包装对象 new Number / Boolean / String  
包装对象有length属性  
普通数据类型调用对象属性时会建立一个对应的临时包装对象，过后自动销毁。  

date对象  
- new Date()
- getFullYear() / getMonth / getDate()  //年月日 （月份是0~11）
- getDay() //星期几
- getHours() /getMinutes() /getSeconds() /getMilliseconds() //时分秒毫秒
- getTime() / now()  //时间戳 1970.01.01 00：00：00

Reg对象  
- \d 匹配数字
- \w 匹配数字或字母
- \s 匹配空格
- *号任意个字符 +号至少一个字符，？表示0或1个字符，{n}表示n个字符，{n,m}表示 n 到 m 个字符 
- [] 表示范围，| 表示或，^表示以什么开头， $表示以什么结尾
- \进行转义
- （）进行捕获分组
- g 全局搜索
- exec() 用来搜索匹配

写法：① reg = /a*/ ② reg = new RegExp('a*') 

json对象  
json是utf8编码,""包含字符串及对象中的键  
序列化 JSON.Stringify()将对象序列化成字符串，第二个参数用于控制如何筛选值.序列化中的值是undefined时属性会自动忽略。NaN，Initial=>null。Date=>UTC格式。  
反序列化 JSON.parse()将字符串反序列化为对象  还可以接收一个函数用来解析属性  

 

##定时器
setTimeOut()  
setInterval()  
clearInterval() &nbsp;&nbsp;//暂停计时器   
clearTimeout()  &nbsp;&nbsp;//暂停计时器  
timer = null &nbsp;&nbsp; //删除定时器

##位置获取
- document.body.clientWidth
- document.body.clientHeight