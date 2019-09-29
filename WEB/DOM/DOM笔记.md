##DOM第六章
6.1dom的概述


6.1.1dom的概念

dom文档对象模型 dom对象不仅仅是一个普通的内置对象，它还是一个巨大的API的 核心对象 它将文档内容呈现在js 面前 病赋予了js操作文档的能力


6.1.2 DOM和Javascript的关系
一个web页面 是一个文档  这文档可以在浏览器窗口或者作为html源代码显示出来但上述两种情况都是同一文档 dom
提供了对同一文档的另一种表现 存储和操作方式 dom能够使用 javascript脚本语言进行修改


6.1.3  Dom节点
加载html伊尔迷谙是 web浏览器生成一个树形结构 用来表示页面的内部结构
DOM将这种结构理解为节点组成 根据为c的html
DOM标准  html文档找那个的所有内容都是节点

》整个文档是一个文档节点
》每个html元素都是元素节点

》html内的文本是文本节点  

》每个html树形都是属性节点

》注释也是节点，叫注释节点


6.1.4 DOM树
DOM树体现着html页面的层级结构，而DOM树有DOM文档树和DOM元素树
两种 DOM元素树只有元素节点 而DOM文档书则包括DOM文档中所有内容



##6.2查找元素




获取元素
 6.2.1 getElementById
getElementById()的方法，接受一个参数：获取元素的id 如果找到 相应元素 则返回该元素的，否则返回null
               //用变量接住  在 文档 找 元素  用 id
                var d= document.getElement.ById()



6.2获取元素名

当我们使用id获取元素的时候 元素名称会和整个元素一起显示出来 如果想要拿到该元素的元素名 也就是标签名则需要用tagName属性该属性只能获取不能设置



在某一个元素中并不是在全局文档中
           <ul id="ul">
                <li>1</li>
                <li>2</li>
                <li>3</li>
            </ul>
    <script>
        var ul =document.getElementById('ul');
     var lis = ul.getElementByTagName('li');
        //伪数组
        console.log(lis);

6.2.2用标签名获取元素（标签）
getElementByTageName()可以获取该元素没名称下的所有元素，返回UI个伪数组，或者说一个节点列表

     var lis = documents.getElementByTagName('li');
        //伪数组
        console.log(lis);




6.2.3 获取元素节点的内容
获取元素之后 如果我们需要拿到元素中的内容（所有东西） 则需要用另一个方法得到 元素里的内容可能包括 ：文本或元素
        var div = document.getElementById('mydiv');
        console.log(div.innerHTML);

innerHTML属性除了可以获取标签内的内容还可以设置标签内的内容



6.2.4
l
利用innerText属性获取的也只是文本集结点 不能是其他  当然 innerText 属性除了获取 也可以设置元素中的文本。
   



##6.2.利用选择器获取元素

QuerySelector    和QuerySelectorAll___All the word

前者可以依靠选择器找到元素 但前者只能找到列表的第一个元素 ，而后者可以全部找到
注意这个很好用很好理解但是性能低下需要重新渲染css下面是老师打的↓↓

6.2.4 用选择器获取元素
querySelector()和querySelectorAll()可以依靠选择器找到元素,但是前者只能找到元素列表的第一个元素,而后者可以全部找到.注意,该方法性能没有直接利用标签寻找高.

        var ul = document.getElementById('ul')
        var x = document.querySelector('#div>div a');
        var lis = ul.querySelectorAll('li');
        console.log(lis);


   
###6.3获取元素中的其他信息

6.3.1获取元素的类名
利用class属性获取元素类名，以字符串的的形式反馈.同时可以设置新的class类名 需要注意的是 返回值是一个字符串 如果换其中一个类别
      var div = document.getElementById('mydiv');
      console.log(div.className);



6.3.1当元素只有一个的时候返回



需求3:
1.一个200*200的红色方框,一个按钮
2.点击按钮,让红色方框变成蓝色
3.必须用className的赋值方法变化


style属性可以获取元素样式的所有属性  当然如果继续在style中找属性名


6.3.2


##9.23
需求:  
1.在html上创建6个div元素  
2.利用js赋予"所有"div样式,样式内容为:50*50,背景红色,间距20px,并横向排列  
3.请不要添加任何id或class类
4.给第三个div用js增加一个"blue"类,在css中定义blue类的背景颜色为蓝色


#####6.3.2 用name属性值获取元素
getElementsByName()方法可以获取相同名称的name元素,返回一个伪数组对象.

        <input type="radio" name="sex" value="0">男 
        <input type="radio" name="sex" value="1">女
    
        var sex = document.getElementsByName('sex');
        console.log(sex);



####6.3.3获取元素属性
getAttribute('')可以获取元素的摸个属性要讲元素名称放在括号里面记得引号括起来，返回值是以字符串形式的属性值



####6.3.7设置元素属性
setAttribute()可以设置元素的摸个属性 第一个参数是属性名第二个是参数是属性值  都需要用用豪阔起来以逗号隔开。


       var div = document.getElemntsByTagName('div');
        var a =document.getElementsByTagName('a');

        div[0].setAttribute('id','mydiv');
        a[0].setAttribute('href','http//www.baidu.com')



###6.3.8删除元素属性
使用removeAttribute（），可以删除摸个属性，括号中放入要删除的属性名，用引号包裹。
      var div = document.getElementById('mydiv');
      div.removeAttribute('id');



6.4 增加元素
  


###6.4.1创建元素节点 
利用js创建一个元素的方法是 现在文档中创纪检一个标签document。createElement()括号中写标签名 当然要用字符串形式
创建之后不是就纯在了 而是要将已创建的元素放到你想放的元素里面（父元素）中去
      //用一个变量惩戒在文档中创建一个元素；
        var div = document.createElement('div');
        //将已经创建的元素放在想放的位置
        document.body.appChild(div);



 ###创建文本节点
利用js创建文本节点 在文档中穿件文本doument.createTextNode（'一段文字'）在括号中将要创建的字符串放入
       var text =document.createTextNode('一段文字');
        p.appendChild(text);

#####6.4.3样式赋予
style.cssText是一个css的样式集合他可以吧css层叠样式表中的css样式直接放在该属性后面，就不需要一条一条去赋予样式了，可以一次性赋予样式：
    div.style.cssText='width:100;height:200px;color:red



###6.4.4'在某元素之前插入新元素
insertBefore()这个函数和appendChild()用法基本一致都是向父级中插入一个子元素但却别是insertbeforr()可以选择插入的位置 一次需要 那个子元素 inseryBefore()有两个参数 第一个参数是需要插入的元素 第二个参数是在谁谁之前插入 两个参数逗号隔开

##6.5删除和替换元素
###6.5.1元素替换
元素的替换是在父元素中一个子元素需要被另一个新的子元素所替代 使用replaceChild()方法。该方法尤里那个参数，第一个参数是将要替换的新元素 第二个是被替换的旧元素 中间用逗号分隔；
       var mydic = document.getElementById('myid');
        var myp = document.CreateElement('p');
        //在父元素中替换子元素第一个是新的第二个是旧的
        document.dody.replaceChild(myp,mydiv);


###6.5.2元素的删除
元素的删除是在父元素的其阿红一个子元素需要删除使用removeChild（）
把需要删除的元素放到括号里面；


          var mydiv = document.getElementById('mydiv');
            document.body.removeChild(mydiv);


###6.6查找节点
节点是在dom树上的每一个节点，其中包括：元素 文本 属性 注释等等
常用的有三个 元素 文本 属性 

       var mydiv = document.getElementById('mydiv');
        console.log (mydiv.nodeType);

####6.6.1 节点属性 




6.6.2所有节点获取
使用childNodes属性拿到的是所有节点![](http://333)


6.6.4获取第一个和最后一个子节点
    console.lg(myul.firstChild);
    console.log(myul.lastChild);


6.6.5获取父节点
使用parentsNode属性可以拿到所有父节点 父节点只有一个

     console.log(myul.parentNode);




6.6.6 获取兄弟节点
获得元素的前一个和后一个兄弟节点但只能获取一个
			previousSIbling//获取前一个节点
			nextSibling//获取后一个
			console.log(myul.previousSibling);
			console.log(myul.nextSibling);


6.7元素的位置属性 
 		var mydiv = document.getElementById('Mydiv')
        console.log(mydiv.style);//用这种方法只能拿到内嵌
        console.log(mydiv.offsetWidth);
获取元素的宽和高 使用style 是无法获取的 所以我们使用 offsetWidth和offsetHeight该属性可以获取该元素的宽高和内外边距；
       console.log(mydiv.clientWidth);
       console.log(mydiv.clientHeight);
client也可以获取元素的宽和高丹玉offsetwidth不同的是不包括边框
        
    
