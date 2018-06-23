#CSS
三种引入方式：元素内引入、html中引入、外部引入、导入@import
##选择器
- 标签选择器
- class选择器
- id选择器
- * 所有元素
- + 紧随的同级标签
- ~ 所有同级标签
- > 子元素的某个类型的所有标签
- [] 拥有某种属性的标签

权重：id>class>标签

##字体属性
可以被继承
- font-size
- font-family
- color
- font-weight
- text-shadow:offx offy width color;
- text-index 文字缩进
- white-spacing
- word-bleak
- word-wrap
- text-overflow ellipase

##常用属性
- text-decration：underline、line-through、none
- text-transform：lowercase、uppercase、
- letter-spacing：文字边距
- height、width、line-height、max- 、min-
- text-align：center、right、left
- vertical-align：top、middle、bottom
- overflow：hidden、
- text-overflow：ellipse
- white-spacing：collapse
- border （width、style、color、radius、）
- visibility：占位置
- position：float、relative、absolute、fixed
- z-index:
- display：block、inline、inline-block、none、flex
- background:(color、image、position、repeat、attachment（fixed）、size、origin )
- cursor：pointer、wait、help、
- list-style-type list-style-image
- a link/active/hover/visited
- table (border-collapse)

##块级元素
p / pre / div / table / dl dt / ol li / ul li / h1~h6 / menu / form
##行级元素
input / img / span / i / a / select / textarea / lable /
##弹性盒子
弹性盒子由弹性容器(Flex container)和弹性子元素(Flex item)组成。 
弹性容器通过设置 display 属性的值为 flex 或 inline-flex将其定义为弹性容器。  
- flex-direction 指定子元素排列方式  
- flex-wrap 指定子元素是否换行  
- justify-content 指定子元素在其横轴的对齐方式  

	justify-content: flex-start | flex-end | center | space-between | space-around

-align-item  指定子元素在其纵轴的对齐方式
	
	align-items: stretch|center|flex-start|flex-end|baseline|initial|inherit;

-align-context 修改行对齐方式  
-order 子元素中使用，指定其排列序列号  
-align-self 在弹性子元素上使用。覆盖容器的 align-items 属性。  
-flex 设置弹性盒子的子元素如何分配空间,常用数字来代表其占用的份额
##浮动
设置浮动后默认display设置为block    
float (left、right)    
清除浮动  clear：left / right / both  
高度坍塌的解决：    
1. 末尾加元素并清除浮动  
2. 伪类中清除浮动

##盒子模型
1. border  
2. padding   
3. margin  
4. outline  
5. box-sizing：border-box / content-box  

##边框
border-radius、border-shadow、border-color...  


##伪类
通过":"来引入  
1. hover  
2. ative  
3. visited  
4. link  
5. disabled  
6. enable  
7. checked  
8. focus  
9. read-only  
10. read-write  
11. nth-child(n) 父标签的第n个标签  
12. nth-last-child(n) 父标签的倒数第n个标签  
13. nth-of-type() 父标签的第n个指定标签  
14. nth-last-of-type  
15. last-child  
16. first-child  
 
##伪元素
通过"::"来引入
1. after
2. before
3. first=letter
4. first-line
5. selection

##定位
position：float、relative、absolute、fixed、static  
-绝对定位会脱离文档流，受top、bottom、left、right影响，位置相对于其父元素中第一个有定位的元素  
-相对定位不会脱离文档流，其位置top、bottom、left、right的设置相对于其所有文档流的状态  
-固定定位脱离文档流，其位置top、bottom、left、right的设置相对于body

##转换、过渡、动画
transform：  
- rotate  
- translate  
- scale  
- skew  
- 三维的分别在上述属性加X Y Z

CSS3 过渡 transition:  
- transition-property  
- transition-duration  
- transition-timing-function  
- transition-delay

CSS3 @keyframes 规则  

	@keyframes 名称
	{
		from{}
		to{}
	}

	@keyframes myfirst
	{
	0%   {background: red;}
	25%  {background: yellow;}
	50%  {background: blue;}
	100% {background: green;}
	}

CSS3 动画animation  
- animation-name  
- animation-duration  
- animation-timing-function  
- animation-delay  
- animation-iteration-count  
- animation-direction 

##渐变
	background: linear-gradient(direction, color-stop1, color-stop2, ...); 
 
	background: linear-gradient(angle, color-stop1, color-stop2);

##响应式布局
@media 结合 max-width / min-width等来实现