# JS利用正则配合replace替换

**定义和用法**

replace\(\) 方法用于在字符串中用一些字符替换另一些字符，或替换一个与正则表达式匹配的子串。

**语法**

stringObject.replace\(regexp,replacement\)

参数　　描述

regexp　必需。规定了要替换的模式的 RegExp 对象。请注意，如果该值是一个字符串，则将它作为要检索的直接量文本模式，而不是首先被转换为 RegExp 对象。

replacement　必需。一个字符串值。规定了替换文本或生成替换文本的函数。

**返回值**

一个新的字符串，是用 replacement 替换了 regexp 的第一次匹配或所有匹配之后得到的。

**说明**

字符串 stringObject 的 replace\(\) 方法执行的是查找并替换的操作。它将在 stringObject 中查找与 regexp 相匹配的子字符串，然后用 replacement 来替换这些子串。如果 regexp 具有全局标志 g，那么 replace\(\) 方法将替换所有匹配的子串。否则，它只替换第一个匹配子串。

replacement 可以是字符串，也可以是函数。如果它是字符串，那么没有匹配都将由字符串替换。但是 replacement 中的 $ 字符具有特定的含义。如下表所示，它说明从模式匹配得到的字符串将用于替换。

字符　　替换文本

$1、$2、...、$99　　与 regexp 中的第 1 到第 99 个子表达式相匹配的文本。

$&与 regexp 相匹配的子串。

$\`　位于匹配子串左侧的文本。

$'　位于匹配子串右侧的文本。

%　直接量符号。

注意：ECMAscript v3 规定，replace\(\) 方法的参数 replacement 可以是函数而不是字符串。在这种情况下，每个匹配都调用该函数，它返回的字符串将作为替换文本使用。该函数的第一个参数是匹配模式的字符串。接下来的参数是与模式中的子表达式匹配的字符串，可以有 0 个或多个这样的参数。接下来的参数是一个整数，声明了匹配在 stringObject 中出现的位置。最后一个参数是 stringObject 本身。

**实例**

例子 1

在本例中，我们将使用 "W3School" 替换字符串中的 "Microsoft"：

```
<script type="text/javascript"> 

var str="Visit Microsoft!" 
document.write(str.replace(/Microsoft/, "W3School")) 

</script>
```

输出：

Visit W3School!

例子 2

在本例中，我们将执行一次全局替换，每当 "Microsoft" 被找到，它就被替换为 "W3School"：

```
<script type="text/javascript"> 

var str="Welcome to Microsoft! " 
str=str + "We are proud to announce that Microsoft has " 
str=str + "one of the largest Web Developers sites in the world." 

document.write(str.replace(/Microsoft/g, "W3School")) 

</script>
```

输出：

Welcome to W3School! We are proud to announce that W3School

has one of the largest Web Developers sites in the world.

例子 3

您可以使用本例提供的代码来确保匹配字符串大写字符的正确：

```
text = "javascript Tutorial"; 
text.replace(/javascript/i, "Javascript");
```

例子 4

在本例中，我们将把 "Doe, John" 转换为 "John Doe" 的形式：

```
name = "Doe, John"; 
name.replace(/(\w+)\s*, \s*(\w+)/, "$2 $1");
```

在本例中，我们将把所有的花引号替换为直引号：

```
name = '"a", "b"'; 
name.replace(/"([^"]*)"/g, "'$1'");
```

在本例中，我们将把字符串中所有单词的首字母都转换为大写：

```
name = 'aaa bbb ccc'; 
uw=name.replace(/\b\w+\b/g, function(word){ 
return word.substring(0,1).toUpperCase()+word.substring(1);} 
);
```

var str="fsaf$a$assdfdasfa$a$dsfadsf";

var strr='$'+'a'+'$';

var name = '"a", "b"';

var reger=new RegExp\("\[$\]a\[$\]","gm"\);

alert\(str.replace\(reger,'555888'\)\);

**Javascript正则表达式在线测试工具：**

[http://tools.jb51.net/regex/javascript](http://tools.jb51.net/regex/javascript)

**正则表达式在线生成工具：**

[http://tools.jb51.net/regex/create\_reg](http://tools.jb51.net/regex/create_reg)

