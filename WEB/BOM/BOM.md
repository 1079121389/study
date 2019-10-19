###第八章 BOM浏览器对象模型
##8.1 BOM简介

###8.1.1
浏览器对象模型， 简称BOM。BOM提供了独立于内容而是与浏览器窗口进行交互的对象。BOM的核心是window对象。与ECMAscript不同的是。BOM针对的是浏览器
鉴于市面上的浏览器多种多样，因此会影响BOM的兼容性。

###8.1.2浏览器的兼容
浏览器因为他的多厂商，导致兼容性问题是不容忽视的，主流浏览器中各个版本的兼容性也不尽相同，因此在bom中运用时可能会出现不同或者毫无结果的情况

###8.2 window对象
####### 8.2.1window对象的概念 ###
window对象是bom的核心对象他除了可以是全局变量的属性和方法之外 还可以执行浏览器
的一些方法

##8.2.2全局作用域
在全局作用于下创建变量和函数都会测iweiwindow的属性和方法
。

###8.2.3 窗口大小
（1）视口的大小  
 //可见内容视口视口相当于document.body的高度和宽度--- clientWidth;
        var w= document.body.clientWidth;
        var h= document.body.clientHeigh;


        console.log(w+','+h);
（2）视口大小
浏览器视口大小是包含左侧和右下的滚动条的--- innerWidth;

       var wh = window.innerHeight;
        console.log(ww +','+ wh);
（3）整个浏览器在整个显示屏上占用的高度和宽度--- outer width;
      var ow =window.outerWidth;
        var oh =window.outerHeight;
        console.log(ow +','+ oh);


↑浏览器大小
整个浏览器上所占有的宽度和高度，包括浏览器的所有部分
###8.2.3 窗口位置
浏览器左边界和上边界到操作系统左面左上角的水平和垂直距离

#8.2.4 open
           document.getElementById('a').onclick = function(){
            window.open('视口大小.html','_top');
            //_self 当前窗口打开
            //_blank 新窗口打开（默认）
        }
window.open('需要打开的地址','窗口打开的方式')；这是最简单的方法但涉及兼容性问题 使用open打开的页面基本可以使用close关闭





对话框 


        alert('弹出框'); //返回值是字符串
        confirm('选择框');//有小判断 返回值是true
        prompt('输入弹出框');//返回值是字符串内容
 

###8.2.6 超时调用（一次性定时器）
超时与间歇用定时器

setTimeout(回调函数，时间)也叫一次性定时器，创建这个定时器后会在一定时间中调用函数 执行函数脚本



###8.2.7循环定时器
循环定时器存在bug执行时间超过等待时间将会出现任务堆叠一般情况使用setTimeout代替



###递归调用法
    // setTimeoout(回调函数,时间);
        setTimeout(function(){
            alert('欢迎光临')
        },5000);
        //递归调用
        function time(){
            //执行代码
            consolie.log('执行代码段');
            setTimeout(function(){
                times();
            },1000)
        }
        //调用
        times();
###8.3location对象
###8.3.1 location对象的概念
window的location对象用于获取当前页面的地址（url）,并把浏览器重新定向到新的页面在编写时可以不用加window前缀


###8.3.2属性方法
返回当前完整的url地址
host返回的是服务器名称和端口号
port 返回端口号
pathname 返回的是目录和文件名
search 返回的是参数也就是问号后面的内容 
protool 返回使用页面的协议，如http/http


###8.4 navigator对象
####8.4.1
window 的navigator对象包含关于浏览器的信息
在编辑的时候不能使用window的前缀，直接使用navigator该对象代表浏览器本省的名称，版本，系统信息的那个信息 但存在兼容性等问题，请慎用；

###
   console.log(navigator);
   navigator.appName: 浏览器名称
   navigator.appVersion:浏览器版本
   navigator.
兼容性问题在固定浏览器版本进行自主寻找


###8.4.3判断浏览器类型
	  if(navigator.userAgent.indexOf('MSIE')!=-1){
                console.log('IE浏览器');
        }else{
                csole.log('非IE浏览器')
        }

工作过的时候用得上 

####8.5 screen对象
####8.5.1概念
screen对象表示一个藕丁目的窗口 他会随着浏览器的不同才窗口大小的位置不同返回不同的值前提是返回的是当前打开窗口的内容


#8.5.2属性
    console.log(screen);



###8.6 history
history对象保存着从窗口被打开的历史记录每一个浏览器窗口，标签页，框架都有自己的的history 对象，为了保护用户隐私 对js访问该对象作出了一部分限制


      console.log(history);




###8.6.2常用方法

history.go(n) 整数 0代表刷新，整数代表向前跳n步，负数代表向后跳n步

history.back(n)代表向后跳n步数
   