一、简介
AJAX = 异步 JavaScript 和 XML
	是一种用于创建快速动态网页的技术
	通过在后台与服务器进行少量数据交换，AJAX 可以使网页实现异步更新
	这意味着可以在不重新加载整个网页的情况下，对网页的某部分进行更新
	传统的网页（不使用 AJAX）如果需要更新内容，必需重载整个网页面

二、运行原理
	页面发起请求，会将请求发送给浏览器内核中的Ajax引擎，Ajax引擎会提交请求到服务器端
	在这段时间里，客户端可以任意进行任意操作
	直到服务器端将数据返回给Ajax引擎后，会触发你设置的事件，从而执行自定义的js逻辑代码完成某种页面功能

三、原生Ajax使用步骤
	1、创建Ajax引擎对象
	2、为Ajax引擎对象绑定监听
	3、发送请求(参数1：请求方式，参数2：请求地址，参数3：是否异步)
		GET:		
			xmlhttp.open("GET","${pageContext.request.contextPath}/ajax?key=value",true);
			xmlhttp.send();
		POST:
			xmlhttp.open("POST","${pageContext.request.contextPath}/ajax",true);
			xmlhttp.setRequestHeader("Content-type","application/x-www-form-urlencoded");//添加请求头
			xmlhttp.send(key1=value1&key2=value2);
	4、接受响应
		xmlhttp.responseText
		xmlhttp.responseXML
			if (xmlhttp.readyState == 4 && xmlhttp.status == 200) {
				var response = xmlhttp.responseText;
				var response = xmlhttp.responseXML;
			}
			
四、JQuery中的Ajax
	1、$.get(url, [data], [callback], [type])		//需要解决请求体中文乱码
	2、$.post(url, [data], [callback], [type])		//不用管请求体中文乱码
	3、$.ajax( { option1:value1,option2:value2... } );	
		常用的option有如下：
			async：是否异步，默认是true代表异步
			data：请求参数，建议使用json格式
			dataType：服务器端返回的数据类型，常用text和json
			contentType:发送数据的格式
					默认: "application/x-www-form-urlencoded"
					发送json："application/json;charset=utf-8"
			success(data)：成功响应之后的回调，对应的类型是function类型
			error(data)：请求失败之后的回调，对应的类型是function类型
			complete(XHR, TS)：请求完成之后的回调，对应的类型是function类型(无论成功/失败都会执行)
			type：请求方式，POST/GET
			url：请求服务器端地址
			......
	get、post是在这种方式上封装的，在get/post无法满足要求时，可以采用这种方式
