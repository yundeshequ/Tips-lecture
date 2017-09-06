# **一些学习中的Tips.**

---

1. 变量提升.概念: 后var的变量如果在var之前操作,不会报错,会以undefined来操作,称为变量提升.let声明的变量不会被提升.

2. 同源策略.由Netscape提出的安全策略,同源是指协议,域名,端口相同,执行脚本时会检查脚本属于哪个页面,只有同源的脚本才会被执行.

3. JSON.stringify(obj)把对象转换成json.

4. web标准:Web标准，不是一个标准,是一些列标准。Web标准由万维网联盟（W3C）制定。包括网站三层:结构层,表现层,动作层的标准,结构层标准主要是规定html,xhtml,xml的相关规范,表现层标准主要包括css的规范,动作层标准包含w3c dom模型,ECMAScript等规范.

5. 阻止冒泡:

  ```javascript
  e.stopPropagation();IE9+
  e.cancelBubble = true;ie6/7/8;
  ```

   事件对象:

  ```javascript
  window.event;ie6/7/8;
  function(e){}中的e.ie9+;
  ```

   阻止默认事件:

  ```javascript
  e.preventDefault();ie9+;
  returnValue = false;IE6/7/8
  ```

   获取滚动条位置:

  ```javascript
  window.pageYOffset;IE9+
  document.documentElement.scrollTop;IE6/7/8
  ```

6. js执行流程流程中第一阶段会创建所有变量,并赋值为undefined,(hoisting(变量声明提升)机制)对象如果添加属性并赋值,也会遵循变量声明提升.

7. typeof 正则表达式;----返回object;

8. if语句里声明函数,在strict mode出现之前,在if内声明函数是没有一致性的,不同浏览器会做出不同解释,最佳的代码规范都要求不在if里声明函数.

9. ECMAScript中的对象分类：

   本地对象：js中的构造器函数（类）；

   宿主对象：所有非本地对象都是宿主对象，即由 ECMAScript 实现的宿主环境提供的对象。

   内置对象：ECMA-262只定义了两个内置对象，即 Global 和 Math （它们也是本地对象，根据定义，每个内置对象都是本地对象）。

10. 暂时性死区:

  块级作用域内存在let命令, 就会绑定这块儿区域, let声明的变量如果在声明之前操作,会报错, 即:

  ```
  var temp = 123;
  if (true) {
    temp = 456;//报错
    let temp;
  }
  ```

  例如上述代码中let绑定了这个区域,所以会报错.

  总之, 在代码块内，使用let命令声明变量之前，该变量都是不可用的。这在语法上，称为“暂时性死区”（temporal dead zone，简称TDZ）。

11. nodejs: 服务器端js的运行环境.

12. jsonp: json with padding, 用json填充函数的实参. 其本质上是利用<script> 标签的src属性可以跨域的原理来实现跨域.

13. 原型链: 一条由__proto__串起来,直到 Object().prototype.__proto__为null的链, 称为原型链.

14. 由于Function的特殊性，它“自己构造自己”。

    ```javascript
    Function.__proto__ === Function.prototype //true
    ```

15. 冻结的对象: 

    ```javascript
    const foo = Object.freeze({});
    //常规模式给foo对象添加属性不起作用;
    //严格模式给foo添加属性报错;
    foo.prop = 111;//报错
    ```

    常量foo指向一个冻结的对象，所以添加新属性不起作用，严格模式时还会报错。

    出了将对象本身冻结, 对象的属性也应该被冻结:

    ```javascript
    var oFree = (obj) {
      Object.freeze(obj);
      Object.keys(obj).forEach( (key, value) => {
        if( typeof obj[key] === 'object' ) {
          oFree(obj[key]);
        }
      });
    };
    ```

16. let 声明的变量不属于全局变量:

    ```javascript
    var a = 1;
    window.a // 1
    //===============
    let a = 1;
    window.a //undefined
    ```

    ​

    ​

---

以后会不定期更新.哈哈哈 .