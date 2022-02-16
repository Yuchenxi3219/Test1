#   《JavaWeb学习笔记》

## 1. HTML&CSS

### 1.1 HTML：

#### 1.1.1概念

* 网页的骨架

* Hyper Text Markup Language:超文本标记语言

  * 网页文件本身是一种**文本文件**
  * 在文本文件中**添加标记符**，告诉浏览器如何显示其中的内容


#### 1.1.2 标签与属性

* HTML的标签

  * 双标签：==<标签 > 数据  </标签>==     
  * 单标签：==<标签/>==

* 属性：标签附加的信息
  * 基本属性
    * class
    * id
    * name
    * value
    * style：css样式
  * 事件属性


```html
<!DOCTYPE html><!--约束，声明-->
<html lang="zh_CN"><!--页面的开始-->
    <head><!--头部信息。1.title标签 2.css样式 3.js代码-->
        <meta charset="UTF-8">
        <title>主页</title>
    </head>
    <body bgcolor="#4682b4">
        哈哈哈哈哈
        <br/><!--换行-->
        <hr/><!--水平线-->
        你好好你好
        <button onclick="alert('真牛逼')">NB</button>> <!--事件属性-->
    </body>
</html><!--页面的结束-->
```

#### 1.1.3 标签语法

* 标签注意事项：

  * 标签不可以嵌套
  * 标签要正确闭合
  * 属性必须有值且必须加引号
  * 注释中不能再有注释

* 块级元素：在页面中独占一行 

  * < div > ==（可以用display：inline-block将< div >变成行内元素(内容多长行就多长)）==

    * 浮动效果

    ```html
    <!DOCTYPE html>
    <html lang="en">
    <head>
        <meta charset="UTF-8">
        <title>今天头条</title>
        <style>
            div {
                border: 1px solid skyblue;
            }
    
            .left {
                width: 20%;
                float: left;
                height: 500px;
            }
    
            .center {
                width: 59%;
                float: left;
                height: 500px;
            }
    
            .right {
                width: 20%;
                float: left;
                height: 500px;
            }
    
            .foot {
                /*清除浮动效果，用clear*/
                clear: both;
                text-align: center; /*控制文本对齐方式*/
                background-color: lightblue;
            }
    
        </style>
    
    </head>
    <body>
    <div align="center" >
        <h1>快讯</h1>
    
    </div>
    <div> <sup>yuchenxi </sup></div>
    <div class="left" align="center">111</div>
    <div class="center" align="center">center</div>
    <div class="right" align="left">222</div>
    <div class="foot">bottom</div>
    </body>
    </html>
    ```

* 行内元素：内容都在同一行

  * < span > //行内元素：span

* 特殊字符：

  * &lt、 &nbsp

* 字体标签：

  * font

* 超链接：< a href... target... >  ...  < /a >

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <title>Title</title>
<style>
  a{
    text-decoration: none; /*去掉下划线*/
    color: powderblue; /*改变超链接颜色*/
  }

  a:hover{ /*鼠标悬浮变色*/
    color: red;
  }
</style>

</head>
<body>
<a href="http://www.qq.com" target="_self">腾讯网</a> <!--target设置在当前页面跳转-->
<br>
<a href="tupian.html" target="_blank>"> 点击我跳转其他html</a>
<br>
<a href="https://tlias-stu.boxuegu.com/#/login" target="_blank" > <img src="../img/学生端.png"> </a> <!--用点击图片的方式跳转网页-->
</body>
</html>
```

* 相对路径：.  （当前文件所在的目录）/ ..（当前文件所在的上一级目录）
* 绝对路径：http://ip:port/工程名/资源路径
* 添加图片并且设置长宽：<img src="./img/1.png"width="120" height="50"border=1/>

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <title>Title</title>
</head>
<body>
<img src="../img/学生端.png" title="audi" alt="图片失踪了" width=210 height=70>
</body>
</html>

<!--
   ../表示当前文件所属目录的上一级目录，./表示当前目录，然后再通过文件名调用-->
```

* 表格
* Iframe

```html
<!DOCTYPE html><!--约束，声明-->
<html lang="zh_CN" xmlns="http://www.w3.org/1999/html"><!--页面的开始-->
<head><!--头部信息。1.title标签 2.css样式 3.js代码-->
    <meta charset="UTF-8">
    <title>主页</title>
</head>
<body bgcolor="#f5f5dc">
<h1 align="left">我是标题</h1> <!--左对齐1号大小标题-->
<h3 align="center">我是标题</h3>
<h6 align="right">我是标题</h6>
你看看还能看嘿嘿

<br/> <!--换行-->

<hr/> <!--水平线-->
你好好你好

<button onclick="alert('真牛逼')">NB</button> <!--事件属性-->

<font color="#e6e6fa" face="宋体" size="7"> 我是字体标签 </font> <!--font标签-->

我是&lt;br&gt;标签 <!--特殊字符-->&nbsp;&nbsp;&nbsp;牛逼空格
<br/>
<a href="http://www.qq.com" target="_self">腾讯网本界面</a> <!--超链接--><br/>
<a href="http://www.qq.com" target="_blank">腾讯网跳转界面</a> <!--超链接-->

<ul>
    <li>张三</li>
    <li>李四</li>
    <li>王武</li><!--无序标签-->
</ul>

<ol>
    <li>巴萨</li>
    <li>皇马</li>
    <li>马竞</li>
    <li>西班牙人</li><!--有序标签-->
</ol>

<img src="img/11.png" width="120" height="50" border=1 alt="找不到"/> <!--添加图片-->

<table align="center" border="1" width="300" height="300" cellspacing="0"><!--表格格式设置-->
    <tr>
        <td align="center"><b>1</b></td> <!--加深居中-->
        <th> 2</th> <!--加深居中简单方法-->
        <th> 3</th>
    </tr>
    <tr>
        <td> 4</td>
        <td> 5</td>
        <td> 6</td>
    </tr>
    <tr>
        <td> 7</td>
        <td> 8</td>
        <td> 9</td>
    </tr>

</table>

</br>

<table align="center" border="1" width="500" height="500" cellspacing="0">

  <thead> /// </thead>  <tbody> /// </tbody>
    <tr>
        <th colspan="2">999</th>
        <th>999</th>
    </tr>
    <tr>
        <th rowspan="2">999</th> <!--合并单元行--> <colsap> 合并单元列 </colsap>
        <th>999</th>
        <th>999</th>
    </tr>
    <tr>
        <th>999</th>
        <th>999</th>
    </tr>

</table>

<iframe src="img/11.png" width="500" height="400"/>


</body>
</html><!--页面的结束-->
```

* ==表单标签：采集用户数据==

  * **input**

  ```html
  <!DOCTYPE html>
  <html lang="en">
  <head>
      <meta charset="UTF-8">
      <title>Title</title>
  </head>
  <body>
  <form action="#" method="get"> <!--action是指定提交数据的URL--> <!--method是提交方式，get/post较为常用-->
      <label for="username">  用户名：<input type="text" name="username" placeholder="请输入用户名" id="username"></label><br> <!--如果要正确提交，则需要加name属性--> <!--placeholder灰色提示-->
      <!--label标签（和id对应）用于定位，用户点击"用户名"的时候，光标自动跳到框框里面-->
      密码：<input type="password" name="password" placeholder="请输入密码"><br>
  
      性别：<input type="radio" name="gender" value="male" checked> 男
           <input type="radio" name="gender" value="female"> 女 <br> <!--radio是单选框，只能选择一个-->
  
      爱好：<input type="checkbox" name="hobby" value="eat" checked> 吃饭 <!--checkbox是复选，可以选择多个-->
           <input type="checkbox" name="hobby" value="sleep"> 睡觉
           <input type="checkbox" name="hobby" value="hitdoudou"> 打豆豆 <br>
  
      日期：<input type="date" name="birthday"><br>
      
      上传图片：<input type="file" name="file"> <br>
  
          <input type="submit" value="登陆">  <!--提交按钮-->
  
  </form> <!--用户数据采集范围，form里面都可以提交-->
  </body>
  </html>
  ```

  * **select：下拉列表** 
  * **textarea：创建文本框**

  ```html
  <!DOCTYPE html>
  <html lang="en">
  <head>
      <meta charset="UTF-8">
      <title>Title</title>
  </head>
  <body>
  省份 <select name="province">
      <option value="">--请选择--</option>
      <option value="1">北京</option>
      <option value="2">上海</option>
      <option value="3">广州</option>
  </select> <br> <br>
  
  写一段话：<textarea cols="20" rows="5"></textarea>
  
  </body>
  </html>
  ```

* <font color='cornflowerblue'>（<u>面试题）提交方式get/post的区别？（通过浏览器直接请求是get方式）</u>：</font>

  * <font color='cornflowerblue'>get的请求参数会显示在地址栏；请求参数的**长度有限制**；*不够安全*、快</font>
  * <font color='cornflowerblue'>post的请求参数会封装在请求体中，而不是在地址栏；请求参数的**长度没有限制；** *较为安全*、较慢</font>

### 1.2 CSS

#### 1.2.1 概念

* **Cascading Style Sheets 层叠样式表，美化网页**

#### 1.2.2 结合方式和选择器

* ==CSS与HTML结合方式== <font color='tomato'>内部样式表和外部样式表的优先级取决于位置的先后，最后定义的优先级最高（就近原则）</font> 

  * **内联：**在标签内部使用style
  * **内部样式：**在head里面定义style标签 < style >  div{ color:blue; }  < /style >
  * **外表样式：**通过编写css文件，再再html文件里添加link标签引入编写的css文件

* ==选择器==

  * **基础选择器**

    * id选择器、元素选择器、元素选择器

    ```html
    <!DOCTYPE html>
    <html lang="en">
    <head>
        <meta charset="UTF-8">
        <title>Title</title>
    
      <style>
        #sss{ /*id选择器*/
          color: skyblue;
        }
    
        div{ /*元素选择器*/
          color: red;
        }
    
        .cls{ /*类选择器*/
          color: blue;
        }
    
      </style>
    </head>
    <body>
    <div id="sss"> hello </div>
    <div id="div2"> fxxk </div>
    <ycx class="cls"> world</ycx>
    </body>
    </html>
    ```

    * *优先级：style内置属性id选择器>类选择器>标签选择* （越是精确优先级越高）

  * **扩展选择器**

    * 属性选择器 []   例如：[*type*]{样式的控制}  //通过定位input *type*来进行修改
    * 伪类选择器：主要针对的是a标签
      * a:link { }  //未访问的状态
      * a:visited { } //已访问的状态
      * a:hover { }//鼠标悬浮的状态
      * a:active { } //已选中的状态
    * 组合选择器
      * 后代选择器 用空格分割：标签名 后代标签名{ }
      * 分组选择器 用逗号分割  

#### 1.2.3 CSS属性

* 字体文本：font-size\color\text-align(对齐方式)\line-height
* 背景：background
* 边框：border
* 尺寸：width\heigth
* **display：none:元素不显示/block:元素显示**
* 盒子属性（根据视角来的）
  * margin：外边距
  * padding：内边距

### 1.3 css盒子模型

* **概念**：设置边框和元素内容实现布局的方式。设置：1.内边距；2.外边距 实现布局。内外边距取决于自己的视角。一般使用外边距
* **margin:(内边距是padding,方法都是一样)**
  * margin: 20px;（上、下、左、右各20px。）
    margin: 20px 40px;（上、下20px；左、右40px。）
    margin: 20px 40px 60px;（上20px；左、右40px；下60px。）
    margin: 20px 40px 60px 80px;（上20px；右40px；下60px；左80px。）
    在css中使用margin可以将margin-top，margin-right，margin-bottom，margin-left，缩写为一个标记，顺序为上右下左（顺时针）。

## 2.  JavaScript

### 2.0 概念

* 客户端脚本**语言**，无需编译，直接被浏览器解析。制作动态的网页效果

### 2.1 javascript与HTML结合的两种方式：

* **内部JS：**直接在HTML文件里面添加< script>内容 < /script>
* **外部JS：** 新建js文件，在js文件里面添加内容，在HTML文件里面用src引入js文件

### 2.3 原始数据类型

* **原始数据类型 5种**  <font color='tomato'>JS是弱类型语言，用var来定义变量；可用typeOf获取数据类型</font> 
  * **number**			
    * 整数
    * 小数
    * NaN：not a number 一个不是数字的数字类型
  * **string** <font color='tomato'>这里是小写</font>
    * 字符/字符串都是字符串 ‘ ’ 、‘’ ‘’都行
  * **boolean**
    * true/false
  * **null**
    * 一个对象为空的占位符
  * **undefined**
    * 未定义：一个变量没有赋初始化值，就被默认为undefined
  * **bigint**
    * 大整数
* **运算符**
  * 一元、算数、赋值
  * 比较
    * 多一个=== ：全等于，先比较数据类型，再比较数据值	<font color='mediumseagreen'>只有这个和Java不一样</font>
  * 逻辑、三元
* **JS特殊语法**  <font color='mediumseagreen'>弱类型语言</font> 
  * let/var：局部变量；
  * ​     ：全局变量；
  * const：常量；
* **流程控制语句**
  * if else
  * switch
    * 在JS中switch中可以**接收任意类型**的数据类型
  * for
  * while
  * do while

### 2.4 引用数据类型

* **JS中的面向对象**

  ```javascript
  <script>
  let stu={ 
    					name:"小明",
              age:22,
              hobby:["吃饭","睡觉"],
              e :function(){
                  document.write("玩游戏")
              }};
          document.write(stu.age+stu.hobby[0]);
          stu.e();
    </script>
  ```

* **Boolean**

* **Number**

  * parseFloat()；将传入的字符串转换成浮点数
  * parseInt()；将传入的字符串转换成整数
  * isNaN；判断传入的值是否是NaN   <font color='mediumseagreen'>不能用==来进行判断</font>

* **String** <font color='mediumseagreen'>以上三个是相当于基本类型的包装类对象</font> 

  * replace(old,new)；将新字符串替换老字符串

* **Function** 函数对象 <font color='mediumseagreen'>切记：这里function是对象，所以也就是有属性等</font> 
  * **特点1**：参数的var可以直接省略
  * **特点2**：因为方法是对象，如果定义了名称相同的方法，后者会将前者覆盖
  * **特点3**：如果实参不全，没有填入的实参就是**undefined**的 <font color='tomato'>重要！这也是Java的不同之处：**JS中，方法的调用只与方法名有关，和参数列表无关**</font> 
  * **特点4**：function里面封装了一个名为arguments的数组对象。每传递一个实参，就是像数组里面放进一个元素。也可以通过遍历arguments求和的方式得出参数之和。
  
  ```javascript
  function fu1(a, b) {        
        alert(a + b);    
      }     
  fu1(3, 4);  /*方法的创建以及调用方式*/
  ------------
   function fu1() {        
        sum = 0;        
     for (let i = 0; i < arguments.length; i++) {            
          sum+=arguments[i];        
       }        
        return sum;    
     }    
  var sum =fu1(1,1,2,3,4,5);    
  alert(sum)  /*特点是4的实现*/
  ```

* **Array**

  * **特点1**：数组中塞入元素是[ ]而非Java的{ }
  * **特点2**：同一个数组可以放进去不同的类型的元素，并且长度可变（类型Java的集合） <font color='mediumseagreen'>这也和JavaScript是弱类型语言是一致的，而非Java这种强类型语言</font> 
  * **数组对象的方法：**
    * **join(参数)：**将数组的元素以指定的分隔符拼接为字符串 （没有参数的话就默认以 , 为分隔符）
    * **push(参数)**：在数组元素末端添加一个或者多个长度，并且返回新的长度
    * pop()：删除数组末尾的元素
    * shift()：删除数组最前面元素
    * includes(参数)：判断数组是否包含此参数
    * reverse()：反转数组中元素
    * sort()：对数组进行排序
    * **高级运算**：**...**

* **Date**

  * **创建方法：**var date =new Date();
  * **Date对象的方法**
    * date.toLocalString()：返回本地事件字符串
    * date.getTime()：返回当前时间与1970.1.1.00.00.00之间相差的毫秒值

  * **封装好的Date方法，专门用来format:**

  ```javascript
  Date.prototype.Format = function (fmt) {
      var o = {
          "M+": this.getMonth() + 1, //月份 
          "d+": this.getDate(), //日 
          "H+": this.getHours(), //小时 
          "m+": this.getMinutes(), //分 
          "s+": this.getSeconds(), //秒 
          "q+": Math.floor((this.getMonth() + 3) / 3), //季度 
          "S": this.getMilliseconds() //毫秒 
      };
      if (/(y+)/.test(fmt)) fmt = fmt.replace(RegExp.$1, (this.getFullYear() + "").substr(4 - RegExp.$1.length));
      for (var k in o)
      if (new RegExp("(" + k + ")").test(fmt)) fmt = fmt.replace(RegExp.$1, (RegExp.$1.length == 1) ? (o[k]) : (("00" + o[k]).substr(("" + o[k]).length)));
      return fmt;
  } 
  
  //自定义日期显示格式
      var time1 = new Date().Format("yyyy-MM-dd");
      var time2 = new Date().Format("yyyy-MM-dd HH:mm:ss");
      document.write(time1+"  <br>   "+time2+"<br>");
  ```

* **Math**

* **RegExp** <font color='mediumseagreen'> 正则表达式对象</font> 

  * <font color='tomato'>**正则表达式：定义字符串的组成规则**</font> <font color='mediumseagreen'>	用于验证字符串是否符合规则</font> 
    * **单个字符**
      * [a] :a 
      * [ab] :a或者b
      * [a-zA-Z0-9_] :a-z || A-Z ||0-9 以及 _
      * 特殊符号 <font color='mediumseagreen'>相当于简写形式</font> 
        * \d：[0-9]
        * \w：[a-zA-Z0-9_] 
    * **量词符号**
      * ？：0或1次
      * *：0次或多次
      * +：1次或多次、
        * {m,n}：m<=数量<=n  <font color='mediumseagreen'>{9}：长度就是9</font>
        * {m,}：最少m次
        * {,n}：最多n次
    * **开始结束符号**
      * 开始：^
      * 结束：$

  ```html
  常用正则表达式：
  
  用户名：/^[a-z0-9_-]{3,16}$/
  密码：/^[a-z0-9_-]{6,18}$/
  十六进制值：/^#?([a-f0-9]{6}|[a-f0-9]{3})$/
  电子邮箱：/^([a-z0-9_\.-]+)@([\da-z\.-]+)\.([a-z\.]{2,6})$/
  URL：/^(https?:\/\/)?([\da-z\.-]+)\.([a-z\.]{2,6})([\/\w \.-]*)*\/?$/
  IP 地址：/^(?:(?:25[0-5]|2[0-4][0-9]|[01]?[0-9][0-9]?)\.){3}(?:25[0-5]|2[0-4][0-9]|[01]?[0-9][0-9]?)$/
  HTML 标签：/^<([a-z]+)([^<]+)*(?:>(.*)<\/\1>|\s+\/>)$/
  Unicode编码中的汉字范围：/^[u4e00-u9fa5],{0,}$/
  
    匹配中文字符的正则表达式： [\u4e00-\u9fa5]
  评注：匹配中文还真是个头疼的事，有了这个表达式就好办了
  
    匹配双字节字符(包括汉字在内)：[^\x00-\xff]
  评注：可以用来计算字符串的长度（一个双字节字符长度计2，ASCII字符计1）
  
    匹配空白行的正则表达式：\n\s*\r
  评注：可以用来删除空白行
  
    匹配HTML标记的正则表达式：<(\S*?)[^>]*>.*?</\1>|<.*? />
  评注：网上流传的版本太糟糕，上面这个也仅仅能匹配部分，对于复杂的嵌套标记依旧无能为力
  
    匹配首尾空白字符的正则表达式：^\s*|\s*$
  评注：可以用来删除行首行尾的空白字符(包括空格、制表符、换页符等等)，非常有用的表达式
  
    匹配Email地址的正则表达式：\w+([-+.]\w+)*@\w+([-.]\w+)*\.\w+([-.]\w+)*
  评注：表单验证时很实用
  
    匹配网址URL的正则表达式：[a-zA-z]+://[^\s]*
  评注：网上流传的版本功能很有限，上面这个基本可以满足需求
  
    匹配帐号是否合法(字母开头，允许5-16字节，允许字母数字下划线)：^[a-zA-Z][a-zA-Z0-9_]{4,15}$
  评注：表单验证时很实用
  
    匹配国内电话号码：\d{3}-\d{8}|\d{4}-\d{7}
  评注：匹配形式如 0511-4405222 或 021-87888822
  
    匹配腾讯QQ号：[1-9][0-9]{4,}
  评注：腾讯QQ号从10000开始
  
    匹配中国大陆邮政编码：[1-9]\d{5}(?!\d)
  评注：中国大陆邮政编码为6位数字
  
    匹配身份证：\d{15}|\d{18}
  评注：中国大陆的身份证为15位或18位
  
    匹配ip地址：\d+\.\d+\.\d+\.\d+
  评注：提取ip地址时有用
  
    匹配特定数字：
  ^[1-9]\d*$　 　 //匹配正整数
  ^-[1-9]\d*$ 　 //匹配负整数
  ^-?[1-9]\d*$　　 //匹配整数
  ^[1-9]\d*|0$　 //匹配非负整数（正整数 + 0）
  ^-[1-9]\d*|0$　　 //匹配非正整数（负整数 + 0）
  ^[1-9]\d*\.\d*|0\.\d*[1-9]\d*$　　 //匹配正浮点数
  ^-([1-9]\d*\.\d*|0\.\d*[1-9]\d*)$　 //匹配负浮点数
  ^-?([1-9]\d*\.\d*|0\.\d*[1-9]\d*|0?\.0+|0)$　 //匹配浮点数
  ^[1-9]\d*\.\d*|0\.\d*[1-9]\d*|0?\.0+|0$　　 //匹配非负浮点数（正浮点数 + 0）
  ^(-([1-9]\d*\.\d*|0\.\d*[1-9]\d*))|0?\.0+|0$　　//匹配非正浮点数（负浮点数 + 0）
  评注：处理大量数据时有用，具体应用时注意修正
  
    匹配特定字符串：
  ^[A-Za-z]+$　　//匹配由26个英文字母组成的字符串
  ^[A-Z]+$　　//匹配由26个英文字母的大写组成的字符串
  ^[a-z]+$　　//匹配由26个英文字母的小写组成的字符串
  ^[A-Za-z0-9]+$　　//匹配由数字和26个英文字母组成的字符串
  ^\w+$　　//匹配由数字、26个英文字母或者下划线组成的字符串
  ```
  
  * **RegExp对象的创建以及test()方法的使用**
  
    ```javascript
    var reg =/^[a-z0-9_-]{3,16}$/  /*创建正则表达式对象的常用格式*/
    
    var flag =reg.test("zhangsan");
    ```
  
* **Global**

  * **特点：**全局对象，无需对象就可以直接用方法名调用；  <font color='mediumseagreen'>所以这个对象名常常处于隐形状态</font>
  * **方法：**
    * encodeURI( ):URL编码  <font color='mediumseagreen'>编码就是将GBK/UTF-8转换成十六进制码的形式（比如一个GBK汉字是两个字节，一个字节是8位二进制码，所以一个汉字是16个二进制码（4*4），就可以将其转换成16进制）</font> 
    * decodeURL( ):URL解码
    * encodeURLcomponent( )；
    * decodeURLcomponent( ):
    * parseInt( ):会将包含数字的字符串转成数字 <font color='mediumseagreen'>判断每一个字符是否为数字，直到不是数字为止，将前边部分转成number</font> 
    * isNaN( )：判断一个值是不是NaN
    * eval( )：将字符串直接转换成脚本语言运行
  
* **Json**

  * 将对象转成json格式字符串：let str =JSON.stringify(weather); //这里weather是json对象
  * 将json格式字符串转成对象：let weather2 = JSON.parse(str); //又转回来了

### 2.5 DOM

* **概念**：Document Object Model 文档对象模型，允许程序和脚本动态访问和更新文档的内容、结构、样式。 **将文本转换成对象**

* **对象种类：**
  * **Document：文档对象**

    * 在html中可以通过window对象来创建document对象

    * **方法**：

      * **1.获取element对象** <font color='tomato'>重要</font>
        *  getElementById()：根据对象定义的id来创建元素对象
        *  getElementsByTagName()：根据元素名称（如div、a）获取元素对象们。<font color='tomato'>返回值是对象数组</font> 
        
        *  getElementsByClassName()：根据Class属性值获取元素对象数组  <font color='tomato'>比如div里面的class</font> 
        *  getElementsByName()：根据Name属性来获取元素对象数组
        
      * **2.创建其他DOM对象的方法**
        * createElement(...)：创建element元素对象
  * **Element：属性对象**

    * 创建对象：通过document来创建
    * **方法**： <font color='mediumseagreen'>属性方法</font> 
      * setAttribute(属性名，属性值)：设置属性 <font color='mediumseagreen'>参数值：属性种类名称，属性内容</font> 
      * getRemove(属性名)
      * removeAttribute(属性名)：删除属性
  * **Text：文本对象**
    * innerText()：纯文本
    * innerHtml()：带标签的文本
  * Comment：注释对象
  * **Node：节点对象** <font color='tomato'>  是其他5个的父对象，所有的DOM对象都可看作是一个节点</font> 
    * 方法：<font color='mediumseagreen'>对节点进行增删改查</font>
      *  appendChild(子元素)
      *  removeChild(子元素)
      *  replaceChild(新元素，旧元素)
      *  getChild()：获取 

==**练习：创建可增加删除表格**==

```html
!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <title>动态表格</title>

    <style>
        table{
            border: 1px solid;
            margin: auto;
            width: 500px;
        }

        td,th{
            text-align: center;
            border: 1px solid;
        }
        div{
            text-align: center;
            margin: 50px;
        }
    </style>

</head>
<body>

<div>
    <input type="text" id="name" placeholder="请输入姓名" autocomplete="off">
    <input type="text" id="age"  placeholder="请输入年龄" autocomplete="off">
    <input type="text" id="gender"  placeholder="请输入性别" autocomplete="off">
    <input type="button" value="添加" id="add">
</div>

    <table id="tb">
        <caption>学生信息表</caption>
        <tr>
            <th>姓名</th>
            <th>年龄</th>
            <th>性别</th>
            <th>操作</th>
        </tr>

        <tr>
            <td>张三</td>
            <td>23</td>
            <td>男</td>
            <td><a href="JavaScript:void(0);" onclick="drop(this)">删除</a></td>
        </tr>

        <tr>
            <td>李四</td>
            <td>24</td>
            <td>男</td>
            <td><a href="JavaScript:void(0);" onclick="drop(this)">删除</a></td>
        </tr>

    </table>

</body>
<script>
    document.getElementById("add").onclick=function(){
            let tr =document.createElement("tr");//创建“行”
            let nameTd=document.createElement("td");//创建“个”
            let ageTd=document.createElement("td");
            let genderTd=document.createElement("td");
            let deleteTd=document.createElement("td");

            tr.appendChild(nameTd);//将四个“个”添加到“行”
            tr.appendChild(ageTd);
            tr.appendChild(genderTd);
            tr.appendChild(deleteTd);

            let name=document.getElementById("name").value;//这里只是获取dom对象，并非文本
            let age=document.getElementById("age").value;
            let gender=document.getElementById("gender").value;
            //获取文本元素
            let nameText=document.createTextNode(name);
            let ageText=document.createTextNode(age);
            let genderText=document.createTextNode(gender);

            //将3个单纯文本添加到“个”
            nameTd.appendChild(nameText);
            ageTd.appendChild(ageText);
            genderTd.appendChild(genderText);

           //单独处理deleteTd

           let a=document.createElement("a");//获取所有的a元素dom对象
            let aText= document.createTextNode("删除");//创建文本对象“删除”,让它可以被append
            
           
            a.setAttribute("href","JavaScript:void(0);");//设置属性防止跳转
            a.setAttribute("onclick","drop(this)"); //给超链接对象设置单击属性，单击之后就调用drop方法
            a.appendChild(aText);//将”删除“文本对象添加到deleteTd这个"个"，和前3个一样,不过这个是给超链接添加
            deleteTd.appendChild(a); //最后再将删除的超链接a添加到deleteTd“个”
            

            //将tr“行”添加到table“表”
            let table =document.getElementById("tb");
            table.appendChild(tr);
    }
    

            //单独定义drop方法，注意这个方法不能在在上一个方法内部
            function drop(obj){
                let table = obj.parentElement.parentElement.parentElement; //获取"表"
                let tr = obj.parentElement.parentElement;//获取“行”
                table.removeChild(tr); //调用"表“的方法来删除“行”
          }
         
</script>

</html>
```

### 2.6 BOM

* **概念**：Browser Object Model 浏览器对象模型，将浏览器的各个组成部分封装成对象。

* **本窗口对象Window**：包含历史记录、包含地址栏、包含DOM对象 <font color='tomato'>widow对象是最重要的</font> 

  * **创建**

  * **方法**

    * **弹出框类**：

      * alert()：警告框
      * confirm()：确认、取消退出框（可以进行提醒用户防止误操作）<font color='mediumseagreen'>可以将confirm方法返回flag（true/false）对象进行操作判断</font>
      * prompt() ：弹出输出框，参数是输入框上面的提示，返回的对象是输入的内容

    * **窗口开闭类**

      * open()：打开新的窗口，参数可以输入要打开窗口的地址，并且此方法可以返回一个新的window对象 <font color='tomato'>	新的window对象可以调用close方法将页面进行关闭</font> 
      * close()：直接关闭当前页面（当前的window） <font color='mediumseagreen'>想要关闭其他页面的话就将其他页面的open方法返回一个window对象，再用window对象调用close()方法</font> 

    * **定时器类**

      * 一次性定时器

        * setTimeout(...; 1000)：在1秒钟之后，执行代码片段... ，返回唯一标识，用于取消定时器

      * 循环定时器

        * setInterval(...,1000)：每隔一秒就执行一次代码

        ```javascript
        <%@ page contentType="text/html;charset=UTF-8" language="java" %>
        <html>
        <head>
            <title>$Title$</title>
        
        </head>
        <body>
        <img src="0.png" id="tupian">
        <script>
            var number=1;
            function f(){
                number++;
                if(number>3){
                    number=1
                }
                var elementByIdt = document.getElementById("tupian");
                elementByIdt.src=number+"0.png"; /*实现放置好了图片1、2、3.png四张*/
            }
            setInterval(f,1000);/*每隔1秒就调用一次f方法*/
        </script>
        </body>
        </html>
        ```

      * 取消定时器

        * clearTimeOut() 、clearInterval() ：取消定时器，参数是设置定时器的返回值
      
    * **加载事件类**：

      * window.onLoad()：页面加载完之后执行方法

  * **属性**

    * 通过window对象获取其他BOM对象（和JSP的PageContext对象效果很像）因为window.可以直接省略，所以直接写其他对象名称就行
    * 获取DOM对象
      * <font color='tomato'>document对象其实是用window.document创建出来的</font>

  * **特点**

    * 直接window.方法名使用方法，无需创建对象。<font color='mediumseagreen'>window. 也是可以省略的</font> 

* **地址栏对象Location**

  * 方法 
    * reload()：刷新页面
  * 属性
    * href：设置/获取完整的URL路径 <font color='mediumseagreen'>所以这个属性既可以用于获取地址、也可以将当前页面跳转成新的地址页面</font> 

* 浏览器历史记录对象History 

* 显示器屏幕对象Screen

* 浏览器对象Navigator

==**练习：设置自动倒计时5秒跳转页面到百度**==

```javascript
 <%@ page contentType="text/html;charset=UTF-8" language="java" %>
<html>
<head>
    <title>$Title$</title>
    <style>
        p {
            text-align: center;
        }
        span {
            color: red;
        }
    </style>
</head>
<body>
<script>

    //创建方法：包括数字减少、将数字输出至页面
    //调用方法，设置一秒调用一次

    var time =5;

    function f(){
        time--;
        if(time<=0){
            location.href="https://www.baidu.com"; //地址栏直接跳转
        }
        var elementById = document.getElementById("time");

        elementById.innerHTML=time;
    }

    setInterval(f,1000);
</script>
<P>
    <span id="time">5</span>秒钟后跳转此页面
</P>
</body>
</html>
```

### 2.7 事件

* **功能**：某些组件被执行某些操作之后，触发某些代码的执行。

* **使用步骤**

  * onlick <font color='mediumseagreen'>目前最重要的</font>

  ```javascript
  <img src="1.png" id="tupian"> <%--设置图片--%>
  
  <script> /*在JS里面*/
      
  function f(){
      alert("点击成功")
  }/*创建函数*/
  
  var x =document.getElementById("tupian"); /*根据ID创建对象元素*/
  
  x.onclick=f; /*将单击事件和函数相关联*/
  
  </script>
  
  <%--使用JS设置点击图片跳出页面提示的效果--%>
  ```

## 3. MySql

### 3.1 概述

* SQL:Structured Query Language：结构化查询语言

### 3.2 SQL语句的具体分类

#### 3.2.1DDL

* *SQL的分类：数据库---->表---->具体数据*

* **<u>DDL（操作数据库、表）</u>**

  * ==操作数据库、表==

    * C(create)：创建 <font color='mediumseagreen'>使用库</font> 

      ```mysql
       create database if not exists yyy character set GBK;
       use yyy; -- 使用库
       create table yyy(
         ...
         ...
       ); -- 创建表格
      ```

    * R(retrieve)：查询

      ```mysql
      show databases ; 
      show create database yyy; -- 这个是查看数据库字符集
      select database(); -- 查询当前的数据库
      ```

    * U(update)：修改

      ```mysql
      alter database yyy character set utf8;
      
      alter table test rename to test1;-- 将表格rename
      alter table test1 add column xxx varchar(10);-- 给表格多添加一列
      alter table test1 change xxx yyy varchar(10); -- 将表中的一列更改名称以及类型
      ```

    * D(delete)：删除

      ```mysql
      drop database if exists yyy; -- 如果是删除视图的话，就是将database修改成view即可
      ```

#### 3.2.2 DML

* **<u>DML（增删改表中的数据）</u>**

  * ==添加数据==
    * insert into 表名（列名1，列名2...）values(值1，值2...)
    * 除了数字类型，其他都要用" "
  * ==删除数据==
    * delete from 表名 where 条件//delete from stu where id=1;（如果没有加条件就删除了表里面所有记录）
    * TRUNCATE TABLE stu;//删除stu并且创建一个空的stu 
  * ==修改数据==
    * UPDATE stu SET name="张大三" where id =1;//注意where条件一定要加，不然 就会把所有的数据全部更改

#### 3.2.3 DQL

* **<u>DQL（查询表中数据）</u>**

  * **基本顺序：**<font color='mediumseagreen'>**select** 字段 	**from** 表名 	**where**条件列表 	**group by**分组字段 	**having**分组后的过滤条件 	**order by** 排序 	**limit** 分页</font> 

  * ==基础查询==

    ```mysql
     select * from stu; -- 查看stu里面所有的元素
     SELECT DISTINCT name from stu; -- 查看去重之后的stu的name数据
     SELECT id, secore   IFNULL(secore1, 0)  as 总分 FROM stu; -- 将null替换掉，并且用as起别名：总分
     select * from stu where secore between 0 and 100; -- 范围查询
     select * from stu where secore =80 or secore=90; -- or查询
     Select * from stu where secore is null; -- 注意null要用is去判断而不是= （is not null） (所以判断的时候不但要判断是'',还要 not null)
     ---------like模糊查询--------------
     Select * from phone  where name like '小米%'; -- 模糊查询，以'小米'开头
     Select * from phone  where name like '_为%'; -- '为'是第二个字的名称
     Select * from phone where name like '%电脑%'; -- 名称中包含'电脑'
     Select * from phone  where name like '____'; -- 长度为4的名称 
    ```

  * ==排序查询==

    ```mysql
    select from stu order by secore DESC/ASC,secore1 ASC ; -- 如果secore一样，看secore1进行排序。 排序就是升序（默认）/降序
    ```

  * ==聚合函数：纵向计算==

    ```mysql
    * count（算个数，可以用IFNULL) :select count(IFNULL(name, 0))from stu;
    * select MAX/SUM/AVG(secore) from stu;
    ```

  * ==分组查询==

    ```mysql
    * select sexual, avg(secore) from stu group BY sexual; -- 注意是分组的字段/聚合函数（注意group by 后面的字段和select后面的第一个字段一致） 
    * select sexual ,avg(secore) ,count(id) from stu where secore>50 group by sexual having count(id)>1; -- 用上了*having*进行筛选 （having是分组之后再次进行筛选）
    -- 注意：分组查询也能去除重复
    ```

  <font color='cornflowerblue'>（面试题）where/having区别：</font>

  ​	<font color='cornflowerblue'>where在分组之前限定，having在分组之后限定</font>

  ​	<font color='cornflowerblue'>where 之后不能跟聚合函数，having 可以进行聚合函数判断</font>

  * ==分页查询==（“方言”，不同数据库有不同的分页查询方式）

    ```mysql
    * select*from stu limit 0,2; -- 0是索引值，2是每页显示的条数；当前的第一页
    * 此处有重要公式：索引值 =（ 想要得到的当前页码-1）*每页显示的条数
    ```

* **<u>DCL（授权）</u>**

  * 定义数据库访问权限和用户级别

### 3.3 约束

* **<u>约束</u>** ：对表中的数据进行限定，保证数据的正确有效完整。

  * **非空约束：not null**

    ```mysql
    create table persons(id int,name varchar(20) not null);
    alter table person modify name varchar(20); -- 去除非空约束。（想要再改成非空约束就在后面添加 not null）
    ```

  * **唯一约束：unique** 

    ```mysql
    create table Employee ( id int,phone_number varchar(20) unique);  -- 不允许phone_number的值重复
    ```

  * **主键约束：primary key：唯一标记**

    * 含义：非空且唯一
    * 一张表只有一个字端是主键
    * 如果添加一个元素之后又将其删除，再添加元素，主键跳过一次。（不会使用已经被删除的那个元素的主键）

    ```mysql
    * create table stu1(
    id int primary key auto_increment,name varchar(20));
    
    * alter table stu1 drop primary key; -- 去除主键特性
    
    * alter table stu1 modify id int primary key; -- 在表创建之后再添加主键特性
    ```

  * **外键约束：foreign key**：让表和表产生关系并且保证数据正确性

    ```mysql
    create table department(
     	id int  primary key auto_increment,
     	depname varchar(20),
     	depaddress varchar(20)
     	);  -- 这个是约束表格
    insert into department values(null,"销售部","北京"),(null,"研发部","大连");
    
    create table employee( 
    	id int primary key auto_increment ,
     	name varchar(20),
     	age int,
     	dep_id int,
     	constraint emp_dep foreign key (dep_id) references department(id)
     	); -- 本质上这个是被约束的表格，被department表格的主键所约束，（必须是主键）
     	insert into employee(name,age,dep_id) values("tom",22,2),("jack",20,1),("mary",19,2); --添加元素
     	
     	alter table employee2 add constraint emp_d foreign key (id) references department(id); -- 在创建表格之后添加外键约束
     	
     alter table employee drop foreign key emp_dep; -- 删除外键约束
     
     -- 老师上课的推荐命名外键的方式：de_fk1 （两个表格的首字母拼接_fk数字）
    ```

    * **级联操作 : casecade**更改被关联的表格的数据，关联表格的与之绑定的数据也随之改变（联动） <font color='mediumseagreen'>真实开发中很少使用</font>

    ```mysql
    * alter table employee add constraint emp_depp foreign key (dep_id) references department(id) on update / delete cascade; -- 级联更新/删除
    ```

### 3.4 数据库设计思想

* 表与表之间的关系：

  * ==**一对一**==
  * ==**一对多**==

  <img src="/Users/yuchenxi/Documents/《ycx-JavaWeb学习笔记》配图/截屏2021-07-01 下午8.29.00.png" alt="截屏2021-07-01 下午8.29.00" style="zoom:30%;" />

  * ==**多对多**==

    *多对多需要中间表格*：至少包含两个字段（前两张表的主键），作为第中间表的外键

    ![截屏2021-07-01 下午8.32.43](/Users/yuchenxi/Documents/《ycx-JavaWeb学习笔记》配图/截屏2021-07-01 下午8.32.43.png)

* 表与表之间的关系练习：

```sql
create table category(
		cid int primary key auto_increment,
		cname varchar(100) not null unique
); -- 创建旅游路程的大区目录

create table route(
 		rid int primary key auto_increment, -- 唯一主键
 		rname varchar(100) not null unique,
 		price double,
 		rdate date,
 		cid int, -- 外键
 		constraint rr foreign key (cid) references category (cid)
);

create table user (
		uid int primary key auto_increment,
		username varchar(100) not null unique,
		password varchar(30) not null,
		name varchar(100),
		birthday date,
		sex char(1) default '男',
		telephone varchar(11),
		email varchar(100)
);

create table favorite(
		rid int,
		uid int,
		primary key(rid,uid), -- 联合主键
		foreign key (rid) references route(rid),
		foreign key (uid) references user (uid)
);
-- category一对多route、route多对多user,通过第三方favorite连接 
```

### 3.5 范式

* **第一范式（1NF）：每一列都是具有原子性的，不可分割**
* **第二范式（2NF）：非主属性必需完全依赖主属性**
  * *函数依赖： 学号-->学生 ，*
  * *完全函数依赖：如果A是一个属性组，那么B属性值的确定需要依赖A属性组中**所有**的属性值：（学号，课程名）-->分数*
  * *部分函数依赖：如果A是一个属性组，那么B属性值的确定需要依赖A属性组中**部分**的属性值：（学号，课程名）-->姓名    （姓名只需要学号即可确定）*
  * *传递函数依赖：A-->B-->C   ：学号-->系名，系名-->系主任*
  * *==码==：如果一个表中，一个属性/属性组完全被其他所有属性依赖（通过该属性/属性组可以得到其他所有值），那么该属性/属性组称为该表的码（学号，课程名称是本例的码）*
    * *主属性：码属性组中的所有属性*
    * *非主属性：除了码属性组的其他属性*
* **第三范式（3NF）：在（2NF）的基础上，消除传递依赖**

<img src="/Users/yuchenxi/Documents/《ycx-JavaWeb学习笔记》配图/截屏2021-07-01 下午8.24.55.png" alt="截屏2021-07-01 下午8.24.55" style="zoom:50%;" />

如上图所示：（学号，课程名称）是选课表的码，分数完全依赖此属性组；学号是学生表的码；系名是系表的码

### 3.6 多表查询

* 多表查询产生笛卡尔积，要消除无用的笛卡尔积。 <font color='mediumseagreen'>多表只有查询操作，没有更改操作</font>

  ```sql
  create table dept(
  		id int primary key auto_increment,
  		name varchar(20)
  );
  insert into dept(name) values('推广部'),('物流部'),('财务部');
  create table emp(
  		id int primary key auto_increment,
  		name varchar(10),
  		sex char(1) default '男',
  		salary double,
  		join_date date,
  		dept_id int,
  		foreign key (dept_id) references dept(id)
   );
   
   insert into emp(name,sex,salary,join_date,dept_id) values ("小明",'男',5000,'2019-11-11',1);
   insert into emp(name,sex,salary,join_date,dept_id) values ("小张",'男',4000,'2018-01-11',3);
   insert into emp(name,sex,salary,join_date,dept_id) values ("小花",'女',2000,'2019-02-14',2);
   insert into emp(name,sex,salary,join_date,dept_id) values ("小红",'女',3000,'2018-05-09',1);
   insert into emp(name,sex,salary,join_date,dept_id) values ("小黄",'男',5400,'2020-02-24',1);
   
   select * from emp,dept; -- 笛卡尔积 （3*5=15条数据）
  ```

  * **==内链接==查询** ：其实就是求两个表交集部分

    * 隐式内链接

      ```sql
      select 
        t1.name,t1.sex,t2.name,t2.id
       from
        emp t1,dept t2
       where 
        t1.dept_id=t2.id;  -- 标准书写格式 条件可以接上and
      ```

    * 显示内链接 <font color='mediumseagreen'>几乎不用</font> 

      ```sql
      select*from 
      	emp t1
      join 
      	dept t2
      on 
      	t1.dept_id = t2.id;  -- 查询全部信息
      ----------------------------------------	
      select 
      	t1.name,t2.name
      from
        	emp t1
      join
      		dept t2
      on 
      	t1.dept_id=t2.id; -- 查询部分信息
      ```

  * **==外链接==查询**

    * 左外链接：左边表的所有部分+右表的交集部分

      ```sql
      select
      	t1.*,t2.name
      from
      	emp t1 -- 这个是左边的表格
      left join
      	dept t2 
      on
      	t1.dept_id =t2.id;
      ```

    * 右外链接：左表的交集部分+右表的所有部分

      ```sql
      select
      	t1.*,t2.name 
      from
      	emp t1 
      right join -- 如果两个表格颠倒（from dept t2 right emp t1），结果就和左外链接结果一致
      	dept t2 -- 这个是右边的表格
      on
      	t1.dept_id =t2.id;
      ```

  * **==子==查询**

    * 当条件为一个数的时候：where  =

    ```sql
      select*from
      	emp 
      where 
      	emp.salary =(select max(salary) from emp); -- 查询salary最高的那个员工的信息。（）里面的是子查询，可以=,<,>
    ```

    * 当条件为多个数的时候：where  in（可能也会用到not in）

    ```sql
      select * from 
      	emp 
      where 
      	dept_id in (select id from dept where name ='推广部' or name ='物流部' );  -- 查询部门中的推广部和物流部的人的信息。子查询可以作为一个查询条件,用in
    ```

    * 查询结果为二维数据时：虚拟表

    ```sql
      select * from 
      	dept t1 , (select * from emp where emp.join_date >'2018-12-12')  t2 
      where
      	t1.id = t2.dept_id; -- 子查询的结果可以作为一张虚拟表，进行二次查询 
    ```

  * **自关联映射**

    * 自己和自己有关联性：每个员工都有自己的id，也有自己的领导（领导也是员工，也有自己的id，也有自己的领导）

    ```sql
    select
      e1.*,
    	e2.name
    from 
      employee e1,
      employee e2
    where 
    	e1.mgr = e2.id 
    ```

==练习：==

```sql
create table dept(
		id int primary key primary key,
		dname varchar(50),
		loc varchar(50)
);
     
insert into dept(id ,dname,loc ) values(10,'推广部','南京'),(20,'物流部','上海'),(30,'财务部','北京'),(40,'法务部','广州');


create table job(
	id int primary key,
	jname varchar(50),
	description varchar (50)
);
  
insert into job (id,jname,description) values (1,'董事长','管理公司'),(2,'总经理','管理员工'),(3,'销售','推广产品'),(4,'文员','使用办公用品');

create table emp(
		id int primary key,
		name varchar(20),
		job_id int,
		mgr int,
		joindate date,
		salary double,
		bonus double,
		dept_id int,
		foreign key (dept_id) references dept(id),
		foreign key (job_id) references job(id)
);

insert into emp(id,name,job_id,mgr,joindate,salary,bonus,dept_id) values(1001,'miaochanwen',1,null,'1995-1-1',99999,99999,10),(1002,'maoliangxi',2,1001,'1995-1-1',66666,66666,10),
(1003,'shilei',3,1002,'2009-1-1',22222,22222,10),
(1004,'guling',4,1002,'2010-1-1',22222,11111,30),
(1005,'wangzhonghua',4,1002,'2004-1-1',12222,12222,20);
insert into emp(id,name,job_id,mgr,joindate,salary,bonus,dept_id) values(1006,'xiaozhang',4,1004,'2018-1-1',9999,0,30);


  create table salarygrade(
  		grade int primary key,
  		losalary int,
  		hisalary int
);

insert into salarygrade(grade,losalary,hisalary) values(1,10000,30000),(2,30000,50000),(3,50000,10000);
  
  -- 1：查询所有员工信息。员工编号，姓名，工资，职务名称，职务描述
  
  select 
  		t1.id,
  		t1.name,
  		t1.salary,
  		t2.jname,
  		t2.description
  from 
  		emp t1,job t2
  where
   		t1.job_id=t2.id; -- 因为已经设置外键约束
   
   -- 2：查询员工编号，姓名，工资，职务名称，职务描述，部门名称，部门位置
  
 select 
  		t1.id,
  		t1.name,
  		t1.salary,
  		t2.jname,
  		t2.description,
  		t3.dname,
  		t3.loc
  from 
  		emp t1,job t2,dept t3
  where 
   	t1.job_id=t2.id and t1.dept_id=t3.id; -- 注意此处用and连接两个条件
   	
   	-- 3：查询员工姓名，工资，工资等级
select  
   	t1.name,t1.salary,t2.grade
from
   	emp t1,salarygrade t2
where
   	t1.salary BETWEEN t2.losalary and t2.hisalary; 	 -- 用between and
   	
   	
   	-- 4 ：查询员工编号，姓名，工资，职务名称，职务描述，部门名称，部门位置，工资等级
   	
select
	t1.id,
	t1.name,
	t1.salary,
	t2.jname,
	t2.description,
	t3.dname,
	t3.loc,
	t4.grade
from
	emp t1,
	job t2,
	dept t3,
	salarygrade t4
where
	t1.job_id =t2.id 
	and t1.dept_id=t3.id
	and 	t1.salary BETWEEN t4.losalary and t4.hisalary;  -- 这里的where让表格全部产生关联
	
	-- 5：查询部门编号，部门名称，部门位置，部门人数

select 
	dept_id,COUNT(id)
from
	emp
group BY
	dept_id;   -- 通过聚合函数计算出人数，并且把这个作为虚拟表
	
	
	select 
	t1.id,
	t1.dname,
	t1.loc,
	t2.total
	
	from
	dept t1,
	(select dept_id,COUNT(id) total from emp group BY dept_id) t2 -- 注意（）里面不能有;
	
	where 
	t1.id=t2.dept_id;
	
	-- 6 查询所有员工以及其直接上级的姓名，没有领导的也要查询
	
	SELECT
	t1.mgr,
	t1.name,
	t2.name
	from 
	emp t1,emp t2  -- 关键步骤，将同一张表取两个名字(自关联映射)
	where
	t1.mgr=t2.id ;
	
	SELECT
	t1.mgr,
	t1.name,
	t2.name
	FROM
	emp t1
	left join 
	emp t2 
	on
	 t1.mgr=t2.id;  -- 左外链接，将null也取值到，注意格式
```

* **视图**

  * **概念：**将多表查询结果封装到一个单表，可以简化相关操作。也可以将敏感信息列隐藏，提高安全性。

  * **创建方法：**

    ```sql
    create view cc (a1,a2,a3) as   -- cc是视图名称，a1 a2 a3是新建视图的列名（格式也很见名知意：直接将查询结果create view ... as。）
    select
    	c1.id,
    	c2.name,
    	c2.name
    from
    	city c1,
    	country c2
    where
    	c1.cid=c2.cid;
    	
    -- 视图是可以改变数据的
    ```

* <font color='lightgrey'>基于这样的原因 :1.良好的学习习惯 自觉 潜移默化的影响 学习习惯 2.精神面貌
  良好的人生和职业规划 3.精通一门语言；精通参与开发架构oa、电商系统这两个系统
  上游生产 销售 下层 
  知识面的广度。4.求知的欲望，把资源利用好，主动出击；5.积极主动人情事故</font> 

**==练习：MySql课后练习题==**

```sql
CREATE TABLE `students` (
  `id` int PRIMARY KEY AUTO_INCREMENT,
  `name` varchar(30),
  `age` int DEFAULT NULL,
  `sex` varchar(10),
  `cid` int
);

insert  into `students`(`id`,`name`,`age`,`sex`,`cid`) values (1,'孙悟空',11,'男',1),(2,'牛魔王',23,'男',1),(3,'铁杉公主',23,'女',1),(4,'玉皇大帝',16,'男',1),(5,'猪八戒',25,'男',1),(6,'沙和尚',73,'男',1),(7,'林冲',15,'男',2),(8,'鲁智深',35,'男',2),(9,'孙二娘',26,'女',2),(10,'燕子张',23,'男',2),(11,'刘备',45,'男',3),(12,'曹操',46,'男',3),(13,'孙权',24,'男',3),(14,'张三',2666,NULL,NULL),(15,'李四',NULL,NULL,1);

select * from students;

CREATE TABLE `classes` (
  `id` int PRIMARY KEY AUTO_INCREMENT,
  `NAME` varchar(30)
);

insert  into `classes`(`id`,`NAME`) values (1,'西游班'),(2,'梁山班'),(3,'三国班');

CREATE TABLE `course` (
  `id` int PRIMARY KEY AUTO_INCREMENT,
  `NAME` varchar(30),
  `tid` int
);

insert  into `course`(`id`,`NAME`,`tid`) values (1,'降妖除魔课',1),(2,'侠义课',2),(3,'建国立业课',3),(4,'划水课',NULL),(5,'三国草稿课',3);

CREATE TABLE `teacher` (
  `id` int PRIMARY KEY AUTO_INCREMENT,
  `NAME` varchar(30),
  `age` int
);

insert  into `teacher`(`id`,`NAME`,`age`) values (1,'吴承恩',40),(2,'施耐庵',50),(3,'罗贯中',40);

CREATE TABLE `grade` (
  `id` int PRIMARY KEY AUTO_INCREMENT,
  `cid` int,
  `sid` int,
  `score` int
);

insert  into `grade`(`id`,`cid`,`sid`,`score`) values (1,1,1,80),(2,1,2,81),(3,1,3,80),(4,1,4,81),(5,1,5,80),(6,1,6,52),(7,1,7,81),(8,1,8,25),(9,1,9,81),(10,1,10,81),(11,1,11,445),(12,2,13,81),(13,2,12,212),(14,2,11,15),(15,2,10,15),(16,2,9,81),(17,2,8,25),(18,2,7,46),(19,2,6,34),(20,2,5,81),(21,3,13,155),(22,3,12,177),(23,3,11,199);


alter table students add CONSTRAINT sc_fk1 foreign key (cid) REFERENCES classes(id);  -- students和classes的外键约束

alter table course add CONSTRAINT ct_fk2 foreign key (tid) REFERENCES teacher(id);

alter table grade add constraint gsc_fk3 foreign key (cid) REFERENCES course(id);

alter table grade add constraint gsc_fk4 foreign key (sid) REFERENCES students(id);


-- 1. 查询学生的ID、姓名、年龄、班级名称。

select 
s.id,s.name,s.age,c.name

from 
students s , classes c

where
s.cid=c.id;

-- 2. 查询所有的学生。展示学生的ID、姓名、年龄、班级名称。(要将无班级的张三展示出来，用左外链接)  

select 
s.id,s.name,s.age,c.name
from
students s
left join
classes c
on 
s.cid=c.id;

-- 3. 查询所有的课程。展示这门课程的老师姓名、课程名称。

select
c.name,t.name
FROM
course c
left join
teacher t
ON
c.tid=t.id;

-- 4. 查询所有学生的信息。显示学生ID、姓名、年龄、所选课程名称。

SELECT
s.id,s.name,s.age,c.name
FROM
grade g,
students s,
course c
where
g.cid=c.id and g.sid=s.id;

-- 5. 查询刘备信息。显示ID、姓名、年龄、所选课程名字、分数。

SELECT
s.id,s.name,s.age,c.name,g.score
FROM
grade g,
students s,
course c
where
g.cid=c.id and g.sid=s.id and s.name='刘备';


-- 6. 查询建国立业课程。显示选这门课程的所有学生姓名和成绩。

select
s.name,g.score,c.NAME
from 
course c,
students s,
grade g
where
c.id=g.cid and s.id=g.sid and c.name='建国立业课';


   -- 7. 查询选罗贯中老师课程。展示罗贯中、学生姓名、课程名称、分数。

select
t.name,s.name,c.NAME,g.score
from 
course c,
students s,
grade g,
teacher t
where
c.id=g.cid and s.id=g.sid and t.name='罗贯中';

   -- 8. 查询西游班所有学生的成绩。展示班级名称、学生信息、课程名称、分数。
  
select
cl.name,s.id,s.name,s.age,s.sex,c.NAME,g.score
from 
course c,
classes cl,
students s,
grade g
where
cl.name='西游班' and c.id=g.cid and s.id=g.sid and s.cid=cl.id ; -- 此处要将‘西游记’放在最前面
   

   -- 9.在8问题基础上：西游班有一个休学的李四就没有他的信息，我也要展示怎么解决呢？
   /*在原有基础上分析：
   	展示所有学生所以班级右连接上学生，
   	我要展示所有学生，然后去查分数，所以学生左连接上分数
   	我要全部展示选的课，所以右连接上课程表（经过前面的筛选，这里左右连接对结果没影响）*/


SELECT 
	cla.name,c.name,g.score,s.name
FROM
	 classes cla
RIGHT JOIN -- 还是以学生为全部，获取添加了班级的信息，单独筛选出西游班的。
	(
	students s
	left join -- 学生与最小表格虚拟表（有课程和学分）是一对多关系。以学生为全部，获取包括课程的其他信息（没上课的学生其他信息就是null）。作为中间表格
		(
			grade g
			right join -- 课程与学分是一对多的关系，最里面的表格是以课程为全部获取信息
			course c
			on 
			g.cid=c.id
		)
	on s.id = g.sid
	)
	ON cla.id = s.cid
WHERE cla.name = '西游班'; 




 -- 10.将第8题查询语句创建视图stu
 
 create view a(c1,c2,c3,c4,c5,c6,c7) as
 select
cl.name,s.id,s.name,s.age,s.sex,c.NAME,g.score
from 
course c,
classes cl,
students s,
grade g
where
cl.name='西游班' and c.id=g.cid and s.id=g.sid and s.cid=cl.id ; 
```

### 3.7 事务

#### 3.7.1事务的概念以及操作

* 概念：被事务管理的操作，要么同时成功，要么同时失败

* 步骤：

  * 设置事务 start transaction

  * 回滚 roolback

  * 提交 commit

  * select @@autocommit;  -- 1 是自动提交的，0 是手动提交

    set @@autocommit = 1;

#### 3.7.2 事务的四大特征（ACID）

<font color='cornflowerblue'>（面试题）事务的四大特性</font>

* **Atomicity原子性**
  * 要么事务所有操作全部成功要么全部失败
* **consistency一致性**
  * 一个事务执行之前和执行之后的状态都是一致的（比如转账前后的金额总数是一致的）
* **isolcation隔离性**
  * 多个用户并发访问数据库的时候，事务之间相互隔离不干扰 
* **durability持久性**
  * **事务一旦提交**，对数据的更改是永久的（将数据保存在硬盘上永久存储）

#### 3.7.3 事务的隔离级别

* **四种隔离级别**  <font color='mediumseagreen'>串行化相当于加锁，单线程，效率低</font> 

| 序号 | 隔离级别 |      英文名      |                     产生的问题                     |
| :--: | :------: | :--------------: | :------------------------------------------------: |
|  1   | 读未提交 | read uncommitted |               脏读、不可重复读、幻读               |
|  2   | 读已提交 |  read committed  |                  不可重复读、幻读                  |
|  3   | 可重复读 |  repeated read   |                        幻读                        |
|  4   |  串行化  |   serializable   | 无（当前事务没有提交的话，别的事务都操作不了数据） |

* **三种问题状态以及产生的现象**

|    问题    | 现象                                                         |
| :--------: | :----------------------------------------------------------- |
|    脏读    | 在一个事务的处理过程中读取到了**另一个未提交事务中的数据**，导致前后两次查询结果不一致（事务未提交就还没有写入硬盘，数据本质还没有更改。（select时候显示已经更改，其他窗口查询并未更改）） |
| 不可重复读 | 在一个事务的处理过程中读取到了另一个事务中修改并已提交的数据（其实也就是没有加锁），导致两次结果不一致（不可重复读是在数据更改的前后读取的数据都是一致的，不会因为数据修改并提交之后窗口二读取数据和事物提交之前的不一样）**一个事物读取过程中，另一个事物提交并且修改了正在读取的事物** |
|    幻读    | select查询某记录明明不存在，insert/delete时却发现已经存在，无法插入/可以删除。（**幻读是添加/删除的问题**，区别于前两者的更改的问题） |

* 查询数据库隔离级别：SELECT @@TX_ISOLATION:
* 修改数据库隔离级别：SET GLOBAL TRANSACTION ISOLATION LEVEL *read uncommitted*; 

#### 3.7.4 分布式事物

* **理论**
  *  **CAP理论**
    * AP：保持可用性，放弃一致性
    * CP：保持一致性，放弃可用性
  * **BASE理论**：是系统达到最终一致性
* **实践**：Seata开源的分布式事物解决方案
  * 

### 3.8 存储过程与存储函数

* 概念：**一段sql语句的集合**，一次请求就能完成操作。类似于Java的方法 <font color='mediumseagreen'>存储函数有**返回值**而存储过程没有</font> 

* 使用场景：银行金融等领域需要安全性（将关键行列封装起来）

  <font color='cornflowerblue'>（面试题）存储过程和函数的好处：1.提高代码的复用性；2.减少数据在数据库与服务器之间的传输，提高效率；3.减少代码层面的业务处理（减少很多操作）</font>

#### 3.8.1 创建与使用

* 使用步骤：

```sql
  INSERT INTO student1(name,age,gender,score) VALUES('张三',23,'男',95),('张三',24,'男',98), ('张三',25,'女',100),('张三',26,'女',90);

 DELIMITER $ 
 CREATE PROCEDURE stu_group()
 BEGIN 
  SELECT gender,SUM(score) getSum FROM student1 GROUP BY gender ORDER BY getSum ASC;
 END$
 DELIMITER ;

CALL stu_group(); -- 调用已经编写好的方法
```

* **查看/删除已经编写的存储过程**

```sql
SELECT *FROM mysql.proc WHERE db ='yyy'; -- 查看
DROP PROCEDURE IF EXISTS stu_group; -- 删除
```

#### 3.8.2 创建变量与赋值

* **创建变量并赋值的三种方法**

  * **default**

  ```sql
  DELIMITER $
  CREATE PROCEDURE s()
  BEGIN
  	DECLARE number INT  DEFAULT 10; -- 默认值，创建存储过程的时候就已经赋值
  	SELECT number; -- 注意这里两个都有;  并且调用方法的时候就执行select
  END$
  DELIMITER ;
  ```

  * **set**

  ```sql
  DELIMITER  $
  CREATE PROCEDURE s1()
  BEGIN
  	DECLARE NAME VARCHAR(20);
  	SET NAME ='牛逼';
  	SELECT NAME ;
  END$
  DELIMITER ; -- 赋值的方式1：用set
  ```

  * **into**

  ```sql
  DELIMITER  $
  CREATE PROCEDURE s2()
  BEGIN
  	DECLARE man,woman INT;
  	SELECT sum(score) INTO man FROM  student1 WHERE gender='男'; -- 将sql语句的查询结果赋值给变量,赋值的方式2：用into
  	SELECT man;
  END$
  DELIMITER ; 
  ```

#### 3.8.3控制流程语句

* **if：** if...then - else if ... then - else - end if  <font color='mediumseagreen'>if直到endif才加 ' ; '、中间只有set语句后面加' ; '</font> 

```sql
DELIMITER $
	CREATE PROCEDURE sif()
		BEGIN
	-- 定义变量
			DECLARE sum INT;
			DECLARE info VARCHAR (20);  -- 每有一条自己写的语句后面都是分号
	-- 给变量赋值
			SELECT sum(score) INTO sum FROM student1;
	-- 进行if判断
				IF sum>380 THEN
					SET info ='很好';
					ELSEIF sum >=320 AND sum <= 380 THEN 
					SET info = '好';
					ELSE 
					SET info ='一般';
				END IF; -- 这里有一个end
			SELECT info,sum;
		END $
DELIMITER ;
```

* **while**：<font color='mediumseagreen'>注意do和endwhile</font> 

```sql
DELIMITER $
CREATE PROCEDURE s8()
BEGIN 
		DECLARE result INT DEFAULT 0;
		DECLARE num INT DEFAULT 1; -- 定义两个变量并且默认赋值
			WHILE num <=100 DO -- 注意while 后面要接 do
				IF num%2=0 THEN
					SET result= result +num;
				END IF ; -- if一定是和endif一起出现的
			SET  num =num +1;
		END WHILE; -- while一定是和endwhile一起出现的
	SELECT result;
END $
DELIMITER ;

CALL s8(); -- 输出结果 result 2550

```

#### 3.8.4 参数的传递

* in：输入参数（默认的，什么都不写就是in）
* out：输出参数，可以作为返回值
* inout：既可以输入又可以输出

```sql
DELIMITER  $
CREATE PROCEDURE s7( IN sum INT,OUT des VARCHAR(20) ) -- 输入参数以及输出参数
BEGIN  -- 这后面不需要declare参数，直接使用参数即可
IF sum > 100 THEN
	SET des ='牛逼';
	ELSE 
	SET des = '不牛逼'	;
END IF;
END $
DELIMITER ;

CALL s7(200,@des); -- @符号是会话变量，代表整个会话过程都是有作用的（全局变量） @@是系统变量

SELECT @des; -- 输出变量
```

#### 3.8.5 存储函数

* 一定有返回值、并且调用是select而不是call

```sql
DELIMITER  $
CREATE FUNCTION xxx( ) -- 创建函数
RETURNS INT -- 设置返回值类型（这个是存储函数的必要条件）
BEGIN 
	DECLARE s_count INT; -- 定义变量
	SELECT count(*) INTO s_count FROM student1 WHERE score >95; -- 用sql语句给变量赋值
RETURN s_count; -- 将返回值返回
END $
DELIMITER ;

SELECT xxx(); -- 调用函数，注意这里是select而不是call

DROP FUNCTION xxx; -- 删除函数
```

### 3.9 触发器

* **概念**：触发器（trigger）：在insert、update、delete之前或之后触发并执行触发器中定义的sql语句
* 在数据库端确保数据的完整性、日志记录、数据校验
* 使用old/new引用触发器中发生变化的内容记录

| **触发器类型**  | OLD的含义                      | NEW的含义                      |
| --------------- | ------------------------------ | ------------------------------ |
| INSERT 型触发器 | 无 (因为插入前状态无数据)      | NEW 表示将要或者已经新增的数据 |
| UPDATE 型触发器 | OLD 表示修改之前的数据         | NEW 表示将要或已经修改后的数据 |
| DELETE 型触发器 | OLD 表示将要或者已经删除的数据 | 无 (因为删除后状态无数据)      |

* **触发器的创建和使用事例**

```sql
 -- 创建被触发的表格
CREATE TABLE account (
	id INT PRIMARY KEY AUTO_INCREMENT,
	NAME VARCHAR(20),
	money DOUBLE
);
INSERT INTO account VALUES (NULL,'张三',1000),(NULL,'李四',2000); -- 先添加两条数据
-- 创建日志表格
CREATE TABLE  account_log(
	id INT PRIMARY KEY AUTO_INCREMENT ,
	operation VARCHAR(20), -- 这里是操作类型，insert、update、delete
	operation_time DATETIME, -- 记录操作时间
	operation_id INT , -- 操作表的id
	operation_params VARCHAR(2000) -- 操作参数 
);
-- 创建触发器
delimiter $
CREATE TRIGGER account_insert
AFTER INSERT -- 此处选择 before/after  insert/update/delete	 
ON account  -- 被触发的表名
FOR EACH ROW  -- 行级触发器
BEGIN 
INSERT INTO account_log VALUES ( -- 触发器被触发的时候就会向日志表格account_log插入信息
NULL, 
'insert',
now(),
NEW.id,
concat('插入后{id=',new.id,',name=',new.name,',money=',new.money,'}')-- 这里的new（old）
);  -- concat函数，进行字符串拼接
END 
$DELIMITER ;
-- 给account表插入数据，此时编写的account_insert触发器会自动触发，给日志表格account_log添加固定格式的数据
INSERT INTO account VALUES (NULL,'小明',3000); 
-- 查询日志表格
SELECT* FROM account_log; 
```

### 3.10 MySql高级

* **MySql四个层次**：**网络连接——核心服务——存储引擎（插件式）——系统文件**

#### 3.10.1 引擎的种类及特点

* **概念**： 存储表的机制，包括存储方式、索引技术、锁定水平等。MySql可以配置不同的引擎

  ```sql
  show table status from yyy; -- 查询存储引擎
  show table status from yyy where name ='student'; -- 查询引擎中的数据表的引擎名称
  create table student (...) engine = MYISAM; -- 创建表格的时候设置引擎
  alter table student engine = INNODB; -- 修改表格的存储引擎
  ```

  * **InnDB**
    * **支持事务、外键，支持并发控制**，占用磁盘空间大。MySql5.5之后默认。**支持表锁和行锁，支持集群（多线程）**。<font color='mediumseagreen'>（频繁读写操作、对事务和并发操作下数据的完整性有要求）</font>

  * **MYISAM**
    * 不支持事务和外键，**访问速度快**。**只支持表锁**，支持全文检索。<font color='mediumseagreen'>（以查询为主、对事务的完整性、并发性要求不高的时候使用）</font>
  * **MEMORY**
    * 基于内存存储，**速度快**，不安全，适用于量快速访问数据。只支持表锁。<font color='mediumseagreen'>（用于更新不太频繁的小表）</font>

#### 3.10.2 索引以及分类

* **概念**：索引的本质是数据结构/算法，以某种方式指向真实数据，实现高级查找算法

* **种类**：

  * 普通索引：最基本的索引，没有任何限制
  * 唯一索引：索引列的值必须唯一，允许有空值
  * 主键索引：特殊的唯一索引，不允许有空值
  * 组合索引：将单索引组合在一起
  * 外键索引：只有InnoDB引擎支持
  * 全文索引：快速匹配全部文档的方式

* **按照算法分类**：

  * BTree索引：<font color='mediumseagreen'>二叉树</font>

  ```sql
  CREATE INDEX idx_name ON student(NAME) ; // 给student表格name属性添加普通索引
  
  CREATE UNIQUE INDEX idx_age ON student(age);//给student表格age属性添加唯一索引
  
  SHOW INDEX FROM student;//查询student表格的索引
  ```

  * <font color='cornflowerblue'>（面试题）BTree与B+Tree索引的区别</font> 
    * BTree：每个节点包含key值，数据，会增加查询数据时的IO次数
    * B+Tree：提高查询速度（效率更加稳定），减少IO次数（磁盘读写代价更低）。是InnoDB的默认索引
    * <font color='cornflowerblue'>1.B+Tree非子叶节点只存储关键字和指针，数据存储在子叶节点上，所有子叶节点都有连接指针。而BTree的关键字、指针、数据都是存储在一起的；2.BTree越是靠近根节点的数据查询速度越快，B+Tree的每条数据记录的查找时间基本相同，同时因为它非子叶节点不存储数据，能够存储更多的键值，故能减少磁盘访问次数，一次访问相当于访问很多次，索引性能更高</font> 

  * Hash索引：

* **索引设计原则**：

  * *<u>查询频次高</u>，数据量大的表建立索引*
  * *用唯一索引区分度高，使用索引效率高*
  * *使用短索引，别搞太长*
  * *索引不易过多*
  * **最左匹配索引（值适用于组合索引）**
    * 在检索数据的时候从联合索引的最左边开始匹配。命中一个就可以完成检索。

<font color='cornflowerblue'>如何对sql语句调优？？：1.添加索引、2.少用模糊查询、3.尽量少用关联查询。</font> 

#### 3.10.3 锁

* **概念**：
  * **按照操作分类**
    * <u>共享锁</u> LOCK IN SHARE MODE：可以被**多个事务查询**，但是**无法修改**（多个窗口可以查询同一份数据，同时还可以再次添加共享锁，因为是兼容的）。<font color='mediumseagreen'>共享锁加载索引列的时候，是行级锁，注意行锁是只锁这一行，其他数据是照样可以修改的，表锁是锁住整个表格</font>   <font color='tomato'>InnoDB在非索引列（例如是以分数为条件查询而不是以id为条件查询）添加锁的时候，此时引擎会将行锁提升为表锁，在修改之前需要添加锁的那个窗口先提交事务（锁效果消失）</font> 
    * <u>排他锁</u> FOR UPDATE：加锁的数据不能被其他事务加锁查询或者修改。（普通查询没有问题，查询的时候加锁就不可以了）<font color='mediumseagreen'>所以排他锁和共享锁以及其他排他锁都是不兼容的</font> <font color='tomato'>其他事务也不能修改数据，会出现锁的情况，除非本事务提交，其他事务才能修改</font>  
    * <u>MYISAM读锁</u> LOCK TABLE xxx READ;  <font color='mediumseagreen'>所有连接只能查询数据，不能修改数据 </font> 
    * <u>MYISAM写锁</u> LOCK TABLE xxx WRITE（UNLOCK TABLES;解锁）; <font color='mediumseagreen'>其他连接不能查询和修改数据，当前连接是可以的</font>   <font color='tomato'>解锁之后其他窗口（一个窗口代表一个线程）就可以查看以及修改数据了</font> 
  * **按照粒度分类**
    * 行级锁
    * 表级锁
    * 页级锁   
  * **使用方式分类**
    * <u>悲观锁</u>：对外界修改持有保守态度，认为数据随时会修改，整个数据处理需要将数据加锁，一般都是依靠关系型数据库自带的锁机制 <font color='mediumseagreen'>在此之前全部都是悲观锁</font> 
    * <u>乐观锁</u>

## 4. JDBC

### 4.1 概念

* JDBC：Java DateBase Connectivity，java语言操作数据库，使用一套统一的java代码（**官方定义了接口，实现类是每一个不同的数据库厂商写的数据库驱动jar包**）操作各种数据库。编程的时候是使用接口的对象变量调用实现类的方法。 
* ==步骤==
  * 1.找驱动（通信协议）：  Class.forName("com.mysql.jdbc.Driver");
  * 2.建立链接： Connection conn = DriverManager.getConnection("jdbc:mysql://localhost:3306/practice1", "root", "541353060");
  * 3.获取执行者（建立通道）：   Statement st = conn.createStatement();
  * 4.执行sql语句： int i = st.executeUpdate(s);
  * 5.处理结果：System.out.println(i);
  * 6.释放资源：conn.close();

```java
package test1;

import java.sql.Connection;
import java.sql.DriverManager;
import java.sql.SQLException;
import java.sql.Statement;

public class JdbcDemo1 {671161
    public static void main(String[] args) throws ClassNotFoundException, SQLException {
        Class.forName("com.mysql.jdbc.Driver");
        Connection conn = DriverManager.getConnection("jdbc:mysql://localhost:3306/practice1", "root", "541353060");
        String s ="update dept set loc ='蓝鲸' where id=10";
        Statement st = conn.createStatement();
        int i = st.executeUpdate(s);
        System.out.println(i);//修改成功后会返回1
        st.close();
        conn.close();//此处必须释放资源
    }
}
```

###  4.2 jdbc对象详解 

* **注册驱动：**Class.forName("com.mysql.jdbc.Driver"); //创建Class对象，随着类被加载，其中的静态代码块（==java.sql.DriverManager.registerDriver(new Driver()：注册驱动==）执行，告诉驱动运行哪个数据库jar包（sql5之后可以省略）
* **数据库连接：**DriverManager.getConnection("jdbc:mysql://localhost:3306/practice1", "root", "541353060");  返回connection对象 <font color='mediumseagreen'>这里可以用sou t(conn.isclosed)看看是否返回false来测试是否链接成功</font> 
* **connection：数据库连接对象** 
  * 功能1: <font color='mediumseagreen'>connection是一个接口</font>
    *  Statement createStatement();
    *  PreparedStatement prepareStatement(String sql)。<font color='mediumseagreen'>预编译执行者对象，参数条件可以变化</font>
       * **PrepareStatement的几点优势：**1.提高代码可读性可维护性；2.提升性能；3。预编译机制防止用户恶意输入类似sql语句造成干扰危险
  * 功能2：管理事务（用connection管理事务）  <font color='mediumseagreen'>commit、rollback（出现异常时）</font> 
* **statement：执行sql对象**  <font color='mediumseagreen'>通道对象，是执行sql语句的。create出来的，就相当于new，区别于get是直接获取</font> 
  * int executeUpdate() :**返回的是影响的行数** （执行DML\DDL ：增删改）
  * ResultSet executeQuery(String sql)：**返回的是结果集**   (执行DQL：查询)<font color='tomato'> 以下两个是ResultSet方法</font> 
    * boolean next()：有数据就返回true，并且索引向下移动一行；没有数据就是返回false
    * 数据类型 get数据类型("列名")

==练习：用JDBC修改表中的数据(DML)==

```java
package test1;

import java.sql.Connection;
import java.sql.DriverManager;
import java.sql.SQLException;
import java.sql.Statement;

public class JDBCtest2 {
    public static void main(String[] args) {
        Statement stat=null;
        Connection conn=null;
        try {
           // Class.forName("com.mysql.jdbc.Driver");
            conn = DriverManager.getConnection("jdbc:mysql://localhost:3306/practice1", "root", "541353060");
            String sql ="update dept set loc='加州' where id =60 ";
             stat = conn.createStatement();
            int i = stat.executeUpdate(sql);
            System.out.println(i);
        }  catch (SQLException e) {
           e.printStackTrace();
        } finally {
            if (stat!=null) {
                try {
                    stat.close();
                } catch (SQLException throwables) {
                    throwables.printStackTrace();
                }
            }
            if (stat!=null) {
                try {
                    conn.close();
                } catch (SQLException throwables) {
                    throwables.printStackTrace();
                }
            }
        }
    }
}
```

==练习：用JDBC查询表中的数据（DQL）==

```java
package test1;

import java.sql.*;
driverClassName=com.mysql.cj.jdbc.Driver
public class JDBCtest2 {
    public static void main(String[] args) {
        Statement stat = null;
        Connection conn = null;
        ResultSet set = null;//数据集也是资源，也要释放
        try {
            // Class.forName("com.mysql.jdbc.Driver");
            conn = DriverManager.getConnection("jdbc:mysql://localhost:3306/practice1", "root", "541353060");
            String sql = "select * from emp ";
            stat = conn.createStatement();
            set = stat.executeQuery(sql);//注意因为是DQL，要用executeQuery()方法

            set.next();//关键步骤，必须先让指针向下移动一行，从目录到数据
            int i = set.getInt(1);
            String name = set.getString("name");
            Date joindate = set.getDate("joindate");
            System.out.println(i + " " + name + " " + joindate);//输出结果为：1001 miaochanwen 1995-01-01
//这里也可以用while（set.next()）{...}进行循环遍历
        } catch (SQLException e) {
            e.printStackTrace();
        } finally {
            if (stat != null) {
                try {
                    stat.close();
                } catch (SQLException throwables) {
                    throwables.printStackTrace();
                }
            }
            if (stat != null) {
                try {
                    conn.close();
                } catch (SQLException throwables) {
                    throwables.printStackTrace();
                }
            }
            if (set != null) {
                try {
                    set.close();
                } catch (SQLException throwables) {
                    throwables.printStackTrace();
                }
            }
        }
    }
}
```

* ==建立JDBCutils类，通过配置文件直接获取Connection对象和释放资源。取得简化代码/封装代码的目的==

```java
package com.ycx.JDBCutils;

import java.io.FileInputStream;
import java.io.FileNotFoundException;
import java.io.IOException;
import java.net.URL;
import java.sql.*;
import java.util.Properties;

public class JDBCutils { //注意基本数据类型都要用包装类
    private static String url;
    private static String user;
    private static String password;
    private static String driver; //关键步骤，要把这几个域设置为静态域


    static { //静态代码块，要让内部代码对着类的加载而执行
        Properties p = new Properties();
        ClassLoader classLoader = JDBCutils.class.getClassLoader();//获取ClassLoader类对象
        URL resource = classLoader.getResource("JDBCutils.properties");//直接通过配置文件名获取URL地址 因为双亲委派机制，先从项目根目录开始查找
        String path = resource.getPath();//通过URL获取配置文件路径
        try {
            FileInputStream fis = new FileInputStream(path);
            try {
                p.load(fis);
                url = p.getProperty("url");
                user = p.getProperty("user");
                password = p.getProperty("password");
                driver = p.getProperty("driver");
                try {
                    Class.forName(driver);
                } catch (ClassNotFoundException e) {
                    e.printStackTrace();
                }
            } catch (IOException e) {
                e.printStackTrace();
            }
        } catch (FileNotFoundException e) {
            e.printStackTrace();
        }
    }

    public static Connection getConnection() { //封装此方法获取Connection对象
        Connection connection = null;

        try {
            connection = DriverManager.getConnection(url, user, password);
        } catch (SQLException throwables) {
            throwables.printStackTrace();
        }
        return connection;
    }


    public static void close(Statement statement, Connection connection) { //用于DML
        if (statement != null) {
            try {
                statement.close();
            } catch (SQLException throwables) {
                throwables.printStackTrace();
            }
        }
        if (connection != null) {
            try {
                connection.close();
            } catch (SQLException throwables) {
                throwables.printStackTrace();
            }
        }
    }

    public static void close(Statement statement, Connection connection, ResultSet resultSet) {//用于DQL
        if (statement != null) {
            try {
                statement.close();
            } catch (SQLException throwables) {
                throwables.printStackTrace();
            }
        }
        if (connection != null) {
            try {
                connection.close();
            } catch (SQLException throwables) {
                throwables.printStackTrace();
            }
        }

        if (resultSet != null) {
            try {
                resultSet.close();
            } catch (SQLException throwables) {
                throwables.printStackTrace();
            }
        }
    }
}

```

### 4.2 用connection管理事务

* ==开启事务的三个步骤==
  * 1.connection.setAutoCommit(false)：开启事务
  * 2.connection.commit()：在可执行代码末端提交事务
  * 3.connection.rollback()：在异常里面回滚

```java
package com.ycx.testShiWu;

import com.ycx.JDBCutils.JDBCutils;
import java.sql.Connection;
import java.sql.PreparedStatement;
import java.sql.SQLException;

public class test3 {
    public static void main(String[] args) {
        Connection connection = null;
        PreparedStatement pre1 = null;
        PreparedStatement pre2 = null;

        try {
            connection = JDBCutils.getConnection();
            connection.setAutoCommit(false);//开启事务
            String sq1 = "update account set money = money -? where id =?";
            String sq2 = "update account set money = money +? where id =?"; //用？代替关键数据，增加可读性以及安全性
            pre1 = connection.prepareStatement(sq1);
            pre2 = connection.prepareStatement(sq2);
            pre1.setDouble(1, 5000); //这里是从1开始，不是0开始！
            pre1.setInt(2, 1);
            pre2.setDouble(1, 5000);
            pre2.setInt(2, 2);//与？一一对应赋值，注意是setInt还是setDouble

            pre1.executeUpdate();
            int i = 3 / 0; //故意写出一个异常再通过事务回滚
            pre2.executeUpdate();//执行更新（executeQuery是执行查看）
            connection.commit();//正常执行没有出问题就提交

        } catch (Exception e) {
            e.printStackTrace();
            try {
                connection.rollback();//如果进入异常就回滚rollback
            } catch (SQLException r) {
                r.printStackTrace();
            }
        } finally {
            JDBCutils.close(pre1, connection);
            JDBCutils.close(pre2, null);
        }
    }
}
```

* **装饰者模式**：在不改变原有类基础上增加相应功能
  * 定义一个实现类去实现原有接口
  * 在实现类里面声明接口类成员变量，构造器赋值
  * 功能方法若是修改则修改，不修改的用原来的
  * 用的时候调用构造器传值
* **适配器模式**：解决实现类与接口之间的矛盾冲突
  * 定义一个类去实现原有接口
  * 在实现类声明接口类成员变量，构造器赋值
  * 功能方法若是修改则修改，不修改的用原来的
  * 自定义类去继承适配器类（不同之处），这样就能保证**有选择的使用方法**
* **动态代理**：在不改变原有的功能基础上，增加或补充相应功能
  * 借助Proxy.newProxyInstance()，从内存对象对原有对象做封装生成一个代理对象，直接使用代理对象去操作

### 4.3 数据库连接池

* **概念**：每一次执行sql数据，如果都要连接数据库的话，会造成资源的浪费并且效率低下；数据库连接池是一个容器，容器中存放着连接对象，用户每次来访问数据库的时候，就会**直接从连接池中获取连接对象，使用完毕之后归还连接对象给容器。**

* **实现方法：**DataSource标准接口

  * 获取连接：**getConnection()**

  * 归还连接：从数据库连接池获取对象的话，close就不是释放资源，而是归还给数据库连接池

  * 种类：

    * c3p0：
    * **Druid**（阿里的，导入jar包）：

    ```java
    package com.ycx.DruidTest; //
    import com.alibaba.druid.pool.DruidDataSourceFactory;
    import javax.sql.DataSource;
    import java.io.InputStream;
    import java.sql.Connection;
    import java.util.Properties;
    
    public class DruidDemo {
        public static void main(String[] args) throws Exception {
            Properties p = new Properties();
            ClassLoader classLoader = DruidDemo.class.getClassLoader();
            InputStream is = classLoader.getResourceAsStream("druid.properties");//通过classloader获取资源流文件
            p.load(is);//加载配置文件
            DataSource ds = DruidDataSourceFactory.createDataSource(p);//获取连接池对象
            Connection conn = ds.getConnection();//获取了connection对象
            System.out.println(conn);
        }
    }
    
    -------配置文件druid.properties的内容--------
    driverClassName=com.mysql.cj.jdbc.Driver
    url=jdbc:mysql://localhost:3306/practice1
    username=root
    password=541353060
    filters=stat
    initialSize=2
    maxActive=300
    maxWait=60000
    timeBetweenEvictionRunsMillis=60000
    minEvictableIdleTimeMillis=300000
    validationQuery=SELECT 1
    testWhileIdle=true
    testOnBorrow=false
    testOnReturn=false
    poolPreparedStatements=false
    maxPoolPreparedStatementPerConnectionSize=200
      
    --------正式操作中都会用已经编写好的工具类Druidutils进行快捷获取connection对象---------
    package com.ycx.Druidutils;
    
    import com.alibaba.druid.pool.DruidDataSourceFactory;
    import com.ycx.DruidTest.DruidDemo;
    
    import javax.sql.DataSource;
    import java.io.InputStream;
    import java.sql.Connection;
    import java.sql.ResultSet;
    import java.sql.SQLException;
    import java.sql.Statement;
    import java.util.Properties;
    
    public class Druidutils {
        public static DataSource ds;//关键操作，将DataSource设置为静态域
    
        static {
            try {
                Properties p = new Properties();
                ClassLoader classLoader = DruidDemo.class.getClassLoader();
                InputStream is = classLoader.getResourceAsStream("druid.properties");//通过classloader获取资源流文件
                p.load(is);//加载配置文件
                ds = DruidDataSourceFactory.createDataSource(p);//获取连接池对象
            } catch (Exception e) {
                e.printStackTrace();
            }
        }
    
        public static Connection getConnecion() throws SQLException {//用于获取connection对象
            return ds.getConnection();
        }
    
        public static void close(Statement statement, Connection connection) { //用于DML
            if (statement != null) {
                try {
                    statement.close();
                } catch (SQLException throwables) {
                    throwables.printStackTrace();
                }
            }
            if (connection != null) {
                try {
                    connection.close();
                } catch (SQLException throwables) {
                    throwables.printStackTrace();
                }
            }
        }
    
        public static void close(Statement statement, Connection connection, ResultSet resultSet) {//用于DQL
            if (statement != null) {
                try {
                    statement.close();
                } catch (SQLException throwables) {
                    throwables.printStackTrace();
                }
            }
            if (connection != null) {
                try {
                    connection.close();
                } catch (SQLException throwables) {
                    throwables.printStackTrace();
                }
            }
    
            if (resultSet != null) {
                try {
                    resultSet.close();
                } catch (SQLException throwables) {
                    throwables.printStackTrace();
                }
            }
        }
    }
    ```

* ==练习：用数据库连接池更新数据库数据==

```java

import com.ycx.Druidutils.Druidutils;

import java.sql.Connection;
import java.sql.PreparedStatement;
import java.sql.SQLException;

public class DruidDemo2 {
    public static void main(String[] args) throws SQLException {
        Connection conn = null;
        PreparedStatement pst = null;
        try {
            conn = Druidutils.getConnecion(); //工具类的作用就是获取了connection对象
            String sql = "insert into account values(null,?,?) ";
            pst = conn.prepareStatement(sql);
            pst.setString(1, "liuqiangdong");
            pst.setDouble(2, 40000);
            int i = pst.executeUpdate();
            System.out.println(i);
        } catch (SQLException throwables) {
            throwables.printStackTrace();
        } finally {
            Druidutils.close(pst, conn);
        }
    }
}
```

### 4.4 JDBCTemplate对象

* 概念：Spring提供的JDBC封装（导入jar包），简化重复代码

* 用JDBCTemplate对象的方法进行**CRUD操作**（）

  * update()：增删改

  * queryForMap()：将查询结果封装成map集合 // 把属性当key，把值当作value;所以这个方法只能操作数据表一条记录

  * queryForList()：将查询结果封装成list集合

  * **query()*：将查询结果封装成Javabean对象**

    * ```java
      public class jdbcTemplateTest {
          public static void main(String[] args) {
              JdbcTemplate jt = new JdbcTemplate(Druidutils.getDataSource());//先创建对象，参数是DataSource对象                                                                            
              String sql = "select*from account;";
              List<person> list3 = jt.query(sql, new BeanPropertyRowMapper<person>(person.class));//Template的简化封装javabean对象集合的方式。注意两个参数的种类   
          }
      }
      ```
  
  * queryForObject()：将查询结果封装成对象（一般是用于聚合函数的查询，如count等）
  
  ```java
   @Test   
  public void test(){     
      JdbcTemplate jdbcTemplate = new JdbcTemplate(Druidutils.getDataSource());        			String sql="select count(id) from account;";      
      Integer i = jdbcTemplate.queryForObject(sql, Integer.class);//参数是sql和想要返回的类型的.class    
  		System.out.println(i);   
      -------------此方法有重载，可以控制“？”---------------      
    String sql="select * from account where name=? and where password=?;";       
   User u=jdbcTemplate.queryForObject(sql,User.class,参数1，参数2)//对应 ?,?  
  }
  ```

## 5. XML

### 4.1 XML概述

* 概述：可扩展（标签的名字可以自己定义）的标记语言（通过标签来描述数据）
* xml标签：
  * <>  
  * 成对出现  < > </ >
  * 特殊标签不成对出现但是有结束标记 如< address / >
  * 标签中定义属性，属性与标签名隔开，属性要加“ ”
  * 注意要正确嵌套
* **xml语法规则：**
  * .xml
  * 文档声明在第一行第一列

### 4.2 DOM解析

* **DOM解析：**
  * Document对象：xml
  * Element对象：所有标签
  * Attribute对象：所有属性

```java
package test;

import org.dom4j.Attribute;
import org.dom4j.Document;
import org.dom4j.DocumentException;
import org.dom4j.Element;
import org.dom4j.io.SAXReader;

import java.util.List;

/*<?xml version="1.0" encoding="utf-8" ?>
<persons>
<person id="1">
<name>张三</name>
<age>23</age>
</person>
</persons>*/
//以上是xml文件的内容
public class t {
    public static void main(String[] args) throws DocumentException {
        SAXReader saxReader = new SAXReader();//首先创建SAXReader对象
        Document read = saxReader.read("xmltest/src/test/Person.xml");//获取文件
        Element rootElement = read.getRootElement();//获取根元素persons
        List<Element> person = rootElement.elements("person");//获取根元素下面所有的person元素
        for (Element el : person) {
            Attribute id = el.attribute("id");
            System.out.println(id.getValue());//id属于person<>里面的属性，要用attribute

            Element name = el.element("name");
            System.out.println(name.getText());//其他的属性都要element（属性名）方法，获取Element对象，再调用getText()方法

            Element age = el.element("age");
            System.out.println(age.getText());
        }
    }
}
```

### 4.3 约束

* ==**1.DTD**==

```dtd
<!ELEMENT persons (person)>
<!ELEMENT person (name,age)>
<!ELEMENT name (#PCDATA)>
<!ELEMENT age (#PCDATA)>//dtd文件
```

```xml
<?xml version="1.0" encoding="utf-8" ?>
<!DOCTYPE persons SYSTEM "persondtd.dtd">//这一行代表了约束
<persons>
    <person>
        <name>aws</name>
        <age>11</age>
    </person>
</persons>//被约束的xml文件
```

* **引入DTD三种方式**：
  * 1.本地DTD ；
  * 2.XML文件内部引入 ；
  * 3.引入网络中的DTD；
* **语法规则**：
  * 简单元素：
    * EMPTY：标签体是空；
    * ANY：标签体可空可不空；
    * PCDATA：字符串
  * 复杂元素：
    * “,”定义子元素的顺序 、
    * “|”子元素只能出现任意一个 、
    * “ ? ” 零次或一次、
    * “ + ”一次或多次、
    * ​    “ * ”零次或多次
  * 定义属性：< !ATTLIST 元素名 属性名 属性类型 属性的约束 > （比如id）
    * CDATA：普通字符串
    * 属性约束：
      * #REQUIRED :必须的
      * #IMPLIED：非必需
      * #FIXED value：属性值固定

* ==**2.schema**==
  * 也是xml，后缀是.xsd
  * 一个xml可以引用多个schema约束文件，使用文件空间区分
  * dtd取值常见就是PCDATA类型，schema可以支持多个数据类型

## 6. TomCat&Http&Servlet

### 6.1tomcat

#### 	6.1.1概念

* 概念：web**服务器（更加强大的计算机）软件（软硬件结合）**，可以部署web项目让用户通过浏览器访问这些项目。
* 轻量级服务器：实现了部分javaee规范；
* tomcat是应用服务器，本质是一个软件，可以跑编写的程序，其他人也可以通过网络访问我的web程序。
* 静态页面可以直接修改即可，不需要重新启动服务器
* （WEB-INF）web.xml是在编辑servlet的时候编写的配置文件

### 6.2 http协议

#### 6.2.1概念

* 概念：超文本传输协议，**定义了客户端与服务器端通信时发送数据的格式**
* 特点
  * 基于TCP/IP的高级协议
  * 默认端口号：80
  * 基于请求响应/模型：一次请求对应一次响应
  * 每次请求相互独立，不能交互数据（无状态的）

#### 6.2.2 请求消息

* **请求消息格式**

  * **请求行**

    * 请求方式 请求url 请求协议/版本

      GET(POST)  /login.html/ http/1.1

  * **请求头**

    * 键值对形式：告诉浏览器请求信息(Host\User-Agent\Accept\Referer\Connection\Upgrade-Insecure-Requests)
    * ==（例如）User-Agent== :浏览器告诉服务器浏览器的信息。可以解决浏览器兼容问题 if(chorm){...}
    * ==（例如）Referer==：告诉浏览器请求从哪里来（1.防盗链 ；2.统计工作）if(referer.equals(...)){...} 

  * **请求空行**

  * **请求体（正文）**

    * post将请求参数封装在请求体中，并且长度没有限制，所以文件的上传也用post

### 6.3 Servlet

* **概念：servlet是一种接口，java代码要遵循它的规则才能被tomcat识别并在服务器执行**
* **servlet控制器，filter过滤器、listener监听器；mvc思想、分层思想（三器两思想）**

#### 6.3.1 使用步骤及原理

* 使用步骤

  * 创建javaweb项目
  * 定义一个类（无需main方法）并且实现servlet，覆盖其中的所有方法
  * 配置servlet

  ```xml
   <servlet>
          <servlet-name>test1</servlet-name> <!--这里就相当于给类起了一个别名-->
          <servlet-class>com.ycx.test.TestServlet</servlet-class> <!--注意这里是全类名-->
      </servlet>
      
      <servlet-mapping> <!--映射-->
          <servlet-name>test1</servlet-name>
          <url-pattern>/testservlet</url-pattern> <!--要部署的url名--> 
      </servlet-mapping> 
  
  <!--以上都是在web.xml文件里面实现配置--> 
  
  <!--该过程达到了通过浏览器输入地址/testservlet实现启动java代码的操作（无需自己创建对象、调用方法）--> 
  ```

* 实现原理

  * 服务器接收到浏览器请求后，会解析url，获取servlet资源路径

  * 查找web.xml有没有< url-partten >标签的内容，有的话再找到servletclass对应的全类名
  * tomcat会将字节码文件加载到内存并且创建对象以及调用方法

####  6.3.2 方法详解

* servlet的五个方法

```java
 @Override
    public void init(ServletConfig servletConfig) throws ServletException {
//servlet创建时执行，只会执行一次
    }

    @Override
    public ServletConfig getServletConfig() {
        return null;
//获取servletconfig（servlet配置对象）
    }

    @Override
    public void service(ServletRequest servletRequest, ServletResponse servletResponse) throws ServletException, IOException {
        System.out.println("hello Servlet");
//每一次servlet被访问的时候就执行，会执行多次
    }

    @Override
    public String getServletInfo() {
        return null;
//获取servlet的一些信息
    }

    @Override
    public void destroy() {
//服务器正常关闭的时候执行，只执行一次
    }
```

* ==servlet生命周期方法==
  * **1.第一次访问init方法时，创建servlet**	(tomcat启动的时候就已经初始化)
    * 可以通过< load-on-starup >手动调整创建时机（负数为第一次访问时创建，0/正数为服务器启动时创建）
    * init只执行一次，说明内存中只能有一个servlet对象（**多线程可能出现线程安全问题**）（所以最好不要在servlet中定义成员变量，直接定义**局部变量**）
    * <font color='cornflowerblue'>（<u>面试题）servlet线程不安全</u></font> ：
      * <font color='cornflowerblue'>servlet是单例的，每个浏览器都相当于一个线程多次访问同一个变量造成混乱。</font>
      * <font color='cornflowerblue'>解决方法就是*1：定义在doPost/doGet方法体内* ； *2：使用同步方法。*</font>
  * **2.每次访问servlet时，service方法就会执行一次**
  * **3.服务器如果不正常关闭的时候，destroy不会执行**
    * 在servlet被销毁之前执行，一般用于释放资源（临终遗言）

#### 6.3.2  servlet3.0使用注解

* *extends HttpServlet*

* 直接在编写的java类上面**添加注解 @webservlet("/路径地址")**。方便快捷得多
* 一个servlet可以**对应多个路径地址**@webservlet({"/test1","/test2","/test3"})
* @webservlet("*.do") //这里 *代表可以输入任何字符，注意前面没有/（但是必须以do结尾）

#### 6.3.3 servlet体系结构

* ==Servlet==
  * ==GenericServlet==：实现了Servlet，只在内部把service方法变成了抽象方法，其他都是正常实现。所以继承GenericServlet只需要重写service方法即可。
    * ==HttpServlet==：在前者的基础上内部添加了**区分get/post请求**的代码。继承此类只需要覆盖doGet()/doPost()方法，无需覆盖service方法。更加简化了操作。

#### 6.3.4 ServletContext*

##### 6.3.4.0 概念

* **概念：**应用上下文对象（应用域对象），每个应用只有这一个对象；
  * 域对象：为了实现数据的共享
  * servlet共有4个域对象：ServletContext是web应用中范围最大的域对象
  * 只要是B/S架构，就有域对象
* **作用：**配置和获取应用的全局化参数，可以实现**servlet之间的数据共享。**
* 生命周期：应用加载的时候创建，应用停止的时候销毁

##### 6.3.4.1 ServletContext常用方法

==ServletContext application=config.getServletContext()==：**获取ServletContext对象的方法**

* getParameter(String name)：根据名称获取**全局配置参数**
* getContextPath()：获取应用的虚拟目录
* getRealPath(String name)：根据虚拟目录获取**绝对路径**，参数是虚拟目录

```java
package com.ycx;

import jakarta.servlet.*;
import jakarta.servlet.annotation.WebServlet;

import java.io.IOException;

@WebServlet("/servletdemo")
public class servletdemo extends GenericServlet {
    @Override
    public void service(ServletRequest servletRequest, ServletResponse servletResponse) throws ServletException, IOException {
        ServletContext context = getServletContext();
        String s1 = context.getContextPath();
        System.out.println(s1);
        String s = context.getRealPath("/WEB-INF/classes/com/ycx/servletdemo");
        System.out.println(s);
    }
}
```

* ==实现数据的共享：==

  * setAttribute(String name,Object value)：设置共享数据（）
  * getAttritbute((String name)：获取共享数据
  * removeAttribute((String name)：删除共享数据

  ```java
  package com.ycx;
  
  import jakarta.servlet.*;
  import jakarta.servlet.http.*;
  import jakarta.servlet.annotation.*;
  
  import java.io.IOException;
  
  @WebServlet(name = "aa", value = "/aa")
  public class aa extends HttpServlet {
      @Override
      protected void doGet(HttpServletRequest request, HttpServletResponse response) throws ServletException, IOException {
          ServletContext application = getServletContext();
          application.setAttribute("username", "yuchenxi");
          System.out.println("aa:" + (String) application.getAttribute("username"));
      }
  
      @Override
      protected void doPost(HttpServletRequest request, HttpServletResponse response) throws ServletException, IOException {
      }
  } 
  
  package com.ycx;import jakarta.servlet.*;import jakarta.servlet.http.*;import jakarta.servlet.annotation.*;import java.io.IOException;
  
  @WebServlet(name = "cc", value = "/cc")
  public class cc extends HttpServlet {
      @Override
      protected void doGet(HttpServletRequest request, HttpServletResponse response) throws ServletException, IOException {
          ServletContext application = getServletContext() String s = (String) application.getAttribute("username");/
          getAttribute(String name) System.out.println("cc:" + s);
      }
  
      @Override
      protected void doPost(HttpServletRequest request, HttpServletResponse response) throws ServletException, IOException {
          this.doGet(request, response);
      }
  }
  ```
  
  

## 7. Requset&Response

### 7.1 概念及原理

* 1.客户端浏览器向服务器端发送url请求，以获取相应的资源
* 2.**tomcat还会创建request、response对象。**将这两个对象作为方法传递给service方法。调用service方法
* 3.自己可以在service方法里面编写代码，通过request对象获取请求消息数据，通过response对象编写响应代码 
* ==服务器创建，自己使用==

### 7.2 request

#### 7.2.1 继承体系结构

* ServletRequest接口
  * HttpServletRequest接口
    * **tomcat里面的RequestFacade类实现了HttpServletRequest接口**

#### 7.2.2 request的功能

##### 7.2.2.1获取请求消息数据

* ==获取请求消息数据==

  * **获取请求行：**

    * String	**getMethod()**  返回get/post

    * String	**getContextPath() ***  返回虚拟目录

  * String	**getServletPath()**  返回servlet路径

    * String	**getQueryString()**   返回get方式的请求参数 <font color='mediumseagreen'>可以通过参数解析写白名单</font>
    * String	**getRequestURI() ***  返回URI <font color='mediumseagreen'>统一资源标识符</font> （虚拟目录+servlet路径）

  * String **getRequestURL()** 返回URL<font color='mediumseagreen'> 统一资源定位符</font>（http: // localhost + URI）

    * getProtocol()：获取协议以及版本
    * String **getRemoteAddr()**：获取客户机的ip地址

  * **获取请求头：**

    * **String getHeader(String name) ***：通过请求头的名称获取请求头的值(referer的值需要点击者通过超链接的方式才能获取。直接通过浏览器输入地址值是没有referer的)
    * **getHeaderNames()**：获取所有请求头的名称 （相当于一个迭代器）

  * **获取请求体：**

    * 只有post方式才有请求体，请求体中封装了post请求的请求参数

    * 步骤1：获取流对象

      步骤2：从流对象中拿出数据

      ```java
      @Override    protected void doPost(HttpServletRequest request, HttpServletResponse response) throws ServletException, IOException {        BufferedReader reader = request.getReader();
              String s =null;
              while ((s=reader.readLine())!=null){
              System.out.println(s); 
          
      ```

* ==其他功能==

  * **获取请求参数通用方式** 

  ```java
  String s = request.getParameter("参数名称");//返回参数值
  
  String[] s1 = request.getParameterValues("参数名称");//返回参数值的数组，多选操作常用，比如hobby的值
  
  Enumeration<String> parameterNames = request.getParameterNames();//返回所有请求的参数名称
  
  Map<String, String[]> map = request.getParameterMap();//返回所有参数的map集合（将相同name作为key，不同value的值（存储为String[]）作为value）（如果value只有一个也是存储在String[]里面）
  
  BeanUtils.populate(stu,map);//这里可以直接用工具类进行封装对象。
  
  request.setCharacterEncoding("utf-8");//设置编码方式防止中文乱码
  ```

* 通过流对象获取路径（只能用post）

* **==* request中文乱码问题==**

  * get：没有乱码问题（tomcat8已经解决此问题）<font color='mediumseagreen'>企业中大部分都是7...用同样的办法解决</font>
  * post：<font color='mediumseagreen'>前后编码没有统一</font> 
    * request.setCharacterEncoding("utf-8");//设置编码方式防止中文乱码4

* ==请求转发==

  * **将request、reponse传给另一个servlet**

  ```java
  request.getRequestDispatcher("/Servletdemo1").forward(request,response);//链式编程
  ```

  * <font color='cornflowerblue'>（<u>面试题）转发的特点</u>：</font>

    * <font color='cornflowerblue'>1.浏览器地址没有发生变化，转发是一次请求</font>

    * <font color='cornflowerblue'>2.是服务器内部跳转，无法访问外部资源</font>

  * 共享数据：**request域对象**（表示一次请求的范围，范围内可以共享数据）

    ```java
    request.setAttribute("name",object);//这一步其实是将键值对储存到request域中
    Object o = request.getAttribute("name");//接收方获取attribute
    request.removeAttribute("name");//此方法可以移除域对象中的键值对
    ```

  <font color='tomato'>直接在浏览器地址输入set方地址可以获取值；但是如果在浏览器地址输入get方地址就无法获取值（地址栏没有、不能发生变化）</font>

  * request.getServletContext( );//获取一个ServletContext对象

* ==*** 综合练习：**创建web项目，编写html登陆页面，并用css美化；登陆获取数据（使用servlet、request）并与数据库（使用数据库连接池、template、编辑sql语句获取对象）比较，返回登陆（跳转、共享）成功与否。*==

![project_JavaWebDay01.](/Users/yuchenxi/Documents/《ycx-JavaWeb学习笔记》配图/project_JavaWebDay01..jpg)

```java
------------LoginServlet类------------------
package com.ycx.login;

import com.ycx.Dao.EmployeeDao;
import com.ycx.domain.Employee;
import jakarta.servlet.ServletException;
import jakarta.servlet.annotation.WebServlet;
import jakarta.servlet.http.HttpServlet;
import jakarta.servlet.http.HttpServletRequest;
import jakarta.servlet.http.HttpServletResponse;

import java.io.IOException;

@WebServlet("/LoginServlet")
public class LoginServlet extends HttpServlet {
    @Override
    protected void doPost(HttpServletRequest req, HttpServletResponse resp) throws ServletException, IOException {
        System.out.println("post");
        req.setCharacterEncoding("utf-8");//设置编码
        String username = req.getParameter("username");
        String password = req.getParameter("password");
        Employee loginEmp = new Employee(username, password);
        EmployeeDao employeeDao = new EmployeeDao();
        Employee e = employeeDao.login(loginEmp);//返回全参对象
        if (e!=null){//成功
            req.setAttribute("e",e);//关键步骤，set.注意这一步一定要放在转发request之前！
            req.getRequestDispatcher("/SuccessServlet").forward(req,resp);
        }else{
            req.getRequestDispatcher("/FailServlet").forward(req,resp);
        }
    }
}
------------SuccessServlet类------------------
 package com.ycx.login;

import com.ycx.domain.Employee;
import jakarta.servlet.ServletException;
import jakarta.servlet.annotation.WebServlet;
import jakarta.servlet.http.HttpServlet;
import jakarta.servlet.http.HttpServletRequest;
import jakarta.servlet.http.HttpServletResponse;

import java.io.IOException;

@WebServlet("/SuccessServlet")
public class  SuccessServlet extends HttpServlet {
    @Override
    protected void doPost(HttpServletRequest req, HttpServletResponse resp) throws ServletException, IOException {
        Employee employee = (Employee) req.getAttribute("e");//get request域中共享的对象
        System.out.println(employee);
        if (employee!=null) {
            resp.setContentType("text/html;charset=utf-8");//用response在页面输出
            resp.getWriter().write("恭喜"+employee.getUsername()+"登陆成功！");
        }
    }
}
//------------FailServlet类------------------
package com.ycx.login;

import jakarta.servlet.ServletException;
import jakarta.servlet.annotation.WebServlet;
import jakarta.servlet.http.HttpServlet;
import jakarta.servlet.http.HttpServletRequest;
import jakarta.servlet.http.HttpServletResponse;

import java.io.IOException;

@WebServlet("/FailServlet")
public class FailServlet extends HttpServlet {
    @Override
    protected void doPost(HttpServletRequest req, HttpServletResponse resp) throws ServletException, IOException {
        resp.setContentType("text/html;charset=utf-8");//用response在页面输出
        resp.getWriter().write("密码错误，登陆失败");
    }
}
//------------EmployeeDao类------------------
package com.ycx.Dao;
//操作数据库中Employee表，增删改查都在这个类里面

import com.ycx.domain.Employee;
import com.ycx.util.Druidutils;
import org.springframework.dao.DataAccessException;
import org.springframework.jdbc.core.BeanPropertyRowMapper;
import org.springframework.jdbc.core.JdbcTemplate;

public class EmployeeDao {
    private JdbcTemplate jt = new JdbcTemplate(Druidutils.getDataSource());//直接将这个对象设置成私有域，成员方法都可以调用这个对象

    public Employee login(Employee loginEmp) { //参数是只有username\password的Employee;返回的全参数的Employee
        try {
            String sql = "select * from Employee where username = ? and password = ?";
            Employee employee = jt.queryForObject(sql, new BeanPropertyRowMapper<>(Employee.class), loginEmp.getUsername(), loginEmp.getPassword());
            return employee;//将查询的结果（全部数据）封装成一个对象并且返回，关键要注意这里的第二个参数。
        } catch (DataAccessException e) {
            return null;
        }
    }
}
```

### 7.3 Response

* **HTTP协议的响应格式**

  * **响应行**

    * POST HTTP/1.1 200(状态码：setStatus(int sc)) OK
    * 状态码是服务器告诉客户端的请求响应的一个状态：
      * 200:成功
      * 302:重定向
      * 304:请求资源没有变化，使用缓存
      * 404:请求资源未找到，如路径错误 <font color='mediumseagreen'>客户端</font> 
      * 405:请求方式不支持
      * 500:服务器错误<font color='mediumseagreen'> 服务器端</font>

  * **响应头**

    * 头名称：值（设置响应头：**setHeader(String name,String value)**）

      * <font color='tomato'>content-Type</font>：服务器告诉客户端响应体数据格式、编码格式（可以处理解决中文乱码:）

      ```java
      response.setContentType("text/html;charset=utf-8");//设置中文编码,写在最前端
      ```

      * <font color='tomato'>content- disposition</font>：服务器告诉客户端以什么格式打开响应数据（in-line（默认）/attachment（以附件形式））

  * **响应空行**

  * **资源文件**:将资源文件发送给客户端浏览器进行解析

  * ==**防止中文乱码的两种形式的区别**==

    * request：request.setCharacterEncoding("utf-8"); // <font color='mediumseagreen'>将从request中取得的值、数据库中取得的值设置为UTF-8</font> 
    * response：response.setContentType("text/html;charset=utf-8")// <font color='mediumseagreen'>设置页面为UTF-8</font> 

#### 7.3.1 response的方法

* **获取输出流，并输出到客户端浏览器会话**

  * **PrintWriter getWriter( )：字符输出流**

    * writer() / print()

  * **servletOutputstream getOutputStream( )：字节输出流**

    * 字节流里面也直接可以用.getBytes输出文本

  * **设置响应图片**

    * new BufferedInputStream(new FileInputStream(...)) <font color='mediumseagreen'> ...路径要用ServletContext对象的getRealPath(相对路径)方法来获得。因为tomcat要将资源打包输出。所以一定要用绝对路径获取资源</font> 

    * response.getOutputStream()
    * 循环读写操作（os.write）

  * **设置缓存**

    * 缓存：不经常变化的数据可以合理设置缓存时间，避免浏览器频繁请求服务器。
    * void setDateHeader(String name,long time)  <font color='mediumseagreen'>name是"Expires"；注意这里时间是以毫秒为单位;这种方法已经不怎么用了</font>

  * **设置定时刷新**

    * setHeader(String name,String ) <font color='mediumseagreen'>"3;URL=/login.html"   (三秒钟跳到这个页面)</font> 

* **重定向（跳转资源、状态码是302）方法：response.sendRedirect("/路径")**

  <font color='tomato'> 1. response而不是request；2.可以跳转地址；3.两次请求：浏览器先请求Servlet A，取得重定向信号再请求Servlet B；4.重定向共享数据用session，先session.setAttribute()、再response.sendRedirect(绝对路径；5.请求转发是本质是传输req，rep两个对象。所以直接用req.setAttribute()。重定向只能用session作为第三者进行数据的存储和获取)。</font>

  * <font color='cornflowerblue'><u>（面试题）重定向/转发的区别</u>：</font>

    * <font color='cornflowerblue'>response/request</font>
    * <font color='cornflowerblue'>客户端/服务器端</font>
    * <font color='cornflowerblue'>速度慢/速度快</font>

    * <font color='cornflowerblue'>地址栏发生变化/ 地址栏不变</font> 
    * <font color='cornflowerblue'>可以访问其他不同服务器/ 只能访问当前的服务器资源</font>.
    * <font color='cornflowerblue'>两次请求（**用session**）/ 一次请求</font> 

  * 转发的路径：

    * 绝对路径：以/开头

    * 相对路径：以./ 开头（也可以省略）；../：后退一级目录

      

* **==练习：文件附件的下载==**

![webdownload](/Users/yuchenxi/Documents/《ycx-JavaWeb学习笔记》配图/webdownload.jpg)

```java
package com.ycx.responseDemo;

import jakarta.servlet.*;
import jakarta.servlet.http.*;
import jakarta.servlet.annotation.*;

import java.io.FileInputStream;
import java.io.IOException;

@WebServlet(name = "DownloadServlet", value = "/DownloadServlet")
public class DownloadServlet extends HttpServlet {
    @Override
    protected void doGet(HttpServletRequest request, HttpServletResponse response) throws ServletException, IOException {
        this.doPost(request, response);
    }

    @Override
    protected void doPost(HttpServletRequest request, HttpServletResponse response) throws ServletException, IOException {
        String filename = request.getParameter("filename"); //获取"a.jpg"这个value
        ServletContext application = getServletContext();//获取servletcontext对象，进一步获取绝对路径
        String realPath = application.getRealPath("/img1/" + filename);//通过拼接获取了绝对路径
        System.out.println(realPath);
        FileInputStream fis = new FileInputStream(realPath);//创建字节输入流将文件加载到内存
        ServletOutputStream sops = response.getOutputStream();//创建响应输出流准备将文件输出

        //关键步骤：设置响应头；不然的话只是内存中的文件只是在浏览器中打开，而不是作为附件下载
        String mimeType = application.getMimeType(filename);//获取文件的资源类型（text/jpg/gif...）
        response.setHeader("content-type",mimeType);//设置响应头类型
        response.setHeader("content-disposition","attachment;filename=fox2.jpg");//设置响应头打开方式

        byte[] b = new byte[1024];
        int len;
        while ((len = fis.read(b)) != -1) {
            sops.write(b, 0, len);
        }//将内存中的文件输出
        fis.close();
    }
}

//如果碰到中文名称无法显示的问题，则用工具类（工具类里面封装了各个浏览器的编码数据）-----步骤如下：

String agent =request.getHeader("user-agent");//先获取浏览器的信息
String filename=DownloadUtils.getFileName(agent,"中文文件名")
```



## 8. Cookie&Session

### 8.1 概念

**概念**：一次会话包含多次请求和响应（在浏览器访问服务器开始到访问服务器结束（或者是到了过期时间）是一次会话） <font color='mediumseagreen'>也就是一次登陆范围</font> 

**效果**：一次会话范围内的多次请求间，共享数据（比如从打开页面到结算是一次会话。不断加入购物车就是多次请求）

**种类**：<font color='mediumseagreen'>Java的技术,其他语言名称不同</font> 

*   客户端会话技术：cookie 
*   服务器端会话技术：session

### 8.2 cookie

#### 8.2.1 基础知识

* **概念：**绑定数据的信息块。客户端浏览器将数据发送给服务器端

* **步骤：**创建cookie，发送cookie，再获取已经绑定数据的cookie。

  * 创建：new cookie(String name,String value) //注意这里字符串不能有空格，否则会报错 <font color='mediumseagreen'>属性包含name、value、path、domain、maxaAge、version、comment</font>
  * 发送：response.add(Cookie cookie)
  * 获取：request.getCookie()：返回的是一个Cookie数组

* **实现原理**：<font color='mediumseagreen'>底层都是通过http的协议进行请求和响应</font>

  * 客户端浏览器接收到cookie（响应头）时候会将数据保存到浏览器上，并且在下一次发送请求 ·=的时候会

    将数据带给服务器（通过请求体：cookie:msg=hello）

#### 8.2.2 扩展知识

* **1.可以创建多个cookie并且多次add发送**
* **2.浏览器关闭的时候cookie被销毁**
  * 用setMaxAge(int seconds)实现持久化存储cookie <font color='mediumseagreen'>直接用方法操纵cookie，切记时间参数是秒</font>
    * 参数是正数：则存储到硬盘（哪怕浏览器关闭了，再次打开浏览器cookie也还存在），seconds是存活的时间。超过时间就会自动删除cookie  
    * 参数是负数：就是默认浏览器关闭cookie消失
    * 参数是零：直接删除留存在硬盘上的cookie信息 
* **3.cookie不可以直接在同一个服务器多个项目上共享**  <font color='tomato'>可以在同一个项目不同的servlet之间共享。和路径有关，在同一个母路径前缀下的子路径可以共享</font> 
  * 想要共享的话就要使用cookie.setPath(String path)：<font color='mediumseagreen'>path可以设置"/"，将共享范围设置到根目录</font>
  * 不同服务器共享cookie：将一级域名设置相同（setDomain(".baidu.com") tieba.baidu.com/news.baidu.com之间的cookie就可以共享）
* **4.特点：**
  * 存储在客户端（不是那么安全）
  * 浏览器对于*单个cookie的大小*（4kb）和*同一个域名*的cookie的数量有限制（20个）<font color='mediumseagreen'>所有网站加起来不能超过300个</font>：存储少量的不敏感数据。
  * <font color='tomato'>作用：在不登陆（登陆情况就是将数据保存服务端数据库上）的情况下使得服务器对客户端进行身份识别。可以保存一些设置数据之类的在本地硬盘上，下次可以继续用</font>

* **==练习：利用向客户端浏览器发送cookie来判断这是本次登录是否首次登陆，如果不是首次，在页面输出上次登陆日期==**

```java
package com.ycx.cookie.cookieTest;

import jakarta.servlet.*;
import jakarta.servlet.http.*;
import jakarta.servlet.annotation.*;

import java.io.IOException;
import java.io.PrintWriter;
import java.text.SimpleDateFormat;
import java.time.LocalDateTime;
import java.util.Date;

@WebServlet("/ct1")
public class ct1 extends HttpServlet {
    @Override
    protected void doGet(HttpServletRequest request, HttpServletResponse response) throws ServletException, IOException {
        this.doPost(request, response);
    }

    @Override
    protected void doPost(HttpServletRequest request, HttpServletResponse response) throws ServletException, IOException {
        response.setContentType("text/html;charset=utf-8");//设置中文编码,写在最前端
        boolean flag = false;//先提前把一个布尔类型的参数设置好为false。如果第一个if能顺利执行。直接break了。
        //如果第一个if语句没有顺利执行，那么这个flag就像一个信号（代表第一个if没执行的信号）一样通知第二个if执行

        Cookie[] cs = request.getCookies();//直接获取cookie。分为两种情况：能获取到包含lastTime的/获取不到包含lastTime的
        if (cs != null && cs.length > 0) {
            for (Cookie c : cs) {
                String s = c.getName();
                if ("lastTime".equals(s)) {
                    flag = true;
                    String value = c.getValue();//获取cookie的值，这里是日期
                    response.getWriter().write("<h1>欢迎回来，上次登陆时间是" + value+"</h1>");//表示上次已经登陆过，所以肯定有"lastTime"+"日期"
                    String ss = LocalDateTime.now().toString();//获取最新的时间字符串
                    c.setValue(ss);//此步骤将获取到的cookie对象的value值更新到本次时间（因为已经有cookie了，无需创建cookie对象）
                    response.addCookie(c);//发送cookie
                    break;
                }
            }
        }
        if (cs == null || cs.length == 0 || !flag) {
            //既然执行到了这个if，证明是首次访问，那么这里就必须要先创建cookie对象并且编写访问时间"lastTime"。并且作为cookie发送给客户端浏览器
            String ss1 = LocalDateTime.now().toString();
            Cookie c = new Cookie("lastTime", ss1);
            response.addCookie(c);
            c.setMaxAge(100);//设置cookie在硬盘上存活的时间
            response.getWriter().write("<h1>欢迎您首次登陆"+"</h1>");
        }
    }
}
/*
练习总结：
一.拿到一个需求首先要仔细分析，本需求核心是要向客户端浏览器发送cookie，而且是分为两种情况：1.确实是首次登陆；2.非首次登陆
二.已经经过判断后确定是首次登陆的话，在页面输出文字的同时也要创建新的cookie对象并且发送给客户端，以备下次使用。非首次登陆的话必须将cookie对象的value值更新。保证数据的实时性
三.其他：writer输出的字符串可以附加css样式、cookie包含的字符串不能有空格，否则浏览器会报500错误，代码是32（ASCII里面是空格）
*/
```

### 8.3 session

#### 8.3.1 基础知识

* **概念：**一种会话技术，在一次会话多次请求间共享数据，将**数据保存在服务器端HttpSession对象**中（区别于cookie）；
* **操作步骤：**
  * 1.无论是set方还是get方；都要先request.getSession()获取HttpSession对象
  * 2.发送方：setAttribute(String name,Object value)
  * 3.获取方法：getAttribute(String name)// 通过名字来获取值
* **原理：**
  * 两个session是同一个session；<font color='mediumseagreen'>服务器确保在一次会话范围内确保是同一个session</font>
  * session是依赖于cookie（请求体，响应头）
  * <font color='tomato'>确保原理：通过查询JESSSIONID找到同一个session对象</font>

#### 8.3.2 扩展知识

* **客户端关闭，**服务端不关闭的情况下：因为会话已经结束了，所以session不是同一个了；<font color='mediumseagreen'>想要相同的话，可以创建cookie，设置cookie的键是JESSIONID，值设置成上一个session的ID，同时让cookie存活下来。这里根据session是依赖于cookie  </font>
* **客户端不关闭**，服务端关闭的情况下：session对象被销毁。不是同一个；<font color='mediumseagreen'>必须确保数据不丢失，哪怕服务器关闭了。（session的钝化/活化）</font>
  * **session的钝化**：在服务器正常关闭之前，将session==对象序列化==至硬盘
  * **session的活化**：服务器启动之后，将session对象从硬盘反序列化
  * 在tomcat本地可以实现钝化和活化，在idea中无法实现活化（work目录被覆盖）
* **session被销毁的时机**
  * 1.服务器关闭; <font color='mediumseagreen'>毋庸置疑，会话已经结束</font> 
  * 2.session超过30min自动死亡；<font color='mediumseagreen'>在web.xml文件里面可以设置时间</font>
  * 3.调用invalidate()方法；<font color='mediumseagreen'>使无效</font> 
* 浏览器禁用cookie的话，session就无法使用。 
  * 解决方式：条件判断之后给用户提示信息，要求开启cookie；if(session==null){ ... } <font color='mediumseagreen'>推荐</font>
  * 解决方式：用方法对访问地址encodeURL()进行重写

#### 8.3.3 session的使用时机

* session区别于cookie，它是可以存储任意类型的文件，同时没有大小限制
* 比如重定向（两次请求）的时候不能使用request对象域共享数据，可以使用session。当然也可以使用ServletContext；<font color='mediumseagreen'>ServletContext范围太大，所以session居多</font> 

## 9. JSP

### 9.1 基础知识

* **概念**：Java Server Pages：一种动态网页标准，既可以定义html的标签，又可以定义Java代码（融合）<font color='mediumseagreen'>本质上就是servlet</font>
* **作用**：用于简化书写 <font color='mediumseagreen'>因为有大量的代码都被转成java文件的过程中自动书写了</font> 
* **原理**：JSP本质就是一个servlet文件（tomcat自动将JSP转化成 .java文件）（java文件内部将html标签都write输出了）
* **JSP指令**：配置JSP页面，导入资源文件
  * **格式**：<%@ page contentType="text/html;charset=UTF-8" language="java" %> <font color='mediumseagreen'>// <&@ 指令种类 属性名1=属性值1 属性名2=属性值2...%></font> 
  * **种类**
    * page：配置页面，就是相当于文档的声明，在JSP文件的开头设置   
      * contentType：相当于response.set ContentType()
      * import：给JSP里面的Java代码导包
      * errorPage：当前页面发生异常后会跳到指定页面 <font color='mediumseagreen'>这个用的多</font> 
      * isErrorPage：标识当前页面是否为错误页面 <font color='mediumseagreen'>isError是true的话才能用exception</font> 
    * taglib：导入资源 <font color='mediumseagreen'>类似于Java的导包，一般用于导入标签库</font> 
    * include：页面包含的
* **JSP注释**：<%--   --%>

### 9.2 JSP脚本 

* **脚本：**在JSP中定义Java代码的方式
* **种类：**
  * <%...%> ：在service中。<font color='mediumseagreen'>就是正常java代码中service方法里面可以写什么，这里也可以写什么</font> 
  * <%=...%>：会将内容直接输出至页面上（可以是字符串也可以是已经赋值的变量）。<font color='mediumseagreen'>就是可以和输出语句一致</font> 
  * <%! ...%>：会写在Java类的**成员变量**的位置。<font color='mediumseagreen'>这个不怎么用，定义成员变量会造成servlet线程不安全</font> <font color='tomato'>不加！就是声明局部变量</font> 

### 9.3 JSP内置对象

* 概念：在JSP中无需创建直接使用的对象 
* 种类：9大对象；<font color='mediumseagreen'>黑体的是域对象</font>
  * **request**：一次请求访问的多个资源（转发）请求对象
  * response：响应对象
  * out ：输出对象 ，JSP writer对象 
  * **application**：所有用户间共享数据 应用域对象 
  * **session**：一次会话的多个请求间共享数据
  * **pageContext**：本页面范围共享数据 <font color='mediumseagreen'>这个对象可以通过方法获取其他8个对象；这个是JSP独有对象，servlet中并没有</font>   
  * config：servlet的配置对象 
  * exception ：页面声明了isError才会有
  * page：相当于this
* **4大域对象详解**

|   *域对象名称*   |   *范围*   |         *级别*         |                   *备注*                   |
| :--------------: | :--------: | :--------------------: | :----------------------------------------: |
|  *pageContext*   | *页面范围* |   *最小，本页面使用*   |             *范围太小，使用少*             |
| *ServletRequest* | *请求范围* |  *一次请求/当期请求*   |     *请求转发之后，再次转发请求域丢失*     |
|  *HttpSession*   | *会话范围* | *一次会话多次请求使用* | *多次请求共享数据，但是不同客户端不能共享* |
| *ServletContext* | *应用范围* |  *最大，整个应用使用*  | *范围太大，如果对数据有修改需要做同步处理* |

### 9.4 MVC开发模式

* M：model： 操纵数据和逻辑，查询数据库，封装数据 <font color='mediumseagreen'>JavaBean</font> 
* V：view ：展示数据 <font color='mediumseagreen'>JSP</font> 
* C：controller： 处理请求和响应；调用模型查询数据；将数据交给view展示（中转站）<font color='mediumseagreen'>Servlet</font> 

![MVC模型](/Users/yuchenxi/Documents/《ycx-JavaWeb学习笔记》配图/MVC模型.jpg)

### 9.5 替换JSP中Java代码的两个技术

#### 9.5.1 EL表达式

* **概念：**Expression language 表达式语言

* **格式：**${ 1>4 }   //输出的是false  

* **注意事项：**JSP是默认支持EL表达式 <font color='mediumseagreen'>如果不想JSP输出EL表达式，就在page指令添加 isELIgnored=“true，如果是忽略单个EL表达式，就在前面添加\”</font>  <font color='tomato'>EL表达式中没有字符串的拼接</font>

* **使用方式**

  * **运算**

    *  算数、比较、逻辑运算符 

    *  空运算符：<font color='tomato'>empty  判断字符串、数组、集合是否为null以及长度是否为0：${empty list} //要想输出true，list要么为null，要么长度为0；判断不为空且长度大于0，直接是${ not empty list }</font> 

  ```jsp
  <% pageContext.setAttribute("gender","man"); %>
    <input type="radio" name="gender" value="男" ${gender=="man" ? "checked":"" }>男<br>
    <input type="radio" name="gender" value="女" ${gender=="woman" ? "checked":"" }>女
  
  <%--用三元运算进行表单多选的选择--%>
  ```

  * **获取值** <font color='mediumseagreen'>重要</font> 

    * EL表达式只能从域对象中获取值 <font color='tomato'>就是只能从4大域中取值，其他干不了</font> 

      * ${域名称.键名 } <font color='mediumseagreen'>四大域：1.pageScope；2.requestScope；3.sessionScope；4.applicationScope</font> 

        特点：获取值如果什么都没获取到的话**就输出空字符串而不是输出null** <font color='mediumseagreen'>安全方便无需判断是否为null且保证了页面的有序和简洁</font> 

      * ${键名}：依次从最小的的域开始查找（p<r<s<a）是否有该键对应的值，直到找到为止。<font color='mediumseagreen'>这样哪怕不同的域的键名相同都行，系统会依次自己查找匹配</font>  <font color='tomato'>这种格式用的比较多</font> 

    * 从对象中获取值：${域名称.键名.属性名}

    ```jsp
    <%
        Person p = new Person("xx", 23, new Date());
        request.setAttribute("u", p); //无论如何这里也要用四大域进行set
    %>
    
    ${u.name}<br> //其实是调用的getName()方法,所以哪怕没有name属性，只要有这个方法，也可直接输出
    ${u.age}<br>
    ${u.birthday}<br>
    <h1>${u.birString}</h1> <%--这个就是自己在类中创建的方法--%>
    ```

    * <font color='tomato'>如果是从外部servlet创建request/session，一定要转发/重定向到JSP中，才能被接收数据并且进行下一步操作</font>
    * list集合、map集合、数组
      * ${list[0]}  //直接输出0索引的值，因为ArrayList集合的底层也是数组，所以输出格式和数组一致
      * ${map.name}//map.键名
      * ${arr[0]} //和普通数组一样，但是哪怕数组下标越界，也不会报空指针异常

* **EL表达式中隐式对象**  <font color='mediumseagreen'>隐式对象是无需创建直接拿过来用的对象</font> 

  * pageContext <font color='tomato'>pageContext.request.contextPath()：动态获取虚拟目录，较为重要</font> 

####  9.5.2  JSTL标签

* 概念：简化和替换JSP页面上的Java代码
* 常用种类：
  * if 
  * choose
  * foreach

### 9.6 三层架构

* 界面层（控制器、视图）<font color='red'>接收用户提交的参数，封装数据，调用业务逻辑层进行处理，转发给JSP页面             </font>业务逻辑层（service）<font color='darkorange'>组合dao层中的简单方法，形成复杂的业务逻辑操作 </font>                                                  数据访问层（dao）<font color='blue'>只是定义对数据库的CRUD</font>



## 10. Filter&Listener

### 10.1 Filter过滤器

#### 10.1.1概念

* 概念：在请求发出访问资源的过程中，过滤器将其拦截，并且完成一些特殊功能。

* 功能种类：
  * 在访问的各种资源中，如果资源中有相同的需求，可以在过滤器中完成，比如在访问增删查改信息的时候，如果请求没有登陆，过滤器就会将其拦截。
  * 又例如将字符编码设置放在过滤器中，简化代码；将用户发言进行关键字过滤等
* 实现步骤：
  * 实现Filter接口
  * 重写方法
  * 配置拦截路径@Webfilter("/...")

#### 10.1.2 扩展内容

* **过滤器的生命周期**

  * innit、destroy方法都是执行一次。分别是加载资源、释放资源
  * doFilter方法可以执行多次 <font color='mediumseagreen'> 就和service类似</font> 

* **过滤器执行流程**

  * **在实行过滤之前需要将：ServletRequest==强制转换==为HttpRequest、 ServletResponse强制转换为HttpResponse**

  * 对request进行过滤操作处理 <font color='mediumseagreen'>在请求通过关卡之前</font> 

  * ```java
    chain.doFilter(request, response); //放行操作
    ```

  * 对response进行增强处理 <font color='mediumseagreen'>在响应返回通过关卡之前</font> 

* **过滤器配置详解**

  * **拦截路径配置**
    * 拦截具体资源：”/index.JSP" <font color='mediumseagreen'>直接拦截对此文件的情求</font> 
    * 拦截目录"/user/*"<font color='mediumseagreen'> 拦截user目录下的所有文件</font> 
    * 拦截文件类型 "*.JSP"  <font color='mediumseagreen'>拦截所有的JSP文件</font>  <font color='tomato'>注意这里没有/</font>
    * 拦截所有 "/*" <font color='mediumseagreen'>暴力拦截所有的文件</font> 
  * **拦截方式方式配置**
    * **注解配置**
      * dispatcherTypes（5种）：REQUEST、FORWARD<font color='mediumseagreen'>这两个最重要</font> 、ERROR、ASYNC、INCLUDE 
      * REQUESYT：添加此注解的话，**浏览器直接请求的时候会被进行过滤，但是通过服务器内部转发请求的时候并不会被过滤**
      * FORWARD：添加此注解的时候，**只有进行转发操作的时候过滤器才会执行，直接访问不会被执行**  <font color='tomato'>同时通过{ , }设置多个不同的过滤方式</font> 
    * **xml配置**

* **过滤器链（多个过滤器）**

  * 多个过滤器执行的**顺序**：根据类名的字符串比较顺序来执行；字符串值小的先执行
  * 在XML文件配置的话，就根据配置的前后顺序来执行

### 10.2 Listener监听器

<font color='cornflowerblue'>（面试题）23种设计模式中的观察者设计模式：事件、事件源、监听器</font>

* **用途：主要是监听出了pageContext之外的三个域对象创建销毁以及各自的属性变化（删除、添加、更改）**

* **事件监听机制概念**
  * 事件：点击按钮（一件事情）
  * 事件源：按钮本身
  * 监听器：一个对象
    * 注册监听：将前三者绑定在一起，当事件发生后，执行监听器代码 <font color='mediumseagreen'>监听器无需执行，自动触发</font> 
* ***ServletContextListener接口** <font color='mediumseagreen'>这个是监听域对象的监听器中的一个</font>  <font color='tomato'>较为重要</font>
  * ServletContext初始化后启动的方法
    * contextInitialized(ServletContextEvent sce )方法 <font color='mediumseagreen'>一旦创建servletContext对象创建（服务器自动创建），自动启动</font>
  * ServletContext销毁之前启动的方法
    * contextDestroied( ) <font color='mediumseagreen'>服务器正常关闭，自动启动方法</font> 
* **ServletContextAttributeListener接口** <font color='mediumseagreen'>监听到属性变化监听器中的一个</font> 
  * attributeRemoved/Replaced/Added() 方法：属性的移除、替换、添加

* **使用步骤**
  * 实现接口
  * 覆盖两个方法
  * 配置 <font color='mediumseagreen'>直接@WebListener</font> 

* ==练习：编写聊天室。控制器，过滤器，监听器，JSP，EL表达式，session，application==

![ChatProgram](/Users/yuchenxi/Documents/《ycx-JavaWeb学习笔记》配图/ChatProgram.jpg)

```java
package com.ycx.day04.Servlet;

import jakarta.servlet.*;
import jakarta.servlet.http.*;
import jakarta.servlet.annotation.*;

import java.io.IOException;
import java.text.SimpleDateFormat;
import java.util.ArrayList;
import java.util.Date;
import java.util.List;

@WebServlet("/doSendServlet")
public class doSendServlet extends HttpServlet {
    @Override
    protected void doGet(HttpServletRequest request, HttpServletResponse response) throws ServletException, IOException {
        this.doPost(request, response);
    }

    @Override
    protected void doPost(HttpServletRequest request, HttpServletResponse response) throws ServletException, IOException {
        String message = request.getParameter("message");
        HttpSession session = request.getSession();
        String username = (String) session.getAttribute("username");
        Date date = new Date();
        SimpleDateFormat simpleDateFormat = new SimpleDateFormat("yyyy-MM-dd HH:mm:ss");
        String time = simpleDateFormat.format(date);
        String message1=username+"："+message+"   "+time;//将信息拼接

        ServletContext application = getServletContext();
        List<String> list = (List<String>) application.getAttribute("list");//如果是第一次接收就是null
        if (list==null){
             list = new ArrayList<String>(); //第一次的话就创建集合
        }
        list.add(message1);//要么是新建集合，要么是从application获取的集合。添加拼接好的元素

        application.setAttribute("list",list);//再将list放进application中
        response.sendRedirect("send.jsp");//重定向回去
    }
}

----------------------  package com.ycx.chatprogram;import package com.ycx.day04.Servlet;

import jakarta.servlet.*;
import jakarta.servlet.http.*;
import jakarta.servlet.annotation.*;

import java.io.IOException;

@WebServlet("/doLoginServlet")
public class doLoginServlet extends HttpServlet {
    @Override
    protected void doGet(HttpServletRequest request, HttpServletResponse response) throws ServletException, IOException {
        this.doPost(request, response);
    }

    @Override
    protected void doPost(HttpServletRequest request, HttpServletResponse response) throws ServletException, IOException {
        String username = request.getParameter("username");
        HttpSession session = request.getSession();
        session.setAttribute("username",username);
        response.sendRedirect("index.jsp");
    }
}
```

## 11. MyBatis

### 11.1 概述以及操作步骤

* **概念**：基于Java的持久型框架，内部封装了JDBC。让开发者只需要关注sql语句本身

* **对象关系映射**：解决面向对象和关系型数据库不匹配的问题，数据表---类，字段---属性，数据---对象

* **操作步骤**：

  * 导入三个jar包
  * 编写MyBatisConfig.xml配置文件（可以直接关联jdbc.properties)配置数据库信息以链接数据库
  * 编写StudentMapper.xml映射文件，在此文件里面编写sql语句

  ```xml
  <?xml version="1.0" encoding="UTF-8" ?>
  <!--MyBatis的DTD约束-->
  <!DOCTYPE mapper
          PUBLIC "-//mybatis.org//DTD Mapper 3.0//EN"
          "http://mybatis.org/dtd/mybatis-3-mapper.dtd">
  
  <!--
      mapper：核心根标签
      namespace属性：名称空间
  -->
  <mapper namespace="StudentMapper">  <!--命名空间-->
      <!--
          select：查询功能的标签
          id属性：唯一标识
          resultType属性：指定结果映射对象类型
          parameterType属性：指定参数映射对象类型
      -->
      <select id="selectAll" resultType="com.ycx.MyBatisTest.bean.student">
          SELECT * FROM student
      </select>
  
      <insert id="insertStudent" parameterType="com.ycx.MyBatisTest.bean.student">
          insert into student values (#{id},#{name},#{age})   /*这里并没有写具体的要传入的参数，只是写了相当于占位符*/
      </insert>
  
      <update id="updateStudent" parameterType="com.ycx.MyBatisTest.bean.student"> /*是因为要将数据封装到对象里面，然后再将数据从对象中拿出来*/
          update student set name=#{name},age=#{age} where id=#{id}
      </update>
      
      <delete id="deleteStudent" parameterType="java.lang.Integer">
          delete from student where id = #{id}
      </delete>
  
  </mapper>
  ```

* **注意事项：**
  * 除了delete语句，其他三个语句的paramterType都是Javabean封装类，如student·，delete是索引参数的种类，比如Integer类的id；<font color='mediumseagreen'>其实mybatis已经给Integer定义别名为int，其他的几个类型类似</font> 
  * 可变参数不是JDBC中的？，而是#{ },大括号里面填写参数名称，要和封装的对象的域以及数据库汇总的参数一致；

### 11.2 Mybatis的Dao层实现

* **概念**：代理开发模式，就是自己编写接口，由mybatis进行方法的实现，获取多态对象，用多态对象调用对于id的sql语句方法，获取返回的对象。<font color='tomato'>只需要编写mappper接口即可，sqlSession.getMapper(接口.class)自动将其中方法重写。我们只需要在service层写个serivce接口、实现类即可，（接口的方法是和mapper方法一致，实现类最重要的就是sqlSession.getMapper(接口.class)，获取mapper对象）</font> 

* **代理模式的要求**：

  * 1.mapper.xml里面的namespace=接口的全类名对象
  * 2.编写mapper.xml中的sql语句方法，id、parameterType、resultType一致
  * 3.再service类中用sqlsession调用getMapper(接口的class)，返回对象
  * 4.用对象调用sql语句方法

  ```java
  InputStream is = Resources.getResourceAsStream("MyBatisConfig.xml"); //获取流对象
  SqlSessionFactory sqlSessionFactory = new SqlSessionFactoryBuilder().build(is);//工厂类
  SqlSession sqlSession = sqlSessionFactory.openSession();//前三步都是一样的，都是为了获取SqlSession对象
  studentDao mapper = sqlSession.getMapper(studentDao.class); //配置好代理，直接使用这个方法用接口获取对象
  ```

* **相关类详解**：

  * **Resoures**：加载资源的工具类，通过类加载器返回指定资源的字节输入流

  * **SqlSessionFactoryBuilder**：获取工厂对象的功能类，通过指定资源字节输入流获取SqlSession工厂对象

  * **SqlSessionFactory**：获取SqlSession构建者对象的工厂接口  <font color='mediumseagreen'>有两个方法</font> 

    * openSession()：获取SqlSession对象，开启手动提交事务
    * **openSession(boolean autoCommit) ：参数为true的话，就是开启自动提交事务**

  * **Sqlsession**：构建者对象接口 <font color='mediumseagreen'>打开一个数据库连接池连接</font> 
    * 获取代理mapper  <font color='tomato'>这个就是接口代理</font> 
    
    * 直接执行sql方法
    * 管理事务：commit、rollback
  
* **parma注解**

  *  作用：给多个参数起名字
  * 使用步骤：在mapper接口的参数前面：**(@parma("a") String name,@parma("b") int age)**,再次使用参数的时候直接用新的参数名即可。<font color='tomato'>正常参数是bean类对象， mybatis会自动解析对象属性当作参数和xml文件相匹配。如果是用@parama来一一设置参数的话，xml文件中就要设置对应相同名称的参数</font> 

### 11.3 动态sql语句

* **概念**：根据实体类的不同取值，使用不同的sql语句进行查询，就是对同一个id，sql语句并不是固定的，而是动态的。比如可以用**用户名**或者**账号**查询登陆的时候，用户输入其中一个即可，这时候再mapper.xml文件中就要求进行if非空判断

* **集中动态sql语句类型：**

  * **if判断**  <font color='mediumseagreen'>利用where</font> 

  ```xml
   <select id="selectByCondition" parameterType="com.ycx.MyBatisTest.bean.student"
              resultType="com.ycx.MyBatisTest.bean.student">
          select * from student
          <where>
              <if test="id!=null">
                  and id=#{id}
              </if>
              <if test="name!=null">
                  and name=#{name}
              </if>
              <if test="age!=null">
                  and age=#{age}
              </if>
          </where>
      </select>
  这个就是进行where if判断的具体格式
  ```

  <font color='tomato'>解决mybatis中文无法检索与录入的方式：url=jdbc:mysql://localhost:3306/MyBatisTest1?useUnicode=true&characterEncoding=UTF-8</font>

  * **foreach循环 ** <font color='mediumseagreen'>in、not in、内连接查询会用上</font> 

  ```xml
  <!--集合就用list，数组就用array，注意#{id}不能丢-->
      <select id="selectByIds" parameterType="list" resultType="com.practice01.bean.Person"> 
          SELECT *  FROM person
          <where>
           <foreach collection="list" open="id in(" item="id" separator="," close=")" >
              #{id}
           </foreach>
          </where>
      </select>
  ```

  * **sql语句的抽取**  <font color='mediumseagreen'>将重复的sql语句抽取出来，方便使用和更改</font> 

  ```xml
  <sql id="selectStudent"> select * from student </sql> <!--设置被抽取的sql语句-->
  <include refid="selectStudent"></include> <!--插入被抽取的语句-->
  ```

### 11.4 mybatis核心配置文件深入理解

#### 11.4.1 TypeHandler标签

* **概念**：TypeHandlers标签：处理类型转换，在Java和mysql之间相同的类型可能具体名称不同，如String和Varchar，类处理器负责处理二者的转换，也可以定义自己的类处理器标签或者覆盖已存在的标签	

<img src="/Users/yuchenxi/Documents/《ycx-JavaWeb学习笔记》配图/mybatis核心配置文件信息.png" alt="mybatis核心配置文件信息" style="zoom:50%;" />

* **具体实现步骤**： <font color='mediumseagreen'>这里的例子是将Java的Date类在存入数据库的时候转成varchar类的从1970开始的毫秒值，再从数据库放回Java的时候再次转成Date类</font> 
  * 1.先定义转换类，要继承类BaseTypeHandler< T >，范型是Java中想要转换的类型
  * 2.覆盖方法
  * 3.在mybatis核心配置文件中注册

```java
package com.ycx.MyBatisTest.Test;

import org.apache.ibatis.type.BaseTypeHandler;
import org.apache.ibatis.type.JdbcType;
import org.apache.ibatis.type.TypeHandler;

import java.sql.CallableStatement;
import java.sql.PreparedStatement;
import java.sql.ResultSet;
import java.sql.SQLException;
import java.util.Date;

public class TestTypeHandler extends BaseTypeHandler<Date> { //此处泛型的选择自动决定了实现方法的Object
    @Override //将java类型转成sql类型
    public void setNonNullParameter(PreparedStatement preparedStatement, int i, Date date, JdbcType jdbcType) throws SQLException {
        long time = date.getTime(); //将date对象转成long类型
        preparedStatement.setLong(i,time);//i是当前参数的位置
    }

    @Override //将sql类型转成java类型
    public Date getNullableResult(ResultSet resultSet, String s) throws SQLException {
        long aLong = resultSet.getLong(s); //s是字段名称
        Date date = new Date(aLong);
        return date;
    }

    @Override
    public Date getNullableResult(ResultSet resultSet, int i) throws SQLException {
        long aLong = resultSet.getLong(i); //这里将s换成了i，由名称变成了索引位置
        Date date = new Date(aLong);
        return date;
    }

    @Override
    public Date getNullableResult(CallableStatement callableStatement, int i) throws SQLException {
        long aLong = callableStatement.getLong(i);
        Date date = new Date(aLong);
        return date;
    }
}
//这是类的编写过程，完了之后要再核心配置文件中添加:
<typeHandlers>
        <typeHandler handler="com.ycx.MyBatisTest.Test.TestTypeHandler"></typeHandler>
    </typeHandlers>
```

#### 11.4.2 Plugins标签

* **PageHelper分页插件的使用**

  * **概念**：将复杂的分页操作进行封装，从而使得分页功能变得简单。通过配置config核心配置文件

  * **实现步骤**：

    * 导入jar包
    * 在核心配置xml文件添加数据

    ```xml
     <plugins>
            <plugin interceptor="com.github.pagehelper.PageInterceptor"></plugin>
        </plugins>
    ```

    * 测试文件中调用静态方法 PageHelper.startPage(当前页码,每页数据数量); <font color='mediumseagreen'>此方法要在用mapper对象调用sql方法之前使用</font>

* **新建PageInfo对象来获取分页参数**

  ```java
  PageInfo<student> info = new PageInfo<>(stus); //新建对象，再调用封装的方法
  info.getTotal(); //总条数
  info.getPages();//总页数
  info.getPageNum();//每一页的条数
  info.getPrePage(); //获取上一页 nextPage下一页
  isFirstPage();//是否是第一页
  isLastPage()//是否是最后一页
  ```

### 11.5 MyBatis多表查询

* **一对一** 

  * **操作步骤**： <font color='mediumseagreen'>需要编写的映射文件，编写接口，两个javabean（主属关系），测试类</font>

    * 建立javabean类，与数据库中的两个表的属性对应（注意这两个表已经进行了外键约束操作）<font color='tomato'>这里要注意外键的那个属性所对应的javabean属性是被约束的对象（被约束的对象是主键被绑定的那一个）</font> 

    * 创建映射文件Mapper.xml  <font color='tomato'>核心重点就是编写映射文件</font> 

      * 在映射文件中确定namespace。 <font color='mediumseagreen'>namespace是编写的接口的全类名</font> 
      * 配置resultMap标签（id是唯一标识，type是Javabean类名），id和selec标签中的resultMap一致；<font color='tomato'>注意这里是resultMap</font>
      * 在resultMap标签内部，**id是配置主键字段**，**result是配置非主键字段**，<u>column是数据库表中列名</u>，<u>property是javabean中相对应的属性名</u>。
      * 属性对象（被外键约束的）要用association标签包裹，*property是javabean属性名*，*javaType是javabean的类名*

      ```xml
      <?xml version="1.0" encoding="UTF-8" ?>
      <!--MyBatis的DTD约束-->
      <!DOCTYPE mapper
              PUBLIC "-//mybatis.org//DTD Mapper 3.0//EN"
              "http://mybatis.org/dtd/mybatis-3-mapper.dtd">
      
          <mapper namespace="com.ycx.duobiaochaxunTest.OneToOneMapper">
          <!--配置数据库字段和对象属性（主要对象card和属性对象user）映射关系-->
          <resultMap id="oneToOne" type="card">
              
              <id column="cid" property="id"/> <!--这个id标签是配置主对象主键的-->
              <result column="number" property="number" /> <!--这个是数据库card表格的number字段对应java的card对象的number属性-->
      
              <association property="U" javaType="USER"> <!--属性对象的配置要单独用association配置，因为属性对象已经是单独的一张表格，需要"联合"-->
             <id column="id" property="id"/> <!--依然是主键是用id进行编写-->
              <result column="name" property="name"/>
                  <result column="age" property="age"/>
              </association>
              
          </resultMap>
      
      
          <select id="selectAll" resultMap="oneToOne">
              SELECT c.id cid,c.number,u.id,u.name,u.age FROM USER u,card c WHERE u.id=c.uid
          </select>
      
          </mapper>
      ```

    * 将映射文件绑定录入到核心配置文件Config.xml中

      ```xml 
      <mappers>
              <mapper resource="com/ycx/OneToOne/OneToOneMapper.xml"></mapper>
          </mappers>
      ```

* **一对多**

  * **注意事项**：

    * 在一对多关系里面，约束表格的属性值是对应多个被约束表格的属性值，也就List集合容器，要将约束表格的javabean类的域中添加**List集合属性**

    * 一对多是**collection**标签，区别于一对一的association标签
    * 其他编写mapper.xml文件以及与核心文件的绑定、接口的编写与一对一一致 <font color='mediumseagreen'>注意接口的编写的select all返回的集合的范型对象是约束表而不是被约束表</font> 

* **多对多**

  * **注意事项**：
    * 与一对多类似，但是虽然mysql中创建了第三者表格，但是Javabean类还是两个主表格
    * 多对多的两表格关系是平等的，比如对于表格emp、course，既可以是emp.java里面的实例域是List< course>，也可以是course.java的实例域List< emp>

* **==例子：在项目1传智健康中，页面需要通过套餐id获取多对多关系的检查组信息，再通过检查组信息获取多对多的检查项信息==**

  * **分析**：这个是两层套娃的多对多sql查询，涉及到resultmap配置的编写、sql语句的编写等

  * 具体代码：

    ```xml
    <!--在SetmealDao.xml（套餐）中。。。。。。。-->
     <!--resultmap是实体类和字段的关系，单独抽取出来，干干净净明明白白-->
        <resultMap id="baseResultMap"       type="com.itheima.pojo.Setmeal">
            <id column="id" property="id"/>
            <result column="name" property="name"/>
            <result column="code" property="code"/>
            <result column="helpCode" property="helpCode"/>
            <result column="sex" property="sex"/>
            <result column="age" property="age"/>
            <result column="price" property="price"/>
            <result column="remark" property="remark"/>
            <result column="attention" property="attention"/>
            <result column="img" property="img"/>
        </resultMap>
    
        <!--这个是继承上面那一大段，本段是最重要的-->
        <!--注意多对多是collection而不是association,并且property是java类的域名-->
        <!--先通过套餐查询检查组（findCheckGroupById），再通过检查组查检查项，套娃-->
        <resultMap id="findByIdResultMap" type="com.itheima.pojo.Setmeal" extends="baseResultMap"><!--本条sql第二天-->
            <collection
                    property="checkGroups" //这个就查出来的结果，是域名
                    javaType="ArrayList" //是哪个Java类
                    ofType="com.itheima.pojo.CheckGroup" //在哪个包
                    column="id" //        select="com.itheima.dao.CheckGroupDao.findCheckGroupById">
            </collection>
        </resultMap>
    ```

    

### 11.6 MyBatis注解开发

* **概念**：省去映射配置文件，只要在接口上添加注解即可，简化配置步骤 <font color='tomato'>包括增删改和三种查询</font> 

* **具体操作步骤**：

  * 1.编写接口，在接口的抽象方法上面添加注解，注解的内容是sql语句 <font color='tomato'>注意只需要接口即可，无需实现类，并且无需xml文件</font> 

  * 2.在核心配置文件中用mappers里面的package标签绑定接口所在的包名
  * 3.在测试类中前三步一样<font color='mediumseagreen'>（加载流文件，获取工厂类，获取sqlsession类）</font>,再用sqlSession.getMapper(接口名.class)获取mapper对象，再调用sql方法 <font color='tomato'>注意添加信息的时候一定要记得提交事务，或者设置自动提交</font> 

* **注解的具体种类**：

  ```java
   @Select("select * from emp") //查询数据
  @Insert("insert into emp values(#{id},#{name},#{age})")//添加数据
  @Options(useGeneratedKeys = true,keyColumn = "id",keyProperty = "id")//返回自增结果
  @Update("update emp set name=#{name},age=#{age} where id =#{id}")//修改数据
  @Delete("delete from emp where id=#{id}")//删除数据
  
  扩展：也可以用@parm来指定具体参数，而不用封装对象
    @Delete("delete from emp1 where id =#{idd}")
      Integer deleteEmp(@Param("idd") Integer id); 
  ```

* **利用注解进行多表操作**：

  * **一对一**

    * 注解查询多表，test类的编写和javabean类的编写和xml的多表查询基本一致
    * 最主要的是两个mapper接口的编写 <font color='tomato'>其中约束表格的注解编写最复杂，被约束表格只要直接按照主键查询就行</font>

    ```java
    public interface CardMapper {
        @Select("select * from card")
        @Results({//注意这里的{}
                @Result(column = "id", property = "id"), //依旧是colum代表数据库的列，property代表javabean的属性
                @Result(column = "number", property = "number"),
                @Result(
                        property = "user", //javabean类的user对象属性的属性名
                        javaType = user.class,
                        column = "uid",//按照这个外键约束进行查找user表格数据
                        one = @One(select =  "com.ycx.annotation.oto.UserMapper.selectById")//一对一的固定格式，UserMapper接口的selectById方法
                )
        })
        List<card> selectAll();
    }
    ----------------------------------------------------------
    public interface UserMapper {
        @Select("select * from user where id=#{id}")
        user selectById(Integer id);
    } //被约束表格
    
    ```

  * **一对多**

    * 和一对一步骤差不多，就是注意区分约束表与被约束的表格以及对应的javabean类，在约束的javabean类添加被约束的表格javabean类的List对象属性
    * <font color='mediumseagreen'>注意被约束的StudentMapper里里面注解内容的编写：cid=#{cid}  <font color='tomato'>student表格是cid指向clazz表的提供的id</font></font> 

    ```java
    public interface ClazzMapper {
        @Select("select * from clazz")
        @Results({
                @Result(column = "id" ,property = "id"),
                @Result(column = "name" ,property = "name"),
                @Result(
                        property = "students",//对象属性的名称
                        javaType = List.class,//对象属性的类
                        column = "id", //注意这里是clazz自己的id,本质上是要根据id=cid进行匹配
                        many = @Many(select = "com.ycx.annotation.otm.StudentMapper.selectByCid")
                )
        })
        List<Clazz> selectAll();
    }
    ------------------------------------------------------------
    public interface StudentMapper {
        @Select("select * from student where cid=#{id}")
        List<Student> selectByCid(Integer id); //注意这里是cid，是按照cid来查询数据
    }
    ```

  * **多对多**

    * mapper接口的注解编写以及javabean类的编写基本和一对多一致
    * 最主要的是被当作集合属性的javabean类（这里的例子是course类）的mapper接口的注解编写方式

    ```java
    public interface empMapper {
        @Select("select * from emp")
        @Results({
                @Result(column = "id" ,property = "id"),
                @Result(column = "name" ,property = "name"),
                @Result(column = "age" ,property = "age"),
                @Result(
                        property = "courses",//对象属性的名称
                        javaType = List.class,//对象属性的类
                        column = "id", //
                        many = @Many(select = "com.ycx.annotation.mtm.courseMapper.selectByEid")
                )
        })
        List<emp> selectAll();
    }
    -------------------------------------------------------------
    public interface courseMapper {
        @Select("SELECT c.id,c.name FROM e_c ec,course c WHERE ec.cid=c.id AND ec.eid=#{id}")//根据eid的不同进行多次查询
        List<course> selectByEid(Integer id);
    }
    ```

## 12. JQuey

### 12.1 概念与使用

* **概念**：JS的框架，本质上是一些JS文件，封装了JS的代码，能简化编写JS代码的操作

* **使用步骤**：

  * 导入JQuey文件（这回不是jar包了，是js文件）

  * ```javascript
    <script src="../js/jquery-3.3.1.min.js"></script> <!--在head处引入JQuery文件-->
    ```

  * ```javascript
    <script>
        var a = $("#a");
        alert(a.html());
    </script> /*用$获取对象*/
    ```

*  **JQuey对象与JS对象的区别与转换**

  * **方法不通用**：比如JS对象的innerHtml对应的是JQuery对象html()
  * **可以相互转换**：JS——>JQuery: $( JS对象 )、 JQuery——>JS:JQuery对象[索引]

* **JQuey事件绑定**

  * **调用click函数**

  * **入口函数** <font color='mediumseagreen'>script定义在head里面</font> 

    ```javascript
    <script>
        $(function () {
            $("#a1").click(
                function () {
                    alert("弹出来一段话");
                });
        });  //就是将单击事件裹在一个$(function(){...})匿名函数里面，此代码会在body代码执行之后执行。区别于window.onload，此方法可以定义多次
    </script>
    ```

### 12.2 选择器

* **概念**：获取有相似特征的元素/标签

* **5种选择器**：

  * **基本选择器** <font color='mediumseagreen'>这个基本和css那三个差不多</font>  <font color='tomato'>如果是并集的话：$("div,#xxx ")</font> 
    * 元素选择器：$("div") <font color='mediumseagreen'>div元素的全部选上</font> 
    * id选择器：$("#xxx") <font color='mediumseagreen'>id=“xxx”的选上</font> 
    * 类选择器：$(".yyy") <font color='mediumseagreen'>class=”yyy“的选上</font> 
    
  * **层级选择器**
  
    * 后代选择器：$("A B") <font color='mediumseagreen'>选择一个元素以及其所有后代的元素</font> 
    * 子选择器：$("A>B") <font color='mediumseagreen'>只选择一个元素和其子元素（孙子、曾孙子不会选上）</font> 
  
  * **属性选择器**
  
    * 有aaa属性的div：$("div[aaa]") <font color='mediumseagreen'>只要有aaa属性即可，无所谓aaa的值等于什么</font>
    * 有aaa属性且等于111的div：$("div[aaa='111']") <font color='mediumseagreen'>不等于就是!=</font> 
    * 有aaa属性且值是以c开头的div：$("div[aaa^='c']")<font color='mediumseagreen'>联动正则表达式^开始，$结束，在这里*是包含</font> 
  
  * **过滤选择器** <font color='tomato'>过滤选择器都有  :  </font> <font color='mediumseagreen'>并且与索引有关</font> 
  
    * $("div:first") / $("div:last")：选择第一个/最后一个div
  
    * $("div:not(.xxx)")：选择class类不是xxx的元素
    * $("div:even") / $("div:odd")：选择第偶数个元素/第奇数个元素
    * $("div:lt(5)") / $("div:eq(5)") / $("div:gt(5)")：选择索引小于5/等于5/大于5的元素
  
  * **表单过滤选择器**  <font color='mediumseagreen'>关于表单属性的一些操作，如果是表单A就往往是input</font> 
  
    * $("A:enabled")：可用元素
    * $("A:disabled")：不可用元素
    * $("A:checkbox")：单选/复选
    * $("A:selected")：下拉列表元素选择 <font color='mediumseagreen'>这里往往是  #A > option 一起使用</font> 

### 12.3 DOM操作

* **内容操作**：三个方法 <font color='mediumseagreen'>DOM操作就是已经选择了，要对他们进行操作</font> 
  * html( )：获取/设置元素的标签体内容
  * text( )：获取/设置元素的标签体纯文本内容
  * val( )：获取/设置元素的value属性值
  
* **属性操作**：

  * **一般属性** <font color='mediumseagreen'>固有属性用prop，自定义属性用attr</font> 
    * attr() / prop() ：获取/设置元素属性 <font color='tomato'>设置值的话直接attr(name,value)</font> 
    * removeAttr() / removeProp() : 删除属性

  * **class属性**
    * addClass()：添加class属性
    * removeClass()：去除class属性
    * toggleClass()：切换class属性  <font color='mediumseagreen'>toggleClass("xxx"),若存在xxx的class属性，则删除，若无则添加</font> 

* **CRUD操作** <font color='mediumseagreen'>操作对象</font> 

==**案例：全选/全不选/反选**===

```javascript
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <title>选择</title>
    <script src="../js/jquery-3.3.1.min.js"></script>
</head>
<body>
<button type="button" id="selectAll">全选</button>
<button type="button" id="selectNone">全不选</button>
<button type="button" id="selectReverse">反选</button>
<br>
男：<input type="checkbox" class="item"><br>
女：<input type="checkbox" class="item"><br>
其他：<input type="checkbox" class="item">

</body>
<script>
    $("#selectAll").click( /*创建单击事件，单击事件是绑定函数的*/
        function () {
            $(".item").prop("checked", true); /*获取所有的class是item的对象数组，并且设置其checked的属性为true*/
        });

    $("#selectNone").click(
        function () {
            $(".item").prop("checked", false);
        });
    $("#selectReverse").click(
        function () {
            let x = $(".item"); /*获取对象数组*/
            x.each( /*用each获取数组中的每一个元素*/
                function () {
                    $(this).prop("checked", !$(this).prop("checked")); /*this代表的就是每一个元素，设置对象属性，获取属性并且取反*/
                }
            );
        }
    );
</script>
</html>
```

==**案例：循环图片**==

```javascript
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <title>随机选择图片</title>
    <script src="../js/jquery-3.3.1.min.js"></script>
</head>
<body>
<div style="width: 50px;height: 50px;border: solid red">
    <img src="pop/13.png" id="small" style="width: 50px;height: 50px">
</div>
<div style="width: 250px;height: 250px;border: solid gold">
    <img src="" id="big" style="width: 250px;height: 250px">
</div>
<input type="button" id="start" value="开始">
<input type="button" id="end" value="结束">
</body>
<script>
    let arr = [ /*创建数组，数组元素是图片的路径名*/
        "pop/1.png",
        "pop/2.png",
        "pop/3.png",
        "pop/4.png",
    ];
    let count = 0; /*设置计数器，为循环做准备*/
    let time = null;
    let imgSrc = "";
    time = $("#start").click(function () { /*将此事件赋值给time，便于使用clearInterval结束循环*/
        $("#start").prop("disabled", true); /*设置点击开始之后，开始按钮无法点击，只能点击结束*/
        $("#end").prop("disabled", false);
        setInterval(function () {
            let index = count % arr.length; /*用取模设置循环，获取索引*/
            imgSrc = arr[index]; /*用索引获取数组中的元素*/
            $("#small").prop("src", imgSrc); /*将数组中的元素赋值给imgSrc*/
            count++; /*计数器更新*/
        }, 200); /*200毫秒进行一次循环*/
    });
    $("#end").click(function () {
        clearInterval(time);
        $("#start").prop("disabled", false);
        $("#end").prop("disabled", true);
        $("#big").prop("src", imgSrc);
    });
</script>
</html>
```



## 13. AJax&Json

### 13.1Ajax概念与使用

* **异步**：客户端无需等服务器端响应，在服务器处理过程中，客户端可以处理其他事情

* **概念**：Ajax是在无需重新加载整个网页的情况下，能够更新部分网页的技术

* **1.使用get实现Ajax**

  * **格式**：$.get(url,[data],[callback],[type])
    * url:请求服务端的url地址
    * data：发送到服务器的数据，一般都是JS对象模式，也可是键值对模式
    * callback：回调函数，可以编写逻辑代码
    * type：预期返回的数据类型，可以是xml,html,script,json,text,_default  <font color='mediumseagreen'>注意json和text</font>

  ```html
   $.get(
          "/day1401/ajaxServlet2",
           "name=yuchenxi&age=25",
            function(data){
             alert(data);
          },
        "text"
       );
  ```

* **2.使用post实现Ajax**
  * **格式**：$.post(url,[data],[callback],[type])  <font color='mediumseagreen'>其他的都和get方式一样</font> 

* **3.使用JQuery实现Ajax**

  * **格式**：$.ajax({键值对,键值对,键值对...});  <font color='mediumseagreen'>下面就是各种键值对</font> 
    * url：请求资源路径
    * async：是否发送异步请求，默认是true
    * data：发送到服务器的数据，一般都是JS对象模式，也可是键值对模式
    * type：选择POST或者是GET
    * dataType：即将返回数据的类型  <font color='mediumseagreen'>1.里面是dataType</font> 
    * success：请求成功时调用的回调函数
    * error：请求失败时调用的回调函数

  ```html
  <!DOCTYPE html>
  <html lang="en">
  <head>
      <meta charset="UTF-8">
      <title>Title</title>
      <script src="jquery-3.3.1.min.js"></script>
      <script>
          function f() {
              $.ajax({
                  url:"ajaxservlet",
                  type:"post",
                  data:{"username":"yuchenxi"}, //json写法（js对象方式），
                  success:function (data) {
                      alert(data);
                  }
              });
          }
      </script>
  </head>
  <body>
      <input type="button" value="发送异步请求" onclick="f()">
  </body>
  </html>
  ```

### 13.2 Json概念与使用

* **概念**：Javascript Object Notation：JS**对象**表示法。作用是进行数据的传输，用于交换文本信息的语法

* **定义数据**：

  * json数据是由键值对组成的
  * 键可以使用引号，也可以不使用引号
  * 值的类型
    * 数字
    * 字符串
    * true/false
    * 数组 <font color='mediumseagreen'>[ ]里面</font> 
    * 对象 <font color='mediumseagreen'>{ }里面</font> 

* **获取数据**：

  * 三种方式
    * json对象.键名
    * json对象.数组名[索引].键名 <font color='mediumseagreen'>{[ ]}类型</font> 
    * json对象[索引].键名  <font color='mediumseagreen'>[{ }类型]</font> 
  * 遍历y对象、ys对象中所有的键、值方式：

  ```javascript
  <script>
      var y = {name: "张三", age: 12, gender: true};
      for(var key in y){
          alert(key+":"+y[key])
      }
  </script>
  ------------------
  <script>
      var ys = [
          {name: "张三", age: 12, gender: true},
          {name: "张是", age: 12, gender: false},
          {name: "张上", age: 12, gender: true},
      ];
      for (var i = 0; i < ys.length; i++) {
          var y=ys[i];
          for(var key in y){
              alert(key+":"+y[key])
          }
      }
  </script>
  ```

### 13.3 Json对象和Java对象相互转换

* **Json解析器**：jackson解析器 <font color='mediumseagreen'>SpringMVC框架的内置解析器</font> 

* **Java转换Json**

  * 导入jar包

  * 创建Jackson核心对象ObjectMapper

  * 调用ObjectMapper的相关方法

    * writeValue(参数1,obj): <font color='mediumseagreen'>这里的参数1可以是 File、Writer、OutputStream</font>
    * writeValueAsString(obj)

    ```java
    import com.fasterxml.jackson.databind.ObjectMapper;
    import com.ycx.testJackson.bean.Person;
    import org.junit.Test;
    
    import java.io.File;
    import java.io.IOException;
    
    public class Test01 {
        @Test
        public void m() throws IOException {
            Person p = new Person();
            p.setId(1);
            p.setName("张三");
            p.setAge(13);
            ObjectMapper mapper = new ObjectMapper();
            String s = mapper.writeValueAsString(p);//直接输出的是json格式{"id":1,"name":"张三","age":13}
            System.out.println(s);
            mapper.writeValue(new File("/Users/yuchenxi/Desktop/a.txt"),p);//直接输出至目录下的文件内容
        }
    }
    
    ```

  * **注解**

  ```java
  @JsonIgnore //这个是将bean的birthday这个属性在转换的时候忽略掉
  @JsonFormat(pattern = "yyyy-MM-dd")//这个是将birthday格式化成设置的格式
  private Date birthday; //bean的属性
  ```

  * **List&Map集合形式转换成json**

  ```java
   @Test
      public void m1() throws JsonProcessingException {
          Map<String, Object> map = new HashMap<>();
          map.put("name", "张三");
          map.put("age", 12);
          map.put("gender", true);
          ObjectMapper mapper = new ObjectMapper();
          String s = mapper.writeValueAsString(map);
          System.out.println(s); //{"gender":true,"name":"张三","age":12}
      }
  ```

* **Json转换Java** <font color='mediumseagreen'>了解</font> 

  ```java
   @Test
      public void m2() throws IOException {
          String s="{\"id\":1,\"name\":\"张三\",\"age\":13,\"birthday\":\"2021-07-28\"}";
          ObjectMapper mapper = new ObjectMapper();
          Person person = mapper.readValue(s, Person.class);
          System.out.println(person);
      }
  ```

## 14. Vue&Element

### 14.1 vue概念与使用步骤

* **概念**：一款前端框架，用简单的API实现**响应数据的绑定**和**组合的视图组件** (视图+脚本)

* <font color='cornflowerblue'>（面试题）vue的优点：1.易用，在前端三驾马车基础上即可快速入门；2.灵活，渐进式技术栈，足以应付任何规模的应用；3.性能：20kbmin+gzip运行大小，超快虚拟DOM,优化省心；4.采用MVVM模型，数据视图分离，视图渲染效率高，速度快；5.代码可读性高，视图和数据耦合性低</font> 

* **使用步骤**：

  * **创建vue对象**：let v=new Vue({ 选项列表 }); <font color='mediumseagreen'>每一个vue程序都是从vue对象开始的</font> 
  
  * **选项列表**：<font color='tomato'>脚本部分</font>
    
    * el选项：获取页面元素 <font color='mediumseagreen'>类似选择器</font>   
    
    * data选项：给视图中声明的变量赋值
    * method选项：定义方法，可以直接使用对象名称进行调用，this代表当前vue对象
    
  * **数据绑定**： <font color='tomato'>视图部分</font>
    
    *  {{变量名}}：在视图部分获取脚本部分的数据
  
  ```html
  <!DOCTYPE html>
  <html lang="en">
  <head>
      <meta charset="UTF-8">
      <title>test2</title>
  </head>
  <body>
  <div id="test">
      <span>姓名:{{name}}</span>
      <span>年纪:{{age}}</span>
      <button onclick="x()">显示信息</button>
      <button onclick="y()">修改年纪</button>
  </div>
  </body>
  <script src="vue.js"></script>
  <script>
      let vm = new Vue({
          el: "#test", //获取元素对象
          data: { //给对象的参数赋值
              name: "俞晨曦",
              age: "23"
          },
          methods: { //创建方法，能够使用参数，这里是methods而不是method!
              xx() {
                  alert(this.name + "是一个" + this.age + "的男生");
              }
          }
      });
  
      function x() {
          vm.xx(); //直接通过对象名调用方法
      }
  
      function y() {
          vm.age = "15"; //用对象名调用属性并且赋值
      }
  </script>
  </html>
  ```

### 14.2 vue的指令

* **概念**：以v-为前缀的特殊属性，具有一定的含义，如v-html, v-if, v-for
* **指令种类**：
  * **文本插值v-html**：若在脚本层定义的带有样式的msg文本的话，此指令可以将样式文本完整地在页面显示。<font color='mediumseagreen'>如果没使用此指令的话，页面就会原封不动地输出类似< b > fuck< /b ></font> 
  
  * **绑定属性v-bind:**：给标签的属性赋值，比如超链接href；class属性赋值，便于被选择。  <font color='mediumseagreen'>v-bind可以被省略，可以只留下:</font> 
  
  * **条件渲染**：
    
    * v-if、v-else、v-else-if、v-show：按照条件给出的值确定是否进行视图的渲染
    
  * **列表v-for**：用for来进行数据的遍历
  
    ```javascript
    <!DOCTYPE html>
    <html lang="en">
    <head>
        <meta charset="UTF-8">
        <meta name="viewport" content="width=device-width, initial-scale=1.0">
        <title>列表渲染</title>
    </head>
    <body>
        <div id="div">
            <ul>
                <li v-for="apples in box">
                    {{apples}}
                </li>
            </ul>
        </div>
    </body>
    <script src="js/vue.js"></script>
    <script>
        new Vue({
            el:"#div",
            data:{
                box:["一个苹果","两个苹果","三个苹果"],
            }
        });
    </script>
    </html>
    ```
  
  * **事件绑定v-on**：例如单击事件
  * **表单绑定 v-model** ：（双向绑定，页面和data都可以将数据更新）

<font color='cornflowerblue'>**（面试题）MVVM模型：MVC模型的改进版**：</font>

<font color='cornflowerblue'>1.在前端页面上，JS对象表示Model，页面代表View，两者做到了最大限度的分离；</font>

<font color='cornflowerblue'>2.将Model和View关联起来就是ViewModel，作为桥梁；</font>

<font color='cornflowerblue'>3.ViewModel负责将Model数据同步到View中，并且负责将View 修改的数据同步返回到Model。   举例子：Vue的v-model指令；应用：输入表单框时，Model层也会随着改变，反之亦然</font>

<font color='cornflowerblue'>（适用于数据驱动的场景，数据操作比较多的场景，区别于MVC适合中大型项目的分层开发）</font>

### 14.3 ElementUI

* 概念：基于vue的快速搭建前端页面的框架，使用必须基于vue.js。

  ```javascript
  <head>
      <meta charset="UTF-8">
      <meta name="viewport" content="width=device-width, initial-scale=1.0">
      <title>快速入门</title>
      <link rel="stylesheet" href="element-ui/lib/theme-chalk/index.css"> element核心样式文件
      <script src="js/vue.js"></script> 引入vue
      <script src="element-ui/lib/index.js"></script> 引入element核心文件
  </head>
  ```

### 14.4 Vue高级

* **自定义组件**：

  ```javascript
  Vue.component("my-button",{ //定义一个叫”我的按钮“的红色的按钮
    props:["style"],
    data:function(){
      return{
        msg:"我的按钮" //将定义好的数据进行返回
      }
    },//解析标签模版
    template:"<button style='color:red'>{{msg}}</button>"
  });
  ```

* **Vue的生命周期**：

  * 创建前后：创建el \message\data
  * 载入前后：加载数据
  * 更新前后
  * 销毁前后

<font color='cornflowerblue'>（面试题）vue生命周期：创建之前（都没开始）——vue对象被创建data,methods被初始化（此时el并没有被加载）——el和页面上的标签绑定，但是数据没更新——将数据挂在到el绑定的标签上（挂载完毕之后进行销毁，销毁之后不能修改数据）——更新vue对象数据——再更新页面层标签内容</font> 

* **Vue的异步操作**：

  * 使用axios核心js文件

  * 调用axios对象方法发起异步请求

    * get：发起get方式

    ```javascript
    <body>
      <div id="div">
        {{name}}
        <button@click="send()">发起请求</button>
        </div>
      </body>
    <script>
    new Vue({
      el:"#div",
      data:{
        name:"zhangsan",
      },
     		 methods:{
           axios.get("testServlet?name="+this.name)//用get方式
      		.then(resp=>{
        			alert(resp.data);//回调成功显示
      }
     			 .catch(error=>{
       				 alert(error);//回调失败显示
      })
    }
    });
    </script>
    ```

    * post：发起post方式

  * 调用axios对象方法处理响应的数据

    * then(response)：请求成功后的回调函数
    * catch(error)：请求失败后的回调函数

## 15. Redis

### 15.1 概念与使用

* **NoSql**：泛指非关系型数据库，对关系型数据库的补充。应对海量数据以及用户前提下的数据处理

* **Redis**：高性能key-value数据库。 <font color='mediumseagreen'>主要作用：1.为热点信息加速（热点新闻之类访问量大的）；2.即时数据的查询（热搜排行榜等要即时更新的）；3.具有实效性的信息（例如验证码）4.队列</font> 
  * *数据库之间没有必然联系*
  
  * *单线程*
  * *持久化*，*可以进行数据的恢复*
  * *多数据类型支持*
    * string：字符串类型
    * list：列表类型
    * hash：散列类型
    * set：集合类型
    * zset/sorted_set：有序集合类型

### 15.2 5种数据类型的应用场景和基本操作

* 进入redis的数据都是以key-value形式进行存储的，key必然是字符串，value是5大数据类型。redis-cli进入redis
* ==**string**==
  * **具体操作**:
    * set zhangsan 12(设置键zhangsan,值12)；get zhangsan(通过key获取值“12”)
    * 
    * append zhangsan aa (此时value就是”12aa“)
    * mset lisi 13 wangwu 14 (一次性设置多个值)
    * setnx zhangsan 122 (返回1或者0，设置成功就是1,失败就是0)
    * strlen zhangsan(返回value值的长度) <font color='mediumseagreen'>以上是基本操作</font>
    * incr/decr num (给num的value进行+1/-1操作，如果不是数字就会报错)
    * setex key 10 value(设置这个键值对只能存活10秒)
  * **应用场景**
    * 比如微博大v的微博数量和粉丝数量的值
    * key的命名规范：**表名：主键名：主键值：字段名 (user: id : 35434364: name)**
* ==**hash**== ：value是hashmap,也就是说value中还有key(filed) value
  * **具体操作**：
    * hset、hmset、hdel、hsetnx、hget、hmget、hgetall、hlen、hexists、hincrby
  * **应用场景**：
    * 一个商家id（key）卖多种商品（field）,每个商品库存100个（value）
* ==**list**==：因为底层采用双向列表结构，所以可以从左边/右边进行数据的插入
  * **具体操作**：
    * 添加数据：左右两个方向：lpush、rpush。
    * 取出第一个数据（无需参数）：lpop、rpop <font color='mediumseagreen'>可以把结束索引直接设置成-1以获取全部数据</font>
    * 查询list数据:lrange、lindex、llen
  * **应用场景**：有顺序的添加数据，企业在运营的时候，系统会产出大量运营数据，要保障多台服务器操作日志的统一输出：用list将多台服务器的日志数据集中在一个日志中
* ==**set**==：魔改版的hash，将field数据作为值，value全部是nil。区别于list，set是无序不可重复的
  * **具体操作**：
    * sad、srem、spop、smember、sismember
  * **扩展操作**：
    * 交集：sinter s1 s2
    * 并集：sunion s1 s2
    * 差集（a-b/b-a,两者结果不同）:sdiff s1 s2
    * 以上三个如果想将得出的新set存储：在三个单词后面加上store
  * **应用场景**：不法分子会用爬虫技术将数据快速获取。用set技术设定黑名单、白名单（将用户放进黑白名单）
* **消息队列**

### 15.3 Jedis

* 概念：连接java和redis的工具

```java
import org.junit.Test;
import redis.clients.jedis.Jedis;

public class TestJedis {
    @Test
    public void m1(){
        Jedis j = new Jedis("127.0.0.1", 6379);
        j.set("zhangsan", "1123");
        j.close();
    }
    @Test
    public void m(){
    Jedis j1 =new Jedis("127.0.0.1",6379);
        String s = j1.get("zhangsan");
        System.out.println(s);
    }
}
```

* **持久化**

  * **概念**：将内存中的文件进行自动备份，防止断电之内的造成文件消失。（特定的时间将保存在硬盘中的数据恢复到内存）

  * **redis两种持久化方案：**<font color='cornflowerblue'>面试题</font> 
    * **快照**：保存某一时刻的数据（二进制数据）: RDB
      * 三种指令：
        * save：1.dbfilename；2.dir：在save执行时会阻塞redis服务器
        * bgsave：发送指令，调用fork函数生成子进程，创建rbd文件，返回消息（专门优化save，bgsave是主流方式）它是异步的
        * save配置文件自动完成：这是最主流方式 （save second(监控时间范围) changes（监控数量））在10秒以内监控的key数量超过2个 ，没有达到的话，10秒到了马上就执行...11秒执行第一次指令的时候...（后台还是执行的bgsave）后面基本所有的服务都是学习它的配置
        * 优缺点：
          * 恢复速度快，灾难性的恢复首选RDB。
          * 备份速度慢，fork创建子进程额外消耗内存
    
    * **日志**：保存数据的操作过程 : AOF
      *  目前主流方式，将记录数据改成了记录数据修改的过程
      * 就是配置appendonly。三种写数据策略：always、everysycn、no
      * AOF重写：降低磁盘使用率

### 15.4 Redis高级

#### 15.4.1 过期数据

* **概念**：redis中的数据可以通过TTL指令获取其状态：xx:具有时效性的数据；-1：永久有效的数据；-2：已经过期的数据或者被删除的数据或者未定义的数据（就是干掉-2的）

* **时效性数据存储结构**：设置key value的时候，每个value都有一个内存地址，有一块独立的存储空间**expires**，保存着过期描述

* **三种删除策略**：(操作expires，在内存占用和cpu占用寻找一种平衡)

  * **定时删除**：创建定时器，用cpu换内存。
  * **惰性删除**：当数据达到过期时间的时候，不做处理，等下次访问该数据的时候：1.没有过期，返回数据；2.发现过期，删除，返回不存在。（本质上是操作之前有一个检测环节，节约cpu，但是占用内存空间，与上者相反）
  * **定期删除**：redis服务器初始化的时候会读取配置server.hz的值，默认为10，每秒执行server.hz次，activeExpireCycle()对每一个expires进行检测。。。（周期性地循环，随机挑取key进行检测（随机抽查、重点抽查），过期删除。好处是cpu性能占用有峰值，检测频度可以自定义设置，内存压力不是很大，长期占用内存的冷数据会被持续清理。）  <font color='mediumseagreen'>redis默认16个库，这种策略是将每一个库都查一遍，看看有没有过期的</font> 
  * **三种策略对比**：redis是惰性+定期删除方式

* **淘汰策略**： 

  * **概念**：当新数据进行redis是，内存不足的时候，就要进行淘汰数据。redis在使用内存存储数据的时候，会先调用freeMemoryIfNeeded()方法检测内存是否充足，如果不满足要求，会执行指令清理空间，清除数据

  * **相关配置**：

    * maxmemory

    * maxmemory-sample

    * **==maxmemory-policy==**：policy的取值如下：

    * 影响数据淘汰的相关配置：

      * 针对会过期的数据集(server.db[i].expires)
        * **volatile-lru:长时间不用的淘汰**
        * **volatile-lfu:一段时间使用次数最少的淘汰**
        * volatile-ttl:挑选要过期的淘汰
        * volatile-random：任意选择数据淘汰

      * 检测全局：(server.db[i].dict)
        * allkeys-lfu:一段时间使用次数最少的淘汰
        * allkeys-ttl:挑选要过期的淘汰
        * allkeys-random：任意选择数据淘汰

#### 15.4.2 主从复制

* **概念**：互联网中三高（高并发、高性能、高可用）架构，必须要将redis强化成高可用模式：将多台服务器连接，如果其中一台宕机了，其他服务器仍然可以继续使用。（必须要保证**数据同步**）收集数据的叫做**主服务器master**，其他提供数据的叫做**从服务器slave**。 <font color='tomato'>是一对多结构，主只负责写数据（增删改），从只负责读数据（查）</font> 

* **作用**：读写分离；负载均衡；故障恢复；数据冗余备份；高可用基石

* **主从复制工作流程**

  * **建立连接阶段**（原理：是slave连接master，master给slave同步。1.设置master的地址和端口；2.建立socket连接；3.定时发送ping，确保没有掉线；4.发送slave端口信息）

    * **具体连接步骤**：

      ```java
        1.起master redis服务，复制一个配置文件：redis- 6381.conf
        2.起slave redis服务，复制一个配置文件：redis-6382.conf
        3.三种连接方式
          1.slaveof master masterport //发送命令
          2.redis-server --slaveof masterip masterport
          3.slave redis.conf配置 //推荐
      redis-server /redis/conf/...
      ```

  * **数据同步阶段**：

    * 1.请求同步数据
    * 2.创建RDB同步数据：(RDB：持久化方案，通过bgsave全量打包生成xx.rdb文件，用 来保存数据)（一边打包一边输入指令的话，会将指令放置到复制缓冲区中）
    * 3.恢复RDB同步数据

  * **命令传播阶段**

    * **特别注意**：这个阶段有可能发生部分复制的情况（比如网络波动造成的连接断开）
    * **三个要素**：（**RunId**（记录哪个slave）、**数据偏移量**（数字标识，用来记录宕机时缺失数据的范围）、**复制缓冲区**（缓冲区是记录网络波动时候的指令（字节值）），默认是1M）

  * **完整版本+心跳机制**

    * 全量复制：RDB打包
    * 部分复制：AOF记录指令

    * 心跳机制：
      * 概念：master和slave通过心跳机制来进行维护，实现双方保持连接
      * master：10秒/次，判断slave是否掉线。slave多数掉线或者延迟过高的时候，master为了保持数据稳定性，将拒绝所有的信息同步操作
      * slave：1秒/次

* **常见问题**

  * 全量复制：

    * 伴随着系统的运行，master的数据量会越来越大，一旦master重启，runid将发生变化，会导致全部slave的全量复制操作 ：对于这类问题，我们做一些故障转移的手段，例如master发生故障宕掉，我们选举一台slave晋升为master（哨兵或集群）

    * 频繁的全量复制：修改复制缓冲区的大小

  * 频繁的网络中断

    * 频繁的网络中断：设置合理的超时时间，确认是否释放slave
    * 由master发送Ping的频率比较低造成的网络中断：提高ping指令发送的频率

  * 数据不一致

    * 多个slave获取相同的数据不同步：监控offset，如果slave延迟过大，暂时屏蔽Java客户端对该slave的数据访问

#### 15.4.3 哨兵模式

* **概念**：一旦master断掉，让一台slave代替master。**哨兵是一个分布式系统（在一台服务器上）**，监控每一个服务器运行，并且在master出席故障的时候，采用投票的机制选出新的slave成为新的master。

  * 检查master和slave是否正常运行；  <font color='mediumseagreen'>哨兵的作用</font> 
  * 检查master是否存活、master和slave的运行情况检测；
  * 监控服务器出现问题的时候，向其他发送通知
  * 选取一个slave作为master，将其他slave连接新的master，并告知客户端新的服务器地址
  * 旧的master复活之后变成slave

* **启动哨兵模式**

  * 1.起一主两从（slaveof iip port）
  * 2.起三个哨兵redis服务，配置三个哨兵的配置文件

  * 是redis-sentinel而不是redis-server，注意区别

* **演示**

* **哨兵模式工作原理**

  * 三个阶段：

    *  连接阶段：所有哨兵都要连接redis的所有主从

    * 通知阶段：保持联通，保证所有消息都是对等的
    * 故障转移阶段：从slave中选取一个主机（排除反应慢的、回复慢的）

  * 两个概念：

* **JavaAPI操作哨兵**

#### 15.4.4 集群模式

* **概念**：**将多个主从结构连接在一起**，统一管理，使其对外进行服务，可以防止某一个服务器宕机造成压力
* **Cluster集群设计**：
  * 1.将key通过算法得到一个编码值，作为key保存的区域。
  * 2.槽：对redis主机进行数字分区，第1部计算出来的编码值（hash值）对槽的总数进行取模，得出来的值就是放在哪个主机当中
  * 3.数据查询：最多两次命中。
* **Cluster集群搭建**
  * 1.增加redis节点（加一个主机/在一个主机上增加一个从机）
  * 2.分槽：分区间，然后数据得出hashcode在哪个区间里面（三个机器分16384），如果新增了一个机器，就要重新分槽（三个机器每个拿出一点给它作为区间）
  * 3.如果取消这个主机，就得重新将槽还回去
* **JavaAPI操作集群**

#### 15.4.5 企业级解决方案

* **缓存预热**  <font color='cornflowerblue'>以下三个都是面试题</font> 
  * 用脚本先添加访问量高的数据到redis（service层中）中进行预热，在代码中先从redis查询，如果没有再在MySQL中查询
* **缓存雪崩**
  * **现象**：数据库崩了。原因：缓存中大批量数据集中到期，查询数据的流量依旧巨大，引起MySQL压力过大而宕机。
  * **方案**：
    1. 缓存数据的**过期时间设置随机**，防止同一时间大量数据过期现象发生。
       - 根据业务数据有效期进行分类错峰，A类90分钟，B类80分钟，C类70分钟 ， 过期时间使用固定时间+随机值的形式，稀释集中到期的key的数量
    2. 缓存数据量不大的话，可以设计**多层级缓存**，一级缓存过期后，去找二级缓存。
    3. 设置热点数据永远不过期。
    4. 限流、降级 
       - 对访问数据库接口进行限流、降级 ，短时间范围内牺牲一些客户体验，限制一部分请求访问，降低数据库的压力，保证部分用户可正常操作。
       - 对访问应用系统层接口进行限流、降级 ，降低应用服务器压力，待业务流量峰值降低后再逐步放开访问
* **缓存击穿**
  * 现象：redis中某个key过期，但是突然此key访问量暴增
  * 方案：预先设定key时长延长、设置永久、限流、设置高流量阈值
* **缓存穿透**
  * 现象：大量非法请求（比如直接用url地址访问）造成mysql宕机
  * 方案：设置黑白名单
* **性能指标监控**
  * 性能指标  
  * 内存指标
  * 基本活动指标
  * 持久性指标
  * 错误指标
* **性能监控工具**

## 16. maven

### 16.1 概念与使用

* **概念**：maven是项目管理工具，能将项目的开发和管理抽象成一个项目对象模型（POM模型，将项目看成一个对象）,统一项目结构，拆分多个工程模块，项目打包一站式发布。    
* **作用**：1.自动建立**标准化、跨平台**项目构建方式；2.方便**管理jar包**，避免资源间版本冲突
* **maven结构的基本概念**：
  * **仓库**：存储资源，里面有很多jar包。*maven开发团队维护着**中央仓库**（存储开源的jar包）。**私服**（公司维护的，具有版权的jar包）是中央仓库和本地的中转站。可以将其下载，变成**本地仓库**（本地是中央的子集）。*
  * **坐标**：maven中用坐标定义资源的位置（组织id+项目id+对应的版本号）。https://mvnrepository.com/ 在此地址查询具体jar包的坐标
  * **仓库配置**：

### 16.2 使用idea搭建maven

* **依赖**：通过dependencies - dependency 设置jar包的信息，实现maven托管jar包

  * **直接依赖**：直接在依赖配置中设置的依赖

  * **间接依赖**：若A资源被B依赖，B又被C依赖，则A是C的间接依赖

  * **依赖冲突**：若依赖版本发生冲突，后配置的覆盖先配置的

  * **可选依赖**：设置依赖不透明化（看不到用不着）

    ```xml
    <optional>true</optional> //在被可选的依赖中这样设置
    ```

  * **排除依赖**：直接断开依赖之间的相互连接（不需要）

    ```xml 
    <exclusions>
            <exclusion>
              <groupId>xxx</groupId>
              <artifactId>xxx</artifactId>
            </exclusion>
    </exclusions>
    ```

  * **依赖范围**：可以设置< scope >标签设置jar包的作用范围

    |     scope     | 主代码 | 测试代码 | 打包 |    例子     |
    | :-----------: | :----: | :------: | :--: | :---------: |
    | compile(默认) |   y    |    y     |  y   |    log4j    |
    |     test      |        |    y     |      |    junit    |
    |   provided    |   y    |    y     |      | servlet-api |
    |    runtime    |        |          |  y   |    jdbc     |

### 16.3 生命周期与插件

* **生命周期**：

  * clean：清理工作

  * default：核心工作

    * 在执行某个步骤的时候，就会将其全部所有步骤执行一遍

      ```
      ● validate（校验）校验项目是否正确并且所有必要的信息可以完成项目的构建过程。
      
      ● initialize（初始化）初始化构建状态，比如设置属性值。生成包含在编译阶段中的任何源代码。
      
      ● generate-sources（生成源代码）
      
      ●process-sources（处理源代码）处理源代码，比如说，过滤任意值。
      
      ● generate-resources（生成资源文件）生成将会包含在项目包中的资源文件。
      
      ● process-resources （处理资源文件）
      
      复制和处理资源到目标目录，为打包阶段最好准备。
      
      ● compile （编译）编译项目的源代码。
      
      ●process-classes（处理类文件）
      
      处理编译生成的文件，比如说对Java class文件做字节码改善优化。
      
      ● generate-test-sources（生成测试源代码）生成包含在编译阶段中的任何测试源代码。
      
      ● process-test-sources（处理测试源代码）处理测试源代码，比如说，过滤任意值。
      
      ● generate-test-resources（生成测试资源文件）为测试创建资源文件。复制和处理测试资源到目标目录。
      
      ● process-test-resources（处理测试资源文件）编译测试源代码到测试目标目录.
      
      ●test-compile（编译测试源码）处理测试源码编译生成的文件。
      
      ●process-test-classes（处理测试类文件）
      
      ●test（测试）使用合适的单元测试框架运行测试（Juint是其中之一）。
      
      ● prepare-package （准备打包）在实际打包之前，执行任何的必要的操作为打包做准备。
      
      ● package （打包）将编译后的代码打包成可分发格式的文件，比如JAR、WAR或者EAR文件。
      
      ● pre-integration-test（集成测试前）在执行集成测试前进行必要的动作。比如说，搭建需要的环境。
      
      ● integration-test（集成测试）处理和部署项目到可以运行集成测试环境中。
      
      ● post-integration-test（集成测试后）在执行集成测试完成后进行必要的动作。比如说，清理集成测试环境。
      
      ● verify （验证）运行任意的检查来验证项目包有效目达到质量标准。
      
      ● install（安装）安装项目包到本地仓库，这样项目包可以用作其他本地项目的依赖。
      
      ● deploy（部署）将最终的项目包复制到远程仓库中与其他开发者和项目共享。
      ```

  * site：产生报告，发布站点

* **插件**：插件与对应的生命周期阶段绑定，执行到生命周期时执行对应的插件功能

### 16.4 maven高级

#### 16.4.1 多模块开发SSM

* **概念**：将一个个ssm拆分成多个模块，用maven进行统一管理，**模块之间靠接口通信**

* **maven依赖过程**：idea——>maven<——>私服<——>中央仓库

  ​								|本地仓库目录|

*  **ssm_pojo**
  * 创建的时候不用模板，resources、test文件夹都删除
* **ssm_dao** 
  * 首先要知道哪个模块哪些类、配置文件、pom坐标是与dao有关的
  * userDao.xml、applicationContext-dao.xml、jdbc.properties留着。pom.xml中和数据库有关的全部，表现层的去掉           <font color='mediumseagreen'>注意：分页插件留下。事物不留下，它不属于dao层，属于service层</font> ，
  * **联动pojo：将pojo坐标导入到pom.xml中**
    * **pojo执行install（将其安装到本地仓库repository），再dao中执行complie**
* **ssm_service**
  * resources文件夹只留下applicationContext-service.xml		 <font color='mediumseagreen'>注意："dataSource"爆红不用管、事物要记得配置</font> 
  * 整理pom.xml，导入dao坐标（无需导入pojo坐标，因为依赖传递）
  * test测试类(不参与打包)上的location加载xml文件可以是**数组**，加载多个xml文件
* **ssm_controller**
  * 注意这里需要webapp文件夹了，创建时候用web模板创建
  * 只需要导入service的坐标，并且install service
  * Exception、interceptor、result文件夹也是在块
  * **注意web.xml中加载的是:classpath * : application-*.xml**
  * <font color='tomato'> 注意pom.xml中是war而不是jar</font>

#### 16.4.2 聚合

* **多模块的构建维护**
  * **概念**：如果其中一个模块更新了...咋办? 解决方法：用一个单的模块管理这个几个模块，统一进行install、complie，这就叫做聚合
  * **具体步骤**：
    * 创建一个ssm模块，只留下一个pom.xml文件，在其中添加：<packaging>pom</packaging>  <modules>...<module>../ssm_pojo</module>... </modules>
    * complie编译，此时会发现控制台显示的模块顺序是依赖的顺序
    * 任何一个模块的代码进行修改之后，都要在ssm主工程模块**重新insatall**进行更新打包

#### 16.4.3 继承

* **概念**：各个模块中可能会用到相同的资源，比如Spring-context，同时可能存在版本差异。让子工程的继承父工程的依赖，达到统一目的  <font color='mediumseagreen'>将通用的依赖抽取出来在父工程中写，并且在父工程中定义版本！（最大的好处）</font> 
* **具体步骤**：
  * 1.在ssm的pom.xml中<dependcyManagement><dependcies...<dependcy...                                         <font color='mediumseagreen'>< pluginManagement >搞定plugin</font> 
  * 2.在子工程的pom.xml中添加 <parent><groupId......<relativePath>../ssm/pom.xml
  * 3.子工程pom.xml可以简化，只剩下项目id     <font color='tomato'>并不是依赖坐标不用写，而是坐标的版本不用写（父工程没有这个坐标的话，子工程就要写版本号）</font> 

* **注意事项**
  * 继承和聚合可以做成两个工程，也可以两个工程
  * 聚合是快速构建项目，继承是快速配置
  * 聚合和继承都是只有pom.xml
  * **聚合可以感知参与聚合的模块，继承不知道哪些子工程继承了它**

#### 16.4.4 属性

* **概念**：类似于Java中的变量

* **自定义属性**  <font color='mediumseagreen'>比如控制版本号</font> 
  * 定义：<properties>  < spring-version >5.1.9</ spring-version >  </properties>
  * 使用：${spring-version}
* **项目属性**
* **setting**
* **Java系统属性**
* **环境变量属性**

#### 16.4.5 版本管理

* release：已完成版本
* snapshot：正在开发版本

#### 16.4.6 资源配置

* **概念**：将dao模块的pom.xml中信息（<jdbc.url>.....</jdbc.url>）动态发送到jdbc.properties文件中（${jdbc.url}），让数据一一匹配。

* **寻找资源路径**：<resources><resource><directory>${project.basedir}src/main/resources<directory><filtering>true<filtering><resource></resources>  <font color='tomato'>注意这是在<build>里面，只有编译打包的时候才能进去</font> 
* 将所有的配置文件在maven中统一管理，过滤器为true的选择性地集中管理。

#### 16.4.7 多环境配置

* **概念**：多环境配置就是为什么进行资源配置的原因，动态地设置配置信息(一般是动态url和密码)，让项目自动适应多重环境（生产，测试...）
* **具体步骤**：
  * **创建多环境**：<profiles><profile><id>pro_env</id> <properties>... </properties></profile>   <profile><id>dep_env</id> <properties>... </properties></profile> <profiles>     <font color='mediumseagreen'>id区分不同的环境</font> 
  * **打包**：mvn istall -p test   <font color='mediumseagreen'>在tomcat的configurations里面的vm options添加</font>  
  * 可以设置默认启动：<activation> <activeByDefault> true </activeByDefault> </activation>   <font color='mediumseagreen'>在想要默认的< profiles>里面添加</font> 

#### 16.4.8 跳过单元测试

* **概念**：因为install或者package打包的时候执行clean、compile等命令，单元测试会执行大量命令，非常耗时，所以必要时候要跳过单元测试
* **使用方式**：使用idea 窗口 maven--> 选中命令 ---> 点击上方蓝色小闪电

#### 16.4.9 私服

* **概念**：建立公共计算机，达到小范围资源共享目的
* **安装、启动、配置**
* **操作私服资源**
* **本地仓库和私服之间配置**
* **项目配置私服地址**

## 17. Javaweb综合案例

### 17.1项目创建过程

#### 17.1.1 part01

* 1.使用maven-webapp骨架搭建项目空壳，在**pom.xml**文件中注入相关的依赖，分别设置main/test的java、resource文件。并且在addcondition处配置tomcat启动
* 2.利用AdminLTE快速搭建页面
* 3.创建domain层的**Company类**，Dao层的接口**CompanyDao**（CompanMapper），放入工厂工具类、事务工具类。jdbc.properties和核心配置xml文件放在resources文件夹。CompanyDao.xml放在resoures子文件夹中
*  4.搭建service层的**CompanySerivce、CompanyServiceImpl**实现类,（其中涉及到工厂、工具类，分页查询pageinfo），对接口的功能进行实现，在test报包创建test类创建CompanyServiceImpl对象，调用其各个方法进行测试
* 5.创建web表现层。
  * 这里只先写了company相关的，对于后端来说，最重要的还是**CompanyServlet**的编写，之前的练习大多都是从网页书写账号密码来提交到servlet，只能一对一，现在使用**operation=list**，if("list"=request.parameter("operation")) else if(){...}来进行输入源的信息判断，进而采取不同的措施。
  * 此处是在servlet内部创建CompanyServiceImpl对象，调用findAll方法，获取pageinfo对象，并且设置相应分页参数，将对象进行requset转发到jsp页面，在jsp页面用el表达式获取对象和值（值是通过对象的**list结果集属性**一一获取的），从而进行数据的展示
* 6.实现添加操作
  * 在CompanyServlet添加两个方法**toAdd/save**分别作为if else选项，其中toAdd只是为了将页面转发到add.jsp进行信息的输入，add.jsp会operation=save跳转到CompanyServlet调用save方法
  * save方法内部使用工具类**BeanUtil**将requset所携带的信息封装成对象返回，调用实现了的save方法将对象数据存储至数据库，同时页面重定向operation=list到CompanyServlet(此时list方法自动调用查询数据)
* 7.用Company相同的增删查改的方式实现Dept的增删查改，但是注意Dept的数据库表是自关联的，要在xml文件里使用association，并且类中将类自身作为属性
* 8.创建User的增删查改，注意用户的密码save到数据库的过程，需要使用工具类加密。其次是在修改用户信息的时候，并非所有的信息都要修改，根据实际需要更改xml文件中的sql语句。

#### 17.1.2 part02

* 9.创建Course模块，基本和之前一致，注意两点：1.在impl文件中save方法中，注意要添加setCreateTime(new Date())，让数据创建的时候添加真实日期。2.设置过滤器，将所有的字符编码改成utf-8
* 10.创建Catalog模块（题目类型），其中它与Course是多对一的关系，创建javabean类的时候要多一个Course属性
* 11.创建Question模块，它有两个一对多（企业，学科），所有创建javabean类的时候注意要有Catalog属性和Company属性
* 12.用apche的common-fileupload组件完成文件上传，文件的上传是一整套流程，此项目是将本地文件文件上传到项目内部upload文件内部。注意testFileUpload.jsp里面enctype="multipart/form-data"不能少，同时在servlet里面添加**DiskFileItemFactory\ServletFileUpload**...
* 13.给QuestionServlet增加添加包含文件上传功能的save。注意用工具类Beanutil获取对象的时候，参数由request改成了**List< FileItem >** 类（这个集合包含了上传文件的所有信息）的fileItems。当然jsp文件也要添加enctype... （这里学到了一个小技巧：**if(true) return;** 可以暂时忽略后面的代码的执行，快速进行代码的调试）
* 14.解决上传文件重名问题，使用uuid生成的唯一id编号作为picture属性的值（小技巧将save方法的void返回值改成String，并且return id；这样在servlet中调用save方法的时候直接能通过返回值获取id）
* 15.修改question这块，最主要的问题在于**原图片的显示**，核心要求是修改前后的picture值是一致的，达到一个替换的目的，但是picture的值（也就是id值）在修改图片前后是不变的。我这里为了更好地将图片显示，在write的时候**+“.jpg”**，同时在update.jsp显示图片处+“.jpg”。注意这个只是图片的名字加了后缀，和picture没有关系
* 16.此处是对15功能的补充和修复，必须要添加**flag=true/flase来判断是否上传了图片**（用StringUtils.isNotBlank(item.getName())来获取flag值），如果上传了，和之前都一样，如果没有上传，则picture不被赋值，是null，并且update.jps图片预览那一块直接不显示。
* 17.QuestionItem模块的创建，注意类的questionId属性，进行查询的时候，一道question和一个questionItem肯定是一一对应的，所有实现类**findAll方法肯定是要根据questionId属性来**的。并且选择题选项有限，所有无需制作分页功能
* 18.给QuestItem(选择题)增加选项，最重要的是**找到questionId一一对应**。这里的方法是来自Question包的list.jsp的questionId进入到QuestionItemservlet中，获取再通过request.setAttribute发送。在QuestionItem包下list.jsp获取questionId。（小技巧：可以直接在servlet的save方法里面调用list(request,response),实现简单快速跳转）
* 19.删除questionItem。关键问题在于删除之后，页面能即时跳转，且显示被删除之后的剩下的几个选项。解决此问题的方法在于首先在questionItem的list.jsp删除的时候，能将**questionId也request转发到servlet**里面。同时delete方法执行之后能够调用list(request,response)，在list里面重定向到同一个list.jsp文件中（此时已经携带着questionId了），list.jsp就会且只会显示当前questionId的问题下的各个questionItem（记住:在前几个步骤，已经将findAll方法修改，只能查询指定了的questionId的数据信息了）（通过数据库表格也会发现，多个item的question_id是相同唯一的）。
* 20.修改questionItem。核心问题在于，一组表单如果承载多项功能的时候，要用动态数据的方式，这里是用request.setAttribute("operation","save"/"edit")，来控制到底是进入servlet中的save方法还是edit方法。因为request是一次请求，数据使用后失效。在save方法判断getAttribute("operation")==null之后又可以使得给表单赋值"save"。第二个问题是修改的时候要注意确定好questionItem的id。
* 21.创建saveOrUpdate方法，**将添加和修改相结合**，通过判断id是否为null来决定调用哪个方法。是对步骤20的整合
* 22.删除操作：核心问题在于**删除Question的时候，对应的几个QuestionItem也应该被删除**。

#### 17.1.3 part03

* 23.用poi进行写读数据

* 24.创建下载功能，导出表格
* 25.研究别人的代码的过程
  * 观察整体页面结构
  * 去除无效的基础信息（head\body\html）
  * 去除页面无效的基础信息（我不需要的信息）
  * 分析页面js内容
  * 一步步试错，修改，删除校验代码存在的必要性，最后剩下最核心的代码
* 26.加载显示数据库中role和module关系，给角色添加权限
  * 通过jsp页面数据在role的servlet里获取相对应的role对象，将role对象转发到jsp，以显示role的name等信息
  * 在module模块里面编写findAuthorDataByRoleId(roleId)方法，能通过role的id获取所有的module信息（以map集合的方式，注意此处sql语句的编写，最重要的是通过第三表表获取checked是true/false，用的是when...then...else...end）
  * 将map集合以json数据格式传输到页面
* 27.上一个是单纯显示数据库里面role和module的关系，现在是编辑（先删除老关系（在数据库中delete），再建立全新关系(insert)），关键在页面获取roleId和moduleId，注意jsp传过来的moduleId是1,2,3,4形式的，要用切割器将字符串切割，然后再调用roleDao.saveRoleModule(roleId,moduleId)循环进行绑定insert操作。

#### 17.1.4 part04

* 28.显示当前user绑定role的情况，这两张表也是多对多的关系，在jsp页面中要点击“角色”按钮之后，当前user对应的role选项就要自动被选择上，核心问题是使用sql语句进行判断在第三张表格里面，该user和哪一个role对应（when...then...else...end，对应为‘checked’,不对应为‘ ’）
* 29.更user和role绑定情况，先deleteRole，再saveUserRloe。
* 30.增加校验登陆功能，核心还是直接根据email\password查询数据库封装成user对象，如果user!=null，则进入。
* 31.创建根据登陆user——role——module来显示对应的用户拥有的模块，是通过sql用use表格中的id获取module表的数据，将获取到的List< Module > setAttribute到jsp页面，在页面上用循环方式将内容显示，注意显示的路径问题
* 32.用过滤器进行权限校验，主要思想就是将模块的curl拼接成一个大字符串，将requset.getRequstURI()和request.getQueryString拼接并且判断是否被大字符串所包含，所有包含的话在过滤器中就放行。

### 17.2结构分析详解

### 17.3项目心得总结

* 这是迄今为止第一个项目，基本包含了web阶段的绝大部分内容，也包含了大量的知识，核心代码就是Dao\Service\Control层的架构的设计，里面很多代码都是大致重复的。但是有些阶段步骤也是让人学习甚多，最重要的还是其中的设计思想以及代码语感。

## 18.Spring

### 18.1 概念与使用

* spring是分层的JAVASE/JAVAEE应用的轻量级开源框架
  * **底层是核心容器**
    * Beans
    * Core
    * Context
    * SpringEl表达式
  * **中间层技术**
    * AOP（类似接口）
    * Aspects（类似实现）
  * **应用层技术**
    * 数据集成
    * web集成
    * web实现
  * **基于Test测试**

### 18.2 IoC

*  IoC：Inversion Of Control，Spring反向控制应用程序所需要的外部资源

#### 18.2.1 入门案例

* 步骤：1.在maven加载spring依赖；2.创建applicationContext.xml文件，里面配置<bean id="userservice" class="com.ycx.impl.UserServiceImpl"/>；3.在测试类新建applicationContext类对象ctx并且加载xml文件；4通过ctx通过getBean获取对象，通过对象调用方法。
* 与传统方法的不同：之前都是要创建JAVAbean类，通过new创建对象。现在直接用接口——实现类——spring来getBean获取对象，调用对象的方法。

#### 18.2.2 loC配置详解

* **bean**：name可以取多个值（多个名称），效果和Id一致
* bean属性**scope**（prototype、singleton）：非单例、单例。<font color='mediumseagreen'>单例是在加载配置文件的时候就创建好对象了，非单例是在getBean的时候才创建对象</font>  <font color='tomato'>spring创建非单例的时候，不归spring管理，只是new一下（所以无法运行destroy方法）；单例是归spring管，会执行destory方法</font> 
*  **factory-bean，factory-method**：实例工厂创建bean、静态工厂创建bean

#### 18.2.3DI

* **概念**：Dependency Injection:依赖注入。应用程序依赖的资源由spring提供，资源被注入应用程序

* **注入方式**：

  * **set注入（主流）**： < bean> <property/ > < /bean>; < property name=" " value=" " ref=" "/>

  ```xml
  <?xml version="1.0" encoding="UTF-8"?>
  <beans xmlns="http://www.springframework.org/schema/beans"
         xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance"
         xsi:schemaLocation="http://www.springframework.org/schema/beans
          https://www.springframework.org/schema/beans/spring-beans.xsd">
  
      <bean id="userService" class="com.ycx.Service.UserServiceImpl"> <!--就是给service注入dao的类-->
          <property name="userDao" ref="userDao"/> <!--用property标签引用要被注入的资源，这里的name是set后面的一段，ref是被注入的id-->
          <property name="dogDao" ref="dogDao"/> <!--引用类型都是ref-->
          <property name="number" value="1224235" /> <!--基本类型是value-->
      </bean>
  
      <bean id="userDao" class="com.ycx.Dao.UserDaoImpl"/> <!--这是要注入的资源，要在配置文件中定义为bean-->
      <bean id="dogDao" class="com.ycx.Dao.DogDaoImpl"/> <!--这是要注入的资源，要在配置文件中定义为bean-->
  </beans>
  ```

  ```java
  package com.ycx.Service;
  
  import com.ycx.Dao.DogDao;
  import com.ycx.Dao.UserDao;
  
  public class UserServiceImpl implements UserService {
  
      private UserDao userDao;//第一步骤是声明一个私有的变量
      private DogDao dogDao;
      private int number;
  
  
      public void setUserDao(UserDao userDao) {//这个就是普通JAVAbean类的setter方法
          this.userDao = userDao;
      }
  
      public void setDogDao(DogDao dogDao) {
          this.dogDao = dogDao;
      }
  
      public void setNumber(int number) {
          this.number = number;
      }
  
      @Override
      public void save() {
          System.out.println("Service...");
          userDao.save();
          dogDao.bark();
          System.out.println(number);
      }
  }
  ```

  * **构造方法注入**
  * **集合类型的数据注入**
    * **list**
    * **map**
    * props
    * array
    * set

  ```xml
  <?xml version="1.0" encoding="UTF-8"?>
  <beans xmlns="http://www.springframework.org/schema/beans"
         xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance"
         xsi:schemaLocation="http://www.springframework.org/schema/beans
          https://www.springframework.org/schema/beans/spring-beans.xsd">
  
      <bean id="userService" class="com.ycx.Service.UserServiceImpl"> <!--就是给service注入dao的类-->
            <property name="clazz" ref="clazzhhh"/>
      </bean>
  
      <bean id="clazzhhh" class="com.ycx.Dao.ClazzImpl">
          <property name="age" value="12"/>
          <property name="name" value="xiaohua"/>
          <property name="listname" >
              <list>
                  <value>xiaohong</value>
                  <value>xiaozhang</value>
              </list>
          </property>
  
          <property name="map">
              <map>
                  <entry key="hh" value="3434"/>
                  <entry key="dd" value="333"/>
              </map>
          </property>
      </bean>
  </beans>
  ```

  * **总结**：
    * 1.和接口没关系，没有接口也能正常输出；
    * 2.本质是在一个类引用其他类，并且还能直接调用那个类的方法，并不需要创建对象并且赋值。因为赋值的操作已经在xml文件解决，大大降低耦合性。

#### 18.2.4 properties

* **概念**：用配置文件的方式输入信息
* **步骤**：1.准备properties文件；2.开启context命名空间支持；3.加载指定properties文件；4.使用加载的数据：< property name="propertyName" value="${propertiesName}"/>
* **import标签**：加载多个配置文件

### 18.3 Spring的注解开发

#### 18.3.1常用注解

* 启动注解功能：要添加以下内容，开启注解扫描

```xml
<!--首先配置注解驱动，开启扫描，配置包-->
    <context:component-scan base-package="com.ycx"/>
```

* **bean的定义**：
  * 种类：**@Component；@Controller；@Service；@Repository**  <font color='mediumseagreen'>后三者是第一个的衍生注解，效果相同</font> 
  * 类型：属于类注解，在类的上方添加  <font color='mediumseagreen'>value：定义bean的访问id</font> 
  * 作用：和配置< bean>...一样，将这个类设置为归spring管理
* **bean的作用域：**
  * 名称：**@Scope**
  * 类型：类注解，再类定义的上方
  * 作用：设置该类作为bean对应的scope属性 <font color='mediumseagreen'>value：定义bean的作用域，默认是singleton</font> 
* **bean的生命周期**
  * **@PostConstruct、@PreDestroy**
  * 类型：方法注解，定义在方法上面
  * 作用：设置生命周期方法
* **加载第三方资源：@Bean("xxx")** 
  * ==放在方法上面==
  * 别忘记在类上添加@Component
* **bean的非引用类型属性注入**
  * 在非引用类型域上面添加**@value**("xxx")，给域赋值 <font color='mediumseagreen'>如果赋值了，就无需使用setter了，因为setter目的本身也就是给属性赋值</font> 
* **bean的引用类型属性注入**
  * 在引用类型域上面添加**@AutoWired**  <font color='mediumseagreen'>匹配接口实现类的时候会先通过属性类型找相应接口，如果这个接口有多个实现类则通过属性名称找实现类</font> 
  * 添加**@Qualifier("xxx")**  <font color='mediumseagreen'>这个是专门用来指定名称的</font>  
  * 可以添加**@Primary**来优先配置同一个接口下的这个类

* **properties属性**
  * 在类上面添加**@PropertySource("classpath:jdbc.properties")** 则在下面的属性添加**@value("${jdbc.username}")**，就可以使用该路径下的properties 文件的内容了

* **使用纯注解模式（去除xml文件）**

  * 1.创建SpringConfig，添加注解

    ```java
    @Configuration //设置为配置文件，相当于xml文件开头一大块
    @ComponentScan("com.ycx")//设置bean的扫描目录
    ```

  * 2.在测试类中，用.class文件创建ctx对象

    ```java
    ApplicationContext ctx=new AnnotationConfigApplicationContext(SpringConfig.class);
    ```

* **使用注解加载第三方资源**

  * 添加注解

    ```java
    @Import(JDBCConfig.class) //注意这里面能同时添加多个资源，用,隔开。但是不能多次import
    ```

  * 注意如果资源已经被Import的话，可以不用在资源类上面添加@Component（无需声明为bean）

#### 18.3.2 bean加载控制

* **依赖加载**
  * **@DependsOn("xxx")** :在类/方法上面添加这个注解，那在加载这个bean之前，会加载xxx这个bean类
  * 方法是单独依赖，类是全部依赖
* **顺序加载**
  * 如果在appliacationContext同时加载多个类.class（注意），可以在这几个类上面**@Order(1)、@Order(2)**来设置加载顺序
* **延迟加载**
  * **@Lazy**，放在类、方法上面。控制bean的加载时机，让它延迟加载

#### 18.3.3 整合第三方技术

##### 18.3.3.1 整合mybatis

* **流程分析：**
  * 核心目的就是将mybatis案例从配置文件开发转成注解开发
  * 业务类使用@Component形式，属性使用@AutoWired形式
  * 分类管理外部资源（JDBC,MyBatis），并且使用@Bean
  * 注解形式扫描bean
  * 使用AnnotationConfigApplicationContext加载配置类

* **具体步骤：**

  * 1.创建**SpringConfig**文件，作为xml的替代，其功能是：配置文件、扫描bean、加载外部properties文件、导入整合两个外部资源。

    ```java
    @Configuration
    @ComponentScan("com.itheima") //这两个注解是第一步骤，让这个类作为配置文件，并且开启扫描
    @PropertySource("classpath:jdbc.properties")//第三步骤，载入外部jdbc文件
    @Import({JDBCConfig.class,MyBatisConfig.class})//第五步骤，将外部资源类整合进来了，直接可以同anno...进行使用,第九步骤，添加第二个class文件
    public class SpringConfig {
    }
    ```

  * 2.创建**JDBCConfig**文件，功能是：创建获取DataSource、用jdbc的方式给连接池对象的四大天王赋值

    ```java
    public class JDBCConfig {//这个第三步骤，加载外部数据库连接池
        @Value("${jdbc.driver}")
        private String driver;
        @Value("${jdbc.url}")
        private String url;
        @Value("${jdbc.username}")
        private String userName;
        @Value("${jdbc.password}")
        private String password;
    
        @Bean("dataSource") /*注意这个是放在方法上面*/
        public DruidDataSource getDataSource() {
            DruidDataSource ds = new DruidDataSource();
            ds.setDriverClassName(driver);
            ds.setUrl(url);
            ds.setUsername(userName);
            ds.setPassword(password);
            return ds;
        }
    }
    ```

  * 3.在**AccountServiceImpl**文件中：将自己通过注解引入到spring中、再注入引用对像

    ```java
    @Service("accountService") //第六步骤
    public class AccountServiceImpl implements AccountService {
    
        @Autowired//第七步骤，注入引用对象
        private AccountDao accountDao;
    
    
        @Override
        public void save(Account account) {
            accountDao.save(account);
        }
    
        @Override
        public void delete(Integer id) {
            accountDao.delete(id);
        }
    
        @Override
        public void update(Account account) {
            accountDao.update(account);
        }
    
        @Override
        public List<Account> findAll() {
            return accountDao.findAll();
        }
    
        @Override
        public Account findById(Integer id) {
            return accountDao.findById(id);
        }
    }
    ```

  * 创建**MyBatisConfig**文件，将两个有返回值的方法作为bean注入到spring中，这两个方法一个是整合domain，一个是整合dao。这个文件本身会被import到SpringConfig中

    ```java
    public class MyBatisConfig {
    
        //第八步骤，整合mybatis里面的东西
        @Bean
        public SqlSessionFactoryBean getSqlSessionFactoryBean(@Autowired DataSource dataSource){//自动装配dataSource
            SqlSessionFactoryBean ssfb = new SqlSessionFactoryBean();
            ssfb.setTypeAliasesPackage("com.itheima.domain");//domain里面，bean关系
            ssfb.setDataSource(dataSource);
            return ssfb;
        }
    
        @Bean
        public MapperScannerConfigurer getMapperScannerConfigurer(){
            MapperScannerConfigurer msc = new MapperScannerConfigurer();
            msc.setBasePackage("com.itheima.dao");//dao里，映射关系
            return msc;
        }
    }
    ```

  * 创建**test_junit**进行单元测试，在这里，无需ctx对象（被注解代替了）；无需通过ctx.getBean获取对象（直接@Autowired注入）

    ```java
    @RunWith(SpringJUnit4ClassRunner.class )
    @ContextConfiguration(classes = SpringConfig.class)
    public class test_junit {
    
        @Autowired
        private AccountService accountService;
    
        @Test
        public void m(){
            List<Account> all = accountService.findAll();
            Assert.assertEquals(3,all.size());//通过断言进行审查
        }
    }
    ```

![截屏2021-08-17 上午10.34.45](/Users/yuchenxi/Documents/《ycx-JavaWeb学习笔记》配图/截屏2021-08-17 上午10.34.45.png)

#### 18.3.4 loC底层原理

### 18.4 AOP

#### 18.4.1 概念与使用

* Aspect Oriented Programming：面向切面编程，是一种编程范式。用的最多的是**日志监控**（监控每个方法执行）和性能监控（比如监控每个方法的执行时间长短）

* **作用**：开发整合共性功能，最后以功能组合来完成开发

* **入门案例**

  * 连接点Joinpoint：实现类的所有方法  <font color='mediumseagreen'>这个是用于获取参数</font> 

  * 切入点Pointcut：具有共性的方法

  * 通知Advice：共性功能

  * 切面Aspect：描述切入点和通知的关系

  * 目标对象：简化的方法功能的运行对象

  * 织入：将共性功能放进残缺的方法里

  * 代理：通过创建原始对象的代理对象实现

  * 引入：给原始对象添加成员变量或者成员方法

  * **具体步骤：**

    * 创建普通接口，实现类，在pom中添加两个坐标

    * 创建共性功能类AopAdvice，将共性功能放入方法function里面

    * 在xml文件中声明bean（实体和aop的bean），就是刚刚创建的类，再配置<aop:config >（包括切入点、切入面）

      ```xml
      <?xml version="1.0" encoding="UTF-8"?>
      <beans xmlns="http://www.springframework.org/schema/beans"
             xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance"
             xmlns:p="http://www.springframework.org/schema/p"
             xmlns:context="http://www.springframework.org/schema/context"
             xmlns:aop="http://www.springframework.org/schema/aop"
             xsi:schemaLocation="http://www.springframework.org/schema/beans
              https://www.springframework.org/schema/beans/spring-beans.xsd
              http://www.springframework.org/schema/context
              https://www.springframework.org/schema/context/spring-context.xsd
              http://www.springframework.org/schema/aop
              https://www.springframework.org/schema/aop/spring-aop.xsd">
      
          <!--3.开启AOP命名空间-->
          <bean id="userService" class="com.itheima.service.impl.UserServiceImpl"/>
          <!--2.配置共性功能成功spring控制的资源-->
          <bean id="myAdvice" class="com.itheima.aop.AOPAdvice"/>
      
          <!--4.配置AOP-->
            <aop:config>
              <!--5.配置切入点-->
              <aop:pointcut id="pt" expression="execution(* *..*(..))"/>
              <!--6.配置切面（切入点与通知的关系）-->
              <aop:aspect ref="myAdvice">
                  <!--7.配置具体的切入点对应通知中那个操作方法-->
                  <aop:before method="function" pointcut-ref="pt"/>
              </aop:aspect>
          </aop:config>
        
      </beans>
      ```

#### 18.4.2 AOP配置

##### 18.4.2.1 xml配置

* **切入点**：

  * **expression**(切入点表达式)：类似于正则表达式，用于快速匹配方法描述的通配格式。**语法格式**：==关键字（访问修饰符 返回值 包名.类名.方法(参数)异常名）== ）
  * **举例**：<font color='mediumseagreen'>execution（public User com.ithema.servlice.UserService.findById（int））</font> "当执行 com.ithema.servlice包下的UserService类的返回值是User的访问修饰符是public的参数类型是int的finById方法时执行切入操作"
  * **通配符**：可以用逻辑运算符把多个表达式链接在一起
    * "  * "：单个任意
    *  " .. "：多个任意
    * " + "：匹配子类类型
  * **三种切入点配置**：
    * 公共切入点
    * 局部切入点：在aspect内部配置，和公共切入点一致
    * 特殊切入点：不是用pointcut-ref引入expression了，二是直接pointcut="execution..."

* **通知**：

  * **5种通知类型**

    * 前置通知before

    * 后置通知after

    * 返回后通知after_returning：方法 正常执行完毕返回结果后执行

    * 抛出异常后通知after_throwing

    * 环绕通知around：可以在原始方法前后都可以执行（需要调用原始方法 pjp.proceed();），甚至还可以阻止原始方法执行

      ```java
          public void around(ProceedingJoinPoint pjp) throws Throwable {
              pjp.proceed();
              System.out.println("AopAdvice的around执行");
          }
      }
      ```

  * **通知获取数据**

    * **概念**：就是在通知方法中**获取原始方法的数据**（参数，返回值之类...）

    *  **获取参数：**直接取得原始方法的参数值，在通知方法里面进行使用

      * (JoinPoint jp){  jp.getArgs(); } <font color='tomato'>主要方式！</font> 
      * (int x){直接使用x即可 }    <font color='mediumseagreen'>这种方式需要修改xml配置，如下列所示</font> 

      ```java
      public void save(int x ,int y){
        ...;
      }//原始方法
      ------------------
      public void before(int x,int y){
        ...
      }//通知方法
      ------------------
      <aop:aspect ref="myAdvice"> 
          <aop:pointcut id="pt" expression="execution(* *(..)) &amp;&amp; args(a,b) "/> //修改的xml配置，参数名称要和advice中的参数名一致
      	<aop:before method="before" pointcut-ref="pt" arg-names="b,a"/>
      </aop:aspect> //xml中的配置（注意此事ab顺序互换）
      ```

    * **获取返回值**：只有1.after-returning、2.around才会用到这个

      * 1.Advice里面要在参数（Object ret）;2.xml里面after-returning里面配置returning="ret"
      * 2.直接用around里面的Object ret=pjp.proceed()；注意此时Advice里的around()的必须加返回值，不能为void，可以return null。

      ```java
      //原始方法
      public int save（）{
        sout(111);
        return 222;
      }
      ---------------------------------
       //通知方法
      @Around("pt()")
          public Object around(ProceedingJoinPoint pjp) throws Throwable {
        			sout(333);
              Object proceed = pjp.proceed(pjp.getArgs());//直接通过此方式获取返回值
              return proceed; //必须返回东西，可以是null
          }
      ```

    * **获取异常**：1.after-throwing、2.around

      * 1.方式和获取返回值类似，就是没return
      * 2.around里面直接从抛出改为try catch就行

##### 18.4.2.1 注解配置

* **具体步骤**：

  * 1.在xml文件中添加两条，开启aop注解驱动识别、磁盘扫描

    ```xml
    <aop:aspectj-autoproxy/>  //开启aop注解驱动识别（区别于sprinf）
    <context:component-scan base-package="com.itheimaAop"/>  //开启磁盘扫描,注意命名空间需要设置
    ```

  * 2.在AopAdvice中添加几个注解

    ```java
    @Component //设置为spring组件
    @Aspect //设置为切面
    public class AopAdvice {
    
        @Pointcut("execution(* *..*(..))") //注意，这里将切入点体现为一个无返回值无实体的方法
        public void pt() {
        }
    
        @Around("pt()") //引用这个方法，（）不能省略
        public void around(ProceedingJoinPoint pjp) throws Throwable {
            pjp.proceed();
            System.out.println("AopAdvice的around执行");
        }
    }
    ```

  * 3.可以将切入点的pt()方法单独放到一个类里面，引用的时候直接（类名.pt()）就行

  * **附加：用纯注解+junit测试** <font color='tomato'>这是重点</font> 

    * SpringConfig

    ```java
    @Configuration
    @ComponentScan("com.itheimaAop") //这两个注解是第一步骤，让这个类作为配置文件，并且开启扫描
    @EnableAspectJAutoProxy //这个不能少，开启注解驱动的
    public class SpringConfig {
    }
    ```

    * Test_junit_Aop

    ```java
    @RunWith(SpringJUnit4ClassRunner.class)
    @ContextConfiguration(classes = SpringConfig.class)
    public class Test_junit_Aop {
        @Autowired
        private UserService userService;
    
        @Test
        public void m(){
            userService.save();
        }
    }
    ```

#### 18.4.3 综合案例

```java
@Component
@Aspect
public class Advice {
    @Pointcut("execution(* com.itheimaAopExample.service.AccountService.findById(..))")
    public void pt() {
    }

    @Around("pt()")
    public Object runTimeAround(ProceedingJoinPoint pjp) throws Throwable {
        Signature signature = pjp.getSignature();
        String typeName = signature.getDeclaringTypeName();
        String methodName = signature.getName();
        long startTime = System.currentTimeMillis();
        Object proceed = pjp.proceed(pjp.getArgs());
        long endTime = System.currentTimeMillis();
        System.out.println("方法："+typeName+methodName+" 运行时间:" + (endTime - startTime));
        return proceed;
    }
}
```

#### 18.4.4 AOP底层原理

* 装饰者设计模式：在不改变原有业务逻辑的基础上进行功能增强
* JDK Proxy：**面对接口的代理**：Proxy.newProxyInstance来实现的
* Cglib动态代理：code生成类库，是**面对的类的代理**。（对字节码继承再生成动态字节码）
* 织入时机：编译期织入，加载期织入，运行期织入

### 18.5 事物管理

#### 18.5.1 Spring事物核心对象

* spring在**业务层**处理事物，**区别于mysql只能执行一个语句，spring事物可将多个sql语句包裹。**
* **三个接口**
  * **PlatformTransactionManger**：提交、回滚、获取事物对象（spring的专门监督事物用的）
  * **TransactionDefinition**：封装了事物的基本信息（名称、读写属性、隔离等级、超时时间、传播行为特征）
  * **TransactionStatus**：描述事物所处的状态（检测事物提交成功与否）

#### 18.5.2 编程式事物

* 案例：在转账的时候，一个异常阻止了代码的运行，A的钱发送出来，B的钱没收到

  ```java
  public class AccountServiceImpl implements AccountService {
      private AccountDao accountDao;
      private DataSource dataSource;//注入以上两个对象
  
      public void setDataSource(DataSource dataSource) {
          this.dataSource = dataSource;
      }
  
      public void setAccountDao(AccountDao accountDao) {
          this.accountDao = accountDao;
      }
  
      @Override
      public void transfer(String outName, String inName, Double money) {
          PlatformTransactionManager ptm =new DataSourceTransactionManager(dataSource);//DataSource应对MyBatis，事物平台
  
          TransactionDefinition pd=new DefaultTransactionDefinition();//事物定义
  
          TransactionStatus ts=ptm.getTransaction(pd);//事物状态
  
          accountDao.inMoney(outName,money);
          int i =1/0;//现在哪怕抛了异常，事物不会提交，直接回滚
          accountDao.outMoney(inName,money);
  
          ptm.commit(ts);//提交事物
      }
  }
  ```

* 也可以将通用部分制作成一个AopAdvice

  ```java
  public class Advice {
  
      private DataSource dataSource;//注入以上两个对象
  
      public void setDataSource(DataSource dataSource) {
          this.dataSource = dataSource;
      }
  
      public Object shiWu(ProceedingJoinPoint pjt) throws Throwable {
  
          PlatformTransactionManager ptm = new DataSourceTransactionManager(dataSource);//DataSource应对MyBatis，事物平台
  
          TransactionDefinition pd = new DefaultTransactionDefinition();//事物定义
  
          TransactionStatus ts = ptm.getTransaction(pd);//事物状态
  
          Object ret = pjt.proceed(pjt.getArgs());
  
          ptm.commit(ts);//提交事物
  
          return ret;
      }
  }
  ```

#### 18.5.3 声明式事物（xml）

* 概念：spring已经替我们创建好了那些固定的关于事物的代码
* 使用tx命名空间配置**事物专属通知类**
* 使用aop，其中**advisor**是专门引用事物专属通知类
* **tx配置**：从下到上归属关系
  * advice：专门用于声明事物通知
  * attributes：定义通知属性
  * method：设置具体事物属性

#### 18.5.4 声明式事物（注解）

* 在service事物的那个方法上直接@Transactional <font color='tomato'>(更好的方式是配置在接口上面)</font>
* xml文件要加载注解驱动（因为还要扯上DataSource）

```java
public class AccountServiceImpl implements AccountService {
    private AccountDao accountDao;

    public void setAccountDao(AccountDao accountDao) {
        this.accountDao = accountDao;
    }

    @Transactional(
            readOnly = false,
            timeout = 1,
            isolation = Isolation.DEFAULT,
            rollbackFor = {},
            noRollbackFor = {},
            propagation = Propagation.REQUIRED
    ) //在注解中设置method属性
    public void transfer(String outName, String inName, Double money) {

        accountDao.inMoney(outName, money);
        int i = 1 / 0;//现在哪怕抛了异常，事物不会提交，直接回滚
        accountDao.outMoney(inName, money);

    }
}
```

```xml
//在xml中添加注解驱动
<bean id="txManager" class="org.springframework.jdbc.datasource.DataSourceTransactionManager">
        <property name="dataSource" ref="dataSource"/>
    </bean>

<tx:annotation-driven transaction-manager="txManager"/>
```

* **纯注解驱动方式（不需要xml文件）** <font color='tomato'>重要</font> 

  * 在AccountService接口方法处@Transactional

  * 在SpringConfig类上@EnableTransactionManagement

  * 在JdbcConfig类中搞定DataSource

    ```java
        @Bean
        public PlatformTransactionManager getPlatformTransactionManager(DataSource dataSource) {
            return new DataSourceTransactionManager(dataSource);
        }
    }
    ```

  * 其他纯注解部分和上一节的内容一致

#### 18.5.5 事物传播行为

* 事物管理员：事物管理、定义、状态、提交等一大串
* 事物协调员：自己定义的用dao调用的方法
* 事物传播行为：协调员对管理员所携带的事物的态度（7种），主要定义事物之间的关系
  * required
  * supports

#### 18.5.6 RedisTemplate

* 在业务层注入
* redisTemplate.opsForValue.set()、redisTemplate.opsForValue.get()（非阻塞式）
* boundValueOps().set()、boundValueOps().get()（阻塞式：第一个人塞完之后才能继续塞，单线程。效率慢，安全性高）

#### 18.5.7 事物的底层原理

* **策略模式**  使用不同策略的对象实现不同的行为方式

  

## 19. SpringMVC

### 19.1 概念与使用

* **概念**：一种web框架，是表现层技术，相当于进阶版servlet(在servlet基础上进行封装的框架)
* **具体使用步骤**：
  * 1.导入javax.servlet-api、jsp-api、spring-web、spring-webmvc 坐标
  * 2.建立servlet类，让它被spring控制（@controller、< bean>）
  * 3.web.xml配置SpringMvc核心控制器（就是相当于配置servlet的xml文件），
  * 4.在servlet中设置访问路径（比如（"/save"））,返回值String的值是跳转的页面
* **技术架构图**：

![截屏2021-08-22 上午10.23.36](/Users/yuchenxi/Documents/《ycx-JavaWeb学习笔记》配图/截屏2021-08-22 上午10.23.36.png)

### 19.2 基本配置

#### 19.2.1controller加载控制

* 就是加一个控制，让springmvc只扫描该扫描的

```xml
    <context:component-scan base-package="com.itheima">
        <!--这样就只会加载@Controller的类了-->
        <context:include-filter type="annotation" 			              expression="org.springframework.stereotype.Controller"/> 
    </context:component-scan>
```

#### 19.2.2静态资源加载

* 问题在于：web.xml配置的是"/"（拦截所有请求），导致图片这样的静态资源也无法加载

```xml
<mvc:default-servlet-handler/> //注意bug,必须加上 <mvc:annoation-driven/ >
```

#### 19.2.3中文乱码处理

* SpringMVC提供专门的中文字符过滤器，用于处理乱码问题

```xml
<filter>
    <filter-name>CharacterEncodingFilter</filter-name>
  <filter-class>org.springframework.web.filter.CharacterEncodingFilter</filter-class>
    <init-param>
      <param-name>encoding</param-name>
      <param-value>UTF-8</param-value>
    </init-param>
  </filter>
  <filter-mapping>
    <filter-name>CharacterEncodingFilter</filter-name>
    <url-pattern>/*</url-pattern>
  </filter-mapping>
//这个是在web.xml中配置
```

#### 19.2.4纯注解驱动

* 和xml的区别在于scan是用注解处理的

* 定义类ServletContainersInitConfig，相当于web.xml

  ```java
  public class ServletContainersInitConfig extends AbstractDispatcherServletInitializer {
      @Override
      protected WebApplicationContext createServletApplicationContext() {
          AnnotationConfigWebApplicationContext ctx =new AnnotationConfigWebApplicationContext();//web上下文
          ctx.register(SpringMvcConfig.class);//加载配置文件
          return ctx;
      }
  
      @Override
      protected String[] getServletMappings() {
          return new String[]{"/"};
      }
  
      @Override
      protected WebApplicationContext createRootApplicationContext() {
          return null;
      }
  
      @Override
      public void onStartup(ServletContext servletContext) throws ServletException {
          super.onStartup(servletContext);
          CharacterEncodingFilter cef = new CharacterEncodingFilter();
          cef.setEncoding("UTF-8");
  
          FilterRegistration.Dynamic registration=servletContext.addFilter("characterEncodingFilter",cef);
          registration.addMappingForUrlPatterns(EnumSet.of(DispatcherType.REQUEST,DispatcherType.FORWARD,DispatcherType.INCLUDE),false,"/*") ;
  
      }
  }
  ```

* 定义类 SpringMvcConfig，相当于Spring-mvc.xml

  ```java
  @Configuration
  @ComponentScan(value = "com.itheima", includeFilters =
  @ComponentScan.Filter(type = FilterType.ANNOTATION, classes = {Controller.class})
  )
  @EnableWebMvc //加载注解驱动
  public class SpringMvcConfig implements WebMvcConfigurer {
  
      @Override
      public void configureDefaultServletHandling(DefaultServletHandlerConfigurer configurer) {
          configurer.enable(); //放行所有普通资源
      }
  }
  ```

### 19.3 请求

#### 19.3.1 请求参数

* name就是方法的参数
* **普通类型**
  * int和name一起在参数里面
  * **@RequestParam（value="userName"）** :==形参注解==，在参数name前面改。这样浏览器直接输入userName也可传参数
* **引用类型**
  * 直接在参数里面写上（对象类型 对象名）
  * 引用和基本同名的时候，会被同时赋值
  * 传多个相同名称的值可以用list集合接收
  * list的泛型是实体类的方式：
  * map集合的传值：
* **数组**
  * 接受String[] nick
* **集合**
  * 注意在于List不能直接new对象，要@RequestParam("nick")List< String >nick     (是否是实体类、实体类里面是否有该属性)

#### 19.3.2 类型转换

* @DateTimeFormat（partten="yyyy-MM-dd"）.  参数前面可以直接加

#### 19.3.3 请求映射RequestMapping

* 可以在类和方法上

* 如果类上加了请求映射，则下面所有路径在浏览器路径之前都要+类请求映射（相当于前缀）
* 属性parm：浏览器输入地址就会自带这个参数。value是默认的

### 19.4 响应

#### 19.4.1 无数据跳转

* return "xxx.jsp";  return "forward:xxx.jsp";  return "redirect:xxx.jsp"; 
* redirect进不了WEB-INF文件夹（因为这个是安全目录，不允许地址栏跳转进去）
* 可以设置**快捷设置** <bean ...
* 返回值是void的话就会用访问路径作为浏览器路径而不是返回值

#### 19.4.2 带数据跳转

* 方式1：参数是HttpServletRequest request，直接request.setAttribute();
* 方式2：参数是Model model，model.addAttribute()
* 方式3：参数是ModelAndView modelAndView（也可以在方法里new），**注意这里返回值也是ModelAndView**，==modelAndView.addObject("yyy",yyy) ;modelAndView.setViewName("xxx.jsp")，这里也可加redirect:==

#### 19.4.3 纯数据跳转（Json）

* **@ResponseBody** ,返回的字符串就变成响应内容了
* 方法1：导入Jackson坐标，用工具。 ObjectMapper om =new ObjectMapper ; om.setStringAsValue();
* 方法2：@ResponseBody，再直接返回**对象本体**，但是要加载注解驱动 **<mvc:annoation-driven/ >**（注解的加载驱动是@EnableWebMvc ）  <font color='tomato'>重要</font> 

### 19.5 异步调用

#### 19.5.1 异步数据接收

* 同步（浏览器直接发出请求到服务器代码中），异步（发送请求到ajax,ajax再发送到服务器代码）

* **@RequestBody，在参数前面添加（形参注解）**

#### 19.5.2 异步数据响应

* 类的方上面添加@ResponseBody之后，就不会将返回值"page.jsp"解析
* **返回值写对象类型（多个对象就List），准备对象，返回对象。（jackson坐标，@ResponseBody都要弄）** <font color='tomato'>重要</font> 

#### 19.5.3 跨域访问

* 概念：不同域名下的访问资源（域名、IP地址、协议、端口(不同应用)不同等等，只要有一个不同）
* **@CrossOrigin：在方法上面添加（也可以在类上面添加），添加了就能跨域访问了**

### 19.6 拦截器

#### 19.6.1 概念

* **作用**：类似AOP，一种动态拦截方法调用的机制。作用：**1.指定方法前后执行的代码；2.阻止原始方法执行**。多个拦截器按照一定顺序，**对原始被调用功能进行==增强==**  <font color='tomato'>注意正着进来倒着出去</font> 
* **与过滤器的区别**：过滤器拦截所有东西（是servlet技术，tomcat启动的时候执行），拦截器只拦截springmvc（在springmvc内部，方法调用的时候执行）

#### 19.6.2 自定义拦截器

* **拦截器功能类（通知）**：实现HandleInterceptor接口，前置方法的返回false的时候表示不再向下运行了

  ```xml 
   <!--开启拦截器使用-->
      <mvc:interceptors>
          <!--开启具体的拦截器的使用，可以配置多个-->
          <mvc:interceptor>
              <!--设置拦截器的拦截路径，支持*通配-->
              <!--/**         表示拦截所有映射-->
              <!--/*          表示拦截所有/开头的映射-->
              <!--/user/*     表示拦截所有/user/开头的映射-->
              <!--/user/add*  表示拦截所有/user/开头，且具体映射名称以add开头的映射-->
              <!--/user/*All  表示拦截所有/user/开头，且具体映射名称以All结尾的映射-->
              <mvc:mapping path="/*"/>
              <mvc:mapping path="/**"/>
              <mvc:mapping path="/handleRun*"/>
              <!--设置拦截排除的路径，配置/**或/*，达到快速配置的目的-->
              <mvc:exclude-mapping path="/b*"/>
              <!--指定具体的拦截器类-->
              <bean class="MyInterceptor"/>
          </mvc:interceptor>
          <!--配置多个拦截器，配置顺序即为最终运行顺序-->
          <mvc:interceptor>
              <mvc:mapping path="/*"/>
              <bean class="MyInterceptor2"/>
          </mvc:interceptor>
          <mvc:interceptor>
              <mvc:mapping path="/*"/>
              <bean class="MyInterceptor3"/>
          </mvc:interceptor>
      </mvc:interceptors>
  ```

* **拦截器方法详解**

  * request：可以获取信息，可以做判断；response：；Object handler参数：是对method封装
  * ModelAndView：可以setViewName()，返回另一个页面

* **位置（切入点）**

#### 19.6.3 拦截器流程分析

![截屏2021-08-23 上午11.28.45](/Users/yuchenxi/Documents/《ycx-JavaWeb学习笔记》配图/截屏2021-08-23 上午11.28.45.png)

#### 19.6.4 责任链模式

* 一种行为模式，沿着一条预先设定的任务链顺序执行，每个节点都具有独立的工作任务。具有独立性、隔离性、灵活性、解耦

### 19.7 异常处理

#### 19.7.1 异常处理方案

* **1.普通方式**：
  * **定义异常处理器类ExceptionResolver**（全局异常通知类，不然太多try catch显得业务逻辑臃肿），实现**HandleExceptionResolver接口**，在类上面**@Component**，让这个异常处理类被spring管理。通过ModelAndView通知用户，用addObjec、serViewName.
  * 把处理器类功能区分，对不同异常进行不同的处理。用 if(...instanceof..){ ... }...else...  <font color='mediumseagreen'>这种方式没法具体定位哪块业务额代码出现问题</font> 
  * 底层也是AOP
* **2.注解方式**：
  * **@ControllerAvice** ,在**新建的ExceptionAdvice类**上面添加 ，在方法上面添加**@ExceptionHandler(NullPointerException.class)**,还可以添加@ResponseBody 返回json
  * 也可用ModelAndView返回页面（@ResponseBody就不加了） <font color='tomato'>和上面一样都是有局限性</font>

#### 19.7.2 项目实现异常处理的方案

* **可能出现的异常种类**：
  * **业务异常**：发信息给用户提醒规范操作
  * **系统异常**：发送固定消息安抚用户
  * **其他异常**：发信息给运维人员，需要记录日志

* **==自定义异常：==**
  * 定义BusinessException类（SystemException类...）继承RuntimeException类（程序都是在运行过程中遇到异常），然后在ExceptionAdvice类用注解的方式搞定自定义类.class。满足一个BusinessException类处理多个异常
  * **这里面的过程**：Controller判断异常原因抛到如BusinessException类中， 此时ExceptionAdvice类（这里面已经搞定了BusinessException.class）自动回应已经设定好的内容。

### 19.8 实用技术

#### 19.8.1 文件上传下载

* 1.导入common-fileupload坐标，用**MultipartResolver接口，commonMultipartResolver实现类**，整合上传下载步骤
* 2.在spring-mvc中配置<bean....class=...commonMultipartResolver
* 3.页面表单配置，要用entype....表示
* 4.file.transferTo()

#### 19.8.2 Restful

* 概念：一种网络资源的访问风格，定义了网络资源的访问方式

  * **url:  http://localhost:8080/user?username=123&password=666**
  * **restful:  http://localhost:8080/user/123/666  (注意在方法里面已经用(@PathVariable username,password)**

* 4中行为：GET/POST/PUT/DELETE（规范约定）

* 步骤

  ```java
  @RequestMapping(value="{id}"，method=Request.GET) //注意这里是{},不指定method就是查询GET
  public String x (@PathVariable Integer id){ //此处注解不能少
    sout("get:"+id);
    return"success.jsp";
  }
  ```

* 可以用**@RestController、@GetMapping("{id}")/@PostMapping("{id}")...**注解方式类似方式简单设置 <font color='tomato'>重要</font> 

* **用postman工具来发送Restful风格请求**

  * 19.9 校验框架

* js303规范、框架校验技术

  ```java
  <!--导入校验的jsr303规范-->
          <dependency>
              <groupId>javax.validation</groupId>
              <artifactId>validation-api</artifactId>
              <version>2.0.1.Final</version>
          </dependency>
  <!--导入校验框架实现技术-->
          <dependency>
              <groupId>org.hibernate</groupId>
              <artifactId>hibernate-validator</artifactId>
              <version>6.1.0.Final</version>
          </dependency>
  
  ```

* **具体步骤以及细节**

  * 1.在controller类创建方法，参数是三个：1.@valid javabean类；2.Errors类；3.Model类

  * 2.注意在javabean类的属性上面要添加注解@NotBlank("xxx不能为空")，这个xxx是属性名  <font color='mediumseagreen'>这里的校验规则注解可以有多种</font> 

  * 3.嵌套校验：引用类型属性要在属性上面添加@Valid。具体检验规则在这个类的内部的各个属性上面写

  * **4.分组校验：group=(GroupA.class)，定义接口GroupA，注意是@validated，想要单独校验哪个属性就在类的属性上面的注解添加标识groups={GroupA.class}**

    ```java
    public class Employee{
        //设定校验器，设置校验不通过对应的消息，设定所参与的校验组
        @NotBlank(message = "姓名不能为空",groups = {GroupA.class})//分组校验标识
        private String name;
    
        //一个属性可以添加多个校验器
        @NotNull(message = "请输入您的年龄",groups = {GroupA.class})
        @Max(value = 60,message = "年龄最大值不允许超过60岁")
        @Min(value = 18,message = "年龄最小值不允许低于18岁")
        private Integer age;
    
        //实体类中的引用类型通过标注@Valid注解，设定开启当前引用类型字段中的属性参与校验
        @Valid
        private Address address;
    }
    ```

  * 5.@NotNull、@NotEmpty、@NotBlank区别

    | 表单数据            | @NotNull | @NotEmpty | @NotBlank |
    | ------------------- | -------- | --------- | --------- |
    | String s = null;    | false    | false     | false     |
    | String s = “”;      | true     | false     | false     |
    | String s = “     “; | true     | true      | false     |
    | String s = “Jock”;  | true     | true      | true      |

### 19.10 SSM框架整合

* **概念**：用Spring整合SpringMvc和MyBatis

* **步骤概括**：

  * part1：Spring（框架基础）
  * part2：MyBatis（druid、pagehelper、mysql）
  * part3：Spring整合MyBatis（junit）
  * part4：SpringMvc（restful、json）
  * part5：Spring整合SpringMvc（Controller调用Service）
  * part6：其他（自定义异常、表现层数据封装）

* **具体步骤**：

  * part1+part2:
    * 创建Spring配置文件（扫描组件）
    * 创建MyBatis映射文件
    * 将MyBatis整合进Spring（sqlSessionFactoryBean、数据源（druid、jdbc.properties）、映射扫描、事物、分页插件）
    * 创建单元测试

  * spring整合springMVC，设置web.xml中的listener（意义监听、匹配。就是将appliactionContext.xml加载进web.xml中），再在controller中注入service对象，调用增删改查的方法
  * **表现层数据封装**：将几种类型的数据（true/false、单个数据、json、集合）进行格式统一划分
    * 数据格式：状态编码code、数据data、消息message
    * 数据状态code细节：用static final 给各个不同的状态码进行赋值

* 其他注意事项：

  * Restful风格是规范而不是规定，灵活使用

  * 用纯注解方式整合框架，就是干掉以下几个文件，保留jdbc.properties文件

    * **web.xml**

      * 与applicationContext融合的监听器
      * utf-8过滤器
      * DispatcherServlet核心控制器

    * **applicationContext.xml**

      * bean scan扫描，排除controller
      * mybatis
        * domain
        * dao
        * 分页插件
      * placeholder
      * dataSource

      * 事物管理器和事物管理驱动

    * **spring-mvc.xml**

      * 扫描controller
      * 注解驱动

    * **UserDao.xml**

## 20.dubbo

### 20.1 集群与分布式

#### 20.1.1 集群

* **概念**：同一个业务模块部署在多个服务器

#### 20.1.2 分布式

* **概念**：一个大业务，拆成许多小的业务模块，放在不同的服务器上

* **单体**：项目启动慢，性能低，可靠性差
* **垂直**：单体架构中多个模块拆分成多个独立的项目，形成多个独立的单体架构；问题：重复功能多
* **分布式**：将公共重复的模块或者组件抽离出来，作为独立的服务，供其他调用者消费，以实现服务的共享和重用；问题：服务的提供方一旦发生变更，所有消费方都需要变更
* **SOA**：通过ESB总线（服务中介）来进行调用
* **微服务**：在SOA上进行升华，业务需要彻底组件化和服务化，原有的单个业务系统会拆分成多个独立开发，设计，运行的小应用，小应用通过服务完成交互和集成。

### 20.2 dubbo

#### 20.2.1 概念与架构

* **概念**：高性能、轻量级的 Java RPC(rpc-网络协议) 框架。提供高性能和透明化的 RPC **远程服务调用方案**，以及 SOA 服务治理方案。

* **节点角色说明**：
  * **Provider**：服务的提供者
  * **Container**：容器
  * **Registry**：注册中心，相当于中介，记录提供者，消费者的信息   <font color='tomato'>最重要的！zookeeper就是注册中心</font> 
  * **Customer**：消费者，invoke调用
  * **Monitor**：统计服务的调用次数和调用时间的监控中心count

#### 20.2.2 dubbo快速入门

* dubbo用zookeeper作为注册中心（本质是将本地的注入改成远程的调用）
* **配置服务提供者（service）**
  * 配置pom.xml，将spring包下面的@service改成dubbo包下面**@service**，就是将这个类对外发布，端口地址等信息放进zookeeper
  * 在applicationContext.xml 配置<dubbo.....
* **配置服务消费者（web）**
  * ==去除依赖==，配置pom.xml
  * 去除@Autowird，添加**@Reference**（远程注入，从zookeeper里面获取url再封装）
  * 在springmvc.xml里面配置<dubbo.....
* **单独创建公共接口模块dubbo-Interface**
  * 让service、web都依赖这个接口模块
* dubbo damin客户端可防止开发分布式的时候开发人员扯皮...

#### 20.2.3 dubbo高级特性

* **序列化**

  * 作用：是在两个机器传输对象数据的时候，对象要进行序列化和反序列化，通过流进行传输
  * **创建类对象的时候必须要实现Serializable接口**

* **地址缓存**

  * 概念：注册中心挂了，服务还是可以访问的！
  * 原因是dubbo服务消费者第一次调用的时候，会将服务方地址缓存到本地，以后访问的时候不会访问调用中心

* **超时与重试**

  * 概念：消费者调用提供者的时候，如果出现阻塞，等待情况的时候，消费者会一直等待下去，如果大量请求造成线程堆积，势必会造成雪崩
  * **dubbo利用超时机制解决此问题，设置超时时间，在这个时间段里面，无法完成服务访问，自动断开连接** @service3）：三秒超时，重试0次，一般都是在服务的提供方配置timeout

* **多版本**

  * 灰度发布：当做出新版本提供者的时候，先让一部分消费者试用
  * 在@Reference处指定

* **负载均衡** loadBalance

  * 发送多个请求被多个服务器接受，这些请求会被平均分配到多个服务器中

  * 4种负载均衡的策略：
    * Random：按权重设置随机概率
    * RoundRobin：按权重轮询
    * LeastActive
    * ConsistenHash

* **集群容错**

  * 看服务是否正常运行，不正常就找下一个

  * FailOverCluster：失败重试，当出现失败的时候，重试其他服务器，默认2次，一般用于读的操作

* **服务降级**

  

## 21. zookeeper

### 21.1 zookeeper概念

* **概念**：Apache Hadoop（大数据框架）下的子项目，是一个树形的目录服务，是一个分布式的，开源的**==分布式==应用程序的==协调服务==**  <font color='mediumseagreen'>只负责管理</font> 
* **主要功能**：
  * **配置管理**：配置中心管理多个服务（公有的配置信息放到配置中心）
  * **分布式锁**：让数据只让一个人访问到（之前的锁是jdk的，在分布式里面不管用。这个锁是第三方锁）<font color='tomato'>重要</font> 
  * **集群管理**：作为服务者消费者的注册中心

### 21.2 安装与配置

* 先启动服务端再启动客户端注意

### 21.3 zookeeper 命令操作

#### 21.3.1 zookeeper数据模型

* zookeeper是树形目录结构，具有层次化的结构，
* **ZNode：节点，每个节点都会保存自己的数据和节点信息**
* 节点拥有自节点，同时允许少量的数据存储在该节点之下  <font color='mediumseagreen'>直接在节点保存ip,接口之类的信息</font> 
* **节点4大类**：
  * 持久化节点
  * 临时节点 -e   <font color='mediumseagreen'>和客户端会话绑定，一旦会话失效，客户端所创建的节点就消失</font> 
  * 持久化顺序节点 -s
  * 临时顺序节点 -es

#### 21.3.2 服务端常用命令

* ./zkServer.sh start  <font color='tomato'>以下都是终端命令</font> 
* ./zkServer.sh stop
* ./zkServer.sh status
* ./zkServer.sh restart 先停后启动

#### 21.3.3 客户端常用命令

* **持久化节点**： 
  * ./zkCli.sh  默认是连接本机的地址，直接输入这个即可
  * ./zkCli.sh -server ip:prot  连接其他服务端
  * ls /  看所有根目录下的节点
  * create /app1  创建app1这个节点
  * set /app1 ycx   get /app1  添加值、获取值  <font color='mediumseagreen'>节点是可以存储信息的的，也可以连接子节点</font> 
  * delete /app1 删除节点（如果下面有子节点就不能直接删除）
  * deletall /app1 删除带有子节点的节点

* **临时节点**：

  * create -e /app1   临时节点

  * create -es /app1  临时顺序节点
  * ls -s /app1 查看节点的详细信息  <font color='mediumseagreen'>注意中间的空格</font> 

### 21.4 zookeeper javaAPI操作

#### 21.4.1Curator介绍

* **概念**：zookeeper的Java客户端，类似redis的jedis。

#### 21.4.2Curator API 常用操作

* **建立连接** <font color='mediumseagreen'>需要导入坐标</font> 

  ```java
   @Before
      public void testConnect() {
          RetryPolicy retryPolicy = new ExponentialBackoffRetry(3000, 10);
          client = CuratorFrameworkFactory.builder()
                  .connectString("192.168.149.135:2181")
                  .sessionTimeoutMs(60 * 1000)
                  .connectionTimeoutMs(15 * 1000)
                  .retryPolicy(retryPolicy)
                  .namespace("itheima")
                  .build();
  
          //开启连接
          client.start();
      }
  ```

* **添加节点**

  ```java
  /**
       * 创建节点：create 持久 临时 顺序 数据
       * 1. 基本创建 ：create().forPath("")
       * 2. 创建节点 带有数据:create().forPath("",data)
       * 3. 设置节点的类型：create().withMode().forPath("",data)
       * 4. 创建多级节点  /app1/p1 ：create().creatingParentsIfNeeded().forPath("",data)
       */
      @Test
      public void testCreate() throws Exception {
          //2. 创建节点 带有数据
          //如果创建节点，没有指定数据，则默认将当前客户端的ip作为数据存储
          String path = client.create().forPath("/app2", "hehe".getBytes());
          System.out.println(path);
  
      }
  
      @Test
      public void testCreate2() throws Exception {
          //1. 基本创建
          //如果创建节点，没有指定数据，则默认将当前客户端的ip作为数据存储
          String path = client.create().forPath("/app1");
          System.out.println(path);
  
      }
  
      @Test
      public void testCreate3() throws Exception {
          //3. 设置节点的类型
          //默认类型：持久化
          String path = client.create().withMode(CreateMode.EPHEMERAL).forPath("/app3");
          System.out.println(path);
  
  
      }
  
      @Test
      public void testCreate4() throws Exception {
          //4. 创建多级节点  /app1/p1
          //creatingParentsIfNeeded():如果父节点不存在，则创建父节点
          String path = client.create().creatingParentsIfNeeded().forPath("/app4/p1");
          System.out.println(path);
      }
  ```

* **删除节点**

  ```java
   /**
       * 删除节点： delete deleteall
       * 1. 删除单个节点:delete().forPath("/app1");
       * 2. 删除带有子节点的节点:delete().deletingChildrenIfNeeded().forPath("/app1");
       * 3. 必须成功的删除:为了防止网络抖动。本质就是重试。  client.delete().guaranteed().forPath("/app2");
       * 4. 回调：inBackground
       * @throws Exception
       */
  
  
      @Test
      public void testDelete() throws Exception {
          // 1. 删除单个节点
          client.delete().forPath("/app1");
      }
  
      @Test
      public void testDelete2() throws Exception {
          //2. 删除带有子节点的节点
          client.delete().deletingChildrenIfNeeded().forPath("/app4");
      }
      @Test
      public void testDelete3() throws Exception {
          //3. 必须成功的删除
          client.delete().guaranteed().forPath("/app2");
      }
  
      @Test
      public void testDelete4() throws Exception {
          //4. 回调
          client.delete().guaranteed().inBackground(new BackgroundCallback(){
  
              @Override
              public void processResult(CuratorFramework client, CuratorEvent event) throws Exception {
                  System.out.println("我被删除了~");
                  System.out.println(event);
              }
          }).forPath("/app1");
      }
  ```

  

* **修改节点**

  ```java
  /**
       * 修改数据
       * 1. 基本修改数据：setData().forPath()
       * 2. 根据版本修改: setData().withVersion().forPath()
       * * version 是通过查询出来的。目的就是为了让其他客户端或者线程不干扰我。
       *
       * @throws Exception
       */
      @Test
      public void testSet() throws Exception {
          client.setData().forPath("/app1", "itcast".getBytes());
      }
  
  
      @Test
      public void testSetForVersion() throws Exception {
  
          Stat status = new Stat();
          //3. 查询节点状态信息：ls -s
          client.getData().storingStatIn(status).forPath("/app1");
  
  
          int version = status.getVersion();//查询出来的 3
          System.out.println(version);
          client.setData().withVersion(version).forPath("/app1", "hehe".getBytes());
      }
  ```

* **查询节点**

  ```java
  /**
       * 查询节点：
       * 1. 查询数据：get: getData().forPath()
       * 2. 查询子节点： ls: getChildren().forPath()
       * 3. 查询节点状态信息：ls -s:getData().storingStatIn(状态对象).forPath()
       */
  
      @Test
      public void testGet1() throws Exception {
          //1. 查询数据：get
          byte[] data = client.getData().forPath("/app1");
          System.out.println(new String(data));
      }
  
      @Test
      public void testGet2() throws Exception {
          // 2. 查询子节点： ls
          List<String> path = client.getChildren().forPath("/");
  
          System.out.println(path);
      }
  
      @Test
      public void testGet3() throws Exception {
  
  
          Stat status = new Stat();
          System.out.println(status);
          //3. 查询节点状态信息：ls -s
          client.getData().storingStatIn(status).forPath("/app1");
  
          System.out.println(status);
  
      }
  ```

* **watch事件监听**

  * **概念**：zookeeper允许用户在指定节点上设置watch监听器，并且通过一些特定的事件触发的时候，zookeeper服务端会将事件通知到感兴趣的客户端上去。 <font color='tomato'>重要机制</font> 

  * 订阅机制：多个订阅这同时监听一个对象，对象自身状态发生变化 的时候，会通知所有订阅者
  * **三种watcher**
    * NodeCache：监听某一个节点
    * PathChilrenCatch：监听一个节点的子节点
    * TreeCache：监听某一个节点的整个树上面的所有节点 <font color='tomato'>注意只是是包含它以及它的下面的子节点。而不是整个树</font> 

#### 21.4.3 分布式锁

* **概念**：是前面几个操作的综合应用。因为跨JVM之间已经无法通过多线程锁解决同步问题。所以需要**跨机器的进程之间的数据同步**问题，这个就是分布式锁。抢票、秒杀都会使用此技术。

* **分布式锁原理**： <font color='cornflowerblue'>面试题</font> 
  * **核心思想**：当客户端需要获取锁的时候，则**创建节点**，使用完锁，则**删除该节点**。 <font color='tomato'>一定注意是分布式才能用</font> 
  * 1.客户端在获取锁的时候，在lock节点下创建**临时顺序**节点    <font color='mediumseagreen'>(临时：即使宕机了，还能删除；顺序：记录顺序，自己创建的节点是最小的话就获取锁)</font>    
  * 2.然后获取lock下的所有子节点，若**发现自己创建的子节点序号最小，那么就认为该客户端获取到了锁**。使用完锁之后，将该节点删除
  * 3.如果序号**不是最小的，说明没有获取到锁，此时客户端要找比自己小的那个节点，同时对其注册时间监听器，监听删除事件**
  * 4.如果比自己小的那个节点被删除，此时客户端监听获取了通知，此时再判断自己创建的节点序号是不是最小的，是的话获取锁，不是的话，再次重复上面过程。
* **5种锁方案**：
  * InterProcessSemaphoreMutex：分布式排它锁（非可重入锁）
  * InterProcessMutex：分布式可重入排它锁
  * InterProcessReadWriteLock：分布式读写锁
  * InterProcessMultiLock：多个锁作为单个实体管理的容器
  * InterProcessSemaphoreV2：共享信号量

#### 21.4.4模拟12306售票案例

* 开启服务连接（用静态方法）——获取锁lock.acquire()——做逻辑操作ticket--——释放锁lock.release()

### 21.5 zookeeper 集群搭建

* **概念**： 
  * **Leader选举**：
    * Serverid：服务器id，编号越大在选择算法中的权重越大
    * Zxid：数据id，越大说明数据越新，在选举算法中权重也就越大
    * 在Leader选举中，如果某台ZooKeeper获取了超过半数选票（注意自己也会投自己），则成为Leader（后面就不会参与投票了）
* **集群搭建**：

### 21.6 zookeeper 核心理论

* 集群角色：
  * Leader领导者
    * 1.处理**事物**（增删改）请求
    * 2.集群内部各个服务器的调度者
  * Follower跟随者
    * 1.处理客户端非事物请求
    * 2.转发事物请求给Leader服务器
    * 3.参与Leader选举投票
  * Observer观察者
    * 1.处理客户端非事物请求
    * 2.转发事物请求个Leader



## 22.Git

### 22.1 概念与使用

* **概念**：git是分布式版本控制系统，可以自动记录版本的改动，也可以让同事协助编辑。每次改动的时候都可以编辑相应的改动日志。
* **使用方法**：先让一个文件夹里面使用**$ git init** 命令让它作为git的仓库repository（此时该文件夹里面会有一个隐藏的.git文件夹），==必须在该文件夹里面创建文件==，每次修改后用命令行**$ git add xxx**，将改动的文件夹暂存到暂存区中，再**$ git commit -m"这里写日志信息"**，将暂存区的文件发送到本地历史仓库。

* **常用的几个命令**
  * **$ git reflog**：显示所有的修改版本
  * **$ git reset --hard 76a4ea5**：回溯到76a4ea5这个版本，可以转到任何版本 

### 22.2 分支

* **概念与应用场景**
  * **概念**：分支是每次提交的代码，串成一条时间线，将自己的开发从主线分离，以免影响主线的开发。
  * **应用场景**：
    * 比如开发周期较长的模块，中途需要暂时先放下当前的工作，开启新的功能开发，但是现在的代码不能舍弃或者丢失。此时需要用分支开启新的版本控制
    * 尝试一个新的模块，相当于支线任务
  * **分支的工作流程**：
    * Master：主分支（具有指针的性质，**指向提交的代码版本**）
    * Head：指向的是**==当前==所使用的分支**（可能是主分支也可能是其他分支）
    * 创建开启新的分支dev之后，Head就会指向这个dev，如果删除支线之后，Head重新指向Master（相当于合并了分支）
    * 创建分支——切换分支——合并分支——删除分支
  * **分支的相关命令**：
    * **$ git branch 分支名**：创建分支
    * **$ git checkout 分支名** ：转到一个分支     <font color='mediumseagreen'>注意，如果我在分支dev1中创建了一个文件a，此时ls可以显示a和之前所有的文件，但是如果此时分支切换到master，发现ls是，a就不存在了。分支这个支线任务可以包含之前所有的文件数据，但是主线不能包括在支线创建的文件</font>
    *  **$ git merge 分支名**：融合分支（一般都是将分支融合到master中）
    * **$ git branch -d 分支名**：删除分支

### 22.3 远程仓库

* **概念**：企业是将本地历史仓库推送put到远程仓库，个人是从远程仓库克隆clone或者拉取pull
* **拉取和克隆的区别**：拉取是获取更新之后的新的内容；克隆的全盘获取
* **==在企业中一定要先拉取再推送，防止冲突==**
* 用码云pull push 流程：
  * add、commit 、**git push -u origin master**（提交）
  * **git pull origin master**（拉取）
* **代码冲突**：原因：多个人同时修改了同一个文件或者同一个 Java 类，提交时会显示提交失败。解决方法是先 pull 再push，如果失败就手动解决

### 22.4 idea集成

* 注意直接从 gitee上面拉项目的话直接在 idea开始界面Get from VCS 进行操作
* 版本回滚注意是用 revert...



## 23.项目一

### 23.1Day01

* 首先创建父模块 **health_parent**，只是 利用它的pom 文件（存放了所有的依赖坐标，用 depemdyManagement管理）作为统一管理，

  ```xml
   <dependencyManagement>
          <dependencies>
              <dependency>
                  <groupId>org.springframework</groupId>
                  <artifactId>spring-context</artifactId>
                  <version>${spring.version}</version>......
  ```

* 再创建公用模块 **health_common**，作为工具类、依赖大全的存放地（注意此时依赖是继承父工程，因为父工程用depemdyManagement管理了坐标并且统一管理了版本，此工程还是得写如下设置）

  ```xml
   <dependencies>
          <dependency>
              <groupId>com.github.pagehelper</groupId>
              <artifactId>pagehelper</artifactId>......
  ```

* 创建接口模块 **health_interface**模块，直接依赖 health_common 模块

* 创建 **health_service_provider** 业务模块，用 spring 进行管理，注意这里将spring 之前的 applicationContext.xml 文件拆分成了：

  * spring-dao.xml（数据库相关的三个）
  * spring-tx.xml（事物相关的配置）
  * spring-service.xml（注册 dubbo）
  * SqlMapConfig.xml（分页）
  * web.xml （设置监听器）

### 23.2 Day02

* 今日需求：
  * 检查项：具体的项目
  * 检查组：和检查项目是多对多的关系
  * 体检套餐：和检查组是多对多关系



## 24. SpringBoot

### 24.1 概念与使用

#### 24.1.1 概念

* **概念**：springboot是提供了一种**快速使用spring的方式**，让使用者将**精力集中在逻辑代码的开发中，而非配置上**，大大提高开发效率（解决spring最大的两个缺点：配置文件、依赖 ）
* **功能**： <font color='mediumseagreen'>不是对spring功能上的增强，而是提供了快速使用spring的方式</font> 
  * 1.**自动配置**：在项目启动时候springboot会自动决定spring的配置文件
  * 2.**起步依赖**：将多个依赖打包在一起，项目直接依赖这个汇总的依赖就行，本质就是依赖传递
  * 3.其他的一些辅助功能：如嵌入式服务器、安全、健康检测、外部配置

* **操作步骤**：

  * 1.用maven构建项目，注意打包方式是jar

  * 2.在pom文件中继承父工程

    ```xml
      <parent>
           <groupId>org.springframework.boot</groupId>
           <artifactId>spring-boot-starter-parent</artifactId>
           <version>2.1.8.RELEASE</version>
       </parent>
    ```

  * 3.在pom文件中定义起步依赖

    ```xml
        <dependencies>
            <dependency>
                <groupId>org.springframework.boot</groupId>
                <artifactId>spring-boot-starter-web</artifactId>
            </dependency>
        </dependencies>
    ```

  * 4.编写引导类（springboot项目的入口），这个是springboot特有的类，注意注解的添加。

    ```java
    package com.ycx;
    
    import org.springframework.boot.SpringApplication;
    import org.springframework.boot.autoconfigure.SpringBootApplication;
    
    /**
     * @author YuChenXi
     * @date 2021/9/17 9:23 下午
     */
    @SpringBootApplication
    public class hhhApplication {
        public static void main(String[] args) {
            SpringApplication.run(hhhApplication.class,args);
        }
    }
    //其他步骤就和之前一样，定义controller...
    ```

* **直接用idea启动springboot工程...终极简化版，连打包的依赖坐标都不用记录了**，直接创建项目的时候点击springboot项目，进行一步步的配置

### 24.2 起步依赖原理分析

#### 24.2.1 spring-boot-starter-parent

* 层层依赖，最上层是一个大pom文件**spring-boot-dependencies-2.1.8.RELEASE.pom**，依赖了所有的坐标 ，最重要的是**==定义的版本信息==**（这些都是springboot开发者配置好的，保证不会产生版本冲突）

#### 24.2.2 spring-boot-starter-web

* 和上面原理类似，**==定义了具体完成该功能的坐标合集==**，其中大部分坐标信息（共性的）来自于父工程，少部分坐标信息（个性的）是本工程自己定义的。**这个也就是本工程的依赖**。

### 24.3 springboot配置

#### 24.3.1 配置文件分类

* application.properties：修改springboot的给出的默认配置

#### 24.3.2 yaml格式

* application.yml 配置文件改进版本

* 大小写
* 数据值前有空格
* 缩进只允许用空格而非tab
* 注释是#

```xml
sever:
	port: 8080
-----注意空格------
person:
  name: ${name}
  age: 11
```

#### 24.3.3 读取配置文件内容 （三种方式）从配置文件中将值拿出来

* @Value (适用少量的值)
* @Environment  
* **@ConfigurationProperties("person") //"person"：存在后缀：先找到person层级再进行匹配（无后缀的话就是从第一层级开始匹配）**  <font color='mediumseagreen'>用的最多</font> 

#### 24.3.4 profile

* **概念**：springboot简单配置配置不同的环境（开发、测试、生产。。。数据库地址、服务器端口都是不同的）

* **用法**：

  * **profile**：配置application-test.properties ,在application.properties中spring.profiles.active=test；进行配置转换

  * **yaml**：

    ```yaml
    ---
    server:
      port: 8086
      
    spring:
      profile: test
    ---
    server:
      port: 8087
      
    spring:
      profile: dev #用yml文件设置多环境配置
    ---
    spring:
      profiles:
        active: test （这个是指定激活哪个环境）
      
    ```

  * **打包激活方式**：

    * 直接在配置文件中：spring.profiles.active=dev 

    * 在idea中，VM option指定： -Dspring.profiles.active=dev
    * **在控制台：打包成jar包，java -jar xxx.jar --spring.profiles.active=dev （用的最多）**

#### 24.3.5 内/外配置加载顺序

### 24.3 springboot整合其他框架

#### 24.3.1 整合Junit

* 直接使用springboot自己创建的junit项目，无需创建springboot

#### 24.3.2 整合mybatis

* 选择MySQL、MyBatis的jar依赖

* 注解方式

  ```java
  @SpringBootTest
  class SpringBootMybatis2ApplicationTests {
  
      @Autowired
      private UserMapper userMapper; //dao接口
  
      @Test
      void contextLoads() {
          List<User> all = userMapper.findAll();
          System.out.println(all);
      }
  
  }
  ```

* xml文件方式

  ```xml
  <?xml version="1.0" encoding="UTF-8" ?>
  <!DOCTYPE mapper PUBLIC "-//mybatis.org//DTD Mapper 3.0//EN" "http://mybatis.org/dtd/mybatis-3-mapper.dtd">
  
  <mapper namespace="com.example.springbootmybatis2.mapper.UserMapperXml">
      <select id="findAll" resultType="user">
          select * from USER
      </select>
  </mapper>
  ```

#### 24.3.3 整合redis

* 只需要勾选redis那一个就行

```java
package com.example.springbootredis2;

import org.junit.jupiter.api.Test;
import org.springframework.beans.factory.annotation.Autowired;
import org.springframework.boot.test.context.SpringBootTest;
import org.springframework.data.redis.core.RedisTemplate;

@SpringBootTest
class SpringBootRedis2ApplicationTests {

    @Autowired
    private RedisTemplate redisTemplate;

    @Test
    void testSet() {
        redisTemplate.boundValueOps("name").set("yuchenxi1111");
    }

    @Test
    void testGet(){
        Object name = redisTemplate.boundValueOps("name").get();
        System.out.println(name+"!!!!!!!!!!");
    }

}
```

### 24.4 SpringBoot原理分析

#### 24.4.1 SpringBoot 自动配置

* **注解**：特殊的接口，将注解的值或者方法在程序运行的时候织入进业务代码中。

* **condition**

  * **疑问**：为什么在引用坐标之后就可以直接Autowird使用坐标对象，

  * **概念**：让spring满足某些条件（condition）之后，才创建bean。这里condition就是检测是否依赖了特定坐标

* **切换内置web服务器**

  * springboot内置四个服务器，通过一定的机制进行切换

* **@Enable*注解**

  * **疑问**：如果直接导入第三方jar包（不走依赖），是不能直接使用jar对象，那么如何？
  * **注意：**@ComponentScan只能扫描和引导类同一级以及子级的文件夹的内容（如果想要额外的扫描直接@@ComponentScan("xxx")，但是很不方便）

* **@import注解**

  * **概念**：专门解决上面的问题，用import注解加载类，这些类都会被spring创建，并且放进IOC容器

    **Import可以被封装成Enable注解**

  * **细节**： **4种Import导入方法（导入外部第三方对象（第三方Jar、自己写的其他模块））**

    * 1.导入Bean： @Import(User.class)
    * 2.导入配置类：@Import(UserConfig.class)
    * **3.导入Importselector实现类**  <font color='mediumseagreen'>这个就是springboot导入外部第三方对象</font> 
    * 4.导入ImportBeanDefinetionRegistrar实现类

* **@EnableAutoConfiguration** 

  * <font color='tomato'>自动配置原理</font> 
    * 1.项目启动，加载注解@springbootApplication——————>加载@EnableAutoConfiguration(——————>@Import)
    * 2.@Import里使用了**自定义选择器Importselector**（加载文件META-INF/spring.factories），此文件定义了该依赖坐标的**大量的配置类**（更大量的bean对象）
    * 3.根据condition**进行判断**是否需要将该bean加载到springIOC（@ConditionOnMissBean、@ConditionOnProperty...）

* **自定义starter实现**

  * 步骤分析
  * 具体操作
    * 

#### 24.4.2  SpringBoot 监听机制

* **java监听机制**
  * 事件：Event（必须继承EventObject类）
  * 事件源：Source
  * 监听器：Listener
* **SpringBoot监听机制**
  * springboot项目启动的时候，会对几个监听器进行回调，可以**实现这几个接口**，进行下一步操作
  * **生命周期**
    * ApplicationContextInitailizer：启动，bean还没有加载，容器初始化，资源加载
    * SpringApplicationRunListener：运行，bean的初始化，资源加载完成，容器创建
    * CommandLineRunner：系统运行完成
    * ApplicationRunner：系统运行完成

#### 24.4.3 SpringBoot 启动流程

### 24.5 监控

* 概述：springboot自带的actuator插件，可以监控状况、bean加载、配置信息。。。
* 使用：1.导入依赖；2.访问URL地址
* SpringBootAdmin

### 24.6 项目部署

## 25. ElasticSearch

### 25.1 概念

* **概念**：解决关系型数据库性能低，功能弱的缺点（比如MySQL模糊查询不走索引而是全表查询），主要用于网站的页面搜索服务。原理是倒排索引。
* **倒排索引**：通过词条（文本按照一定规则推出来的）反推出来完整内容
* **存储和搜索原理**：
  * 用户——>索引库——>文档
  * 一个term词条可以对应多个value。每个value都是对应的完整的json数据信息。这样term就会成为**树形结构**的根部
  * 一条语句拆分成多个term，每个term对应的value可能有重复的或者完全不同。取得**交集或者并集**即可。
  * Mysql是存储和管理数据的，ES是搜索数据的。数据由Mysql实时同步给ES，直接通过ES进行查询，增删改还是在MySql中进行
* **核心概念**：
  * 索引库index（类似数据库）
  * 映射mapping（类似数据表）
  * 文档documents（类似数据）

### 25.2 脚本操作

* 简单数据类型：（字符串）
  * text：会分词，不支持聚合
  * keyword：不会分词，支持聚合
  * 数值、布尔、二进制、范围类型（integer_range...）
* 复杂数据类型
  * 数组：[]
  * 对象：[]

```json
PUT /ycxtest
  {
    "mappings": {
      "properties": {
        "name":{
          "type": "keyword"
        },
        "age":{
          "type": "text"
        }
      }
    }
}
#创建索引ycxtest

GET /ycxtest/_mapping
#查看所以的结构

PUT ycxtest/_doc/1
{
  "name":"yuchenxi",
  "age":18
}
#不指定id只能用post,上面那个1就是id


GET ycxtest/_doc/1
#ycxtest是索引，增删改都要加上索引的名称，_doc代表类型是文档



GET ycxtest/_search
#_search就是查询所有数据


POST ycxtest/_doc/1
{
  "name":"yuchenxi111",
  "age":188
}
#修改数据
```

* **分词器**：默认的分词器对中文不友好（只能一个字一个字分）。使用ik分词器插件效果好。

  ```json
  PUT ycxtest/_doc/3
  {
    "name":"ycx",
    "age":"减肥大概要多久食发鬼华容道未亡人多少"
  }
  #注意这里的age是text的是可以分词的，但是默认的standard,只能一个字一个字
  
  GET ycxtest/_search
  {
    "query":{
      "term": {
        "age": {
          "value": "肥"
        }
      }
    }
  }
  #这里查"减"可以，"减肥"不行
  
  
  PUT /ycxtest1
    {
      "mappings": {
        "properties": {
          "name":{
            "type": "keyword"
          },
          "adress":{
            "type": "text"
            , "analyzer": "ik_max_word"
          }
        }
      }
  }
  
  PUT ycxtest1/_doc/4
  {
    "name":"ycx",
    "adress":"太费劲和人格化如火如荼"
  }
  
  PUT ycxtest1/_doc/5
  {
    "name":"ycx",
    "adress":"人格豆腐火锅医防结合"
  }
  
  GET ycxtest1/_search
  {
    "query":{
      "term": {
        "adress": {
          "value": "人格"
        }
      }
    }
  }
  #这里就查询出了两条数据
  ```

### 25.3 JavaApi操作

```java
package com.ycx.test1;

import com.alibaba.fastjson.JSON;
import com.ycx.test1.domain.Person;
import org.apache.http.HttpHost;
import org.elasticsearch.action.admin.indices.delete.DeleteIndexRequest;
import org.elasticsearch.action.delete.DeleteRequest;
import org.elasticsearch.action.delete.DeleteResponse;
import org.elasticsearch.action.get.GetRequest;
import org.elasticsearch.action.get.GetResponse;
import org.elasticsearch.action.index.IndexRequest;
import org.elasticsearch.action.index.IndexResponse;
import org.elasticsearch.action.support.master.AcknowledgedResponse;
import org.elasticsearch.client.IndicesClient;
import org.elasticsearch.client.RequestOptions;
import org.elasticsearch.client.RestClient;
import org.elasticsearch.client.RestHighLevelClient;
import org.elasticsearch.client.indices.CreateIndexRequest;
import org.elasticsearch.client.indices.CreateIndexResponse;
import org.elasticsearch.client.indices.GetIndexRequest;
import org.elasticsearch.client.indices.GetIndexResponse;
import org.elasticsearch.cluster.metadata.MappingMetaData;
import org.elasticsearch.common.xcontent.XContentType;
import org.junit.jupiter.api.Test;
import org.springframework.beans.factory.annotation.Autowired;
import org.springframework.boot.test.context.SpringBootTest;

import java.io.IOException;
import java.util.HashMap;
import java.util.Map;

@SpringBootTest
class Test1ApplicationTests {

    @Autowired
    private RestHighLevelClient client;

    @Test
    void contextLoads() {
        System.out.println(client);

    }
/*
    @Test
    void contextLoads1() {
        RestHighLevelClient client1 = new RestHighLevelClient(RestClient.builder(new HttpHost("127.0.0.1", 9200, "http")));
        System.out.println(client1);

    }*/

    //创建索引

    /**
     * @param
     * @return void
     * @author YuChenXi
     * @date 2021/9/25 9:12 下午
     * 创建索引
     */
    @Test
    void addIndexAndMapping() throws IOException {
        IndicesClient indicesClient = client.indices();
        CreateIndexRequest request = new CreateIndexRequest("myfirst1");
        String mapping = "{\n" +
                "      \"properties\": {\n" +
                "        \"name\":{\n" +
                "          \"type\": \"keyword\"\n" +
                "        },\n" +
                "        \"address\":{\n" +
                "          \"type\": \"text\"\n" +
                "          , \"analyzer\": \"ik_max_word\"\n" +
                "        }\n" +
                "      }\n" +
                "    }\n" +
                "}";
        request.mapping(mapping, XContentType.JSON);
        CreateIndexResponse response = indicesClient.create(request, RequestOptions.DEFAULT);
        System.out.println(response.isAcknowledged());
    }

    /**
     * @param
     * @return void
     * @author YuChenXi
     * @date 2021/9/25 9:12 下午
     * 查询索引
     */
    @Test
    void queryIndex() throws IOException {
        IndicesClient indicesClient = client.indices();
        GetIndexRequest request = new GetIndexRequest("myfirst1");
        GetIndexResponse response = indicesClient.get(request, RequestOptions.DEFAULT);
        Map<String, MappingMetaData> mappings = response.getMappings();
        for (String s : mappings.keySet()) {
            System.out.println(s + ":" + mappings.get(s).getSourceAsMap());
        }
    }

    /**
     * @param
     * @return void
     * @author YuChenXi
     * @date 2021/9/25 9:12 下午
     * 删除索引
     */
    @Test
    void deleteIndex() throws IOException {
        IndicesClient indicesClient = client.indices();
        DeleteIndexRequest request = new DeleteIndexRequest("myfirst");
        AcknowledgedResponse response = indicesClient.delete(request, RequestOptions.DEFAULT);
        System.out.println(response.isAcknowledged());
    }

    /**
     * @param
     * @return void
     * @author YuChenXi
     * @date 2021/9/25 9:13 下午
     * 判断索引是否存在
     */
    @Test
    void existIndex() throws IOException {
        IndicesClient indicesClient = client.indices();
        GetIndexRequest request = new GetIndexRequest("myfirst");
        boolean exists = indicesClient.exists(request, RequestOptions.DEFAULT);
        System.out.println(exists);
    }


    /**
     * @param
     * @return void
     * @author YuChenXi
     * @date 2021/9/25 9:14 下午
     * 添加文档（数据）
     */
    @Test
    void addDoc() throws IOException {
        Map data = new HashMap();
        data.put("name", "小鱼11");
        data.put("address", "我爱南京的美食");
        IndexRequest request = new IndexRequest("myfirst1").id("5").source(data);
        IndexResponse response = client.index(request, RequestOptions.DEFAULT);
        System.out.println(response.getId());
    }

    /**
     * @param
     * @return void
     * @author YuChenXi
     * @date 2021/9/25 9:27 下午
     * 将map集合改成Person对象
     */
    @Test
    void addDoc1() throws IOException {
        Person person = new Person();
        person.setName("小王111");
        person.setAddress("喜欢南京的建筑");

        String data = JSON.toJSONString(person);
        IndexRequest request = new IndexRequest("myfirst1").id("3").source(data, XContentType.JSON);
        IndexResponse response = client.index(request, RequestOptions.DEFAULT);
        System.out.println(response.getId());
    }

    /**
     * @param
     * @return void
     * @author YuChenXi
     * @date 2021/9/25 9:36 下午
     * 根据索引和id查询数据信息
     */
    @Test
    void findDocById() throws IOException {
        GetRequest request = new GetRequest("myfirst1", "5");
        GetResponse response = client.get(request, RequestOptions.DEFAULT);
        System.out.println(response.getSourceAsString());
    }

    @Test
    void delDoc() throws IOException {
        DeleteRequest request = new DeleteRequest("myfirst1", "5");
        DeleteResponse response = client.delete(request, RequestOptions.DEFAULT);
        System.out.println(response.getId());
    }

}
```

### 25.4 ES的高级查询

#### 25.4.1 Bulk批量操作

* **脚本**：

  ```json
  GET myfirst1/_search
  
  POST _bulk
  {"create": {"_index":"myfirst1","_id":"7"}}
  {"name":"小华","address":"住在北京胡同里"}
  
  POST _bulk
  {"create": {"_index":"myfirst1","_id":"4"}}
  {"name":"小画华","address":"住在安徽"}
  {"delete":{"_index":"myfirst1","_id":"4"}}
  
  POST _bulk
  {"create": {"_index":"myfirst1","_id":"6"}}
  {"name":"小画华","address":"住在安徽"}
  {"update":{"_index":"myfirst1","_id":"6"}}
  {"doc":{"name":"小名化11"}}
  
  #_bulk一次性操作多个语句再同时执行
  ```

* **JavaAPI**

  ```java
      /**
       * @param
       * @return void
       * @author YuChenXi
       * @date 2021/9/26 9:47 上午
       * 先删除再添加
       */
      @Test
      public void testBulk() throws IOException {
          BulkRequest request = new BulkRequest();
          //删除
          DeleteRequest deleteRequest = new DeleteRequest("myfirst1", "6");
          request.add(deleteRequest);
  
          HashMap map = new HashMap();
          map.put("name", "用JavaAPI");
          IndexRequest indexRequest = new IndexRequest("myfirst1").id("6").source(map);
          request.add(indexRequest);
  
          client.bulk(request, RequestOptions.DEFAULT);
      }
  ```

#### 25.4.2 分析创建索引

* **从MySQL导入数据**

  ```java
  /**
       * @param
      * @return void
      * @author YuChenXi
      * @date 2021/9/26 11:08 上午
       * 导入数据
       * 最重要的是space属性的格式转换
      */
      @Test
      public void importGoods() throws IOException {
          List<Goods> goodsList = goodsMapper.findAll();
          System.out.println(goodsList.size());
  
          //2.bulk导入
          BulkRequest bulkRequest = new BulkRequest();
  
          //2.1 循环goodsList，创建IndexRequest添加数据
          for (Goods goods : goodsList) {
            
              String specStr = goods.getSpecStr();
              //将json格式字符串转为Map集合
              Map map = JSON.parseObject(specStr, Map.class);
              //设置spec map
              goods.setSpec(map);
              //将goods对象转换为json字符串
              String data = JSON.toJSONString(goods);//map --> {}
            
              IndexRequest indexRequest = new IndexRequest("goods");//创建goods索引
              indexRequest.id(goods.getId()+"").source(data, XContentType.JSON);
              bulkRequest.add(indexRequest);
          }
  
          BulkResponse response = client.bulk(bulkRequest, RequestOptions.DEFAULT);
          System.out.println(response.status());
      }
  ```

#### 25.4.3 脚本大全

```json

PUT goods
{
	"mappings": {
		"properties": {
			"title": {
				"type": "text",
				"analyzer": "ik_smart"
			},
			"price": { 
				"type": "double"
			},
			"createTime": {
				"type": "date"
			},
			"categoryName": {	
				"type": "keyword"
			},
			"brandName": {	
				"type": "keyword"
			},
	
			"spec": {		
				"type": "object"
			},
			"saleNum": {	
				"type": "integer"
			},
			
			"stock": {	
				"type": "integer"
			}
		}
	}
}

POST goods/_doc/1
{
  "title":"小米手机",
  "price":1000,
  "createTime":"2019-12-01",
  "categoryName":"手机",
  "brandName":"小米",
  "saleNum":3000,
  "stock":10000,
  "spec":{
    "网络制式":"移动4G",
    "屏幕尺寸":"4.5"
  }
}


GET goods/_search
{
  "query": {
    "match_all": {}
  },
  "from":100,
  "size":200
}

#term不会分词
GET goods/_search
{
  "query": {
    "term": {
      "title": {
        "value": "华为啊啊啊"
      }
    }
  }
}

#match会分词，就是将华为手机啊啊啊分开之后和数据库里面能分开的进行等值匹配
GET goods/_search
{
  "query":{
    "match": {
        "title": "华为手机啊啊啊"
      }
    }
  }

#模糊查询

#wildcard ,一个字是？、多个是*
GET goods/_search
{
  "query":{
    "wildcard": {
      "title": {
        "value": "华?"
      }
    }
  }
}
  
# 正则查询
GET goods/_search
{
  "query": {
    "regexp": {
      "title": "\\w+(.)*"
    }
  }
}  
  
# 前缀查询
GET goods/_search
{
  "query": {
    "prefix": {
      "brandName": {
        "value": "三"
      }
    }
  }
}  
  
  
# 范围查询
GET goods/_search
{
  "query": {
    "range": {
      "price": {
        "gte": 2500,
        "lte": 2900
      }
    }
  },
  "sort": [
    {
      "price": {
        "order": "asc"
      }
    }
  ]
}
  
# queryString 多条件查询
GET goods/_search
{
  "query": {
    "query_string": {
      "fields": ["title","brandName"],
      "query": "手机 AND 三星"
    }
  }
}
  
# 布尔查询，多个查询条件连接，连接方式有：must(and)、must_not(not)
#should(or)、filter
  
GET goods/_search
{
  "query": {
    "bool": {
      "must": [
        {
          "term": {
            "brandName": {
              "value": "三星"
            }
          }
        }
      ],
      "filter":[ 
        {
        "term": {
          "title": "电视"
        }
       },
       {
         "range":{
          "price": {
            "gte": 2000,
            "lte": 8000
         }
         }
       }
      
      ]
    }
  }
}

#聚合查询
#桶聚合：相当于groupBy,不可对text进行分组
#指标聚合：相当于聚合函数，max,min,avg,sum

GET goods/_search
{
  "query": {
    "match": {
      "title": "三星"
    }
  },
  "aggs": {
    "max_priceeee": {
      "max": {
        "field": "price"
      }
    }
  }
}

#桶聚合，key就是brandName（分组条件），后面跟的是数量
GET goods/_search
{
  "query": {
    "match": {
      "title": "电视"
    }
  },
  "aggs": {
    "goods_brandsssss": {
     "terms": {
       "field": "brandName",
       "size": 101
     }
    }
  }
}
 
#高亮查询
GET goods/_search
{
  "query": {
    "match": {
      "title": "电视"
    }
  },
  "highlight": {
    "fields": {
      "title": {
        "pre_tags": "<font color='red'>",
        "post_tags": "</font>"
      }
    }
  }
}

# 重建索引

#老索引结构
PUT user_index_v1
{
  "mappings": {
    "properties": {
      "bitrhday":{
        "type": "date"
      }
    }
  }
}

put user_index_v1/_doc/1
{
  "birthday":"1999-11-22"
}

GET user_index_v1/_search

#新索引结构
PUT user_index_v2
{
  "mappings": {
    "properties": {
      "birthday":{
        "type": "text"
      }
    }
  }
}

POST _reindex
{
  "source": {
    "index": "user_index_v1"
  },
  "dest": {
    "index": "user_index_v2"
  }
}

PUT user_index_v2/_doc/2
{
  "birthday":"1987年1月1日"
}

GET user_index_v2/_search
#经过转化(其实就是一个将v1数据拷贝个v2的过程)，v2结构发生变化，老数据依旧能查到，新数据类型可以改变

#更加简单的方式是起别名：将新数据名字改成老数据库的：
DELETE user_index_v1

POST user_index_v2/_alias/user_index_v1

#这种方式是给v2起个别名v1，查询v1的本质还是v2
GET user_index_v1/_search
```

## 26. RocketMQ

### 26.1 概念与使用

* **概念**：MQ:MessageQueue，中间件、**消息队列**。特点是先进先出。这里是使用的RocketMQ。（如果不使用消息队列的坏处：比如在分布式服务中service挂了，controller无法发送信息过去。此时使用MQ可以存储controller发送的消息，service重新启动的时候，可以从MQ再次获取消息并且进行处理）
* **作用**：
  * **应用解耦**：生产者、消费者。异步  <font color='mediumseagreen'>上面讲了，其中工作模式是将消息完全记录下来，不是消息进来再删除，而是通过消息的偏移量来发送那个位置的消息</font> 
  * **快速应用和变更维护**：异步
  * **流量削峰**：靠着MQ将流量错位开来，而不是一起挤过来
* **缺点**：
  * 系统可用性降低、复杂度提高
  * 因为异步机制的原因：
    * 消息顺序性
    * 消息丢失
    * 消息一致性
    * 消息重复使用
* **使用步骤**
  * **组成部分**：
    * **Producer**（发送消息，返回信息）
    * **NameServer**（命名服务器：用于识别，被broker注册。类似与zookeeper）
    * **Broker**（消息服务器：接受消息，提供消息，消息持久化，过滤消息，高可用）
    * **Consumer**（监听机制，接受 消息）
    * 注意：      <font color='mediumseagreen'>用心跳机制进行连接</font>    <font color='tomato'>MQ只是包含NameServer、Broker</font>  
  * **过程**：producer发送消息（包含Message、Topic、Tag）

### 26.2  消息发送

* **发收消息工作流程**：

  * **单生产者单消费者**

    ```java
    package com.ycx.base;
    
    import org.apache.rocketmq.client.producer.DefaultMQProducer;
    import org.apache.rocketmq.client.producer.SendResult;
    import org.apache.rocketmq.common.message.Message;
    
    /**
     * @author YuChenXi
     * @date 2021/9/28 11:35 上午
     * Producer发送消息步骤
     */
    public class Producer {
        public static void main(String[] args) throws Exception{
    
            DefaultMQProducer producer = new DefaultMQProducer("group1");//区分群组
    
            producer.setNamesrvAddr("localhost:9876");//连接NameServer
    
            producer.start();
    
            Message msg= new Message("topic1","hello rocketmqqqqq!!!".getBytes());
    
            SendResult result = producer.send(msg);//发送信息
    
            System.out.println("返回结果 = " + result);//返回结果
    
            producer.shutdown();//关闭服务器
    
        }
    }
    ```

    ```java
    package com.ycx.base;
    
    import org.apache.rocketmq.client.consumer.DefaultMQPushConsumer;
    import org.apache.rocketmq.client.consumer.listener.ConsumeConcurrentlyContext;
    import org.apache.rocketmq.client.consumer.listener.ConsumeConcurrentlyStatus;
    import org.apache.rocketmq.client.consumer.listener.MessageListenerConcurrently;
    import org.apache.rocketmq.common.message.MessageExt;
    
    import java.util.List;
    
    /**
     * @author YuChenXi
     * @date 2021/9/28 11:35 上午
     */
    public class Consumer {
        public static void main(String[] args) throws Exception {
            DefaultMQPushConsumer consumer = new DefaultMQPushConsumer("group1");
            consumer.setNamesrvAddr("localhost:9876");
            consumer.subscribe("topic1", "*");
            //提前开启监听器
            consumer.registerMessageListener(new MessageListenerConcurrently() {
                public ConsumeConcurrentlyStatus consumeMessage(List<MessageExt> msgs, ConsumeConcurrentlyContext context) {
                    for (MessageExt msg : msgs) {
                        System.out.println("消息:" + new String(msg.getBody()));
                    }
                    return ConsumeConcurrentlyStatus.CONSUME_SUCCESS;
                }
            });
    
            consumer.start();//开启不关闭,一直监听
    
            System.out.println("消费者已经运行");
        }
    }
    ```

  * **单生产者多消费者**：默认是负载均衡

  * **多生产者多消费者**：多个生产者生产的消息可以被多个不同消费者消费

* **消息的种类**

  * **同步消息**：(普通返回值)

  * **异步消息**：(无返回值匿名内部类，开了另一个线程)

  * **单向消息**：(没有返回结果)

  * **延时消息**：延时

  * **批量消息**：一个集合添加多个消息一起发送，总长度不能超过4mb

  * **tags过滤消息**：添加tags的值进行选择性消费

  * **SQL过滤消息**：本质是根据producer里面的属性，在customer中设置sql语法，对属性进行过滤（比如age>20）

  * **错位消息** <font color='cornflowerblue'>面试题</font> 

    * **顺序发送**：保证属于同一个业务的往同一个队列去放。原理是指定唯一id（id是hashcode，取队列的模，得出的效果就是**相同的业务（比如1下单、2支付、3推送消息）在同一个队列中**），同时for循环，保证了消息的顺序性。
    * **顺序接受**：让**一个线程**只服务一个消息队列，new MessageListenerOrderly()。

    ```java
    package com.ycx.shunxu;
    
    import com.ycx.shunxu.damain.Order;
    import org.apache.rocketmq.client.producer.DefaultMQProducer;
    import org.apache.rocketmq.client.producer.MessageQueueSelector;
    import org.apache.rocketmq.client.producer.SendResult;
    import org.apache.rocketmq.common.message.Message;
    import org.apache.rocketmq.common.message.MessageQueue;
    
    import java.util.ArrayList;
    import java.util.List;
    
    /**
     * @author YuChenXi
     * @date 2021/9/28 11:35 上午
     * Producer发送消息步骤
     */
    public class Producer {
        public static void main(String[] args) throws Exception{
    
            DefaultMQProducer producer = new DefaultMQProducer("group1");//区分群组
    
            producer.setNamesrvAddr("localhost:9876");//连接NameServer
    
            producer.start();
    
    
            ArrayList<Order> arrayList = new ArrayList<Order>();
    
            Order order1 = new Order();
            order1.setId("a");
            order1.setMsg("a1");
            arrayList.add(order1);
    
            Order order2 = new Order();
            order2.setId("a");
            order2.setMsg("a2");
            arrayList.add(order2);
    
            Order order3 = new Order();
            order3.setId("a");
            order3.setMsg("a3");
            arrayList.add(order3);
    
            Order order4 = new Order();
            order4.setId("a");
            order4.setMsg("a4");
            arrayList.add(order4);
    
    
            Order order5 = new Order();
            order5.setId("b");
            order5.setMsg("b1");
            arrayList.add(order5);
    
            Order order6 = new Order();
            order6.setId("b");
            order6.setMsg("b2");
            arrayList.add(order6);
    
            Order order7 = new Order();
            order7.setId("b");
            order7.setMsg("b3");
            arrayList.add(order7);
    
            Order order8 = new Order();
            order8.setId("b");
            order8.setMsg("b4");
            arrayList.add(order8);
    
            //将相同id的放进一个消息队列
            for (final Order order : arrayList) {
                Message msg= new Message("orderTopic",order.toString().getBytes("UTF-8"));
    
                SendResult result = producer.send(msg, new MessageQueueSelector() {
                    public MessageQueue select(List<MessageQueue> mqs, Message msg, Object arg) {
                        int index = order.getId().hashCode() % mqs.size();
    
                        return mqs.get(index);
                    }
                }, null);
    
                System.out.println("返回结果 = " + result);//返回结果
    
            }
    
    /*
            Message msg= new Message("topic1","hello rocketmqqqqq3333!!!".getBytes("UTF-8"));
    
            SendResult result = producer.send(msg);//发送信息*/
    
    
    
            producer.shutdown();//关闭服务器
    
        }
    }
    ```

    ```java
    package com.ycx.shunxu;
    
    import org.apache.rocketmq.client.consumer.DefaultMQPushConsumer;
    import org.apache.rocketmq.client.consumer.listener.*;
    import org.apache.rocketmq.common.message.MessageExt;
    
    import java.util.List;
    
    /**
     * @author YuChenXi
     * @date 2021/9/28 11:35 上午
     * Consumer接收消息
     */
    public class Consumer {
        public static void main(String[] args) throws Exception {
            DefaultMQPushConsumer consumer = new DefaultMQPushConsumer("group1");
            consumer.setNamesrvAddr("localhost:9876");
            consumer.subscribe("orderTopic", "*");
            //提前开启监听器
    
    
            consumer.registerMessageListener(new MessageListenerOrderly() {
                public ConsumeOrderlyStatus consumeMessage(List<MessageExt> msgs, ConsumeOrderlyContext context) {
                    for (MessageExt msg : msgs) {
                        System.out.println(new String(msg.getBody()));
                    }
                return ConsumeOrderlyStatus.SUCCESS;
                }
            });
    
            consumer.start();//开启不关闭,一直监听
    
            System.out.println("消费者已经运行");
        }
    }
    ```

    

  * **事物消息**：(三种状态)

    * 提交
    * 回滚
    * 补偿

### 26.3 高级特性

#### 26.3.1 RocketMQ集群

* **概念**

  * 多个broker提供服务  <font color='mediumseagreen'>就是为了同步消息</font> 
  * 多个master多个salve
    * 方式1：master和slave是同步方式消息同步
    * 方式2：异步（性能较高，有延迟）

* **集群特征**

  * master的brokerid=0，slave的brokerid=1\2\3...
  * broker注册到nameServer上会通过长连接进行通信
  * nameServer和broker（包括master、slave）之间连接的重要信息是Topic，producer和customer都是通过nameServer来获取信息并且与broker相连接。（如果Topic存在，nameServer会直接分配，如果不存在就和broker创建并且分配）
  * producer在broker的topic选择一个消息队列（从列表中选择），producer与broker建立长连接，用于发送消息

* **消息存储**

  * 介质：文件系统磁盘（不是内存）
  * 顺序写和零拷贝：
    * 顺序写是在磁盘空间颗粒的按照顺序写入（其实是模拟顺序写，预留的空间）
    * 零拷贝是将4次拷贝简化成3次赋值，Java中的MappedByteBuffer类，预留的1G空间

* **高可用性**

* **负载均衡**

* **死信队列**：消息重复超过16次未成功会加入死信，死信只归属于Group Id,超过3天会被自动删除

* **消息重复消费**：

  * 原因：生产者发送重复的消息：网络闪断、生成着宕机

  * 消息服务器投递了重复的消息

  * 动态的负载均衡的过程

  * 解决方案：消息幂等（无论消费多少次，结果都是保持一致），用业务id或者业务key作为最后的使用。

    

## 27. MyBatisPlus

### 27.1 概念与使用

* **概念**：是mybatis的增强工具，在其基础上简化开发，提高效率
* **操作流程**：
  * 创建工程，最好是Springboot工程
  * 导入MyBatisplus依赖坐标
  * 编写mapper、pojo（需要扫描mapper，可能需要编写配置类），在application.yml编写数据库连接信息
  * 在测试类中直接创建mapper的bean，直接调用MybatisPlus已经编写好的增删改查方法即可

### 27.2 具体方法

* **pojo**

  ```java
  package com.example.mybatisplus.pojo;
  
  import com.baomidou.mybatisplus.annotation.IdType;
  import com.baomidou.mybatisplus.annotation.TableField;
  import com.baomidou.mybatisplus.annotation.TableId;
  import com.baomidou.mybatisplus.annotation.TableName;
  import lombok.Data;
  import lombok.Getter;
  import lombok.Setter;
  
  import java.io.Serializable;
  import java.util.Date;
  import java.util.HashSet;
  import java.util.Set;
  
  /**
   * 用户
   */
  
  //@TableName("t_user")//将表的名字填上去
  @Data
  public class User implements Serializable{
  
    //  @TableId(type = IdType.AUTO)//设置Id自增
      private Integer id; // 主键
      private Date birthday; // 生日
      private String gender; // 性别
  
   //   @TableField("user_name")//属性与数据库名字不一样的情况
      private String userName; // 用户名，唯一
      private String password; // 密码
      private String remark; // 备注
      private String station; // 状态
  
      @TableField(exist = false)//让这个属性和数据库无关
      private String info;
  }
  ```

* **dao层**

  ```java
  package com.example.mybatisplus.dao;
  
  import com.baomidou.mybatisplus.core.mapper.BaseMapper;
  import com.example.mybatisplus.pojo.User;
  
  /**
   * @author YuChenXi
   * @date 2021/9/30 9:46 上午
   * 需要继承一个父接口！！！！！！！！！！！
   * 并不要在这个mapper接口里面添加方法，只需要继承接口就行（方法被自动添加了）
   */
  public interface UserMapper extends BaseMapper<User> {
  }
  
  ```

* **service接口**

  ```java
  package com.example.mybatisplus.service;
  
  import com.baomidou.mybatisplus.extension.service.IService;
  import com.example.mybatisplus.pojo.User;
  
  /**
   * @author YuChenXi
   * @date 2021/10/1 9:42 下午
   *泛型是封装的pojo
   */
  public interface UserService extends IService<User> {
  }
  
  ```

* **serviceImpl类**

  ```java
  package com.example.mybatisplus.service;
  
  import com.baomidou.mybatisplus.extension.service.impl.ServiceImpl;
  import com.example.mybatisplus.dao.UserMapper;
  import com.example.mybatisplus.pojo.User;
  import org.springframework.stereotype.Service;
  
  /**
   * @author YuChenXi
   * @date 2021/10/1 9:42 下午
   *继承一个接口，获取mp已经写好的方法
   */
  @Service
  public class UserServiceImpl extends ServiceImpl<UserMapper,User> implements UserService{
  
  }
  ```

* **基本的增删改查测试**

  ```java
  package com.example.mybatisplus;
  
  import com.baomidou.mybatisplus.extension.plugins.pagination.Page;
  import com.example.mybatisplus.dao.UserMapper;
  import com.example.mybatisplus.pojo.User;
  import org.junit.jupiter.api.Test;
  import org.springframework.beans.factory.annotation.Autowired;
  import org.springframework.boot.test.context.SpringBootTest;
  
  import java.util.ArrayList;
  import java.util.HashMap;
  import java.util.List;
  
  @SpringBootTest
  class MybatisPlusApplicationTests {
  
      @Autowired
      private UserMapper userMapper;
  
      @Test
      void testFindById() {
          User user = userMapper.selectById(4);//这个方法已经被MyBatis自动写好了
          System.out.println(user);
      }
  
      @Test
      void insertUser() {
          User user = new User();
          user.setUserName("mybatisPlus2");
          userMapper.insert(user);
      }
  
      @Test
      void delete1() {
          userMapper.deleteById(100);
      }
  
      @Test
      void delete2() {
          List list = new ArrayList<>();
          list.add(99);
          list.add(101);
          userMapper.deleteBatchIds(list);
      }
  
      @Test
      void delete3() {
          HashMap<String, Object> map = new HashMap();
          map.put("user_name", "ycx");
          map.put("remark", "vvv");
          userMapper.deleteByMap(map);
      }
  
      @Test
      void updateById() {
          User user = new User();
          user.setId(23);
          user.setUserName("mybatisPlus3");
          userMapper.updateById(user);
      }
  
      /**
       * @param
       * @return void
       * @author YuChenXi
       * @date 2021/9/30 11:30 上午
       * 分页查询
       */
      @Test
      void teestPage() {
          int current = 1;
          int size = 2;
          Page<User> page = new Page(current, size);
          userMapper.selectPage(page, null);
  
          List<User> records = page.getRecords();
          long pages = page.getPages();
          long total = page.getTotal();//以上两个需要添加配置类
  
          System.out.println(records);
          System.out.println(pages);
          System.out.println(total);
  
      }
  }
  ```

* **带条件的查询**

  ```java
  package com.example.mybatisplus;
  
  import com.baomidou.mybatisplus.core.conditions.Wrapper;
  import com.baomidou.mybatisplus.core.conditions.query.LambdaQueryWrapper;
  import com.baomidou.mybatisplus.core.conditions.query.QueryWrapper;
  import com.baomidou.mybatisplus.core.conditions.update.UpdateWrapper;
  import com.baomidou.mybatisplus.extension.plugins.pagination.Page;
  import com.example.mybatisplus.dao.UserMapper;
  import com.example.mybatisplus.pojo.User;
  import org.junit.jupiter.api.Test;
  import org.springframework.beans.factory.annotation.Autowired;
  import org.springframework.boot.test.context.SpringBootTest;
  
  import java.nio.file.Watchable;
  import java.util.ArrayList;
  import java.util.HashMap;
  import java.util.List;
  
  @SpringBootTest
  class MybatisPlusApplicationTestsWrapper {
  
      @Autowired
      private UserMapper userMapper;
  
      /**
       * @param
       * @return void
       * @author YuChenXi
       * @date 2021/9/30 3:01 下午
       * 这个就是条件查询，相当于select * from t_user where user_name = 'admin' and id <5 and remark in( 'fff' ,'测试','aaa')
       */
      @Test
      public void testWapper() {
  
          QueryWrapper<User> wrapper = new QueryWrapper<>();
  
          wrapper.eq("user_name", "admin")
                  .lt("id", 5)
                  .in("remark", "fff", "测试", "aaa");
  
          List<User> users = userMapper.selectList(wrapper);
  
          System.out.println(users);
      }
  
      @Test
      public void testWapperOrderBy() {
  
          QueryWrapper<User> wrapper = new QueryWrapper<>();
  
          wrapper.orderBy(true, true, "id");
  
          List<User> users = userMapper.selectList(wrapper);
  
          System.out.println(users);
      }
  
      @Test
      public void testWapperSelect() {
  
          QueryWrapper<User> wrapper = new QueryWrapper<>();
  
          wrapper.orderBy(true, true, "id").select("user_name");
  
          List<User> users = userMapper.selectList(wrapper);
  
          System.out.println(users);
      }
  
      /**
       * @param
       * @return void
       * @author YuChenXi
       * @date 2021/10/1 9:56 上午
       * 条件查询之分页查询
       * 1.构建分页对象
       * 2.构建条件对象
       */
      @Test
      public void testWapperFenYe() {
  
          int current = 1;
          int size = 2;
          Page<User> page = new Page(current, size);
  
          QueryWrapper<User> wrapper = new QueryWrapper<>();
          wrapper.orderBy(true, true, "id").select("user_name");
  
          userMapper.selectPage(page, wrapper);
  
          List<User> records = page.getRecords();
  
          System.out.println(records);
      }
  
      @Test
      public void testWapperLambda() {
  
          LambdaQueryWrapper<User> wrapper = new LambdaQueryWrapper<>();
          wrapper.eq(User::getUserName, "admin");
          User user = userMapper.selectOne(wrapper);
          System.out.println(user);
      }
  
  
      @Test
      public void testWapperUpdate() {
  
          UpdateWrapper<User> wrapper = new UpdateWrapper<>();
  
          wrapper.eq("user_name", "admin");
  
          User user = new User();
          user.setPassword("888888");
          user.setRemark("bbb");
  
          userMapper.update(user,wrapper);
      }
  }
  
  ```

* **Service层的封装**

  ```java
  package com.example.mybatisplus;
  
  import com.baomidou.mybatisplus.core.conditions.query.QueryWrapper;
  import com.example.mybatisplus.pojo.User;
  import com.example.mybatisplus.service.UserService;
  import org.junit.jupiter.api.Test;
  import org.springframework.beans.factory.annotation.Autowired;
  import org.springframework.boot.test.context.SpringBootTest;
  
  /**
   * @author YuChenXi
   * @date 2021/10/1 9:45 下午
   */
  
  @SpringBootTest
  public class UserServiceTest {
  
      @Autowired
      private UserService userService;
  
      @Test
      public void m1(){
          QueryWrapper<User> wrapper = new QueryWrapper<>();
  
          wrapper.eq("user_name", "admin");
  
          User user = userService.getOne(wrapper);
          System.out.println(user);
      }
  }
  
  ```

## 28. Spring Cloud

### 28.1概念与操作

* **概念**：
  * **微服务**：Microservices，将单个系统拆分成**多个微型系统**，这些系统都能各自运行在独立的进程中，服务之间通过**Restful API**进行通信。每个服务维护着**自身的数据存储**（自己有自己数据库）、业务开发自动化测试案例以及独立部署。每个微服务可以用不同的语言编写。
  * **springcloud**：一系列框架的**有序**集合，将各家公司开发的成熟框架组合起来。利用**springboot风格**再封装屏蔽掉复杂的配置和实现原理，最终得出一套简单易用的**分布式系统开发工具包**。  <font color='mediumseagreen'>基于springboot做的开发</font> 

* **spring cloud与dubbo区别：**
  * RPC/Restful
  * 只实现了服务治理（性能更好）/覆盖了微服务架构下的众多架构（功能齐全）

### 28.2 SpringCloud组件1：服务治理

#### 28.2.1 Eureka

* **概念**：就是一个**注册中心组件**，用于服务注册与发现。provider会将自己的地址放到注册中心中，consumer从注册中心获取地址（无需将地址写死。解耦合）  <font color='mediumseagreen'>区别于zookeeper，这个要自己搭建</font> 
* **组成**：Eureka Server（注册中心）、Eureka Client（服务提供方、消费方）
* **流程**：
  * 1.搭建Provider和Consumer服务  <font color='mediumseagreen'>在一个父工程下面创建两个子工程，分别是消费者、生产者</font> 
  * 2.使用RestTemplate完成远程调用  <font color='mediumseagreen'>定义配置类，在类里面定义bean，在Controller里面注入ResetTemplate类，调用.getForObject()方法，这里参数url是写死的 </font>  <font color='tomato'>这个是不用Eureka的情况</font> 
  * 3.搭建Eureka Server服务  <font color='mediumseagreen'> 导入坐标，创建引导类，添加注解，修改配置文件</font> 
  * 4.改造Provider和Consumer为Eureka Client   <font color='mediumseagreen'>添加Eureka-client依赖，添加注解（基本就是将@EnableEurekaServer都改成@EnableEurekaClient），修改配置（地址就是配置好的Server的地址），provider配置好了之后，consumer类似</font> 
  * 5.Consumer服务通过从Eureka Server中抓取Provider地址完成远程调用  <font color='mediumseagreen'>在引导类激活@EnableDiscoveryclient，在controller中注入discoveryClient，调用方法getInstance("EUREKA-PROVIDER")，返回集合。通过集合获取实例instance，再调用方法.gethost()/getport()，获取地址和端口，再进行地址字符串的动态拼接</font> 
* **相关配置与特性**：
  * server
  *  client
  * instance
  * dashboard
* **高可用**：
  * 搭建集群让Eureka高可用

#### 28.2.2 Consul

* **概念**：直接启动就行，类似于zookeeper

#### 28.2.3 Nacos

* **概念**：阿里开源项目，注册中心+配置中心

### 28.3 SpringCloud组件2： Ribbon客户端负载均衡

* **概念**：==**消费者客户端负载均衡**==工具，Eureka内置这个，替换RestTemplate模板对象。
* **作用**：1.简化RestTemplate远程调用、2.作为负载均衡器
* **简化RestTemplate调用**
  * 1.在声明restTemplate的bean的时候，添加**@loadBanlanced注解**
  * 2.在使用restTemplate的时候，定义url时，**host:port可以替换为服务提供方应用名称**(就是那个字符串)
* **负载均衡演示**
  * 1.准备至少两个provider节点
  * 2.启动consumer，刷新浏览器的时候，会发现多个provider会相对交替提供服务（视频演示方法是将端口号信息放进对象的一个属性中，在页面会显示出来）
* **7种负载均衡策略**
  * 随机
  * 轮询（默认）
  * 最小并发
  * 过滤
  * 响应时间
  * 轮询重试
  * 性能可能性

### 28.4 SpringCloud组件4：Feign

* **概念**：==**声明式REST服务调用**==（就是进一步优化restTemplate模板调用，可以取代Ribbon），**基于==接口==的注解方式**，方便实现客户端的配置

* **使用步骤**：

  * 导入依赖
  * 编写调用接口，在接口上面**@FeignClient(value="FEGIN-PROVIDER")**，==在接口里添加方法，和提供方法接口保持一致==
  * 在引导类上添加注解**@EnableFeignClient**，开启Feign功能
  * 测试功能，在消费方Controller里**注入接口**，直接用注入的对象调用接口里面的方法(取代了之前的注入restTemplate)

* **其他功能**

  * **超时设置**：Fegin底层是使用Ribbon，可以使用远程调用和负载均衡的功能。Ribbon默认1秒超时

    ```yaml
    ribbon:
    	ConnectTimeout: 1000 #连接超时时间(网络波动超时)
    	ReadTimeOut: 3000 #逻辑处理超时时间（业务代码处理超时）
    ```

  * **日志记录**：

    * 设置当前的日志级别debug（在配置文件中配置）
    * 写配置类xxx，@Bean return new logg...
    * 在接口注解@FeignClient（configuration=xxx.class）

### 28.5 SpringCloud组件5：Hystrix

* **概念：**==熔断器==，**保护微服务不受到破坏**。一个延迟和容错库，隔离访问远程服务、第三方库，防止雪崩（级联调用的时候， 一个服务失败，整条链路的服务都失败的情况） 。

* **主要功能**：

  * *隔离*

    * 线程池隔离、信号量隔离

  * *降级* 

    * **概念**：调用失败（异常/超时）的话，做降级处理（可以返回默认提示给用户），**分为提供者降级和消费者降级**
    * **提供者降级步骤**：1.在服务提供方，引入hystrix依赖；定义降级方法xxx(返回值和参数要和原方法一样)；2.@HystrixCommand(fallbackMethod="xxx")；3.在引导类@EnableCircuitBreaker激活服务  <font color='mediumseagreen'>说白了就是出现问题就调用指定方法</font> 
    * **消费者降级步骤**：1.定义feign调用接口实现类，重写方法（这个就是降级方法）；2.在@FeignClient注解除使用fallback设置降级处理类；3.配置开启feign.hystrix.enabled=true        
    *  <font color='tomato'>如果两边都写了降级，以提供者的降级为准</font>          

  * *熔断*

    * **概念**： 出现的错误（降级也算）次数太多（预定的阈值：监控5秒失败20次/失败率50%）的时候，开启熔断机制，拒绝所有请求（正常的调用也会降级）（一会儿进入半开状态），直到服务恢复正常为止。
      * **断路器的状态**：打开、关闭、半开   <font color='mediumseagreen'>三种状态来回切换。断路器打开5秒进入半开，如果调用失败，再回到打开，如果成功次数达到阈值，重回关闭状态</font> 
      * 注意熔断的属性是在@HystrixCommand注解上面添加

    * Hystrix-dashboard监控
    * Turbine进行聚合监控：1.搭建监控模块：添加依赖、编写配置、创建引导类。2.搭建被监控模块：  

  * *限流*

### 28.6 SpringCloud组件6：Gateway

* **网关概念**：为微服务提供统一的**API路由管理**方式（不然的话微服务相互之间调用，较为复杂。用了网关之后，只需要建立一次连接就行，用户直接通过网关进行调用其他服务）

* **常用的解决方案**：Spring Cloud Gateway、Nginx+Lua、Netflix Zuul

* **具体步骤**：

  * 导入依赖、设置启动类@EnableDiscoveryClient

  * 配置yml文件

    ```yaml
    server:
    	port: 80
    	
    spring:
    	application:
    		name: api-gateway-server
    		
    cloud:
    	gateway:
    		routes: 
    		- id: gateway-provider #这个是模块名
    			uri: http://localhost:8001/
    			predicates: - path=/goods/**  #路径匹配规则 ：这样就可以用80代替8001,拼接上这个规则
    ```

* **静态路由与动态路由**

  * 静态就是将具体地址写死在yml文件

  * **动态路由**就是**配合Eureka**获取动态地址  比如：*uri：lb://GATEWAY-PROVIDER*

  * 开启微服务名称功能： 直接在地址栏用微服务名称代替地址

    ```yaml
    discovery:
    	locator:
      	enabled: true
      	lower-case-service-id: true #改成小写
    ```

* **Gateway过滤器：**

  * **种类**

    * **pre**：前置过滤器，处理请求

    * **post**：后置过滤器，处理响应

    * **局部过滤器**：在yml添加配置，各种功能：添加参数，添加Header，剔除重复数据。。。。（在Controller类的方法上的路径）

      ```yml
      filters: AddRequestParmeter=username,zhangsan
      ```

    * **全局过滤器**：区别于局部过滤器，这个不需要配置。编写过滤器类，实现GlobalFilter，Ordered接口，在重写的方法里面添加内容，再return  chain.filter(exchange)放行。实现的int getOrder()方法可以确定执行顺序，return越小，越先执行。

## 29. Docker

### 29.1 概念

* **概念**：将环境和代码装进一个容器（docker），规避因为环境不同而造成的bug（软件跨环境迁移的问题），docker是一种轻量级、可移植的容器技术。 <font color='mediumseagreen'>就是为了部署项目用的，类似小型服务器，如果不使用Docker的话可能得自己安装MySQL、redis...Docker帮我们解决了</font> 
* **架构**：
  * **Clients**：docker（客户端）、docker machine（服务端）
  * **Hosts**：Image（镜像(类)）、Container（容器(实例)，在这里部署应用） <font color='mediumseagreen'>一个项目部署会有很多个容器，用来部署各种应用（鲸鱼背上的小格子）</font> 
  * **Registries**：image1，image2，image3....（远程仓库）

### 29.2 Docker命令

* 进程相关命令

* 镜像相关命令

  * docker images 列出本地镜像；

      docker rmi IMAGE ID ：删除的镜像；

      exit:退出镜像

* 容器相关命令

  * docker ps ：查看正在运行的容器；

     docker ps -a：查看所有的容器；

     docker run 参数 ：创建并启动容器（-it 创建的容器一般称为交互式容器，-id 创建的容器一般称为守护式容器，--name：为创建的容器命名。）（例如：docker run -it --name rediss redis ）

      docker stop CONTAINER ID：停止正在运行的容器；

      docker start CONTAINER ID：启动容器；

      docker rm -f webserver：命令来移除正在运行的容器；

      docker rm CONTAINER ID：删除容器；

### 29.3 容器的数据卷

* **概念**：宿主机的一个目录或文件，当容器目录和数据卷目录绑定后，修改会立即同步。一个数据卷可以被多个容器挂载。

* 数据卷的配置：docker tun -it --name=c4 -v/root/data:/root/data1 centos:7 /bin/bash

* 数据卷容器配置:

  ```shell
  #1. 创建启动c3数据卷容器，使用 –v 参数 设置数据卷
  [root@localhost /]$ docker run –it --name=c3 –v /volume centos:7 /bin/bash 
  
  #2.   创建启动 c1 c2 容器，使用–-volumes-from 参数 设置数据卷
  [root@localhost /]$ docker run –it --name=c1 --volumes-from c3 centos:7 /bin/bash
  [root@localhost /]$ docker run –it --name=c2 --volumes-from c3 centos:7 /bin/bash  
  ```

### 29.4 Docker应用部署

* MySQL
* Tomcat
* Nginx
* Redis

### 29.5 Dockerfile

* Docker镜像原理
  * 本质是特殊的分层文件系统堆叠而成，统一文件技术能将不同的层整合到一个文件系统。会有父镜像和基础镜像，当一个镜像启动系统的时候，Docker会在最顶层加载读写系统

* Dockerfile概念与作用

  * 概念：一个文本文件，包含一条条指令，每条指令构建一层，基于基础镜像，最终构建出一个新的镜像。

* Dockerfile关键字

  | 关键字      | 作用                     | 备注                                                         |
  | ----------- | ------------------------ | ------------------------------------------------------------ |
  | FROM        | 指定父镜像               | 指定dockerfile基于那个image构建                              |
  | MAINTAINER  | 作者信息                 | 用来标明这个dockerfile谁写的                                 |
  | LABEL       | 标签                     | 用来标明dockerfile的标签 可以使用Label代替Maintainer 最终都是在docker image基本信息中可以查看 |
  | RUN         | 执行命令                 | 执行一段命令 默认是/bin/sh 格式: RUN command 或者 RUN ["command" , "param1","param2"] |
  | CMD         | 容器启动命令             | 提供启动容器时候的默认命令 和ENTRYPOINT配合使用.格式 CMD command param1 param2 或者 CMD ["command" , "param1","param2"] |
  | ENTRYPOINT  | 入口                     | 一般在制作一些执行就关闭的容器中会使用                       |
  | COPY        | 复制文件                 | build的时候复制文件到image中                                 |
  | ADD         | 添加文件                 | build的时候添加文件到image中 不仅仅局限于当前build上下文 可以来源于远程服务 |
  | ENV         | 环境变量                 | 指定build时候的环境变量 可以在启动的容器的时候 通过-e覆盖 格式ENV name=value |
  | ARG         | 构建参数                 | 构建参数 只在构建的时候使用的参数 如果有ENV 那么ENV的相同名字的值始终覆盖arg的参数 |
  | VOLUME      | 定义外部可以挂载的数据卷 | 指定build的image那些目录可以启动的时候挂载到文件系统中 启动容器的时候使用 -v 绑定 格式 VOLUME ["目录"] |
  | EXPOSE      | 暴露端口                 | 定义容器运行的时候监听的端口 启动容器的使用-p来绑定暴露端口 格式: EXPOSE 8080 或者 EXPOSE 8080/udp |
  | WORKDIR     | 工作目录                 | 指定容器内部的工作目录 如果没有创建则自动创建 如果指定/ 使用的是绝对地址 如果不是/开头那么是在上一条workdir的路径的相对路径 |
  | USER        | 指定执行用户             | 指定build或者启动的时候 用户 在RUN CMD ENTRYPONT执行的时候的用户 |
  | HEALTHCHECK | 健康检查                 | 指定监测当前容器的健康监测的命令 基本上没用 因为很多时候 应用本身有健康监测机制 |
  | ONBUILD     | 触发器                   | 当存在ONBUILD关键字的镜像作为基础镜像的时候 当执行FROM完成之后 会执行 ONBUILD的命令 但是不影响当前镜像 用处也不怎么大 |
  | STOPSIGNAL  | 发送信号量到宿主机       | 该STOPSIGNAL指令设置将发送到容器的系统调用信号以退出。       |
  | SHELL       | 指定执行脚本的shell      | 指定RUN CMD ENTRYPOINT 执行命令的时候 使用的shell            |

### 29.6 Docker其他

#### 29.6.1 Docker 服务编排compose

* **概念**：编排多容器分布式部署的工具，提供命令集**管理容器**化应用的**完整开发周期**，包括服务构建、启动停止。（管理者）
  * 1.利用Dockerfile定义**运行**环境镜像
  * 2.使用docker-compose.yml定义组成应用的各服务
  * 3.运行docker-compose up启动应用

#### 29.6.2 Docker 私有仓库

#### 29.6.3 相关概念

## 30.kafka

### 30.1概念与使用

* 
