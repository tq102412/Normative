# 开发规范

## 关于

- 创建日期：`2018-11-27`
- 最后一次更新时间：`2018-11-28`

## 目的

```
 为了更好的提高工作效率，保证开发的有效性和合理性，并可最大程度的提高程序代码的可读性和可重复利用性，指定此规范。开发团队根据自己的实际情况，可以对本规范进行补充或裁减。
```

## 编码规范

### 命名

1. 普通变量

```
普通变量命名遵循以下规则：
    a．首字母都使用小写；
    b．多个单词组成的变量名使用驼峰
例如：baseDir、redRosePrice等。
```

2. 局部变量

```
 局部变量命名遵循以下规则：
     a．"_"使用下划线前缀；
     b. 首字母使用小写
     c．多个单词间使用驼峰。
 例子：_baseDir、_redRosePrice等。
```

3. 全局变量

```
全局变量应该带前缀G_且所有字母大写,知道一个变量的作用域是非常重要的。
例子：
    G_LOG_LEVEL;
    G_LOG_PATH;
```
4. 全局常量

```
全局变量命名遵循以下规则：
    a．所有字母使用大写；
    b．全局变量多个单词间使用_作为间隔。
例子：
const BASE_DIR = './'
const RED_ROSE_PRICE = 'ok'
```

5. 类命名

```
类命名遵循以下规则：
    a．以大写字母开头；
    b．多个单词组成的变量名，单词之间不用间隔，各个单词首字母大写。
​例子：HomeController等。
```

6. 列表等包含多个数据的变量

```
变量命名遵循以下规则：
    a．使用复数
    b．多个单词间使用驼峰。
例子：users
```


7. 单个数据的变量

```
变量命名遵循以下规则：
    a．使用单数
    b．多个单词间使用驼峰。
例子：user
```

8. 方法或函数

```
方法或函数命名遵循以下规则：
    a．首字母小写；
    b．多个单词间不使用间隔，除第一个单词外，其他单词首字母大写。
例子：function myFunction() 或 function myDbOracle()等。

```

9. 缩写词

```
当变量名或者其他命名中遇到缩写词时，参照具体的命名规则，而不采用缩写词原来的全部大写的方式。

例子：function myPear（不是myPEAR） functio getHtmlSource（不是getHTMLSource）。
```

10. 数据库表名

```
数据库表名命名遵循以下规范：
    a．表名均使用小写字母；
    b．对于多个单词组成的表名，使用_间隔；
例子：user_info 和 book_store等。
```

11. 数据库表字段

```
数据库字段命名遵循以下规范：
    a．全部使用小写；
    b．多个单词间使用_间隔。
例子：user_name、rose_price等。
```

12. 接口命名
```
接口命名后缀添加Interface
例子：
    UserInterface
```

### 书写规范

1. 代码缩进

```
在书写代码的时候，必须注意代码的缩进规则，我们规定代码缩进规则如下：
    a．使用4个空格作为缩进，而不使用tab缩进（IDE可以进行预先设置）。
例子：

for ($i=0; $i<$count; $i++) {
    echo 'test';
}
```

2. 大括号

```
在程序中进行结构控制代码编写，如if、for、while、switch等结构，大括号传统的有两种书写习惯，分别如下：
直接跟在控制语句之后，不换行，如：
for ($i = 0; $i < $count; $i++) {
    echo 'test';
}
```

3. 小括号

```
小括号、关键词和函数遵循以下规则：
    a．不要把小括号和关键词紧贴在一起，要用一个空格间隔；如if ($a < $b)；
    b．小括号和函数名间没有空格；如$test = date("ymdhis")；
    c．除非必要，不要在Return返回语句中使用小括号。 如Return $a；
```

4. 等号

```
在程序中=符号的书写遵循以下规则：
    a．在=符号的两侧，均需留出一个空格；如 $a = $b 、$a = 'test'等；
    b．在=符号与!、=、<、>等符号相邻时，不需留一个空格；如 if ( $a == $b ) 、if ( $a != $b ) 等；
    c．在一个申明块，或者实现同样功能的一个块中，要求=号尽量上下对其，左边可以为了保持对齐使用多个空格，而右边要求空一个空格；
如下例：
$a   = 10;
$ab  = 20;
$abc = 30;
```

5. if else swith for while等书写

```
对于控制结构的书写遵循以下规则：
    a．在if条件判断中，如果用到常量判断条件，将常量放在等号或不等号的左边，例如：if (6 == $errorNum) ,因为如果你在等式中漏了一个等号，语法检查器会为你报错，可以很快找到错误位置，这样的写法要注意；
    b．switch结构中必须要有default块；
    c．在 for 和 wiile 的循环使用中，要警惕 continue 、 break 的使用，避免产生类似 goto 的问题；
    d. 花括号不能省略如下：
    //禁止此种写法：
		if(1 === a) a = 5;
		//禁止此种写法：
		if(1 === a)
			a = 5;
		//必须这样写：
		if(1 === a){
			a = 5;
		}
```

6. 类的构造函数

```
如果要在类里面编写构造函数，必须遵循以下规则：
    a．不能在构造函数中有太多实际操作，顶多用来初始化一些值和变量；
    b．不能在构造函数中因为使用操作而返回false或者错误，因为在声明和实例化一个对象的时候，是不能返回错误的；
```

7. 语句断行

```
在代码书写中，遵循以下原则：
    a．尽量不要使一行的代码太长，一般控制在100个字符以内；
    b．如果一行代码太长，字符串请使用类似 .= 的方式断行书写，代码直接敲断；
    c. 需要换行时，在运算符后换行。如逗号、与或非符号、加减乘除号

例子：
$sql  = 'SELECT username,password,address,age,postcode FROM test_t ';
$sql .= ' WHERE username=\'aaa\'';
$res  = mysql_query($sql);
```

8. 数字

```
一个在源代码中使用了的赤裸裸的数字是不可思议的数字，因为包括作者，在三个月后，没人知道它的含义。例如：

if ( 22 == $foo ) {
    start_thermo_nuclear_war();
} elseif ( 19 == $foo){
    refund_lotso_money();
} else {
    cry_cause_in_lost();
}

你应该用define()来给你想表示某样东西的数值一个真正的名字，而不是采用赤裸裸的数字，例如：
define('PRESIDENT_WENT_CRAZY', '22');
define('WE_GOOFED', '19');
define('THEY_DIDNT_PAY', '16');

if ( PRESIDENT_WENT_CRAZY == $foo ) {
    start_thermo_nuclear_war();
} elseif ( WE_GOOFED == $foo){
    refund_lotso_money();
} elseif ( THEY_DIDNT_PAY == $foo ){
    infinite_loop();
} else {
    cry_cause_in_lost();
}
```

9. 嵌入赋值

```
在程序中避免下面例子中的嵌入式赋值：
不使用这样的方式：
while ( $a != ( $c = getchar() ) ) {
    process the character
}
```

10. 语句结尾使用分号
```
var a = 10;
```

11. 对象属性结尾使用逗号
```
var obj = {
	a:1,
	b:2,//最后一个属性也必须加逗号
};
```

12. 对象键名使用小驼峰
13. es6使用let const来定义变量，禁止使用var。
14. 字符串直接量使用单引号
15. 禁止使用with语句
16. 禁止throw后不捕获异常
17. for…in…只能用于遍历对象，语句块内部必须判断hasOwnProperty
18. 禁止使用eval函数、new Function
19. setTimeout第一个参数禁止使用字符串，必须传函数。
20. 禁止使用setInterval
21. 注释的书写规范
```
a. 方法的注释使用如下：
b. 单行注释应当单独写一行
c. if else 内第一行为该分支的注释
例子：
/**
 * 获取用户id
 * @param id
 * @returns {string}
 */
function getUserById(id) {
    return "";
}

// 用户名
var userName = "tq";

if ("tq" !== userName) {
    //如果是tq则

    // tq长得帅
    var userAge = 18;

    return "tq长得帅";
} else {
    //如果不是tq
    return true;
}

```

### CSS规范

1. 禁止专门给一个样式属性建立一个class或id名。例如给红色一个专门的class：
```
.red{
    color:red;
}
```
2. 选择器级数最大3层，3层以上使用后代选择模式
3. 能使用直接选择器必须使用。例如.box>.title，禁止.box .title
4. 禁止选择器中使用元素名。不能控制元素时可以
5. 样式属性能合并都必须合并。如：
```
font: 100%/1.6 serif;//代表：font-family:serif;font-size:100%;line-height:1.6;
```
6. 0值后面禁止带上单位。例如：禁止height:0px，应写为：height:0
7. 颜色值：使用3位16进制小写值，如：红色#f00、绿色#0f0、蓝色#00f。不能被此法表示，再使用6位16进制
8. 每个样式属性以分号结束
9. 合并选择器时，一行一个选择器。例如：
```
.box1,
.box2{
    background:#fff;
}
```
10. 使用双引号，禁止单引号

### HTML规范：能遵循html5规范的都必须遵循

1. 文档类型声明：html5格式<!DOCTYPE html>
2. 自关闭元素，必须加上斜杠。例如：<br /><input />
3. Css样式放在头部，javascript等脚本放在页面body底部
4. Head、body元素必须要有。Head中必须有title、meta元素
5. Html元素名、自定义属性名、class值、id值：全小写、横杠分隔单词。例如nav-title/nav-content/nav-footer
6. Img元素必须有alt属性，且值具有意义
7. 属性值使用双引号包含
8. Id属性作为javascript定位使用，禁止专用于样式。一个页面中id必须唯一
9. 关注点分离。信息（html）、外观（css）、行为（javascript）分离
10. 能用伪元素、伪类的，必须用，这种情况禁止使用真实元素
11. Script和link元素的type属性可以省略。Link的rel属性必须有
12. 善用tabindex属性，优化页面体验
13. 尽量做到微格式、SEO优化
14. 目前前端路由使用hash来记录，所以锚点禁止使用。没有前端路由的页面，可以使用锚点
15. 名称长度不需要限制，必须要尽量体现名称的意义




## 其他规范

- 统一开发环境
- 数据库时间戳字段不能使用`int`类型而应当选用`bigint`或者`timestamp`
- 状态字段必须写明每一个值的含义
- 数据表中的字段必须有字段说明
- 不能随意修改框架代码



## 存放规则

- 控制器：`/app/Http/Controllers`
- ORM模型：`/app/Models`
- 业务逻辑：`/app/Service`
- 服务提供者：`/app/Providers`
- 路由：`/routes`
- 视图： `/resources/views`
- 公共函数：`/Helpers`
- 数据仓库：`/app/Repositories`

```
注：文件存放路径不得随意修改乱放，如有特殊原因提出讨论
```
