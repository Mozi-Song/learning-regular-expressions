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
| [b]            | 回退（backspace）   | 
| \f             | 换页符              |
| \n             | 换行符              |
| \r             | 回车符              |
| \f             | 换页符              |
| \t             | 制表符（Tab）        |
| \v             | 垂直制表符           |


### 2. 与换行有关的符号有哪些，代表什么含义？
（参考来源https://knowledge.ni.com/KnowledgeArticleDetails?id=kA00Z0000019KZDSA2）
The Carriage Return ("CR") character (0x0D, \r) moves the cursor to the beginning of the line without advancing to the next line. This character is used as the new line character in Commodore and Early Macintosh operating systems (Mac OS 9 and earlier).

 The Line Feed ("LF") character (0x0A, \n) moves the cursor down to the next line without returning to the beginning of the line. This character is used as the new line character in Unix based systems (Linux, macOS X, Android,etc).

 The End of Line ("EOL") character (0x0D0A, \r\n) is actually two ASCII characters and is a combination of the CR and LF characters. It moves the cursor both down to the next line and to the beginning of that line. This character is used as the new line character in most other non-Unix operating systems, including Microsoft Windows and Symbian OS.
 
 ### 3. 应如何同时匹配Windows和Linux的空白行？
 
 ### 4. 什么是类元字符，它们是不是必要的？
 
 ### 5. 与数字有关的类元字符有哪些？
 
 ### 6. 与字母数字有关的类元字符有哪些？
 
 ### 7. 与空白字符有关的类元字符有哪些？
 
 
 
 

