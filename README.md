# learning-regular-expressions
Notes of 正则表达式必知必会

# 第一章 正则表达式入门
### 1. 正则表达式的两种基本用途是什么？
搜索和替换。

### 2. 搜索的惯常含义是什么，“相等”测试本质上是一种什么操作？
搜索的惯常含义是寻找一个匹配的子字符串。
“相等”测试本质上是一种搜索。

### 3. 正则表达式的起源和发展历史是怎样的？
正则表达式起源于20世纪50年代数学领域的一些研究工作。几年后，计算机领域借鉴这些工作的思路和成果开发出了Unix世界里的Perl语言和grep等工具。

多年间，正则表达式仅限于Unix社群，但现在情况发生了变化，几乎所有的计算平台都以不同形式对正则表达式提供支持。

### 4. 正则表达式是什么？
是一些用来匹配和处理文本的字符串。

### 5. 各种正则表达式的“祖师爷”是谁？
是Perl，其他大多数实现都试图与Perl兼容。正则表达式支持是Perl的核心内容。


# 第二章 匹配单个字符
### 1. 哪个特殊字符可以匹配任意单个字符？
.
### 2. 元字符是什么，表示什么？
元字符有特殊含义，代表的不是字符本身，如"."。可以在字符前加上\（反斜杠）进行转义。
### 3. 正则表达式里\字符的用法是什么？
\总是出现在具有特殊含义字符序列的开头，如.表示匹配任意单个字符，\.表示匹配.字符本身。\后面的序列可以由一个或多个字符构成。

# 第三章 匹配一组字符
### 1. 元字符 [ ] 的含义是什么？
[ ] 定义一个字符集合，必须匹配其中某个成员。
### 2. 如何排除某些字符？
可通过元字符^来排除某个字符集合，如［^0-9]
# 第四章 使用元字符
### 1. 空白元字符都有哪些，代表什么含义？
| 元字符          | 说明               |
| :------------- | :----------------:| 
| [\b]            | 回退（backspace）   | 
| \f             | 换页符              |
| \n             | 换行符              |
| \r             | 回车符              |
| \t             | 制表符（Tab）        |
| \v             | 垂直制表符           |


### 2. 与换行有关的符号有哪些，代表什么含义？
| 元字符          | 说明               |
| :------------- | :----------------:| 
| \r             | 将光标移到当前行的开始，不进行到下一行   | 
| \n             | 将光标移到下一行，不移到行首   | 

（参考来源https://knowledge.ni.com/KnowledgeArticleDetails?id=kA00Z0000019KZDSA2）
The Carriage Return ("CR") character (0x0D, \r) moves the cursor to the beginning of the line without advancing to the next line. This character is used as the new line character in Commodore and Early Macintosh operating systems (Mac OS 9 and earlier).

 The Line Feed ("LF") character (0x0A, \n) moves the cursor down to the next line without returning to the beginning of the line. This character is used as the new line character in Unix based systems (Linux, macOS X, Android,etc).

 The End of Line ("EOL") character (0x0D0A, \r\n) is actually two ASCII characters and is a combination of the CR and LF characters. It moves the cursor both down to the next line and to the beginning of that line. This character is used as the new line character in most other non-Unix operating systems, including Microsoft Windows and Symbian OS.
 
 ### 3. 应如何同时匹配Windows和Linux的空白行？
 Windows系统使用的文本行结束标记是\r\n，而Unix/Linux及Mac OSX只使用\n。
 理想的正则表达式应该能适应这种情况：包含一个可选的\r和必须匹配的\n。
 ### 4. 什么是类元字符，它们是不是必要的？
 类元字符代表一些常用的字符集合，它不是必不可少的，总能通过逐一列举有关字符或定义字符区间来实现相同的效果。不过类元字符在实践中极其有用。
 ### 5. 与数字有关的类元字符有哪些？
| 元字符          | 说明               |
| :------------- | :----------------:| 
| \d             | 任何一个数字字符（等价于[0-9]）   | 
| \D             | 任何一个非数字字符（等价于[^0-9]) |
 ### 6. 与字母数字有关的类元字符有哪些？
| 元字符          | 说明               |
| :------------- | :----------------:| 
| \w             | 任何一个字母数字字符或下划线字符（等价于[a-zA-Z0-9_]）   | 
| \W             | 任何一个非字母数字字符或下划线字符（等价于[^a-zA-Z0-9_]) |
 ### 7. 与空白字符有关的类元字符有哪些？
| 元字符          | 说明               |
| :------------- | :----------------:| 
| \s             | 任何一个空白字符（等价于[\f\n\r\t\v]）   | 
| \S             | 任何一个非空白字符（等价于[^\f\n\r\t\v]）  |

注：用来匹配退格字符的[\b]元字符不在\s的覆盖范围内，\S也没有将其排除。
### 8. 正则表达式里可以有十六进制值吗？如何用十六进制值匹配数字5？
可以，十六进制值以\x开头。可用\x35匹配数字5。
### 9.正则表达式里可以有八进制值吗？如何用八进制匹配制表符？如何用八进制值匹配数字5？
可以，八进制值以\0开头。可用\011（对应ASCII字符9，也就是制表符）匹配制表符；用\065匹配数字5。
### 10.POSIX字符类有哪些？使用时应该注意什么？

# 第5章 重复匹配
### 1.如何匹配一次或多次重复？

### 2.如何匹配a@b.c这样的电子邮件地址？
 
### 3.如何进一步匹配a.b@c.d.e（可能有多个.）这样的电子邮件地址，应注意什么？

### 4.如何匹配0个或多个字符？

### 5.用\*表示，一个
可通过元字符^来排除某个字符集合，如［^0-9]
