# HTML

## HTML概述

HTML全称（hypertext markup language）译为***超文本标记语言***，是一种标记语言。



## http协议

http是无连接的，每一次都需要重新请求，一次浏览器的请求过程。



![image-20230320191043134](https://raw.githubusercontent.com/lrv618/html-css_foundation/main/images/202304192315148.png)



> 1. 浏览器通过 DNS 把域名解析成对应的IP地址；
> 2. 根据这个 IP 地址在互联网上找到对应的服务器，建立连接；
> 3. 客户端向服务器发送HTTP协议请求包，请求服务器里的资源文档；
> 4. 在服务器端，实际上还有复杂的业务逻辑比如服务器可能有多台，到底指定哪台服务器处理请求。都需要一个负载均衡设备来平均分配所有用户的请求，还有请求的数据是存储在分布式缓存里还是一个静态文件中，或是在数据库里，完成以上操作之后，服务器将相应的数据资源返回给浏览器；
> 5. 客户端与服务器断开。由客户端解析HTML文档，在客户端屏幕上渲染图形结果。



## 快捷键

| **HTML****骨架**     | **html:5** **→ tab**                           |
| -------------------- | ---------------------------------------------- |
| **快速生成元素**     | 元素名→tab                                     |
| **自动生成多个元素** | div*5 → tab                                    |
| **生成h1-h6**        | h$*6 → tab                                     |
| **复制当前行文本**   | shift+alt+键盘上下箭头                         |
| **删除当前行**       | ctrl+shift+k                                   |
| **选中多个光标**     | 按住滚轮键不松手，向下拖动鼠标（不是滚动滚轮） |
| **在任意位置换行**   | 按住ctrl+enter                                 |
| **放大或缩小文字**   | Ctrl+键盘（+或者-）                            |
| **注释**             | **ctrl+/**                                     |



## HTML骨架



![image-20230320234702681](https://raw.githubusercontent.com/lrv618/html-css_foundation/main/images/202304192315634.png)



***DOCTYPE表示文档类型*，**html就是HTML超文本标记语言

DTD（Document Type Definition，文本类型定义）

必须出现在第一行。让浏览器知道是什么格式的文件



```
<head></head> ： 网页的配置
<body></body> ： 网页的正式内容，浏览器可视区域
```



标签有一个属性lang，是英语language语言的意思，表示整个网页的主体语言。

en表示英语。中文的表示法有三种。zh、cn、zh-CN。

需要注意的是，*无论哪种语言，都使用英文开发*。

```
<html **lang="en"**>
<html **lang="zh-CN"**>
```





![image-20230321000302602](https://raw.githubusercontent.com/lrv618/html-css_foundation/main/images/202304192316867.png)



### 字符集

| **字符集** | **字库是否全面**                                             | **优缺点**                                                   |
| ---------- | ------------------------------------------------------------ | ------------------------------------------------------------ |
| **UTF-8**  | 这个字库涵盖了地球上所有国家、民族的语言文字。非常全，每年更新，它是一个*国际化的字库* | *每个汉字占3个字节*。所以如果你想网页快一点打开，不能使用UTF-8。 |
| **gb2312** | gb是国标的意思，只有汉族的文字和少量其他符号。               | *每个汉字占2个字节*。  <u>几乎所有的门户网站，都是gb2312</u>。 |
| **gbk**    | <u>gbk是gb2312的略微增强版</u>，文字稍微多了点，  gbk也是只有汉语，只不过多了点怪异汉语字，比如“喆”。 | *每个汉字占2个字节*。  <u>几乎所有的门户网站，都是gbk。</u>  |



什么时候使用utf-8，什么时候使用gbk？

> 答：如果你的网页使用场景是面向群体是国际化的，使用utf-8，如果面向群体主要是国内，使用gbk
>
> 如何修改字符集，比如我们现在的字符集是gbk，修改为utf-8



### title标签



title就是在浏览器选项卡的区域显示的文字：

![image-20230321001756822](https://raw.githubusercontent.com/lrv618/html-css_foundation/main/images/202304192316812.png)



![image-20230321001729976](https://raw.githubusercontent.com/lrv618/html-css_foundation/main/images/202304192316144.png)





### keywords关键字

SEO（search engine optimization，搜索引擎优化）

最基本的SEO技术就是把keywords写好。*keywords就是网页关键字*。

name属性一定要设置为keywords，content就是关键字的内容，中间用逗号隔开

```
<meta name="keywords" content="前端,HTML,JavaScript">
```



### description页面描述

页面描述就是搜索引擎搜到你之后，展示的文字。

```
<meta name="description" content=" 网页的描述" />
```

以腾讯网为例，看到源码，keywords和description                               ![image-20230321002407909](https://raw.githubusercontent.com/lrv618/html-css_foundation/main/images/202304192316567.png)

![image-20230321002425922](https://raw.githubusercontent.com/lrv618/html-css_foundation/main/images/202304192316051.png)





## HTML基本语法



| 单标签 | 双标签 |
| ------ | ------ |
| img    | h1-h6  |
| br     | div    |
| hr     | span   |
|        | p      |
|        | a      |
|        | ul+li  |



根据标签的种类区分两个等级，分别是容器级和文本级。

*容器级：元素内部除了可以存放文本之外，还可以嵌套标签*

*文本级：元素内部只能存放文本或者文本级标签*

 

| 容器级标签                  | 文本级标签     |
| --------------------------- | -------------- |
| div,ol,ul,li,dl,dt,dd,h1-h6 | span,img,b,u,i |



### 标签属性



-  标签名必须书写在一对尖括号<>内部。
-  标签分为单标签和双标签，双标签必须成对出现，有开始标签和结束标签。
-  <u>结束标签必须有关闭符号/</u>。

```
<h1>存放内容的地方</h1>
```



​         标签属性是标签身上的一些特殊性质，通俗讲，给标签加上某个属性就相当于*给标签赋予了职能*，前提是标签必须具备这些职能。



- 书写位置：在*开始标签或单标签的标签名后面*，添加一个空格，空格后面书写属性。
- 属性包含<u>属性名（key）和属性值（value）两部分</u>，根据英文表示，习惯将属性写法称为键值对写法，标签属性的键值对写法是：*key=”value”*

![image-20230321114747174](https://raw.githubusercontent.com/lrv618/html-css_foundation/main/images/202304192316868.png)



### 字符实体

![image-20230321193712262](https://raw.githubusercontent.com/lrv618/html-css_foundation/main/images/202304192316752.png)



w3c手册：https://www.w3school.com.cn/html/html_entities.asp

在网页中普通文字部分，在键盘中是打不出来的，比如我们的版权符号，商标符号等等。还有一种场景就是替代字符，HTML会识别一部分字符





### 空格 换行 注释

```
语法 <!-- 被注释的内容 -->
快捷键ctrl+/
```



- 标签之间对空白换行缩进不敏感
- 空格：可以使用  &nbsp字符  实体替换书写，在代码中书写&nbsp;替换空格
- 换行：可以使用  br 单标签进行书写

![image-20230321114947682](https://raw.githubusercontent.com/lrv618/html-css_foundation/main/images/202304192316211.png)





### 常见标签

### h系列标签

***英文：headline（标题）***

<u>包含一共六级标题，有h1,h2,h3,h4,h5,h6</u>

*都是双标签，容器级标签*

作用：给内部内容添加对应级别标题的语义

标签根据重要性不同，认为权重不同，*所有的标题标签（h标签）的权重都比别的标签要高*

h系列标签的基本使用

![image-20230321115638607](https://raw.githubusercontent.com/lrv618/html-css_foundation/main/images/202304192316969.png)

![image-20230321115740083](https://raw.githubusercontent.com/lrv618/html-css_foundation/main/images/202304192316377.png)



> ​       浏览器的角度去考虑，它的权重在搜索引擎的优化，搜索引擎的优化除了会抓取meta标签配置的keywords之外还会优先抓取标题的内容，h1标签的权重是最高的，一个页面只使用一个h1，*通常用来制作网页的logo*，如果你在页面中设置了多个h1标签，搜索引擎会认为你在作弊，从而降低排名。



![image-20230321120123536](https://raw.githubusercontent.com/lrv618/html-css_foundation/main/images/202304192316348.png)



### p标签

***英文：paragraph（段落）***

*双标签，文本级标签*

作用：添加一个完整段落的语义



![image-20230321120346996](https://raw.githubusercontent.com/lrv618/html-css_foundation/main/images/202304192316251.png)



![image-20230321120158910](https://raw.githubusercontent.com/lrv618/html-css_foundation/main/images/202304192316874.png)



### div和span标签

div和span都是常用的*布局标签*，*俗称盒子*

- *div是容器级标签，双标签*
- *div：分割跨度大跨度*（div主要作用是进行网页布局的拆分，没有明确的语义）
- *span：小区域小跨度*（只适用于文字的跨度划分）

作用是用来分割页面的布局，*div指的是跨度布局分割*，*span是文字分割*

HTML+CSS又叫做div+CSS

<u>div主要作用是进行网页布局的拆分，没有明确的语义</u>

<img src="https://raw.githubusercontent.com/lrv618/html-css_foundation/main/images/202304192317749.png" alt="image-20230321194109204" style="zoom:150%;" />



<img src="https://raw.githubusercontent.com/lrv618/html-css_foundation/main/images/202304192317279.png" alt="image-20230321194118388" style="zoom:150%;" />





### img标签

***英文：image（图片）***

*单标签，文本级标签*

作用：在指定位置插入一张图片

img标签的属性



-  *src: 作用是引入图片的路径*
- *alt: 图片加载不出来时候的替换文本*



```
<img src="images/345345.jpg" alt="我是鸟巢">
```

<img src="https://raw.githubusercontent.com/lrv618/html-css_foundation/main/images/202304192317005.png" alt="image-20230321120600922" style="zoom:150%;" />



- *width: 设置图片的宽度*
- *height: 设置图片的高度*

```
<img src="images/1.jpg" alt="我是鸟巢" width="220px" height="10px">
```

<img src="https://raw.githubusercontent.com/lrv618/html-css_foundation/main/images/202304192317647.png" alt="image-20230321120751788" style="zoom:150%;" />



我们看上图确实将图片变为了理想的高度和宽度，但是实际工作中宽度和高度并不会共同使用，因为如果*只单独设置一个属性比如宽度，高度会等比例进行缩放*

```
<img src="images/1.jpg" width="220px">
```

![image-20230321121132823](.\html\HTML\image-20230321121132823-167937189497017.png)



- *title(标题)：作用是设置鼠标以上图片时候的悬停文本*

```
<img src="images/1.jpg" title="鸟巢的远景">
```



- *border：作用是给图片添加边框*

```
<img src="images/0.jpg" alt="我是鸟巢" border="10" width="220px">
```

<img src="https://raw.githubusercontent.com/lrv618/html-css_foundation/main/images/202304192317236.png" alt="image-20230321121324110" style="zoom:150%;" />

`图片的border属性用来了解就可以了，因为我们真正加边框的时候是通过CSS实现的`



*相对路径*：<u>从html文件出发，找到对应图片位置的路径</u>

如果进入到某个文件夹使用*‘/’*，如果出某个文件夹使用*‘../’*。



引入路径

```
<img src="images/1.jpg" alt="">
```

如果文件夹内部是文件，图片在文件夹的外面

```
<img src="../1.jpg" alt="">
```

<u>如果需要退出出多个文件夹，使用多个../</u>

```
<img src="../../1.jpg" alt="">
```



*绝对路径*

绝对路径重要分为盘符绝对地址，和网站的绝对地址

盘符绝对地址

```
<img src="C:/Users/lmpc/Desktop/1.jpg" alt="">
```

​      通过c盘根目录出发去查找你对应文件位置，<u>工作中不使用这种方法，因为服务器没有c盘...这些目录</u>

<u>网站的绝对地址。</u>



引入网络图片

```
<img src="https://bkimg.cdn.bcebos.com/pic/472309f79052982253a702cad8ca7bcb0a46d426?x-bce-process=image/resize,m_lfit,w_268,limit_1/format,f_jpg" alt="">
```

<img src="https://bkimg.cdn.bcebos.com/pic/472309f79052982253a702cad8ca7bcb0a46d426?x-bce-process=image/resize,m_lfit,w_268,limit_1/format,f_jpg" alt="">



### 锚点标签(超链接)



#### 页面跳转

***英文anchor（锚）***

*双标签，文本级标签*

<u>作用：在指定位置添加一个超级链接，从而实现相应的跳转</u>；

a标签有几个属性，是给超级链接添加相应的作用



- *href: 英文hypertext reference （超文本 引用）*

```
<a href="http://www.baidu.com">跳转到百度</a>
```

上面的代码href属性跳转到百度网站，<u>是绝对路径</u>，我们也可以设置相对路径跳转

```
<a href="12_a标签的跳转.html">跳转到12文件</a>
```



- *target：作用是 是否在新标签打开链接，值一定是”_blank”*

```
<a href="12_a标签的跳转.html" target="_blank"> 跳转到12文件 </a>
```

<img src="https://raw.githubusercontent.com/lrv618/html-css_foundation/main/images/202304192317338.png" alt="image-20230321123051473" style="zoom:150%;" />

<img src="https://raw.githubusercontent.com/lrv618/html-css_foundation/main/images/202304192317610.png" alt="image-20230321123103443" style="zoom:150%;" />



-  *title属性： 作用是鼠标 移上文字之后的 悬停文本*

```
<a href="12_a标签的跳转.html" target="_blank" title="鼠标移上的文字">跳转到12文件</a>
```



#### 页面内锚点的使用

锚点的作用：实现点击超级链接从而实现页面内的跳转

方法一

- 设置一个空锚点，然后给这个空锚点设置一个name属性值和锚的href属性是一的锚，href属性，后面一要加#号。

```
<a href="#jbxx">基本信息</a>
```

锚点的点，name属性设置被跳转的点

```
<a name="jbxx"></a>
```



<img src="https://raw.githubusercontent.com/lrv618/html-css_foundation/main/images/202304192317345.png" alt="image-20230321124247282" style="zoom:150%;" />



方法二

- 设置锚点的点为标签的id属性锚

```
<a href="#jbxx">基本信息</a>
```

锚点的点：由原来的a标签的name属性变为了其他标签id属性，id属性的值要和href一样

```
<h3 id="jbxx">基本信息</h3>
```

<img src="https://raw.githubusercontent.com/lrv618/html-css_foundation/main/images/202304192318627.png" alt="image-20230321124517773" style="zoom:150%;" />



### 列表标签

#### 无序列表

***作用：定义一个 没有顺序 的列表结构***

*由两个标签组成，ul（容器级标签），li（容器级）*

ul：英文***ulordered list（无序列表）***

li：英文***list item（列表项）***



- ul内部嵌套li，它们是父子关系；
- 无序列表项之间没有先后顺序之分的，列表项之前的前缀样式是有CSS去控制的



```
<h2>古典四大名著</h2>
<ul>
    <li>三国演义</li>
    <li>西游记</li>
    <li>红楼梦</li>
    <li>水浒传</li>
</ul>
```

<img src="https://raw.githubusercontent.com/lrv618/html-css_foundation/main/images/202304192318165.png" alt="image-20230321175123490" style="zoom:150%;" />



- 规定：<u>ul标签的内部必须只能嵌套li</u>，<u>li标签的内部可以嵌套任何标签，甚至是ul</u>
- 列表的拓展，li标签内部可以继续嵌套列表结构



<img src="https://raw.githubusercontent.com/lrv618/html-css_foundation/main/images/202304192318965.png" alt="image-20230321175847156" style="zoom:150%;" />



<img src="https://raw.githubusercontent.com/lrv618/html-css_foundation/main/images/202304192318450.png" alt="image-20230321180037616" style="zoom:150%;" />



#### 有序列表

作用：定义一个有序列表的列表结构

需要有两个标签组成ol，li

ol：*英文ordered list（有序列表）*

li：*英文list item（列表项）*

- 需要注意的是，ol内部嵌套li，它们是父子关系。
- 规定：<u>ul标签的内部必须只能嵌套li，li标签的内部可以嵌套任何标签，甚至是ul</u>

```
<h2>三年级排名情况</h2>
<ol>
    <li>三年级2班</li>
    <li>三年级1班</li>
    <li>三年级2班</li>
</ol>
```

<img src="https://raw.githubusercontent.com/lrv618/html-css_foundation/main/images/202304192318641.png" alt="image-20230321180930257" style="zoom:150%;" />





<img src="https://raw.githubusercontent.com/lrv618/html-css_foundation/main/images/202304192318733.png" alt="image-20230321181151535" style="zoom:150%;" />



<img src="https://raw.githubusercontent.com/lrv618/html-css_foundation/main/images/202304192318217.png" alt="image-20230321181249289" style="zoom:150%;" />





我们看得出来ol和ul的最大区别就是使用场景，一个是有序，一个是无序

我们看一下企业中无序列表标签的使用场景

<img src="https://raw.githubusercontent.com/lrv618/html-css_foundation/main/images/202304192318005.png" alt="image-20230321181328349" style="zoom:150%;" />



<img src="https://raw.githubusercontent.com/lrv618/html-css_foundation/main/images/202304192318235.png" alt="image-20230321181338672" style="zoom:150%;" />



#### 定义列表

*作用：定义一个标题和内容自定义的列表结构*

*definition（定义、解析）*

由三个标签组成，dl，dt，dd

dl英文：*definition list 表示创建一个自定义列表结构*

dt英文：*definition term（主题）*定义主题或者定义术语，*表示一个列表的主题*

dd英文：*definition description 定义解释项*，表示解释和说明前面的主题内容



- <u>dl内部只能存放dt和dd，dt和dd是同级关系</u>
- 每个dt主题的后面可以跟0-多个解释的dd，每个dd解释的就是上一个最近的dt
- dt和dd都是容器级标签，内部可以存放任意内容



<img src="https://raw.githubusercontent.com/lrv618/html-css_foundation/main/images/202304192319217.png" alt="image-20230321182130556" style="zoom:150%;" />



<img src="https://raw.githubusercontent.com/lrv618/html-css_foundation/main/images/202304192319814.png" alt="image-20230321182147406" style="zoom:150%;" />



定义列表的使用场景

![image-20230321182454411](https://raw.githubusercontent.com/lrv618/html-css_foundation/main/images/202304192319130.png)

​         京东网站的源码之后发现，dl、dt和dd都是一套标签组成，一个页面有多个dl并不是一个dl内部嵌套多个dt和dd，原因是因为这样会方便搭建布局。

![image-20230321182522246](https://raw.githubusercontent.com/lrv618/html-css_foundation/main/images/202304192319440.png)



![image-20230321182620496](https://raw.githubusercontent.com/lrv618/html-css_foundation/main/images/202304192319888.png)



![image-20230321182629531](https://raw.githubusercontent.com/lrv618/html-css_foundation/main/images/202304192319951.png)



#### 表格标签



表格主要有三个标签组成

- *table英文：table，作用是定义了一个表格的结构*
- *tr英文是table rows作用定义了表格的行*
- *td英文是table dock作用是定义表格的单元格*

关系：table>tr>td



案例：三行四列表格

​		

​         table标签上有两个属性，*border=“1”*，这个属性是用来*设置表格的边框*的，如果没有这个属性，边框不显示，*style="border-collapse:collapse"*是css样式，作用就是*合并表格*

​	表格需要设置表头，可以使用tr>th设置



![image-20230321183428089](https://raw.githubusercontent.com/lrv618/html-css_foundation/main/images/202304192319759.png)



<img src="https://raw.githubusercontent.com/lrv618/html-css_foundation/main/images/202304192319572.png" alt="image-20230321183444191" style="zoom:150%;" />



一部分单元格需要进行跨行跨列合并，可以给对应的td和th标签设置相关属性

*colspan：左右跨列合并*

*rowspan: 上下跨行合并*



属性值是数字，数字是几就代表跨几行或者跨几列



步骤：

1. 确定一行有多少td
2. 然后我们再看一共有几行
3. 观察哪个单元格有合并，设置对应属性

案例：

<img src="https://raw.githubusercontent.com/lrv618/html-css_foundation/main/images/202304192319918.png" alt="image-20230321184050475" style="zoom:150%;" />



![image-20230321185201617](https://raw.githubusercontent.com/lrv618/html-css_foundation/main/images/202304192319618.png)



#### 表格分区

<img src="https://raw.githubusercontent.com/lrv618/html-css_foundation/main/images/202304192320615.png" alt="image-20230321185329394" style="zoom:150%;" />



一个完整的表格主要包含三个部分：表格标题、表格表头、表格的主题

一个table内部实际还有三个分区标签组成

- *caption（说明文字）： 定义表格的主题*
- *thead（表格头）： 定义表格的头部，内部嵌套tr>th*
- *tbody： 定义表格主题，内部嵌套tr>td*



<img src="https://raw.githubusercontent.com/lrv618/html-css_foundation/main/images/202304192320463.png" alt="image-20230321190600644" style="zoom:150%;" />



![image-20230321190615495](https://raw.githubusercontent.com/lrv618/html-css_foundation/main/images/202304192320966.png)



### 表单元素

#### from标签

*form是表单的意思*

*form是容器级标签*，内部存放可输入的控件。如果输入的表单需要提交到数据，所有的控件需要被form表单包裹

- *method：方法的意思，指的数据提交的方法，属性值是post和get*
- *action：是数据提交的位置*



#### input标签

input标签是输入框的一种，但是不仅仅只有输入框，通过type属性，可以拓展多功能

input的type属性非常丰富



##### 输入框

输入框有两个重要属性，一个是value，一个placeholder

- *value：设置默认显示的内容，属性值为自定义内容*
- *placeholder： 属性作用是如果没有value的时候提示用户的文字占位符*

```
<input type="text" placeholder="请输入用户名">
```

<img src="https://raw.githubusercontent.com/lrv618/html-css_foundation/main/images/202304192320398.png" alt="image-20230321191541900" style="zoom:150%;" />



##### 密码框

- 通过*type值为password设置*的

显示效果是输入后通过掩码形式显示的

```
<input type="password" placeholder="请输入密码">
```

![image-20230321191638298](https://raw.githubusercontent.com/lrv618/html-css_foundation/main/images/202304192320498.png)



##### 单选框

- 通过*type值为radio设置的*

单选按钮都是成组出现的

<u>想实现一组单选按钮的互斥，需要设置相同的name属性</u>

```
<p>
    性&nbsp;别：
    <input type="radio" name='sex'>男
    <input type="radio" name='sex'>女
    <input type="radio" name='sex'>保密
</p>
```

![image-20230321191836379](https://raw.githubusercontent.com/lrv618/html-css_foundation/main/images/202304192320521.png)



##### 复选框

- 也叫多选框，*通过type值为checkbox设置*

复选框可以通过对自身进行多次点击实现选择或者取消

多选框可以选择一个或者多个，建议同一组设置同样的name属性

```
<p>
    爱&nbsp;好：
    <input type="checkbox" name="hobby"> 运动
    <input type="checkbox" name="hobby"> 绘画
    <input type="checkbox" name="hobby"> 音乐
    <input type="checkbox" name="hobby"> 阅读
    <input type="checkbox" name="hobby"> 其他
</p>
```



- 设置单选框和多选框都有一个*默认被选择*，需要*给input标签添加一个checked="checked"*

![image-20230321192227761](https://raw.githubusercontent.com/lrv618/html-css_foundation/main/images/202304192320155.png)

![image-20230321192244157](https://raw.githubusercontent.com/lrv618/html-css_foundation/main/images/202304192320645.png)



- 如果点击文字是不能触发对应单选或者多选框的点击事件的，
- *label标签可以扩大触发范围*

![image-20230321192447501](https://raw.githubusercontent.com/lrv618/html-css_foundation/main/images/202304192320912.png)



##### 文本域

只能输入单行文本，如果需要使用多行文本，就使用textarea标签

*textarea是一个双标签，是文本级标签*

*属性值rows和cols*



- *rows：**定义文本域的可视区域有几行，单位是**数字*
- *cols（**表行列数**）:**每行显示的**字节数量（以英文为准），单位是数字*
- *placeholder**（占位符）**:**占位符*
- *设置style性的resize属性，值为none*



textarea默认是可以通过拖动右下角实现放大或者缩小文本域的，如果我们不希望缩放文本域

我们可以通过*设置style性的resize属性，值为none*，*去掉可拖拽区域*



![image-20230321193149214](.\images\image-20230321193149214.png)



![image-20230321192733333](https://raw.githubusercontent.com/lrv618/html-css_foundation/main/images/202304192320305.png)

​                               



##### 下拉菜单

需要一组标签进行制作

需要两个标签select和option

- *select（选择），表示搭建下拉项*
- *option（选项），表示搭建下拉项*
- *如果希望有默认被选中想，使用**selected属性**，值也是selected*

***关系：select>option***

![image-20230321193512793](https://raw.githubusercontent.com/lrv618/html-css_foundation/main/images/202304192321931.png)

![image-20230321193525175](https://raw.githubusercontent.com/lrv618/html-css_foundation/main/images/202304192321647.png)



下拉菜单是*多选（ multiple="multiple"）*

我们可以通过将设置 select name="q[]" 以数 组的方式获取，以下使用 POST 方式提交

```html
<form action="" method="post">
<select multiple="multiple" name="q[]">
<option value="">选择一个站点:</option>
<option value="Baidu">Baidu</option>
<option value="GOOGLE">Google</option>
<option value="TAOBAO">Taobao</option>
</select>
<input type="submit" value="提交">
</form>
```



