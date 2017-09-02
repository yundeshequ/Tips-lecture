* 一些学习中的Tips.

---

1. 变量提升.概念: 后var的变量如果在var之前操作,不会报错,会以undefined来操作,成为变量提升.let声明的变量不会被提升.

2. 同源策略.由Netscape提出的安全策略,同源是指协议,域名,端口相同,执行脚本时会检查脚本属于哪个页面,只有同源的脚本才会被执行.

3. JSON.stringify(obj)把对象转换成json.

4. web标准:Web标准，不是一个标准,是一些列标准。Web标准由万维网联盟（W3C）制定。包括网站三层:结构层,表现层,动作层的标准,结构层标准主要是规定html,xhtml,xml的相关规范,表现层标准主要包括css的规范,动作层标准包含w3c dom模型,ECMAScript等规范.

5.    阻止冒泡:

      ```
      e.stopPropagation();ie9+;
		e.cancelBubble = true;ie6/7/8;
      ```
      
      事件对象:
      
      ```
         window.event;ie6/7/8;
   		function(e){}中的e.ie9+;
      ```
      
      阻止默认事件:
      
      ```
		e.preventDefault();ie9+;
   		returnValue = false;
      ```
      
      获取滚动条位置:
      
      ```
   		window.pageYOffset;
   		document.documentElement.scrollTop;
      ```

6. js执行流程流程中第一阶段会创建所有变量,并赋值为undefined,(hoisting(变量声明提升)机制)对象如果添加属性并赋值,也会遵循变量声明提升.

7. typeof 正则表达式;----返回object;

8. if语句里声明函数,在strict mode出现之前,在if内声明函数是没有一致性的,不同浏览器会做出不同解释,最佳的代码规范都要求不在if里声明函数.

---

以后会不定期更新.哈哈哈 .
