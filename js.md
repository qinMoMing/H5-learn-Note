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
通过[]来访问

- length
- slice //截取后返回
- push(尾+) / pop(尾-) / shift(头-) / unshift(头+)
- sort
- reserve //倒转
- splice //万能方法，从指定索引开始删除若干元素后从该位置插入若干元素，参数有多个
- concat //连接数组后返回
- join //将数组中的元素用指定的字符串连接起来返回字符串

##Set
一组key的集合，且不重复.ES6新增。

- set / add /delete

##对象
通过“.”来访问，是{}包含的键值对形式,键值对之间用。ES6中若键值一样，可只写一个。对象是一种引用类型的变量。键名只能是字符串。无法使用下标来查找。

- delete //关键字，删除
- in //检测是否拥有某一属性
- hasOwnProperty()
- getPrototypeOf()
- defindeProperty()



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
this的指向问题
- 用that=this来转移this的指定，使程序易阅读
- aplly方法来为this指向 aplly(obj,[arguments])
- call(obj,[arg1],[arg2],...)

高阶函数：把函数作为参数传入函数的函数 / 把函数作为返回值的函数


- map(func) arr.map(func) //用func处理arr的每一个数据后返回新的数据，接受一个参数
- reduce(func) //func必须接受两个参数，结果和下一个值。用来递归
- filter（func） //返回func返回值为true的值组成的数组，func接受3个参数，value，index，array
- sort(function(x,y){-1,1,0}) //直接修改原数组，若x>y返回的是1则是从小到大排列

函数若返回一个函数，不会立刻调用，而只是返回了函数的引用，要加上（）后才会调用。而闭包基于这种不立即执行。  
闭包：返回一个函数，函数是内部函数，可以调用外部函数的参数和变量。达到私有函数和私有变量的作用。  

箭头函数：()=>{}  
this的指向，指向定义处的作用域，也就是外层调用者的作用域。而不再是使用时的作用域。

##标准对象
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
序列化 JSON.Stringify()将对象序列化成字符串，第二个参数用于控制如何筛选值  
反序列化 JSON.parse()将字符串反序列化为对象  还可以接收一个函数用来解析属性  

##面向对象编程
概念：类是对象的模板，实例是根据类创建的对象。  
JS通过原型链来实现面向对象的编程。  

创建对象：  
1、用{}来创建  
2、用构造函数来创建(new)   


创建对象继承的方式：  
1、用Object.creat()在对象中创建已有对象的实例，对其属性进行增删改后返回实例的方式来实现继承  
2、

##定时器
setTimeOut()  
setInterval()  
clearInterval() &nbsp;&nbsp;//暂停计时器   
clearTimeout()  &nbsp;&nbsp;//暂停计时器  
timer = null &nbsp;&nbsp; //删除定时器

##位置获取
- document.body.clientWidth
- document.body.clientHeight