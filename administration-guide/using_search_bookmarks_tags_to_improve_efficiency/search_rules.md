# 搜索规则

您可以在查询条件中的冒号之后指定搜索规则。*{搜索规则}*的语法如下所示：

*\<属性\> \<运算符\> \<值\>*

或者

*\<对象类型\>.\<属性\> \<运算符\> \<值\>*

*示例*.
以下表格描述了组成上面语法的各个部分：

**搜索规则的语法**

|组成部分|说明|值|例子|备注|
|--------|----|---|----|----|
|属性|要搜索的资源的属性。也能够是另外一个资源类型（参见对象类型）或者标签（自定义标签）的属性。|限制您的搜索至包含特定属性的对象。例如，只搜索包含有 status 属性的对象。|Status|--|
|对象类型|与要搜索的资源相联系的资源类型。|这些是系统对象，例如数据中心和虚拟机。|Users|--|
|运算符|比较运算符|youerelouai=splashleeelouai!=（不等于）splashleeelouai\>splashleeelouai\<splashleeelouai\>=splashleeelouai\<=splashleesplashyou|--|值选项基于对象类型而不同。|
|值|与前面的表达式进行比较的值。|youerelouai字符串splashleeelouai整形数splashleeelouai等级splashleeelouai日期（按照当地语言设置进行格式化）splashleesplashyou|youerelouaiDunrongsplashleeelouai256splashleeelouainormalsplashleesplashyou|youerelouai字符串中能够使用通配符。splashleeelouai""(一对双引号中间没有空格)能够用以表示没有初始化（空）的字符串。splashleeelouai在字符串或者日期中间包含空格时，必须使用一对双引号将其包含。splashleesplashyou|
