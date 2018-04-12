**后端代码规范文档：**  
**关键**：
**1.命名**  
类  
总是使用首字母大写单词串，ex，`ClassName`  
函数  
全部小写+下划线，ex，`method_name`  
全局变量  
全部大写字母+下划线，ex，`GLOBAL_NAME`  
局部变量  
小写+下划线，ex，`an_example = 1`  
**2.缩进**  
缩进大小为4个空格  
**3.变量声明**  
所有变量声明必须先进行初始化  
**4.语句**  
 通常每个语句应该独占一行

不过, 如果测试结果与测试语句在一行放得下, 你也可以将它们放在同一行. 如果是if语句, 只有在没有else时才能这样做. 特别地, 绝不要对` try/except `这样做, 因为`try`和`except`不能放在同一行.
```
Yes:

  if foo: bar(foo)
No:

  if foo: bar(foo)
  else:   baz(foo)

  try:               bar(foo)
  except ValueError: baz(foo)

  try:
      bar(foo)
  except ValueError: baz(foo)
```
**5.import语句**  
 每个导入应该独占一行

  Yes: import os
         import sys
  No:  import os, sys

导入总应该放在文件顶部, 位于模块注释和文档字符串之后, 模块全局变量和常量之前. 导入应该按照从最通用到最不通用的顺序分组:

+ 标准库导入
- 第三方库导入
- 应用程序指定导入

每种分组中, 应该根据每个模块的完整包路径按字典序排序, 忽略大小写.

  import foo
  from foo import bar
  from foo.bar import baz
  from foo.bar import Quux
  from Foob import ar 

**6.空格**  

按照标准的排版规范来使用标点两边的空格

括号内不要有空格.

按照标准的排版规范来使用标点两边的空格

  Yes: spam(ham[1], {eggs: 2}, [])
  No:  spam( ham[ 1 ], { eggs: 2 }, [ ] )
不要在逗号, 分号, 冒号前面加空格, 但应该在它们后面加(除了在行尾).

  Yes: if x == 4:
         print x, y
     x, y = y, x
  No:  if x == 4 :
         print x , y
     x , y = y , x

参数列表, 索引或切片的左括号前不应加空格.

  Yes: spam(1)
  no: spam (1)
  Yes: dict['key'] = list[index]
  No:  dict ['key'] = list [index]

在二元操作符两边都加上一个空格, 比如赋值(=), 比较(==, <, >, !=, <>, <=, >=, in, not in, is, is not), 布尔(and, or, not). 至于算术操作符两边的空格该如何使用, 需要你自己好好判断. 不过两侧务必要保持一致.

  Yes: x == 1
  No:  x<1

当'='用于指示关键字参数或默认参数值时, 不要在其两侧使用空格.

  Yes: def complex(real, imag=0.0): return magic(r=real, i=imag)
  No:  def complex(real, imag = 0.0): return magic(r = real, i = imag)

不要用空格来垂直对齐多行间的标记, 因为这会成为维护的负担(适用于:, #, =等):

  Yes:
     foo = 1000  # 注释
     long_name = 2  # 注释不需要对齐

     dictionary = {
         "foo": 1,
         "long_name": 2,
         }
  No:
     foo       = 1000  # 注释
     long_name = 2     # 注释不需要对齐

     dictionary = {
         "foo"      : 1,
         "long_name": 2,
         }
**7.空行** 

顶级定义之间空两行, 方法定义之间空一行

顶级定义之间空两行, 比如函数或者类定义. 方法定义, 类定义与第一个方法之间, 都应该空一行. 函数或方法中, 某些地方要是你觉得合适, 就空一行.
 
**8.注释**

确保对模块, 函数, 方法和行内注释使用正确的风格
* 文档字符串
> Python有一种独一无二的的注释方式: 使用文档字符串. 文档字符串是包, 模块, 类或函数里的第一个语句. 这些字符串可以通过对象的__doc__成员被自动提取, 并且被pydoc所用. (你可以在你的模块上运行pydoc试一把, 看看它长什么样). 我们对文档字符串的惯例是使用三重双引号"""( PEP-257 ). 一个文档字符串应该这样组织: 首先是一行以句号, 问号或惊叹号结尾的概述(或者该文档字符串单纯只有一行). 接着是一个空行. 接着是文档字符串剩下的部分, 它应该与文档字符串的第一行的第一个引号对齐. 下面有更多文档字符串的格式化规范.

* 模块
> 每个文件应该包含一个许可样板. 根据项目使用的许可(例如, Apache 2.0, BSD, LGPL, GPL), 选择合适的样板.

* 函数和方法
一个函数必须要有文档字符串, 除非它满足以下条件:

>* 外部不可见
* 非常短小
* 简单明了

文档字符串应该包含函数做什么, 以及输入和输出的详细描述. 通常, 不应该描述"怎么做", 除非是一些复杂的算法. 文档字符串应该提供足够的信息, 当别人编写代码调用该函数时, 他不需要看一行代码, 只要看文档字符串就可以了. 对于复杂的代码, 在代码旁边加注释会比使用文档字符串更有意义.关于函数的几个方面应该在特定的小节中进行描述记录， 这几个方面如下文所述. 每节应该以一个标题行开始. 标题行以冒号结尾. 除标题行外, 节的其他内容应被缩进2个空格.
>* Args:
列出每个参数的名字, 并在名字后使用一个冒号和一个空格, 分隔对该参数的描述.如果描述太长超过了单行80字符,使用2或者4个空格的悬挂缩进(与文件其他部分保持一致). 描述应该包括所需的类型和含义. 如果一个函数接受`*foo`(可变长度参数列表)或者`**bar` (任意关键字参数), 应该详细列出`*foo和**bar`.
* Returns: (或者 Yields: 用于生成器)
描述返回值的类型和语义. 如果函数返回None, 这一部分可以省略.
* Raises:
列出与接口有关的所有异常.
```
def fetch_bigtable_rows(big_table, keys, other_silly_variable=None):
    """Fetches rows from a Bigtable.

    Retrieves rows pertaining to the given keys from the Table instance
    represented by big_table.  Silly things may happen if
    other_silly_variable is not None.

    Args:
        big_table: An open Bigtable Table instance.
        keys: A sequence of strings representing the key of each table row
            to fetch.
        other_silly_variable: Another optional variable, that has a much
            longer name than the other args, and which does nothing.

    Returns:
        A dict mapping keys to the corresponding table row data
        fetched. Each row is represented as a tuple of strings. For
        example:

        {'Serak': ('Rigel VII', 'Preparer'),
         'Zim': ('Irk', 'Invader'),
         'Lrrr': ('Omicron Persei 8', 'Emperor')}

        If a key from the keys argument is missing from the dictionary,
        then that row was not found in the table.

    Raises:
        IOError: An error occurred accessing the bigtable.Table object.
    """
    pass
```
