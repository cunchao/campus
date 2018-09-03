# campus
this is test project
this is another branch
flftfqwxf/mockserver
前端疑难问题
1.通过点击a标签的链接，获取tr下所有td内容，不能把链接的函数写在href属性里，应使用onclick=modify(this),传递当前点击的a元素，然后再根据a元素寻找父元素。
 
 
2.$(“ ”).addEventListener()is not a function?
混淆了jquery对象和javascript对象，https://www.cnblogs.com/Ellen-study/p/7242245.html
document.getElementById('id').addEventListener().
addEventListener is the javascript way to listen for events, but you call it on a JQuery object. Give a look at JQuery.on() to manage events using JQuery.
 

3.Github仓protractor的版本
https://github.com/angular/protractor/releases


4.protractor E2E测试框架
问题定位：chromedriver版本和当前使用的chrome版本不匹配 
附淘宝npm镜像 https://npm.taobao.org/
Csdn博文--Selenium使用中的坑 https://blog.csdn.net/linyuxinqing/article/details/79629587
5.浏览器复制功能的实现
	浏览器提供了copy命令，可以选中复制内容。
	document.execCommand(“copy”)
````element.select()只支持input和textarea标签，选择其他标签内容可以通过这两个标签中转。
 6.jquery获取/设置select选中的值
$(".selector").val("pxx");//设置value为pxx的项选中
$(".selector").find("option[text='pxx']").attr("selected",true);	//设置text=pxx的项选中
$(".selector").val();//获取当前选中的value值
$(".selector").find("option:selected").text();//获取当前选中的text值
7.angularjs动态生成的页面中，ng-click失效解决办法
	定位：无法与当前作用域关联起来
场景：动态添加点击按钮到页面（此时DOM已加载完毕），与当前作用域（$scope）的响应事件关联起来，需要在controller中传入$complie，并用$complie编译html字符串，然后append到DOM 中

 
8.数据传输过程中打印出[object Object]的问题
	object的prototype链中都没有实现自己的toString()的话, 把object转换为String时就会调用Object.prototype.toString, 输出的格式是[object 对象的类型]
例如Object.prototype.toString.call(123)返回"[object Number]", Object.prototype.toString.call('str')返回"[object String]". 使用Object.prototype.toString.call(obj)的方式判断对象类型比用typeof要"准确", 因为typeof []会返回"object"而Object.prototype.toString.call([])会返回"[object Array]"
如果想在调试时查看object里的内容, 可以用console.log(obj)来输出. 在chrome之类的现代浏览器里按下F12打开console可以看到整个obj的结构
定位：实质就是一个对象调用了对象的toString()方法，是对象的字符串形式。可以将其转成json格式数据 获取对象的属性值 
9.ajax传输数据格式
	TaskInfo的值不能直接是复合对象，应用JSON.stringify()转成字符串格式
"[{\"envName\":\"https://10.186.118.227:18008\",\"mName\":\"basic_service\"}]"
 
10.JSON.stringify()将服务端的一个JSON格式的字符串输出给客户端js，客户端接收到的字符串里双引号被转义成“ &quot;”了，导致将json字符串转换成json对象的时候报错。（正则替换）
解决方法： 
 
