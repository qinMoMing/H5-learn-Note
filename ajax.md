#ajax
##语法

		var xmlhttp = new XMLHttpRequest();//构建HttpRequest实例  
		xmlhttp.open("GET","url","async");//规定请求类型，url,及是否是异步
		xmlhttp.send(string);//GET方式没有参数，send参数即发送给服务器的数据，是字符串类型

POST的使用情况：  
    
	