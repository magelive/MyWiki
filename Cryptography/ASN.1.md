## ASN.1介绍
### What's the ASN.1
ASN.1(Abstract Syntax Notation dot one[抽象记法1]).数字1被ISO加在ASN的后边，是为了保持ASN的开放性，可以让以后功能更加强大的ASN被命名为ASN.2等，但至今也没有出现。

### ASN.1功能及特点
1. ASN.1是定义抽象数据类型规格形式的标准。是用于描述数据的表示、编码、传输、解码的灵活的记法。它提供了一套正式、无歧义和精确的规则，以描述独立于特定计算机硬件的对象结构。

2. ASN.1是通信协议中描述数据传输的正式标记（notation），它与语言实现现和物理表示无关，与应用的复杂度无关。ASN.1特别适合表示现代通信应用中那些复杂的、变化的及可扩展的数据结构。

3. ASN.1发送任何形式（音频、视频、数据等等）的信息都必须用数字传送。ASN.1只能包含信息的结构方面（没有已经定义的或考虑到的处理数据值的操作）。它不是一个编程语言。

### ASN.1编码方式简介
ASN.1本身只定义了表示信息的抽象句法，但是没有限定其编码的方。各种ASN.1编码规则提供了由ASN.1描述其抽象句法的数据的值的传送语法（具体表达）。标准的ASN.1编码规则有基本编码规则（BER，BasicEncodingRules）、规范编码规则（CER，CanonicalEncodingRules）、唯一编码规则（DER，DistinguishedEncodingRules）、压缩编码规则（PER，PackedEncodingRules）和XML编码规则（XER，XMLEncoding Rules）。

### ASN.1说明
ASN.1是描述在网络上传输信息格式的标准方法。它有两部分：一部分描述信息内数据，数据类型及序列格式；另一部分描述如何将各部分组成消息。它原来是作为X.409的一部分而开发的，后来才自己独立成为一个标准。

ASN.1在OSI的ISO8824/ITUX.208（说明语法）和ISO8825/ITUX.209（说明基本编码规则）规范。
例如：
```
	Report::=SEQUENCE{
			author OCTET STRING,
			title OCTET STRING,
			bodyO CTET STRING,
			biblio Bibliography
}
```
在这个例子中，"Report"是由名字类型的信息组成的，而SEQUENCE表示消息是许多数据单元构成的，前三个数据单元的类型是OCTET STRING，而最后一个数据类型则下面的ASN.1语法表示它的意义：
```
	Bibliography::=SEQUENCE{
			author OCTET STRING
			title OCTET STRING
			publisher OCTET STRING
			year OCTET STRING
			}
```
ASN.1提供了一些基本的预定义数据类型：
```
UNIVERSAL0				保留给编码规则使用
UNIVERSAL1				布尔类型
UNIVERSAL2				整型
UNIVERSAL3				二进制字符串类型
UNIVERSAL4				八进制字符串类型
UNIVERSAL5				空类型
UNIVERSAL6				对象标识符类型
UNIVERSAL7				对象描述符类型
UNIVERSAL8				外部类型和类型实例
UNIVERSAL9				实数类型
UNIVERSAL10				枚举类型
UNIVERSAL11				嵌入的pdv类型
UNIVERSAL12				UTF8字符串类型
UNIVERSAL13				相关对象标识符类型
UNIVERSAL14-15			保留给本建议的以后版本和国际标准使用
UNIVERSAL16				序列和类型序列
UNIVERSAL17				集合和类型的集合
UNIVERSAL18-22,25-30		字符串类型
UNIVERSAL23-24			时间类型
UNIVERSAL31-...			保留给本建议以外的类型和国际标准使用
```
ASN.1还能够定义如下的数据结构类型：
```
结构(SEQUENCE)
列表(SEQUENCEOF)
类型选择(CHOICE)
```


## ASN.1基本语法规则
到目前为止，ASN.1记法仍然主要是BNF（Backus-NaurForm）形式的。
1. 在ASN.1中，符号的定义没有先后次序：只要能够找到该符号的定义即可，而不必关心在使用它之前是否被定义过。

2. 所有的标识符、参考、关键字都要以一个字母开头，后接字母(大、小写都可以)、数字或者连字符“-”(但不能以连字符“-”结尾，也不能连续出现两个连字符)，不能出现下划线“_”。

3. 关键字一般都是全部大写的，除了一些字符串类型，如PrintableString，UTF8String等，因为这些都是由原类型OCTETSTRING衍生出来的。

4. 在标识符中，只有类型和模块名字是以大写字母开头的，其它标识符都是以小写字母开头的。

5. 字符串有三种形式：
	(1). 用引号引用的字符串：“Thisisastring”
	(2). 单引号引用的二进制串后加大写字母B：‘01101’B
	(3). 单引号引用的十六进制串后加大写字母H：‘0123456789ABCDEF’H

6. 带小数点的小数形式不能在ASN.1中直接使用，在ASN.1中实数实际定义为三个整数：尾数、基数和指数。

7. 注释以两个连字符“--”开始，结束于行的结尾或者该行中另一个双连字符。

8. 如同大多数计算机语言，ASN.1不对空格、制表符、换行符和注释做翻译。但是在定义符号（或者分配符号Assignment）“::=”中不能有分隔符，否则不能正确处理。



[ASN.1编码规则详解(最全最经典)](http://wenku.baidu.com/link?url=D1g054a2I3O19XhSBzVxxHe0TFPjNDT9RBqXewLnbRGvlVZoxurefT1EdvUzT9h7L1eAv26hUgyc1E0Qy0URq-KutTILj2gfZyF_BXG_eAG)
(http://ishare.iask.sina.com.cn/f/23799557.html)