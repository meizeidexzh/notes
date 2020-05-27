## 基础
#### 运算符，表达式，语句
**运算符**

> 那些不常见的运算符
---

- `sizeof` sizeof运算符返回变量的大小
- `? x : y` 条件运算符
- `.`和`->` 成员运算符
- `&`和`*` 取址运算符和间接寻址运算符
- `>>`和`<<` 输入输出运算符
- `::`作用域运算符
- `,` 逗号运算符，顺序的执行一系列的运算，整个逗号表达式的值是列表最后一项的值

```
int a = (9+3, 5, 7-2);

#a = 5

```

> 赋值运算符
---

- 除了`=`还有`+=, -=, *= , /=`等等都是

#### 标准输入与输出
**标准输入输出对象**

- 四个标准输入输出对象： `cin cout cerr clog`
- 操纵符(manipulator)：`endl`
- 字符串字面值常量(string literal)：一对双引号包围的字符序列

**EOF特殊字符**
- 在`stdio.h`中，EOF是一个宏，为-1
- 它是end of file的缩写，表示"文字流"（stream）的结尾。
- 这里的"文字流"，可以是文件（file），也可以是标准输入（stdin）
- 标准输入要产生EOF，得在**一行的开头**，按`Ctrl-D`

#### 注释
- 注释分两种：双斜线`//`和成对注释界定符`/* */`
- 注释界定符不能嵌套
- 注释界定符可以注释多行，但不是必须
- 使用注释界定符注释多行的时候，注释内每行以星号开头，见下方
- 调试代码的时候，推荐使用双斜线注释

```
/*  注释界定符 单行 */

/*
 * 注释界定符 多行
 * 注释内每行开头都是*星号
 * 星号最好保持同一列
 */
 
// 这是单行注释

```
#### 数据类型
**c++的数据类型**
- 非常量类型
- 常量类型
- 符合类型：引用，指针
- 常量对象必须初始化

**关于内置类型**
- 内置数据类型：`int bool`
- 避免无符号和有符号变量之间做运算，结果不可控
- 建议初始化每个内置类型的变量

**变量的初始化**
```
int a = 0;
int b = {0};
int c{0};
int d(0);
```

#### const对象
- const对象**必须初始化**，且不能被改变
- 默认情况下，const对象只在文件内有效
- 如果想在多个文件之间共享const对象，必须在变量定义之前添加extern关键字

#### 引用
- 引用不是对象，而是别名
- 某个变量的引用，等价于这个变量，相当于该变量的别名
- 引用只能引用变量，不能引用常量和表达式
- 
```
int n = 4;
int &ref = n;
```


## 模板
#### 基础
- c++有类模板（class template）也有函数模板（function template）
- 模板本身不是类或者函数，而是一份说明书，编译器根据说明书生成相应的类或者函数
- 编译器根据模板创建类或者函数的过程叫做模板的**实例化**
- 