
Python简介
VS Code
## VS Code是微软提供的一款开源的、轻量级IDE。
- 一些特性。
  - VS Code只是一个编辑器，要安装Python的解释器才能在终端运行，要安装调试的扩展插件才能调试，调试时还需要选择调试环境。
  - 注意看状态栏的几个信息，可以点击切换当前格式。
  - 在资源管理器的“大纲”栏中可以查看定义的各个函数和全局变量。
  - 在左下角可以选择Python解释器。
- 常用快捷键。
  - 按F1打开命令面板。
  - 按F2可以重命名标识符，修改后整个文档中的该标识符都会被替换。
  - 按Ctrl + ` 打开终端。
  - 选中一行或多行之后，按Tab 或 Shift+Tab 可以调整代码块的缩进。不选中的情况下，按Ctrl + ] 或Ctrl + [ 可以直接调整当前行的缩进。
  - 按 F12 转到定义，按 Alt + F12 查看定义。
  - 按住Alt可以连续选取。
  - 按 Alt + ↑/↓ 可以上下移动当前行。
  - 按 Alt + ←/→ 可以切换打开的文档。
  - Ctrl + ←/→ ：以单词为单位移动光标。
Ctrl+Shift + ←/→ ：以单词为单位移动光标，调节选区。
Ctrl + Backspace/Delete ：以单词为单位删除代码。
  - 不选中的情况下，按Ctrl+X或Shift+Delete可剪切当前行。
  - 快速选择某个范围的内容：按End移动光标到行尾，然后按住Shift，再按↑、↓键选择一个范围，然后可以复制或删除。
  - Shift + Enter：在终端运行当前行或选定内容（会自动去掉多余的空行）。
  - 按Ctrl+Shift+ [ 或 ] 可以折叠或展开代码块。
  - 选中一段文本后，按Alt+Shift+↓，会在下方拷贝一份。
- 自定义的修改：
  - 在输入时会自动弹出补全窗口，可以按Tab键补全，也可以按Esc关闭。另外，在设置—>建议中关闭“使用Enter键也可以接受输入建议”，这样按Enter键的作用总是换行。
  - 设置切换行注释的快捷键为Ctrl + Q，切换块注释的快捷键为Ctrl + Shift + Q。
  - 在设置菜单里可以设置对代码自动格式化，设置只在键入一行时自动格式化，再设置手动格式化的快捷方式为Alt+F。
- 自选的扩展插件：
  - one dark pro：颜色主题。
  - vscode-icon：给资源管理器的文件夹加上图标。
  - Align by RegEx：用于对其某字符。按F1选择该命令，然后输入一个空格加# 作为对齐项（这样前面没有空格的# 就不会被移动）。
  - Code Spell Checker：检查单词拼写错误。要忽略的单词记录在settings.json中。通常把它禁用避免干扰，要检查时再启用。
  - Beautify：格式化JS、CSS、HTML。
  - Markdown Preview Enhance：一个增强型的Markdown阅读器。
## 
## 
## 
 
基本语法
代码规范
## Python代码通常采用PEP8规范。
- 标识符可以使用数字、字母或下划线，不能以数字开头，字母要区分大小写。
  - 标识符不能是关键字或保留字。
  - 把变量名的所有字母都小写，函数名的首字母小写，类名的首字母大写。
- 当标识符由多个单词组成时，通常有两种写法：
  - 下划线命名法：把所有单词都小写，单词之间用下划线连接。
  - 驼峰命名法：把所有单词的首字母大写，直接拼接在一起。
  - 建议让变量名和函数名采用下划线命名法，而类名采用驼峰命名法。
  - 常量名的所有字母都大写，因此不能用驼峰命名法，只能用下划线命名法。例如：MAX_LEN。
- 使用缩进距离来划分语句块（虽然允许使用花括号但是不提倡），同一语句块的所有语句的缩进距离必须相同（否则解释器运行时会报错）。
  - 通常每级缩进为4个空格。（Tab在不同编辑器中的值不统一，会引发混乱，应该尽量不使用）
  - 通常类和函数的结尾用两个空行分隔，其它语句块用一个空行分隔。
  - 在交互式编程时，输入完一个语句块后要敲一个空行表示结束。
  - 当一个语句块为空时，解释器可能会报错。可以用关键字pass填补空缺。
  - 每行包括行首缩进的最大宽度为79个字符。
- 每行写一条语句，每条语句的结尾不要加分号（虽然允许加分号但是不提倡）。
  - 如果在语句的结尾加分号，就可以在同一行内写多条语句。例如：str1="Hello!"; print(str1)
- 在操作符的两侧、逗号的右侧加上空格，美化排版（但是括号的两侧不需要加空格）。例如：a = f(1, 2) + g(3, 4)
- 用 # 标明单行注释，用三个引号（'''或"""）标明多行注释。
  - 如果将三个引号的注释放在函数的def语句之下，就会被当做说明文档保存。如下：
>>> def fun1(x, y):
...     """Hello World"""        # 三个引号的注释不会被解释器忽略，可以填补语句块的空缺
...
>>> fun1.__doc__
Hello World
  - 整个模块的说明文档应该放在.py文件的开头位置，如下：
"""
This module collects some functions and classes as follows:
...
"""
## 其它。
- 在Linux中，可以在Python脚本的第一行写入 #!/usr/bin/Python3。当使用 ./test.py 的方式运行Python脚本时，Linux就会使用该路径的Python解释器来运行该脚本。
- Python3默认采用utf-8编码来读取Python脚本文件，而Python2没有，因此要在脚本开头声明：
# -*- coding: utf-8 -*-
## 使用Python的一些高级语法虽然能使代码更优雅、简洁，但是也可能导致代码的阅读门槛变高。
## 
## 
 
输入输出
## print(value, ..., sep=' ', end='\n', file=sys.stdout, flush=False)
- 功能：将value参数的值显示到终端。
  - sep=' '：如果value有多个，就在它们之间加上sep，合并成一个字符串。
  - end='\n'：输出了value之后，在末尾加上一个换行符。
  - file=sys.stdout：默认输出到stdout。可以改为输出到文件流。
  - flush=False：不刷新缓存区。（输出会被先保存到缓存区，累计了一定数量之后才输出到stdout）
- 例：
>>> print("Hello World", end=" "); print("!")
Hello World !
>>> print("Hello", "World", "!")
Hello World !
- 下例是显示一个进度条：
>>> for i in range(101):
...     print("\rProgress: {:12}{}%".format((i // 10) * '▇', i), end='', flush=True)
...     time.sleep(0.1)
...
Progress: ▇▇▇▇▇▇▇▇▇▇  100%
  - 用回车符 \r 回到行首重新编辑。此时要用flush=True强制刷新缓存区。
## input(prompt=None)
- 功能：将prompt输出到stdout（不会自动换行），然后从stdin读取一行字符串（会忽略末尾的换行符），将它作为返回值。
- 例：
>>> x=input("x=")
x=
## 
## 
## 
 
运算符
## 算术运算符。
>>> 1 + 2        # 加
3
>>> 1 - 2        # 减
-1
>>> 1 * 2        # 乘
2
>>> 2 ** 3        # 幂运算
8
>>> 2 / 1        # 一个斜杠 / 表示算术除（保留商的小数部分，结果为浮点型）
2.0
>>> 1 // 2        # 两个斜杠 // 表示整除（去除商的小数部分，结果为整型）
0
>>> 1 % 2        # 取模（即取余数）
1
- 整型与浮点型混合运算时，整数会被自动转换成浮点数。
- 数字不可以与字符串混合运算。
- Python中没有自加、自减运算符，可以用 a+=1 、a-=1 的格式实现相同的功能。
- 被除数为0时会抛出异常。如下：
>>> 1 / 0
ZeroDivisionError: division by zero
>>> 1 // 0
ZeroDivisionError: integer division or modulo by zero
## 赋值运算符：即等号 = 。
- 复合赋值运算符：将算术运算符与赋值运算符组合使用。比如x+=1、x-=1。
- 可以用多个等号给多个变量连续赋值：（赋值运算符按照从右往左的运算顺序）
a = b = c = 1
- 可以在等号左边对多个变量同时赋值：
>>> a, b = b, a            # 此时解释器会把等号右边的值复制成元组再依次赋值，所以可以交换变量的值
>>> a, b = [1, 2, 3]        # 等号右边的元素个数要与等号左边的变量数一致
ValueError: too many values to unpack (expected 2)
## 比较（关系）运算符：与C语言相同，包括 >、<、>=、<=、==、!= 。
- 比较的结果为真则返回True，结果为假则返回False。
- 连续比较的例子：
>>> 1<2<3        # 相当于1<2 and 2<3 ，类似数学中的写法
True
>>> 1<2<2
False
>>> (1<2)<2        # 首先比较1<2，得到True。再比较True<2即1<2，得到True
True

比较运算符可以用于int型对象之间，或str型对象之间。

>>> 1 < 2
True
>>> 1 < 'a'                 # 不能混合比较一个int型对象与一个str型对象
TypeError: '<' not supported between instances of 'int' and 'str'
>>> 'a' < 'b' < 'c' 
True
>>> 'ac' < 'b'                 # 用于str型对象之间时，是比较首字母的大小
True
>>> 'ca' < 'b' 
False
## 逻辑运算符：与C语言不同，与、或、非运算符分别写作and、or、not。
- x and y    相当于：
if x:
    return y
else:
    return x
- x or y    相当于：
if x:
    return x
else:
    return y
- not x    相当于 !bool(x) 
  - Python可以使用 ! 、not两种逻辑非运算符，! 通常用于表达式中，not通常与关键字if、in、is搭配使用。
- 例：
>>> 0 and 1
0
>>> 1 and 0
0
>>> 0 or 1
1
>>> 1 or 0
1
>>> not "Hello"
False
## 三目运算符：与C语言的 ... ? ... : ... 不同，写作以下格式：
>>> True if 1>2 else False
False
## 位运算符：与C语言相同。
>>> x=1; y=0
>>> x & y        # 按位与
0
>>> x | y        # 按位或
1
>>> x ^ y        # 按位异或
1
>>> ~ x            # 取反（相当于 -x-1 ）
-2
>>> x << 1        # 左移
2
>>> x >> 1        # 右移
0
## 成员运算符。
- in    ：判断成员是否在序列或集合中。例如：
>>> 'H' in "Hello"
True
- not in
## 身份运算符。
- is    ：判断两个对象是否相同。例如：
>>> a=1; b=1
>>> a is b        # 相当于id(a)==id(b)
True
  - 运算符 is 是判断两个对象的id是否相同，运算符 == 是判断两个对象的值是否相等。如下：
>>> 0 == 0.0
True
>>> 0 is 0.0
False
- is not：相当于id(...)!=id(...)。
## 
## 
## 
 
选择结构
## Python的选择结构只有if语句。
## if语句：一般格式如下：
if condition:        # if、else语句的末尾要加上冒号
statement_block
elif condition:
statement_block
else:
statement_block
## 
## 
## 
 
循环结构
## Python的循环结构只有for语句和while语句。
- 可以用break跳出当前层循环，用continue跳到下一次循环。
- for语句、while语句可以与else语句连用，当循环正常结束时就会执行else语句，如果是因为break等原因退出循环，则不会执行else语句。
## for语句：不是用于进行指定次数的循环，而是用于遍历一个迭代器中的元素。
- 一般格式如下：
for var in iterable:
statement_block
else:
statement_block
- 遍历时，每次可以取出多个元素。
for var1,var2 in sequence:        # 相当于for line in sequence；var1,var2 = line
statement_block
else:
statement_block
- for语句在开始遍历一个可迭代对象时，会暂存该对象的值。
>>> def fun1():
...     print("fun1")
...     return [1, 2, 3]
... 
>>> for i in fun1():            # Python解释器会调用fun1()，获得一个可迭代对象，然后暂存它
...     print(i)
... 
fun1                            # fun1()只会被执行一次
1
2
3
- 用range()可以方便地控制for语句的循环次数。如下：
>>> for i in range(4):
...     print(i)
...
1
2
3
## while语句：一般格式如下：
while condition:
    statement_block
else:
statement_block
## 
## 
## 
 
变量
## Python中，使用变量之前不需要先定义或声明它，变量会在第一次赋值时被自动创建。
- Python中的变量只是一个标识符，本身没有存储数据。像一个不受限制的指针，可以指向任何类型的对象。
- 访问变量时，实际上是访问变量所指的对象。
- 赋值语句并不会修改变量所指的对象，而是让变量指向另一个对象。
## 变量。
- 创建变量：
>>> a = 1            # 让变量a指向一个值为1的int类对象
>>> a = "Hello"        # 让变量a指向一个str类对象
- 变量本身没有数据类型，只有变量所指的对象才有类的概念。
>>> type(a)            # 用函数type()可以返回变量所指对象的类名
<class 'int'>
- 用关键字 del 可以销毁已创建的变量：
>>> del a
>>> a                # 访问没有创建的变量标识符时会报错
NameError: name 'a' is not defined
## 常量。
- Python中没有关键字const，不能把变量声明成符号常量。通常把一些变量大写所有字母，当作符号常量使用。
- int、float、complex、tuple、str、bytes等数据类型是只读的，也相当于常量。
  - 例如，12345是int类型的常量对象，"Hello World!"是str类型的常量对象。
## 
## 
## 
 
变量与对象
## Python是纯面向对象的语言，所有标识符、常量都是以对象（某个类的实例）的形式保存，都可以赋值给变量。
- 创建一个对象时，Python会自动分配存储空间，并在修改对象时自动调整容量。
  - 例如，可以创建一个任意大的int型常量，可以把一个list型对象扩展到任意大。
- Python解释器有内存自动回收机制：每个对象有一个引用计数器，记录了当前指向该对象的引用数。当引用数减少为0时，解释器就会回收该对象的内存空间。
  - 可以通过 sys 模块的函数 getrefcount(x) 查看某个对象的当前引用数。

每个Python对象实际上是一个C的结构体：

typedef struct _object {
    Py_ssize_t ob_refcnt;        // 该对象的引用计数
    struct _typeobject *ob_type;    // 该对象的类型
} PyObject;


## 引用类型：指向某个对象的内存地址。
- 引用类型是对指针类型的封装，限制了指针的一些灵活却不安全的功能。
  - 引用类型的变量只是一个标识符，本身没有存储数据，相当于对象的别名。
- 引用类型的变量在创建时就必须赋值，不可能为空。
  - 指针在创建时如果不初始化，就会指向一个无法确定的内存地址，操作这个指针就有危险。
- 值类型的变量存储在栈区，引用类型的变量、引用所指的对象实例存储在堆区（因为要动态分配内存）。
  - 值类型、指针类型赋值时采用值传递（拷贝实际存储的数据），而引用类型赋值时采用引用传递（拷贝内存地址）。
- 因为指针存在安全性、操作复杂等问题，C++、Java、C#、Python中用引用类型取代了指针类型。
  - C++中，用 & 创建一个引用。例如：int &b=a;
  - Java中，基本类型的数据存储在堆栈中，赋值时采用值传递，而非基本类型的数据都是对堆栈上某些数据的引用，赋值时采用引用传递。
  - C#中，可以创建值类型、引用类型、指针类型（不推荐使用）。
## 例：
>>> a=1                # 让变量a指向一个值为1的int类对象
>>> id(a)            # 用函数id()返回变量所指对象的地址
1533892880
>>> a=2; id(a)        # 让变量a指向一个值为2的int类对象
1533892896            # a所指的地址改变了
>>> a=1; id(a)        # 让变量a指向一个值为1的int类对象
1533892880            # a又重新指向之前的地址
- 当用户使用了[-5,256]之内的整数常量、20位以内的字符串常量时，Python解释器会将它们缓存起来，不会销毁，避免用户再使用它们时重复创建对象。因此，重复使用这些常量时，会指向相同的内存地址。如下：
>>> a=256
>>> b=256
>>> a is b
True                    # 指向相同的内存地址
>>> a=257
>>> b=257
>>> a is b
False                # 指向不同的内存地址
- Python的赋值一般是采用引用传递，而不是值传递。因此改变原对象时会改变引用者，改变引用者时会改变原对象。
>>> list1 = [1, 2, 3]
>>> list2 = list1        # 引用传递
>>> list2
[1, 2, 3]
>>> list1[0] = 0        # 改变变量list1所指对象
>>> list1
[0, 2, 3]
>>> list2            # 此时变量list2与变量list1指向同一个对象
[0, 2, 3]
>>> list1 = 1            # 让变量list1指向一个值为1的int类对象
>>> list2            # 此时变量list2与变量list1指向不同对象
[0, 2, 3]
- 用list.copy()、切片等方法可实现浅拷贝。
  - list像一个指针数组，每个指针指向一个对象。浅拷贝时，是创建一个新list，拷贝所有指针。
>>> list1 = [1, 2, 3]
>>> list2 = list1.copy()
>>> list2
[1, 2, 3]
>>> list2 is list1            # 新list不是原list
False
>>> list2[0] is list1[0]        # 新list中的元素就是原list中的元素
True
## 
## 
## 
 
变量的作用域
## Python中，变量的作用域分为四种级别。
- 局部作用域（Local）
- 外部非全局作用域（Enclosing）
- 全局作用域（Global）
- 内建作用域（Built-in）
## 访问一个变量的标识符时，解释器会按照L→E→G→B的顺序寻找该变量。
- 例：
dir                    # 访问内建作用域中的函数
g = 3                # 全局作用域
def outer():
e = 2            # 外部非全局作用域
def inner():
l = 1        # 局部作用域
- Python中，只有模块（module）、类（class）和函数（def、lambda）才会创建作用域。
  - 在if语句、for语句、while语句等语句块中创建的变量不会被立即销毁、可以被外部访问。
  - 例：
>>> if True:
...     x=1
...
>>> x
1
- Python中，在局部作用域中可以直接读取外部变量的值（如果不重名的话），但是不可以直接修改外部变量。
  - 如果是外部非全局变量，要用 nonlocal 关键字声明才能修改。
  - 如果是全局变量，要用 global 关键字声明才能修改。
  - 例：
>>> a = 1
>>> def fun1():
...     a = 2        # 不能直接修改外部变量，所以这条语句会创建一个局部变量a
...
>>> def fun2():
...     b = a        # 此时变量a是指全局变量a
...     a = 2        # 此时变量a依然是指全局变量a，不能对它进行赋值，这会导致函数在运行时报错
...
>>> fun2()
UnboundLocalError: local variable 'a' referenced before assignment
  - 例：
a = 1
def outer():
global a
a = 2        # 此时变量a是指全局变量a
b = 2
def inner():
nonlocal b
b = 3
## 
## 
## 
 
基本数据类型
## Python的基本数据类型。
- 可变类型（可读可写）：list、set、dict。
- 不可变类型（只读）：int、float、complex、tuple、str、bytes。
  - 例：
>>> str1 = "Hello"
>>> str1[0] = 'h'        # 修改不可变类型时会报错
TypeError: 'str' object does not support item assignment
>>> str1 = "hello"    # 这并不是修改字符串，而是让变量str1指向另一个对象
>>> str1
'hello'
## Python的数据类型不是关键字，而是通过类来实现的（小写的类名）。
- 数据类型名可以像普通标识符一样修改。
>>> int
<class 'int'>    # int是一个类名
>>> int = 1        # 可以被修改
>>> int
1
- 数据类型名可以用来创建这种类型的对象。
>>> int()
0
- 数据类型名可以用来转换对象的数据类型。
>>> int(3.14)
3
>>> float(3)
3.0
- 数据类型名可以被继承、重载。
## None：空值。属于NoneType类型。
>>> type(None)
<class 'NoneType'>
>>> None == 0            # 空值并不等于0
False
## 
## 
## 
 
bool
## bool：布尔型。取值为True或Flase（首字母大写）。
- True、Flase在底层是以数字1、0存储。
>>> True - 1
0
>>> True + 1
2
>>> True + False
1
>>> True > False
True
>>> True > True
False
## 使用bool(object)时，只有以下情况会被转换成False，其它情况都会被转换成True。
>>> bool(0), bool(0.0), bool(-0), bool(-0.0)                # 整数0、浮点数0.0以及两者的负数
(False, False, False, False)
>>> bool(1), bool(2), bool(-1), bool('0'), bool("False")
(True, True, True, True, True)
>>> bool(""), bool(()), bool([]), bool({}), bool(None)        # 空值、空的基本数据类型对象
(False, False, False, False, False)
>>> bool(1 > 2)                                            # 结果为假的逻辑表达式
False
## 
## 
## 
 
数字
## int：整数。
>>> 1 + 2
3
>>> type(1)
<class 'int'>
- int型常量的前缀。
  - 0b    ：转换为二进制。转换失败的话会抛出异常。
  - 0o    ：转换为八进制。转换失败的话会抛出异常。
  - 0x    ：转换为十六进制。转换失败的话会抛出异常。
>>> 0b1100
12
>>> 0011                        # 普通数字常量不能以0开头
  File "<stdin>", line 1
    0011
       ^
SyntaxError: invalid token
>>> 0o14
12
>>> 0x14
20
## float：浮点数。
- 例：
>>> 1.0            # float型在保存时至少会保留一位小数
1.0
>>> 1.0 - 1.0
0.0
- 浮点数可以用字母 e 声明为科学计数法。
>>> 1.2e+3
1200.0
>>> 1.2e-3
0.0012
- float型在计算机中无法精确存储，因此在运算时会有很小的误差。
>>> 0.1 + 0.2
0.30000000000000004
## complex：复数。实部和虚部都是浮点型，用字母 j 标明虚部。
>>> 2j
2j
>>> 1 + 2j
(1+2j)
>>> complex(1, 2)        # 用complex()创建一个复数
(1+2j)
>>> complex(1)        # 没有虚部时，默认为0j
(1+0j)
## 
## 
## 
 
数制的转换
## 将其它进制的字符串转换成int型数字。
- 使用int()即可转换。
>>> int("100",2)
4
>>> int("100", 8)
64
>>> int("100", 16)
256
  - 字符串中也可以加上表示进制的前缀。
>>> int("0b100",2)
4
>>> int("0bb100",2)            # 前缀不对时会报错
ValueError: invalid literal for int() with base 2: '0bb100'
## 将int型数字转换成其它进制的字符串。
- def bin(int) -> str
  - 功能：将一个整数转换成二进制字符串。
  - 例：
>>> bin(10)
'0b1010'
- def oct(int) -> str
  - 功能：将一个整数转换成八进制字符串。
  - 例：
>>> oct(8)
'0o10'
- def hex(int) -> str
  - 功能：将一个整数转换成十六进制字符串。
  - 例：
>>> hex(16)
'0x10'
## 
## 
## 
 
list
## list：列表类型，按顺序存储一组元素。
- 可以用中括号 [ ] 创建list，各个元素之间用逗号分隔。
>>> list1 = [1, 2, 3]
>>> list1
[1, 2, 3]
>>> [1, 2, 3, "Hello", list1]        # 列表中的元素可以是任意类型
[1, 2, 3, 'Hello', [1, 2, 3]]
- list(iterable=...) -> list
  - 功能：创建一个list。
  - 例：
>>> list()                    # 不输入参数时，是创建一个空list
[]
>>> list("Hello")                # 输入一个可迭代对象时，其中的各个元素会被拆开
['H', 'e', 'l', 'l', 'o']
## 
## 
## 
 
增查
## 增。
- list.append(object) -> None
  - 功能：将一个对象附加到list的末尾，作为最后一个元素。
  - 例：
>>> list1 = [1, 2, 3]
>>> list1.append("Hello")
>>> list1
[1, 2, 3, 'Hello']
- list.extend(iterable) -> None
  - 功能：将一个可迭代对象中的每个元素逐个附加到list的末尾。
  - 相当于for i in iterable: list.append(i)。
  - 例：
>>> list1 = [1, 2, 3]
>>> list1.extend("Hello")
>>> list1
[1, 2, 3, 'Hello', 'H', 'e', 'l', 'l', 'o']
>>> list1.extend(1)
TypeError: 'int' object is not iterable
- list.insert(index: int, object) -> None
  - 功能：将一个对象插入到list的指定位置。
  - 例：
>>> list1 = [1, 2, 3]
>>> list1.insert(2, "Hello")
>>> list1
[1, 2, 'Hello', 3]
## 查。
- list.count(object) -> int
  - 功能：在list中查找某个元素，返回其存在的个数。如果不存在该元素则返回0。
  - 例：
>>> list1 = [1, 2, 3]
>>> list1.count(3)
1
>>> list1.count(4)
0
- list.index(object, start: int=..., stop: int=...) -> int
  - 功能：在list的 [start,stop) 范围内查找某个元素，返回第一个存在的位置。如果不存在该元素则抛出异常。
  - 例：
>>> list1 = [1, 2, 3]
>>> list1.index(3)
2
>>> list1.index(3, 0, 2)
ValueError: 3 is not in list
>>> list1.index(3, 0, 3)
2
- list.copy() -> list
  - 功能：返回list的一个浅拷贝。
## 
## 
## 
 
改删
## 改。
- list.sort(key=None, reverse=False) -> None
  - 功能：对list进行排序。（这会改变原list）reverse=True时是反向排序。
  - 例：
>>> list1 = [1, 3, 2]
>>> list1.sort()
>>> list1
[1, 2, 3]
>>> list1.sort(reverse=True)
>>> list1
[3, 2, 1]
- list.reverse() -> None
  - 功能：翻转list。（这会改变原list）
  - 例：
>>> list1 = [1, 2, 3]
>>> list1.reverse()
>>> list1
[3, 2, 1]
## 删。
- list.clear() -> None
  - 功能：清空list，删除所有元素。
  - 例：
>>> list1 = [1, 2, 3]
>>> list1.clear()
>>> list1
[]
- list.remove(object) -> None
  - 功能：删除list中的某个元素（只会删除第一个存在）。如果不存在该元素则抛出异常。
  - 例：
>>> list1 = [1, 2, 3]
>>> list1.remove(1)
>>> list1
[2, 3]
>>> list1.remove(1)
ValueError: list.remove(x): x not in list
- list.pop(index: int) -> object
  - 功能：删除list中的某个元素（下标为index的那个），并返回它。
  - 如果index所指的元素不存在，则抛出异常。
  - 如果index为空，则取出最后一个元素。
  - 如果list为空，则抛出异常。
  - 例：
>>> list1 = [1, 2, 3]
>>> list1.pop(2)
3
>>> list1.pop()
2
>>> list1.pop()
1
>>> list1.pop()
IndexError: pop from empty list
  - list.pop()的效率很高，可以与list.append()搭配使用，把list用作先入后出的栈。
  - list.pop(index)的效果较低，因为每取出一个前面的元素，都要移动后面所有元素的位置。
## 
## 
## 
 
列表生成式
## 列表生成式：通过遍历某个序列来生成列表。
>>> [i for i in range(5)]
[0, 1, 2, 3, 4]
- 可以加上if条件：
>>> [i for i in range(5) if i%2==0]
[0, 2, 4]
- 可以使用多个for语句（这并不是同时遍历，而是像多维数组一样逐层遍历）。
>>> [x+str(y) for x in "ABC" for y in range(1,4)]
['A1', 'A2', 'A3', 'B1', 'B2', 'B3', 'C1', 'C2', 'C3']
## 用括号 () 写出的是生成器，不是元组。
>>> (i for i in range(5))
<generator object <genexpr> at 0x7fde23dcd780>
## 字典生成式：通过遍历某个序列来生成字典。
>>> {i:bin(i) for i in range(5)}
{0: '0b0', 1: '0b1', 2: '0b10', 3: '0b11', 4: '0b100'}
## 集合生成式：通过遍历某个序列来生成集合。
>>> {i for i in range(5)}
{0, 1, 2, 3, 4}
## 
## 
## 
 
tuple
## tuple：元组类型，相当于只读的list。
- 可以用小括号 ( ) 创建tuple，各个元素之间用逗号分隔。
>>> tuple1 = ("Hello", "World")
>>> tuple1
('Hello', 'World')
  - 如果只有一个元素，则要加上逗号，强调为元组。
>>> (1)            # 被看做int类对象
1
>>> (1,)            # 被看做tuple类对象
(1,)
- tuple(iterable=...) -> tuple
  - 功能：创建一个tuple。
  - 例：
>>> tuple()                    # 不输入参数时，是创建一个空tuple
()
>>> tuple("Hello")
('H', 'e', 'l', 'l', 'o')        # 输入一个可迭代对象时，其中的各个元素会被拆开
- tuple中的元素不能改变（每个位置只能指向固定的对象），但如果这些对象本身是可变类型，则可以被修改。
>>> tuple1=(1, 2, [])
>>> tuple1
(1, 2, [])
>>> tuple1[2] = [3]            # 不能改变某个位置所指的对象
TypeError: 'tuple' object does not support item assignment
>>> tuple1[2].append(3)        # 可以修改这个对象本身
>>> tuple1
(1, 2, [3])
## tuple的常用方法较少，只是兼容两个list的查询方法。
- tuple.count(object) -> int
- tuple.index(object, start: int=..., stop: int=...) -> int
## 
## 
## 
 
str、bytes
## Python中没有字符类型，只有字符串类型。一个字符就是一个长度为1的字符串。
## Python3中，解释器在内存中处理字符串时默认采用str类型，与外部交互时才转换成bytes类型。
- str：字符串类型，采用Unicode编码，以字符为单位处理字符串。
  - str相当于只能存储字符的tuple。
- bytes：字节类型，与str的用法相同，但采用更底层的编码格式（比如utf-8、ASCII），以字节为单位处理字符串。
- bytearray：相当于列表类型的bytes，可以被修改。
  - 例：
>>> bytearray(3)                # 直接输入数字，是创建一个指定长度的bytearray
bytearray(b'\x00\x00\x00')
>>> bytearray('hello')        # 不能直接输入str类型，要转换成bytes类型
TypeError: string argument without an encoding
>>> bytearray('hello'.encode())
bytearray(b'hello')
>>> b = bytearray('hello'.encode())
>>> del b[0]
>>> b
bytearray(b'ello')
## 字符串常量。
- 字符串常量的定界符有三种。
  - 单引号 ' ：此时字符串中不能包含单引号。
  - 双引号 " ：此时字符串中不能包含双引号。
  - 三引号 ''' 或 """    ：此时字符串中可以包含单引号、双引号，而且可以在写入时换行。例如：
>>> """,,,'hello',,,"world"
...    ,,,"""
',,,\'hello\',,,"world"\n\t,,,'
- 字符串常量的可用前缀。
  - r：声明为raw（原始字符)，让反斜杠不发生转义。
>>> print(r"Hello!\n")
Hello!\n
  - b：声明为bytes对象。
>>> b"Hello"
b'Hello'
>>> b"你好"            # 该字符串只能包含ASCII字符，否则不能声明为bytes对象
SyntaxError: bytes can only contain ASCII literal characters.
  - u：声明为Unicode字符。
>>> u"你好"
'你好'
>>> u"\u4f60\u597d"
'你好'
  - ASCII码中的非显示字符可以用一个\x加两个十六进制数表示。
>>> '\v\f\b'
'\x0b\x0c\x08'
## 常用方法。
- str(...)
  - 功能：创建str对象。
  - 例：
>>> str()                            # 不输入参数时，是创建一个空str
''
>>> str(b"Hello", encoding="utf-8")    # 将一个bytes对象转换成str对象
'Hello'
>>> str(5)                            # 将其它类型的对象转换成str对象
'5'
- bytes(...)
  - 功能：创建bytes对象。
  - 例：
>>> bytes()                            # 不输入参数时，是创建一个空bytes
b''
>>> bytes("Hello", encoding="utf-8")    # 将一个str对象转换成bytes对象
b'Hello'
>>> bytes(5)                            # 创建一个5字节大小的bytes对象
b'\x00\x00\x00\x00\x00'
- str.encode(encoding='utf-8', errors='strict')
  - 功能：对str对象进行编码，返回一个bytes对象。
  - errors='strict'表示采用严格模式，一旦编码出错就抛出异常。
  - 例：
>>> "www.你好.com".encode()
b'www.\xe4\xbd\xa0\xe5\xa5\xbd.com'
  - Python解释器中看不到str对象的Unicode值，可以用"unicode_escape"编码格式将str对象显示地转换成Unicode格式。
>>> "www.你好.com".encode("unicode_escape")
b'www.\\u4f60\\u597d.com'                        # 该字符串的内容被改变了，不能按正常格式解码
>>> "www.你好.com".encode("unicode_escape").decode("unicode_escape")
'www.你好.com'
- bytes.decode(encoding='utf-8', errors='strict')
  - 功能：对bytes对象进行解码，返回一个str对象。
  - 例：
>>> b'www.\xe4\xbd\xa0\xe5\xa5\xbd.com'.decode()
'www.你好.com'
## 
## 
## 
 
查
## 查。
- str.count(sub, start: int=..., stop: int=...) -> int
- str.index(sub, start: int=..., stop: int=...) -> int
- str.find(sub, start: int=..., stop: int=...) -> int
  - 功能：在str的 [start,stop) 范围内查找某个字符串，返回第一个存在的位置。如果不存在该元素则返回-1。
  - 当元素不存在时，str.find()、str.rfind()会返回-1，而str.index()会抛出异常。
  - 例：
>>> "Hello".find("H")
0
>>> "Hello".find("o", 0, 4)
-1
>>> "Hello".find("o", 0, 5)
4
- str.rfind(sub, start: int=..., stop: int=...) -> int
  - 功能：在str的 [start,stop) 范围内，从右向左查找某个字符串，返回第一个存在的位置（正常顺序的位置）。如果不存在该元素则返回-1。
  - 例：
>>> "Hello".rfind("H")
0
>>> "Hello".rfind("o", 0, 4)
-1
>>> "Hello".rfind("o", 0, 5)
4
## 判断字符串的类型。
- str.startswith(prefix) -> bool
  - 功能：如果str以指定的字符串开头。则返回True。
  - prefix是一个字符串，或者是包含多个字符串的元组（否则会报错）。
  - 例：
>>> "Hello".startswith("He")
True
>>> "Hello".startswith(("H","h"))
True
- str.endswith(suffix) -> bool
  - 功能：如果str以指定的字符串结尾。则返回True。
  - suffix是一个字符串，或者是包含多个字符串的元组（否则会报错）。
  - 例：
>>> "Hello".endswith("o")
True
>>> "Hello".endswith(("O","o"))
True
- str.isalnum() -> bool
  - 功能：如果str不为空，且所有字符都是字母或数字，则返回True。
  - 例：
>>> "1G".isalnum()
True
>>> "-1G".isalnum()
False
- str.isalpha() -> bool
  - 功能：如果str不为空，且所有字符都是字母，则返回True。
  - 例：
>>> "1G".isalpha()
False
>>> "Hello".isalpha()
True
- str.isdecimal() -> bool
  - 功能：如果str不为空，且所有字符都是十进制数字，则返回True。
  - 例：
>>> "12".isdecimal()
True
>>> "1.2".isdecimal()
False
- str.islower() -> bool
  - 功能：如果str中包含字母，且所有字母都是小写，则返回True。
  - 例：
>>> "12".islower()
False
>>> "12hello".islower()
True
- str.isupper() -> bool
  - 功能：如果str中包含字母，且所有字母都是大写，则返回True。
  - 例：
>>> "HELLO".isupper()
True
>>> "Hello".isupper()
False
- str.istitle() -> bool
  - 功能：如果str为标题格式，则返回True。
  - 例：
>>> "Hello World! 123".istitle()
True
## 
## 
## 
 
改
## 改。
- str.replace(old: str, new: str, count: int=...) -> str
  - 功能：返回str的一个副本，将其中的old字符串替换成new字符串，最多替换count次。
  - 若count为空，或者为负数，则替换无限次。
  - 例：
>>> "Hello".replace("l", "L")            # 替换无限次
'HeLLo'
>>> "Hello".replace("l", "L", -1)        # 替换无限次
'HeLLo'
>>> "Hello".replace("l", "L", 0)        # 替换0次
'Hello'
>>> "Hello".replace("l", "L", 1)        # 替换1次
'HeLlo'
- str.lower() -> str
  - 功能：返回str的一个副本，将其中的所有字母转换成小写。
  - 例：
>>> "Hello".lower()
'hello'
- str.upper() -> str
  - 功能：返回str的一个副本，将其中的所有字母转换成大写。
  - 例：
>>> "Hello".upper()
'HELLO'
- str.title() -> str
  - 功能：返回str的一个副本，将它转换成标题格式，即每个字段的首字母大写。
  - 例：
>>> "hello world! 123".title()
'Hello World! 123'
- str.split(sep: str=..., maxsplit: int=...) -> list
  - 功能：以sep作为分隔符，将str分割成多段，返回一个list。最多分割maxsplit次。
  - 若sep为空，则以所有空白字符（ \t\n\r\x0b\x0c）作为分隔符。
  - 若maxsplit为空，或者为负数，则分割无限次。
  - 例：
>>> "www.baidu.com..test".split(".")
['www', 'baidu', 'com', '', 'test']        # 如果有两个连续的分隔符，分割出来的是空字符串
>>> "www.baidu.com..test".split(".", 1)
['www', 'baidu.com..test']
>>> "11 \t\n\r\v\f22".split()
['11', '22']
- str.join(iterable) -> str
  - 功能：以str作为分隔符，将一个可迭代对象中的各个元素拼接成一个字符串，返回该字符串。
  - 输入的可迭代对象中的所有元素必须都是str类型，否则会抛出异常。
  - 例：
>>> ",".join([1, 2, 3])
TypeError: sequence item 0: expected str instance, int found
>>> ",".join(["1", "2", "3"])
'1,2,3'
## 
## 
## 
 
格式化字符串
## str.format(*args: Any, **kwargs: Any) -> str
- 功能：以str为基础，生成一个经过格式化的字符串。
- 例：
>>> "{} {}!".format("Hello", "World")                # 字符串中的 {} 会被format()中的参数依次替换
'Hello World!'
>>> "{} {}!".format(123, [1, 2])                    # format()中的参数可以是任意类型
'123 [1, 2]!'
>>> "{{{} {}!}}".format("Hello", "World")            # 如果想在字符串中显示花括号，则要转义成 {{ }}
'{Hello World!}'
>>> "{0} {1}!".format("Hello", "World")            # 可以用 {n} 的格式指定要替换的元组参数
'Hello World!'
>>> "{0} {arg2}!".format("Hello", arg2="World")    # 可以用 {key} 的格式指定要替换的字典参数
'Hello World!'
- 在 {} 中可以加上 :n ，控制输出样式。
  - 控制输出位数。
>>> "{:4}".format(12)            # 至少输出4位，不足的位默认用空格填补
'  12'
>>> "{:04}".format(12)        # 至少输出4位，不足的位用0填补
'0012'
  - 关于对齐。
>>> "{:4}".format("12")        # 输入参数为int类型时默认右对齐，为str类型时默认左对齐
'12  '
>>> "{:<4}".format(12)        # 左对齐
'12  '
>>> "{:>4}".format("12")        # 右对齐
'  12'
>>> "{:^4}".format("12")        # 居中对齐
' 12 '
  - 关于正负号。
>>> "{:+4}".format(-12)        # 输出时总是加上正负号
' -12'
>>> "{:-4}".format(12)        # 输出负数时才加上负号
'  12'
  - 转换进制。
>>> "{:b}".format(12)            # 输出为二进制（输入必须为int型）
'1100'
>>> "{:#b}".format(12)        # 加上 # ，则会根据当前进制自动加上0b、0o、0x前缀
'0b1100'
>>> "{:o}".format(12)            # 输出为八进制（输入必须为int型）
'14'
>>> "{:x}".format(12)            # 输出为小写的十六进制（输入必须为int型）
'c'
>>> "{:X}".format(12)            # 输出为大写的十六进制（输入必须为int型）
'C'
  - 关于浮点数。
>>> "{:f}".format(12)                # 输出为float类型（小数点后默认保留6位）
'12.000000'
>>> "{:e}".format(12)                # 输出为科学计数法（小数点后默认保留6位）
'1.200000e+01'
>>> "{:.4f}".format(12.3456789)    # 小数点后最多输出4位（会进行四舍五入）
'12.3457'
>>> "{:.4}".format(12.3456789)    # 总共最多输出4位（会进行四舍五入）
'12.35'
## 其它格式化方法。
- str.ljust(width: int, fillchar: str=...) -> str
  - 功能：返回str的一个副本，将它左对齐，至少输出width位，不足的位用fillchar填补。
  - fillchar只能是单个字符，默认是空格。
  - 例：
>>> "Hi".ljust(4,"-")
'Hi--'
- str.rjust(width: int, fillchar: str=...) -> str
  - 功能：返回str的一个副本，将它右对齐，至少输出width位，不足的位用fillchar填补。
  - 例：
>>> "Hi".rjust(4,"-")
'--Hi'
- str.center(width: int, fillchar: str=...) -> str
  - 功能：返回str的一个副本，将它居中对齐，至少输出width位，不足的位用fillchar填补。
  - 例：
>>> "Hi".center(4,"-")
'-Hi-'
- str.lstrip(chars: str=...) -> str
  - 功能：返回str的一个副本，将它左侧的chars字符去掉。
  - chars是一个字符串，默认匹配所有空白字符（即string.whitespace）。
  - 例：
>>> '  Hi\n\r'.lstrip()
'Hi\n\r'
- str.rstrip(chars: str=...) -> str
  - 功能：返回str的一个副本，将它右侧的chars字符去掉。
  - 例：
>>> '  Hi\n\r'.rstrip()
'  Hi'
- str.strip(chars: str=...) -> str
  - 功能：返回str的一个副本，将它左右两侧的chars字符去掉。
  - 例：
>>> '  Hi\n\r'.strip()
'Hi'
>>> '--Hi--'.strip('--')
'Hi'
## 
## 
## 
 
字符串的转换
## 字符串的转换。
- 可以用int()把int格式的字符串转换成int型对象。
>>> int("123")
123
>>> int("3.14")
ValueError: invalid literal for int() with base 10: '3.14'
- 不能用int()把字符转换成数字，因为Python并不是按ASCII码存储字符。
>>> int("H")
ValueError: invalid literal for int() with base 10: 'H'
- 可以用float()把float格式的字符串转换成float型对象。
>>> float("3.14")
3.14
>>> float("314")
314.0
- 将list转换成str。
  - 直接用str()转换会留下两端的中括号。
"['Hello', 'World', '!']"
>>> str([1, 2, 3])
'[1, 2, 3]'
  - 如果list中的元素全是字符串，可以用join()合并成一个字符串。
>>> ''.join(["Hello", "World"])
'HelloWorld'
  - 如果list中的元素不全是字符串，就先将它们转换成字符串，再用join()合并。
>>> list1 = [1, 2, 3]
>>> list2 = []
>>> for i in list1:
...     list2.append(str(i))
... 
>>> ",".join(list2)
'1,2,3'
## 单个字符的转换。
- def chr(code: int) -> str
  - 功能：根据编码值生成一个Unicode字符。code的取值范围为区间 [0 , 0x110000)。
  - 例：
>>> chr(0)
'\x00'
>>> chr(65)
'A'
>>> chr(1000)
'Ϩ'
- def ord(char:[str, bytes]) -> int
  - 功能：返回一个Unicode字符的编码值。
  - 例：
>>> ord("A")
65
## 
## 
## 
 
序列
## 序列（sequence）：包括list、tuple、str、bytes。
- 序列支持索引和切片。
- 序列支持用加号 + 拼接。
>>> [1] + [2]
[1, 2]
>>> (1,) + (2,)
(1, 2)
>>> "Hello" + "World"
'HelloWorld'
>>> {1} + {2}                # 不支持
TypeError: unsupported operand type(s) for +: 'set' and 'set'
>>> {1:1} + {2:2}            # 不支持
TypeError: unsupported operand type(s) for +: 'dict' and 'dict'
- 序列支持用乘号 * 复制。
## 
## 
## 
 
索引
## 索引：用 [下标] 选取一个元素。
- [0]指向第一个元素，[n]指向第n+1个元素。
>>> list1 = [1, 2, 3]
>>> list1[0]
1
- 下标可以为负数，表示从右往左索引。[-n]指向从右往左的第n个元素。
>>> list1[-1]        # [-1]指向最右端的那个元素，相当于[len(list1)-1]
3
>>> list1[-0]        # [-1]相当于[0]
1
- 下标不能超过列表长度，否则会报错。即下标的取值范围为区间 [-len, len-1] 。
>>> list1[3]
IndexError: list index out of range
>>> list1[-4]
IndexError: list index out of range
## list类型的索引结果可以被修改。
- 修改索引结果会改变原list。
>>> list1 = [1, 2, 3]
>>> list1[0] = 0
>>> list1
[0, 2, 3]
>>> del list1[0]        # 可以用关键字del直接删除选中的元素
>>> list1
[2, 3]
- 如果把索引结果赋值给其它变量，则得到的是该元素的真实引用。
>>> list1 = [1, 2, 3]
>>> list2 = [list1]
>>> a = list2[0]
>>> a is list2[0]
True
>>> a[:] = []            # 可以通过该引用修改元素
>>> list2
[[]]
## 
## 
## 
 
切片
## 切片：用 [头下标:尾下标] 选取一部分元素，区间为 [头下标, 尾下标) 。
>>> list1 = [1, 2, 3]
>>> list1[0:2]
[1, 2]
>>> list1[0:-1]
[1, 2]
>>> list1[0:0]
[]
- 切片中的下标可以不填。
>>> list1[:3]        # 头下标的默认值为0
[1, 2, 3]
>>> list1[0:]        # 尾下标的默认值为 len(list1) 
[1, 2, 3]
>>> list1[:]
[1, 2, 3]
- 切片中的下标可以越界，不会报错。
>>> list1[0:3]        # 当切片长度过大时，只会截取有效元素
[1, 2, 3]
>>> list1[10:3]        # 当切片长度小于1时，截取结果为空列表
[]
>>> list1[0:-4]
[]
- 切片中可以设置第三个参数——步进值：表示每隔几个元素索引一次。
>>> print(str1[::2])
wrd                        # 提取索引为0、2、4的元素
>>> str1[::-1]            # 步长值为-1时可以翻转切片
'dlrow'
>>> list2 = [1, 2, 3, 4, 5]
>>> list2[::1]
[1, 2, 3, 4, 5]
>>> list2[::2]
[1, 3, 5]
>>> list2[::5]
[1]
  - 步进值为负数时是从右向左索引。
>>> list2[::-1]            # 翻转
[5, 4, 3, 2, 1]
>>> list2[::-2]
[5, 3, 1]
## list类型的切片结果可以被修改。
- 修改切片结果会改变原list。
>>> list2
>>> list1[0:2] = [1, 2, 3]    # 赋值时，元素个数不必一致
>>> list1
[1, 2, 3, 3]
>>> list1[0:2] = []            # 赋值为空时，相当于删除这部分元素
>>> list1
[3, 3]
>>> del list1[:]                # 可以用关键字del直接删除选中的元素
>>> list1
[]
- 如果把切片结果赋值给其它变量，则得到的是该片段的浅拷贝，相当于list.copy()。
>>> list1 = [1, 2, 3]
>>> list2 = list1[:]
>>> list1 is list2
False
>>> list1[:] = []
>>> list2
[1, 2, 3]
## 
## 
## 
 
set
## set：集合类型，无序地存储一些元素，并且会自动去重。
- 可以用 {value1, value2, ...} 的格式创建set。
>>> {1, 2, 3, 3}
{1, 2, 3}
  - set中的元素必须是不可变类型。
- set(iterable=...) -> set
  - 功能：创建一个set。
  - 例：
>>> set()                # 不输入参数时，是创建一个空set
set()
>>> set("Hello")            # 输入一个可迭代对象时，其中的各个元素会被拆开，并自动去重
{'l', 'e', 'o', 'H'}
  - 创建空集合时只能用set()，因为空的花括号 {} 表示空字典。
- set可以进行交集、并集、差集运算。
>>> a = {'YY', 'XY'}
>>> b = {'X', 'Y'}
>>> a & b                # 交集
set()
>>> a | b                # 并集
{'X', 'YY', 'XY', 'Y'}
>>> a - b                # 差集（属于集合a但不属于集合b的元素）
{'YY', 'XY'}
>>> a ^ b                # 并集-交集（两个集合不共同拥有的元素）
{'XY', 'YY', 'X', 'Y'}
## 
## 
## 
 
增查改删
## 增。
- set.add(x) -> None
  - 功能：增加一个元素到set中。
  - 每次增加元素时，set会判断该元素是否已存在，如何已存在则不加入。
  - 例：
>>> a = {1, 2, 3}
>>> a.add(3)            # 加入一个重复的元素
>>> a
{1, 2, 3}
>>> a.add(4)            # 加入一个不重复的元素
>>> a
{1, 2, 3, 4}
## 查。
- set.copy() -> set
  - 功能：返回set的一个浅拷贝。
  - 例：
>>> a = {1, 2, 3}
>>> a.copy()
{1, 2, 3}
## 改。
- set.update(iterable) -> None
  - 功能：更新一些元素到set中。
  - 如果输入的元素在原set中存在，则无影响；如果输入的元素在原set中不存在，则加入它们。
  - 例：
>>> a = {1, 2, 3}
>>> a.update({3, 4})
>>> a
{1, 2, 3, 4}
>>> a.update(3)
TypeError: 'int' object is not iterable
## 删。
- set.clear() -> None
  - 功能：清空set，删除所有元素。
  - 例：
>>> a = {1, 2, 3}
>>> a.clear()
>>> a
set()
- set.remove(object) -> None
  - 功能：删除list中的某个元素。如果不存在该元素则抛出异常。
  - 例：
>>> a = {1, 2, 3}
>>> a.remove(1)
>>> a.remove(1)
KeyError: 0
- set.discard(object) -> None
  - 功能：删除list中的某个元素。如果不存在该元素则无影响。
  - 例：
>>> a = {1, 2, 3}
>>> a.discard(1)
>>> a.discard(1)
>>> a
{2, 3}
- set.pop() -> object
  - 功能：删除list中的一个元素（随机一个），并返回它。
  - 如果set为空，则抛出异常。
  - 例：
>>> a = {1, 2, 3}
>>> a.pop()
1
>>> a.pop()
2
>>> a.pop()
3
>>> a.pop()
KeyError: 'pop from an empty set'
## 
## 
## 
 
dict
## dict：字典类型，存储一些键值对形式的元素。
- key必须是不可变类型、取值唯一。value可以是任何类型、可以重复。
  - dict采用哈希表的存储结构，根据key的哈希值确定value的存储地址，因此查询、插入的效率高。
- 可以用 {key:value...} 的格式创建dict。
>>> {"name": "Leo","age": 10}
{'name': 'Leo', 'age': 10}
- dict(iterable=..., **kwargs) -> dict
  - 功能：创建一个dict。
  - 例：
>>> dict()                                # 不输入参数时，是创建一个空dict
{}
>>> dict([("name", "Leo"), ("age", 10)])    # iterable要求是一个能产生二元组 (k, v) 的可迭代对象
{'name': 'Leo', 'age': 10}
>>> dict(name="Leo", age=10)                # 也可以输入关键字参数来创建字典
{'name': 'Leo', 'age': 10}
- 可以用 [key] 进行索引，获取字典中某个key对应的value。
>>> d = {"name": "Leo","age": 10}
>>> d["name"]
'Leo'
>>> d["age"] = 0        # 可通过索引修改value
  - 访问一个不存在的key时会抛出异常。
>>> d["time"]
KeyError: 'time'
  - 为了减少出错，应该先判断key是否存在，再进行访问。
>>> if "time" in d:        # 用in关键字判断key是否存在
...     print(d["time"])
...
>>> d.get("time")            # 用get()方法判断key是否存在
## 
## 
## 
 
查改删
## 查。
- dict.keys()
  - 功能：返回dict的所有key。
  - 例：
>>> d = {"name": "Leo","age": 10}
>>> d.keys()
dict_keys(['name', 'age'])            # 返回的是一个可迭代对象
>>> [k for k in d.keys()]
['name', 'age']
- dict.values()
  - 功能：返回dict的所有value。
  - 例：
>>> d.values()
dict_values(['Leo', 10])
- dict.items()
  - 功能：返回dict的所有键值对。
  - 例：
>>> d.items()
dict_items([('name', 'Leo'), ('age', 10)])
>>> for k,v in d.items():
...     print(k, v)
... 
name Leo
age 10
- dict.get(key, default=None) -> object
  - 功能：返回dict中某个key对应的value。如果不存在该key，则返回default参数。
  - 例：
>>> d = {"name": "Leo","age": 10}
>>> d.get("name")
'Leo'
>>> print(d.get("time"))
None
>>> d.get("time", "")
''
- dict.copy() -> dict
  - 功能：返回dict的一个浅拷贝。
## 改。
- dict.update(iterable=..., **kwargs) -> None
  - 功能：更新一些键值对到dict中。
  - 如果输入的键值对在原dict中存在，则覆盖其value；如果输入的键值对在原dict中不存在，则加入它们。
  - 例：
>>> d = {"name": "Leo","age": 10}
>>> d.update({"name": "Leo","age": 10})    # 可以输入一个能产生二元组的可迭代对象进行update
>>> d
{'name': 'Leo', 'age': 10}
>>> d.update(age=0)                        # 也可以输入关键字参数进行update
>>> d
{'name': 'Leo', 'age': 0}
## 删。
- dict.clear() -> None
  - 功能：清空dict，删除所有元素。
- dict.pop(key, default) -> object
  - 功能：删除dict中某个key对应的键值对，返回其value。
  - 如果不存在该key，且没有输入default参数，则抛出异常。
  - 如果不存在该key，但输入了default参数，则返回default作为value。
  - 例：
>>> d = {"name": "Leo","age": 10}
>>> d.pop("name")
'Leo'
>>> d
{'age': 10}
>>> d.pop("name")
KeyError: 'name'
>>> print(d.pop("name", None))
None
- dict.popitem() -> tuple(k, v)
  - 功能：删除dict中的一个键值对（排在最后的那个），并作为二元元组返回。
  - 如果dict为空，则抛出异常。
  - 例：
>>> d = {"name": "Leo","age": 10}
>>> d.popitem()
('age', 10)
>>> d.popitem()
('name', 'Leo')
>>> d.popitem()
KeyError: 'popitem(): dictionary is empty'
## 
## 
## 
 
函数
## 函数。
- Python中定义函数的一般格式为：
def function_name([arg1, arg2, ...]):
statement_block
return
- Python的return语句可以返回多个值，它们以元组的形式返回。
>>> def fun1(a, b):
...     return a, b
... 
>>> fun1(1, 2)
(1, 2)

- 如果函数中不包含return语句，则会在函数执行完毕之后返回None。
## Python是动态语言，大部分语句要等到被Python解释器执行时，才能发现是否有错误。除非是明显的语法错误。
- 有些语句即使被成功执行了，也可能仍然有错误。
- 比如如果函数内使用了一些标识符，当Python解释器执行到该函数时，才能发现这些标识符是否有效。
>>> def fun1():
...     print(os.name)
... 
>>> fun1()
NameError: name 'os' is not defined
- 比如如果函数内使用了一个外部变量，当Python解释器执行到该函数时，才会尝试读取该变量的值。如下：
>>> funs = [lambda x: x + i for i in range(5)]
>>> funs[0](0)
4
  - 将外部变量作为形参的默认值传入函数，就会在定义函数时就将它的值保存到函数的__defaults__属性中。
>>> funs = [lambda x, i=i: x + i for i in range(5)]
>>> funs[0](0)
0
## 高阶函数：可以接受函数作为输入参数，或者以函数作为返回值。
## 嵌套函数：在一个函数中定义另一个函数。
## 匿名函数：用关键字lambda定义，只有一个形参列表和一行表达式（相当于return语句），没有函数名。
- 一般格式为：
lambda [arg1,arg2,...]:expression
  - lambda函数也属于函数，有独立的作用域、命名空间。
  - lambda函数应该用于只用一次、不需要记录函数名的紧凑情况。
- 例：
>>> fun1 = lambda x,y : x+y
>>> fun1(1, 2)
3
>>> fun1 = lambda x,y : x=y            # 匿名函数的表达式中不可以进行赋值
SyntaxError: can't assign to lambda
>>> fun1 = lambda x,y=0 : x+y            # 匿名函数也可以使用关键字参数、设置默认值
>>> fun1(x=1,y=2)
3
- Python的lambda函数类似于C语言的宏定义、C++的内联函数。
  - C语言中可以通过宏定义实现一些简单的函数功能，C++中把宏定义升级成了内联函数（用关键字inline声明）。
  - 使用内联函数会建议编译器把调用该函数的语句换成实际的函数体（如果函数体并不小，编译器可能并不会这么做）。这样做可以减少程序调用函数的开销（要保存现场、把变量入栈、跳转执行、跳转回来、恢复现场）。不过会导致编译出来的可执行文件体积变大。
## 闭包函数（closure）：一种特殊的嵌套函数。
- 如下，在一个函数内嵌套定义另一个函数，调用外部函数时会返回内部函数。如果内部函数能读取外部函数定义的局部变量，则称为闭包函数。
def fun1():
    x = 1
    def fun2():
        print(x)
return fun2
  - 该变量称为自由变量：可以在作用域之外的位置被访问。
  - 闭包函数只能读取自由变量，不能修改自由变量。
- Python中使用装饰器时，就会把被装饰的函数变成闭包函数。

闭包就是可以使用参数的代码片段，在闭包内创建的变量在闭包被调用的范围内同样可以被引用。
## 
## 
## 
 
函数参数
## 在C语言中，调用函数时如果实参列表与形参列表不一致就会报错。但是在Python中，函数的参数比较灵活。
## 实参的类型：
- positional argument    ：key型，必须与形参的顺序一致。
- keyword argument        ：key=value型，不必与形参的顺序一致，解释器会根据参数名来赋值。
>>> def fun1(x, y):
...     print(x, y)
...
>>> fun1(y=2, x=1)
1 2
>>> fun1(x=1, 2)            # 在实参列表中，key=value型参数必须放在key型参数之后
SyntaxError: positional argument follows keyword argument
## 形参的类型。
- 位置参数：key型，没有默认值，调用函数时必须传入相应的实参。
- 关键字参数：key=value型，有默认值，如果调用函数时没有传入相应的实参，则使用该形参的默认值。
>>> def fun2(x, y=2):
...     print(x, y)
...
>>> fun2(1)
1 2
>>> def fun2(x=1, y):
...     print(x,y)
... 
SyntaxError: non-default argument follows default argument
- 元组参数：用一个星号 * 声明，只能声明一个。调用函数时会将额外传入的key型实参打包成一个元组。
>>> def fun3(x, y, *args):
...     print(x, y, args)
...
>>> fun3(1, 2, 3, 4)
1 2 (3, 4)
>>> fun3(1,2)            # 如果没有传入额外的实参，元组参数就为空元组
1 2 ()
- 字典参数：用两个星号 ** 声明，只能声明一个。调用函数时会将额外传入的key=value型实参打包成一个元组。
>>> def fun4(x, y, **kwargs):
...     print(x, y, kwargs)
...     if "name" in kwargs:
...         print(kwargs["name"])
...
>>> fun4(1, 2, 3, 4)
TypeError: fun4() takes 2 positional arguments but 4 were given
>>> fun4(1, 2, a=3, b=4)
1 2 {'a': 3, 'b': 4}
- 四种参数的排列顺序应该是：Key型、key=value型、元组参数、字典参数。
## 使用元组参数和字典参数的技巧。
- 万能参数：把函数的形参定义成一个元组参数加一个字典参数，就可以给函数传入任何实参而不会报错。
>>> def fun5(*args, **kwargs):
...     print(args, kwargs)
... 
>>> fun5(1, 2, a=3, b=4)
(1, 2) {'a': 3, 'b': 4}
- 在实参列表中，可以用 * 把一个序列拆散成多个key型参数，可以用  ** 把一个字典拆散成多个key=value型参数。
>>> fun5(*(1, 2), **{'a':3, 'b':4})
(1, 2) {'a': 3, 'b': 4}
>>> print(*"Hello")
H e l l o
  - 如果序列或字典为空，拆散之后就没有得到参数。
>>> print(())
()
>>> print(*())


迭代拆包运算符 * 、字典拆包运算符 ** 

## 给函数传参时，要小心实参被函数改变。
- 如果实参是不可变的数据类型，无论如何也不会被改变。
- 如果实参是可变的数据类型，传入函数就可能会被改变（像C语言的指针函数），安全的做法是将实参所指的对象做一个副本，再传入函数。如下：
>>> def fun1(x, y):        # 调用函数时，解释器会创建形参变量，用实参赋值，使它们指向相同的对象
...     x[:] = y            # 修改形参时，是修改实参所指的对象
...     x = [0, 0]        # 对形参赋值时，是改变它所指的对象，不再影响实参所指的对象
...
>>> x = [1, 2]
>>> y = [3, 4]
>>> fun1(x, y)
>>> print(x, y)
[3, 4] [3, 4]
## 
## 
## 
 
装饰器
## 装饰函数：体现装饰模式的函数，用于向某个函数附加功能而不改变其原本内容。
- 例如，已存在函数fun1()，如下：
>>> def fun1(x, y):
...     print(x, y)
...
>>> fun1(1, 2)
1 2
- 通过另一个函数来间接地调用fun1()，就可以附加一些功能。如下：
>>> def wrapper(func, *args, **kwargs):
...     print("[DEBUG]: enter {}()".format(func.__name__))
...     return func(*args, **kwargs)
...
>>> wrapper(fun1, 1, 2)        # 调用wrapper()，输入函数名和参数，间接地执行fun1(1, 2)
[DEBUG]: enter fun1()
1 2
- 也可写作以下格式：
>>> def debug(func):
...     def wrapper(*args, **kwargs):
...         print("[DEBUG]: enter {}()".format(func.__name__))
...         return func(*args, **kwargs)
...     return wrapper
...
>>> debug(fun1)(1,2)            # debug(fun1)会返回装饰函数的函数名wrapper
[DEBUG]: enter fun1()
1 2
## Python提供了装饰器（Decorator）语法：可以在定义函数时用 "@装饰函数名" 的格式方便地添加装饰函数。
- 例：
>>> @debug                    # 指定装饰器为debug()，函数fun1()被调用时会自动被debug()装饰
... def fun1(x, y):
...     print(x, y)
...
>>> fun1(1,2)                # 相当于debug(fun1)(1,2)
[DEBUG]: enter fun1()
1 2
- 加上装饰器之后，原函数的函数名会指向装饰函数的函数名。如下：
>>> fun1
<function debug.<locals>.wrapper at 0x000001A0BF1B8B70>
>>> fun1.__name__
'wrapper'
  - 可以用@wraps(func)装饰wrapper()函数，从而拷贝func的__name__、__doc__等元属性。
- 如果想给装饰器本身传入参数，还要在定义装饰器时外加一层函数。如下：
>>> from functools import wraps
>>> def debug(level=None):
...     print("Decorator was set.")    # 装饰器的外层函数中的语句会在用 @ 指定装饰器时执行
...     def decorator(func):
...         @wraps(func)
...         def wrapper(*args, **kwargs):
...             print("[DEBUG]: enter {}()".format(func.__name__))
...             return func(*args, **kwargs)
...         return wrapper
...     return decorator
...
>>> @debug(level=3)    # 该句会先执行函数debug(level=3)，然后用它的返回值作为装饰器，即@__decorator
... def fun1(x, y):
...     print(x, y)
...
Decorator was set.
>>> fun1
<function fun1 at 0x000001A0BF1E3950>
>>> fun1.__name__
'fun1'
>>> fun1(1, 2)
[DEBUG]: enter fun1()
1 2
## 修改对象的装饰器：需要输入一个obj参数，返回obj参数。
- 这种装饰器用于修改对象的成员，可以作用于函数、类。
- 例：
def wrapper(obj):
    obj.name = "test"
    return obj

@wrapper                # 相当于fun1 = wrapper(fun1)
def fun1():
    pass

@wrapper                # 相当于Test = warp(Test)
class Test():
    pass

## 作用于类方法的装饰器：需要在外层输入一个obj参数，在内层多输入一个self参数。
- 例：
def outer(obj):
    def inner(self, *args, **kwargs):
        print("Hello")
    return inner

class Test:
    @outer
    def fun1(self):
        pass

>>> Test().fun1()
Hello
## 用类实现的装饰器：需要定义类的__call__()方法。
## 
## 
## 
 
类
## 使用class关键字可以定义类。
- 例如：
>>> class Test:                        # 如果没有继承就不需要在类名后加括号
...     def __init__(self, x, y):
...         self.a = x    
...         self.b = y
...         print(self)
...         print("init...")
...     def fun1(self):
...         print(self.a, self.b)        # 通过指针self调用类实例的成员
...
>>> t1 = Test(1, 2)        # 创建Test类的实例，并将实例对象的引用赋值给变量t1
<__main__.Test object at 0x00AC5970>
init...
>>> t1                    # 变量t1和self都指向实例对象
<__main__.Test object at 0x00AC5970>
>>> t1.a                    # 访问对象的实例变量
1
>>> t1.fun1()            # 调用对象的方法
1 2
  - __init__()是类的构造方法，如果不写解释器也会提供一个默认的。
- 可以用类名给变量赋值，让这个变量可以当做类名使用。
>>> Test
<class '__main__.Test'>
>>> a = Test
>>> a
<class '__main__.Test'>
>>> b = a()
>>> b
<__main__.Test object at 0x010C0DF0>
## 
## 
## 
 
类的成员
## 类中定义的变量称为类的“属性”，类中定义的函数称为类的“方法”，它们都属于类的“成员”。
- 属性的分类：
  - 实例变量
  - 类变量
- 方法的分类：
  - 实例方法
  - 类方法
  - 静态方法
## 类成员的访问控制。
- public        ：公有成员，可以被任何访问。
  - 按普通方式定义。
- protected    ：受保护成员，只能在当前类中或子类中访问，不能通过import语句导入。
  - 定义时以一个下划线 _ 开头。
- private        ：私有成员，只能在当前类中访问，对子类或实例对象不可见。
  - 定义时以两个下划线 __ 开头。
- 例：
>>> class Test:
...     a = 0
...     _b = 0
...     __c = 0
...
>>> Test.a
0
>>> Test._b
0
>>> Test.__c
AttributeError: 'Test' object has no attribute '__c'
>>> Test().__c
AttributeError: 'Test' object has no attribute '__c'
## 
## 
## 
 
类的属性
## 类的属性。
- 实例变量：每个实例对象各有一份，互不影响。
  - 定义类时，只能在方法内访问（此时要通过self指针访问）。
  - 定义类之后，只能作为实例对象的成员引用。
>>> class Test:
...     def __init__(self, n):
...         self.num = n
...     def getNum(self):
...         return self.num
... 
>>> Test.num
AttributeError: type object 'Test' has no attribute 'num'
>>> Test(1).num
1
>>> Test(1).getNum()
1
- 类变量：所有实例对象共用一份。
  - 定义类时，既可以在方法内访问（此时可以通过cls指针或self指针访问），也可以在方法外访问。
  - 定义类之后，既可以通过 "对象名.成员名" 的方式访问，也可以通过 "类名.成员名" 的方式访问。
>>> class Test:
...     num = 0                # 在方法外访问类变量
...     def __new__(cls):
...         cls.num = 1        # 在方法内通过cls指针访问类变量
...         return super().__new__(cls)
...     def getNum(self):
...         return self.num    # 在方法内通过self指针访问类变量
...     def setNum(self, n):
...         self.num = n
... 
>>> Test.num
0
>>> Test().num
1
>>> Test.num                    # 类变量被实例改变了
1
>>> Test().getNum()
1
  - 如果类变量与实例变量重名，则通过self指针访问时优先访问实例变量。
>>> t = Test()
>>> t.setNum(2)
>>> t.num            # 此时访问的是实例变量
2
>>> Test.num            # 类变量没有被改变
1
## Python支持给一个已定义的类加上成员。
>>> t.id
AttributeError: 'Test' object has no attribute 'id'
>>> t.id = 1
>>> t.id
1
>>> Test.ID
AttributeError: type object 'Test' has no attribute ID
>>> Test.ID = 1
>>> Test.ID
1
>>> t.ID            # 加上的类变量可以正常被实例对象访问
1
- 因为这个特性，给一个类或对象的成员进行赋值时，即使该成员不存在，也可以赋值成功。如下：
>>> Test.__id
AttributeError: type object 'Test' has no attribute '__id'
>>> Test.__id = 1            # 私有成员显然不能在类外被访问，但这里还是赋值成功了
>>> Test.__id
1
## 
## 
## 
 
类的方法
## 类的方法。
- 实例方法：第一个参数必须是self。
  - 调用实例对象的普通方法时，会自动传入该对象的引用作为第一个参数。一般把该参数命名为self。
  - 普通方法一般通过 "对象名.方法名" 的方式访问，也可以通过 "类名.方法名" 的方式访问，此时需要传入第一个参数self。如下：
>>> Test.getNum()
TypeError: getNum() missing 1 required positional argument: 'self'
>>> Test.getNum(Test())
1
- 类方法：用装饰器 @classmethod 定义，第一个参数必须是cls。
  - 调用类方法时，会自动传入该类名的引用作为第一个参数。一般把该参数命名为cls。
  - 类方法既可以通过 "对象名.成员名" 的方式访问，也可以通过 "类名.成员名" 的方式访问。如下：
>>> class Test:
...     num = 0
...     @classmethod
...     def class_getNum(cls):        # 定义类方法
...         return cls.num
...     @staticmethod                # 定义静态方法
...     def static_getNum():
...         return Test.class_getNum()
... 
>>> Test.class_getNum()
0
>>> Test().class_getNum()
0
- 静态方法：用装饰器 @staticmethod定义，不必传入self或cls参数，相当于一个独立的函数。
  - 静态方法既可以通过 "对象名.成员名" 的方式访问，也可以通过 "类名.成员名" 的方式访问。如下：
>>> Test.static_getNum()
0
>>> Test().static_getNum()
0
  - 通过 "对象名.方法名" 的方式访问时，装饰器会把自动传入的参数self拦截下来，因此没有装饰器就会出错。如下：
>>> class Test:
...     def static_getNum():
...         return 0
... 
>>> Test.static_getNum()
0
>>> Test().static_getNum()
TypeError: static_getNum() takes 0 positional arguments but 1 was given
## @property：将一个方法名转换成属性名（这样就能在读取属性值时执行某些动作）。
>>> class Test:
...     @property
...     def sum(self):
...         return 0
...
>>> Test().sum
0
>>> Test().sum()
TypeError: 'int' object is not callable
## 
## 
## 
 
类的内置方法
## 类的内置方法：以两个下划线 __ 开头、两个下划线 __ 结尾，可以被重载。
- 一些内置方法是每个类都默认自带的，比如__new__()、__init__()、__str__()、__repr__()。
## 关于创建对象的内置方法。
- __new__()    ：实例化类时被自动调用，用于创建对象。
  - 它是一个静态方法，输入的第一个参数是cls，返回新对象的引用即self指针。
  - 让__new__()总是返回同一个对象的引用，就可以实现单例模式。如下：
>>> class Test:
...     def __new__(cls):
...         if not hasattr(cls, 'instance'):
...             cls.instance = super().__new__(cls)
...         return cls.instance
... 
>>> Test()
<__main__.Test object at 0x7f96450d45c0>
>>> Test()
<__main__.Test object at 0x7f96450d45c0>
- __init__()    ：构造函数，对象被创建之后被自动调用，用于初始化对象。
  - 当子类没有重载构造函数时，Python解释器会自动调用父类的__init__()方法。如果子类重载了构造函数，就需要主动调用父类的__init__()方法。如下：
class B(A, C):
    def __init__(self):
        super().__init__()
- __del__()    ：析构函数，用于销毁对象。当对象的被引用数减到0时被自动调用（不能用del语句主动调用）。
  - 一般情况下不用重构__del__()方法。
- 例：
>>> class Test:
...     def __new__(cls, x):
...         print("cls: ", cls)
...         print("Object created successfully.")
...         return super().__new__(cls)            # 通常是调用父类的__new__()方法来创建对象
...     def __init__(self, x, y):
...         self.a = x
...         self.__b = y
...         print("self: ", self)
...         print("initialization completed.")
...     def __del__(self):
...         print("Object was deleted.")
...
>>> t1 = Test(1)
cls:  <class '__main__.Test'>
Object created successfully.
TypeError: __init__() missing 1 required positional argument: 'y'
>>> t1=Test(1, 2)
TypeError: __new__() takes 2 positional arguments but 3 were given
  - 执行Test()时会实例化该类，先调用__new__()方法创建对象，再调用__init__()方法初始化对象。
  - 必须让__new__()与__init__()的形参列表相同，或者使用不定长参数。例如，将上例中的def __new__(cls, x)改为def __new__(cls, *args, **kwargs)之后，便可成功创建一个对象。
## 使对象能够实现一些基本功能的内置方法。
- __str__()    ：当对象被转换成字符串时被自动调用。
- __repr__()    ：当对象在终端上打印时被自动调用。
- __len__()    ：当对象被len()访问时被自动调用。
- __getitem__()        ：可以通过索引获得对象中的某项元素的值。
- __setitem__()        ：可以通过索引对对象中的某项元素赋值。
- __iter__()和__next__()：使对象可以作为迭代器使用。
## 使对象能进行加减乘除运算的内置方法。
- __add__()        ：左加，当对象出现在加号 + 的左边时被自动调用。
- __radd__()        ：右加，当对象出现在加号 + 的右边时被自动调用。
- __sub__()        ：左减。
- __rsub__()        ：右减。
- __mul__()        ：左乘。
- __rmul__()        ：右乘。
- __truediv__()    ：左除。
- __rtruediv__()    ：右除。
- 例如：
>>> class Test:
...     def __str__(self):
...         return "__str__"
...     def __repr__(self):
...         return "__repr__"
...     def __sub__(self, other):
...         return 0 - other
...     def __rsub__(self, other):
...         return other - 0
...
>>> t1 = Test()
>>> t1
__repr__
>>> str(t1)
'__str__'
>>> print(t1)        # print()在显示对象时会先将对象转换成字符串
__str__
>>> t1 - 1
-1
>>> Test() - Test()
0
## 实现了__enter__() 和 __exit__()方法的对象支持用with关键字进行上下文管理。
- 例：
class Test:
    def __init__(self, filename, mode='r'):
        self.filename = filename
        self.mode = mode
    def __enter__(self):
        self.f = open(self.filename, self.mode)
        return self.f
    def __exit__(self, *args):   # 抛出异常时会传入异常名、异常内容、traceback对象
        self.f.close()

with Test("1.txt") as t:
    t.read()
  - 执行with Test("1.txt")时，Python解释器会先创建对象f=Test("1.txt")，然后调用f.__enter__()。当执行完with语句块或者抛出异常时，就调用f.__exit__()。
## 其它内置方法。
- __getattr__()    ：当用户访问对象中没有定义的属性时，就会到__getattr__()中寻找，仍然找不到就会报错。
  - 例：
def __getattr__(self, attr):
    if attr == "age":
        return 18
else
    return None
- __call__()        ：使对象的标识符可以像函数名一样被调用。
  - 例：
>>> t1 = Test()
>>> t1()
TypeError: 'Test' object is not callable    # 如果重载了__call__()，此时就会调用__call__()
- __sizeof__()        ：返回对象占用的内存（单位为bytes）。
  - 例：
>>> "".__sizeof__()
51
## 
## 
## 
 
对象的内置属性
## 函数的内置属性。
- __name__：一个str，存储函数名。
  - 例：
>>> f = print
>>> f.__name__
'print'
- __doc__：一个str，存储函数的说明文档。
  - 例：
>>> print.__doc__
"print(value, ..., sep=' ', end='\\n', file=sys.stdout, flush=False)\n\n
- __closure__：对于非闭包函数，它是None。对于闭包函数，它是一个tuple，记录函数引用的所有自由变量。
  - 例：
>>> def fun1():
...     x = 1
...     def fun2():
...         print(x)
...     return fun2
...
>>> f = fun1()
>>> f.__closure__
(<cell at 0x0000020398E80828: int object at 0x00007FF8C8196290>,)
>>> f.__closure__[0].cell_contents
1
- __defaults__：一个tuple，存储函数的默认值形参。
  - 如果函数形参的默认值为可变类型，就可能被修改。因此，应该尽量使用不可变类型，或者检查函数中所有用到它的语句是否修改了它。
  - 例：
>>> def fun2(x=[], y=[]):
...     print(x, y)        # 没有传入实参时，解释器会用__defaults__[0]、__ddefaults__[1]给形参赋值
...     y.append(0)
...     print(fun2.__defaults__)
...
>>> fun2()
[] []
([], [0])            # 对__defaults__的修改会一直保留，直到解释器关闭
>>> fun2()
[] [0]
([], [0, 0])
- __annotations__：一个dict，存储有注释的形参。
  - 例：
>>> def fun1(a, b: "字符串或None", c: int = 0)-> int:    # 定义函数时，可以用冒号 : 给形参加上注释
...     pass
...
>>> fun1.__annotations__
{'b': '字符串或None', 'c': <class 'int'>, 'return': <class 'int'>}

__class__：指向对象所属的类，返回值与type()一样。
self.__class__相当于cls

>>> a = 1
>>> a.__class__
<class 'int'>
>>> int.__class__
<class 'type'>


## 实例方法的私有属性。
>>> class Test(int):
...     def fun1(self):
...         pass
...
- __self__：指向类的实例。实例的普通方法、类方法具有该属性。
  - 例：
>>> Test().fun1.__self__
0
>>> Test(1).fun2.__self__            # 类方法的__self__属性指向类名
<class '__main__.Test'>
>>> Test(1).fun3.__self__            # 静态方法实际上是个函数，没有__self__属性
AttributeError: 'function' object has no attribute '__self__'
- __func__：指向该方法绑定的函数名。非built-in类的实例的普通方法、类方法具有该属性。
  - 普通方法、类方法本身会绑定到一个静态函数，各个实例对象都是调用该静态函数。
  - 例：
>>> Test(1).fun1
<bound method Test.fun1 of 1>            # 该方法绑定到Test.fun1函数
>>> Test(1).fun1.__func__
<function Test.fun1 at 0x000001AD6E0CA048>
>>> Test(1).fun1.__func__ is Test(2).fun1.__func__
True
>>> Test(1).fun2
<bound method Test.fun2 of <class '__main__.Test'>>
>>> Test(1).fun3                        # 静态方法本身不会绑定
<function Test.fun3 at 0x000001AD6E0CA2F0>
## 
## 
## 
 
类的继承
## 在定义类名时，在类名后加上括号并填入某个类名，就可以让当前类继承某个类的成员。
- Python3中，所有类都隐式地继承object类。
- 例：
>>> class Person:
...     num = 0
...
>>> class Man(Person):        # 创建一个继承类Person的类Man
...     pass
...
  - 这里子类Man继承了父类Person的类变量num，如果子类Man一直不修改num的值，它就会一直引用父类的num，改变Person.num就会改变Man.num。
>>> print(Person.num, Man.num)
0 0
>>> Person.num = 1
>>> print(Person.num, Man.num)
1 1
  - 当子类Man修改了num的值之后，它就与父类的num值在当前位置分叉，从此Person.num与Man.num互不影响。
>>> Man.num = 10
>>> print(Person.num, Man.num)
1 10
>>> Person.num = 20
>>> print(Person.num, Man.num)
20 10
- 类的定义语句执行完之后，该类的定义就确定了。即使重新定义父类，它依然继承的是之前的父类。
>>> class Person:
...     num = 0
...     name = ""
...
>>> Man.name                        # 子类不会继承新父类的成员
AttributeError: type object 'Man' has no attribute 'name'
## 

C++等语言中支持定义多个名称相同、形参列表不同的方法，实现更丰富的多态性。如下，当调用 Test.get(x=1) 时，根据输入的实参与哪个形参列表匹配，从而判断调用哪个方法。
但在Python中不支持这样的多态性，只有同名的方法中只有最后一个定义的方法会生效。

class Test:

    def get(self):
        pass

    def get(self, x):
        pass

    def get(self, x, y):
        pass

## 
 
多继承
## Python的类支持多继承。如下：
>>> class A:
...     def __init__(self, *args):
...         print("A start")
...         print("A end")
...
>>> class B(A):
...     def __init__(self, *args):
...         print("  B start")
...         super().__init__(*args)    # 调用父类的构造方法
...         print("  B end")
...
>>> b = B()
  B start
A start
A end
  B end
- 使用A.__init__()的格式也可调用父类的方法，但是在多继承的情况下可能会重复继承，应该使用super()获取父类，避免重复继承。
- 使用多继承时，几个父类之间不能有继承关系，否则会重复继承某个类。
>>> class C(A, B):
...     def __init__(self, *args):
...         super().__init__(*args)
...
TypeError: Cannot create a consistent method resolution
order (MRO) for bases A, B
- 使用多继承时，几个父类可以继承自相同的超父类。这样并不会重复继承。
>>> class C(A):
...     def __init__(self, *args):
...         print("    C start")
...         super().__init__(*args)
...         print("    C end")
...
>>> class D(B, C):
...     def __init__(self, *args):
...         print("      D start")
...         super().__init__(*args)
...         print("      D end")
...
>>> d = D()
      D start
  B start
    C start
A start
A end
    C end
  B end
      D end
- 定义一个类时，Python会自动决定其方法继承顺序（Method Resolution Order, MRO）。
>>> D.mro()            # 获取该类的MRO列表（子类在前，父类在后）
[<class '__main__.D'>, <class '__main__.B'>, <class '__main__.C'>, <class '__main__.A'>, <class 'object'>]
  - 如果子类调用父类的成员时没有指定路径，解释器会在各个父类中查找该成员。查找顺序按照C3算法，有些类似于广度优先：先从左往右在各个父类中查找，没有找到再进入父类的父类中查找。

## 
## 
## 
 
元类
## 一般的类实际上是type类的实例。当Python解释器执行到class定义语句时，实际上是调用type()创建该类。
- 在代码中使用type()可以动态创建类，使程序更加灵活。
## class type(name: str, bases: Tuple[type, ...], dict: Dict[str, Any]) -> a new type
- 功能：创建一个类。（实际上是type类的实例）
- name参数是类名，bases参数是一个包含所有父类的元组，dict参数是一个包含所有方法名及其绑定的函数的字典。
- 例：
>>> Test = type("Test", (int,), {"fun1": fun1})
>>> Test
<class '__main__.Test'>
>>> Test().fun1()
hello
  - 相当于以下定义：
class Test(int):
    def fun1(self):
        print("hello")
## 元类：继承自type类，可用于创建其它类。
- 使用元类可以方便地初始化其它类，比setattr()更方便。
  - 创建一个类时，Python解释器会优先用它或它父类的元类来创建它，如果没有元类则用type()来创建它。
- 例：
>>> class Mymeta(type):
...     def  __new__(cls, name, bases, attrs):
...         attrs["fun1"] = lambda self: print("hello")
...         return super().__new__(cls, name, bases, attrs)
... 
>>> class Test(metaclass=Mymeta):
...     pass
... 
>>> Test().fun1()
hello
## 
## 
## 
 
迭代器
## 迭代：遍历某个对象中的所有元素。
- 不同的容器实现了迭代器接口之后，就可以使用相同的API进行遍历。
## 可迭代对象（iterable）：具有__iter__()方法。可以被for语句遍历，不能被next()遍历。
- __iter__()：返回一个迭代器。
  - for语句在遍历可迭代对象时，就是先调用对象的__iter__()方法，获得迭代器，再调用next()方法进行遍历。
  - 例：
>>> list1 = [1, 2, 3]
>>> list1.__iter__()
<list_iterator object at 0x7fa01109d048>
>>> next(list1.__iter__())
1
## 迭代器（iterator）：具有__iter__()、__next__()方法。可以被for语句、next()遍历。
- Python中的迭代器属于单向只读迭代器：只能向前遍历，不能后退。
  - 大部分迭代器遍历完所有元素之后就停止迭代，也可以创建无限循环的迭代器。
  - 迭代器只能通过迭代获取其中的元素，不能进行索引。
- __next__()：返回迭代器中的下一个元素，如果没有下一个元素则抛出异常StopIteration。
  - 例：
>> class Number:
...     def __init__(self):
...         self.a = 0
...     def __iter__(self):
...         return self
...     def __next__(self):
...         if self.a < 10:             # 最多迭代10次
...             self.a += 1
...             return self.a
...         else:
...             raise StopIteration
... 
>>> n = Number()
>>> next(n)
1
>>> next(n)
2
## 相关函数。
- def iter(iterable) -> iterator
  - 功能：将一个可迭代对象转换成迭代器。实际上是调用对象的__iter__()方法。
  - 例：
>>> iter("Hello")
<iterator object at 0x7f19cd6e6810>
>>> list(iter("Hello"))
['H', 'e', 'l', 'l', 'o']
- def next(iterator, default=...) -> object
  - 功能：获取迭代器中的下一个元素。如果不存在则报错，或者返回default参数。
  - 实际上是调用对象的__next__()方法。
  - 例：
>>> i = iter("Hello")
>>> next(i)
'H'
>>> next(i)
'e'
## 
## 
## 
 
生成器
## 生成器（generator）：Python特有的一种迭代器。
- 使用yield关键字给出函数的返回值时，函数会返回一个生成器。
  - yield的用法与return类似。函数执行到yield语句时会中断函数并返回一个生成器，当迭代生成器的下一个元素时，会让函数从中断处继续执行。
  - 优点：可以中断函数，让函数在需要时才继续执行，有利于节省CPU和内存、控制函数运行。
  - 例：
>>> def fun1():
...     print("step 1")
...     yield 1
...     print("step 2")
...     yield 1, 2
...     print("step 3")
... 
>>> g = fun1()
>>> g
<generator object fun1 at 0x7fa011114678>
>>> next(g)
step 1
1
>>> next(g)
step 2
(1, 2)
>>> next(g)
step 3
StopIteration
- 使用生成式的语法也可以创建生成器。
>>> g = (i for i in range(100000))        # 不会一次创建所有元素，而是每次迭代后才创建下一个元素
>>> g
<generator object <genexpr> at 0x7fa011114678>
>>> next(g)
0
>>> next(g)
1
## 
## 
## 
 
异常处理
## Python程序的错误分为两种。
- SyntaxError：语法错误，在编译时报出错误。
- exception：异常，在运行时被抛出。
  - 除了语法错误，其它的都算异常。
  - 变量未定义、数据类型不符合要求等问题在运行时才能发现，不属于语法错误。
## 使用try-except语句可以捕捉异常。
- 其语法为：首先执行try语句块，如果有异常抛出，则立即执行异常名与其匹配的except语句块。如果没有与其匹配的except，该异常就会被抛出。
- 例：
try:
x = int(input("Please enter a number: "))
except Exception as e:                # 捕捉一个Exception类的异常并实例化成对象e
print(str(e))                    # 显示用str()提取的简要异常信息
except (RuntimeError, TypeError):        # 一个except可以捕捉多种异常
print("RuntimeError / TypeError")
except :                                # 最后一个except可以不设异常名，从而匹配所有类型的异常
print("Unexpected error:", sys.exc_info()[0])
raise        # 将异常抛出
else:            # 可以在try-except语句后加上一个else语句，没有发生异常时就执行该语句块
pass
finally:            # 可以在try-except语句后加上一个finally语句，不管是否发生异常都会执行该语句块
pass            # 即使有return语句，也会在return之前先执行finally语句块
## 用关键字with可以实现try-finally的作用，保证在执行语句块时一定会执行某种操作。
- 如下，定义一个支持with操作的类，使用with时会调用类的__enter__()方法，当语句块执行结束或出现异常时会调用类的__exit__()方法。
- 例：
>>> class Test():
...     def __enter__(self):
...         return self
...     def __exit__(self, type, value, trace):
...         print("exit")
...
>>> with Test() as t:
...     print("inside")
...
inside
exit
## 抛出异常。
- 使用关键字raise可以抛出已捕捉的异常。
- 使用“raise X”的格式可以主动抛出一个异常。X可以是一个异常类或者异常的实例。
>>> raise NameError
NameError
>>> raise NameError('test...')
NameError: test...
- 使用关键字assert可以写一个断言，当表达式结果为假时则抛出AssertionError异常。
>>> assert 1 == 0
AssertionError
>>> assert 1 == 0, "not equal"        # 可以给该异常加上描述信息
AssertionError: not equal
## BaseException：所有异常类的基类。
- SystemExit
- KeyboardInterrupt
- GeneratorExit
- Exception：Common base class for all non-exit exceptions.
  - EOFError        ：Read beyond end of file
  - ImportError    ：Import can't find module, or can't find name in module.
  - NameError    ：Name not found globally.
  - OSError        ：Base class for I/O related errors.
  - KeyError        ：字典中没有该key。
  - AttributeError：对象没有该属性。
  - RuntimeError    ：Unspecified run-time error.
  - SystemError    ：Python解释器的内部错误。
  - TypeError    ：参数的数据类型错误。
  - ValueError    ：参数的值错误（数据类型正确）。
  - Warning        ：Base class for warning categories.
## 下例是自定义一个异常类：
>>> class MyExcept(Exception):
...     def __init__(self, msg=''):
...         self.message = msg
...     def __str__(self):
...         return self.message
... 
>>> raise MyExcept
__main__.MyExcept
>>> raise MyExcept('test...')
__main__.MyExcept: test...
## 
## 
## 
 
模块和包
## .py脚本文件不但可以被Python解释器直接运行，还可以被其它脚本文件当做模块（module）调用。
- 在脚本中，可以用 import 语句导入某个模块或包。如下：
import sys                    # 导入sys模块
print("path：", sys.path)        # 指定调用sys模块中的path函数
  - 可以用 from … import … 语句选择导入某个模块或包中的成员。如下：
from sys import argv, path
from sys import *            # 导入该模块的全部内容
print("path：", path)        # 导入path之后，使用时就不需要再指定路径sys.path了
  - 可以用 as 将导入的内容重命名。如下：
import os as _os
from sys import argv as _argv 
  - 在没有被直接执行的模块中，可以使用相对地址进行导入。如下：
from .utils import *             # 从当前目录导入（需要当前目录是一个包）
from .. import *                # 从上层目录导入（需要上层目录是一个包
当被直接执行的脚本导入这样的模块时，Python解释器会自动将这些相对地址转换成绝对地址，从而正确地导入。
- 导入一个模块时，解释器会执行其全局作用域中的可执行语句。
  - 例如，在test.py中保存以下内容：
def fun1():
    print("fun1")

def fun2():
    print("fun2")
    fun1()

print("Hello")
  - 然后在终端导入该脚本：
>>> from test import fun2
Hello                        # 执行print("Hello")
>>> fun2()
fun2
fun1                            # 导入某个函数或类时，其调用的其它内容会被自动拷贝
>>> fun1()                    # 但是并不能被直接访问
NameError: name 'fun1' is not defined
>>> from test import fun1        # 再导入该模块时，不会重复执行print("Hello")
>>> fun1()
fun1
- 导入某个模块或包时，解释器会在sys.path的目录列表中依次寻找要导入的文件。
  - 可以在sys.path中加入某个搜索路径（每次重启解释器时，sys.path中的路径会被重置）。
- 局部导入：如果在函数内导入，则导入的模块只能在该函数内被访问。
  - pyinstaller在打包Python脚本时也会收集局部导入的模块，即使它可能不会被导入。
## 用importlib模块的import_module()函数可以根据模块名导入模块：
>>> from importlib import import_module
>>> m = import_module('os')      
>>> m
<module 'os' from 'C:\\Users\\Leo\\AppData\\Local\\Programs\\Python\\Python36\\lib\\os.py'>
>>> m = import_module('os.path') 
>>> m
<module 'ntpath' from 'C:\\Users\\Leo\\AppData\\Local\\Programs\\Python\\Python36\\lib\\ntpath.py'>
>>> m = import_module('sys', package='os')        # 相当于from os import sys
>>> m
<module 'sys' (built-in)>
## 
## 在模块所在文件夹中加入一个__init__.py，就可以使该文件夹变成包（package）。
- 包中必须包含__init__.py才能被识别，它定义了包的属性和方法（相当于把整个包当作一个模块），它可以为空。
- 可以在__init__.py中定义属性__all__，控制使用import * 时会导入该包的哪些部分。如下：
from .test import test_log

__all__ = ["test_log", "fun1"]

def fun1():
    pass
## 脚本的内置属性。
- __name__：表示脚本的名字。当脚本被直接运行时，其值为 "__main__" ；当脚本作为模块被导入时，其值为该脚本的模块名（没有.py后缀）。
  - 在脚本中可以用如下语句作为程序开始运行的入口，当脚本被直接运行时它会被执行，当脚本作为模块被其导入时则不会执行。
if __name__ == "__main__":
    try:
        main()
    except:
        raise
- __file__：表示脚本的文件路径。当脚本被直接运行时，其值为执行该脚本时使用的地址；当脚本作为模块被导入时，其值为该脚本的绝对路径。
  - 例如，在test.py中保存以下两条语句：
print(__file__)
print(__name__)
  - 在终端执行该脚本：
D:\1\test_Python>python test.py
test.py
__main__

D:\1\test_Python>python D:/1/test_Python/test.py
D:/1/test_Python/test.py
__main__
  - 在Python解释器中导入该脚本：
>>> import test
D:\1\test_Python\test.py
test
## 
## 
## 
 
第三方库
## 安装Python解释器时通常会同时安装一些Python的标准库，除此之外，还可以使用其他人开发的第三方库。
- 第三方库一般安装在Python解释器的安装目录的site-packages目录下，比如/usr/lib/Python3.6/site-packages/。
## 
## 制作第三方库。
distutils：Python的标准库，可用于打包、安装Python库，但功能简单。
setuptools：Python的第三方库，相当于改进版的distutils。

通常编写一个setup.py文件，用于打包Python库。如下：

import setuptools

setuptools.setup(
    name='pyexiv2',        # 该第三方库的名字
    version='2.0.0',        # 该第三方库的版本
    author='LeoHsiao',
    author_email='leohsiao@foxmail.com',
    description='Read/Write metadata of digital image, including EXIF, IPTC, XMP.',
    url='https://github.com/...',    # 项目网址
    install_requires=["pybind11==2.4.3"],    # 需要安装的依赖库
    packages=setuptools.find_packages(),
)

打包后的Python库可以保存为 .tar.gz 、.whl 等格式。

## 安装Python第三方库的方法。
- 使用setup.py安装：
  - 下载或拷贝第三方库的源代码到任意目录，其中应该包含setup.py文件，执行以下命令：
python setup.py build
python setup.py install
- 使用easy_install安装。它是一个较老的命令行工具，会调用setup.py进行安装。
- 使用pip安装。pip相当于改进版的easy_install。
## 
## 
 
♢ pip
## pip：一个命令行工具，用于安装、管理Python的第三方库。
- pip本身也是一个Python的第三方库，会安装到某个Python解释器的site-packages目录下，为这个Python解释器服务。
- 安装：
  - 在Window上，官网的Python安装包自带了pip工具。
  - 在Linux上，使用官方的脚本安装：
curl -O https://bootstrap.pypa.io/get-pip.py
python3 get-pip.py
rm -f get-pip.py

给当前用户单独安装：
python get-pip.py --user
echo "export PATH=$PATH:~/.local/bin" >> ~/.bash_profile
source ~/.bash_profile

- 用法：
pip
install <name>            # 安装一个包
install django==2.2.0        # 安装指定版本
    --upgrade            # 安装更新的版本
uninstall <name>            # 卸载一个包
search <name>            # 搜索一个包
list                        # 显示已安装的所有包
-V                        # 显示版本（还会显示该pip绑定到了哪个Python解释器）
-i https://pypi.tuna.tsinghua.edu.cn/simple        # 使用指定的源
  - 可执行 pip install <name> 直接从云端仓库下载第三方库并安装。
  - 也可下载或拷贝第三方库的 .whl 文件到任意目录，然后执行 pip install <name>.whl 安装。
  - 可以用python -m pip命令快速找到某个Python解释器使用的pip。
- 备份当前环境：
pip freeze > requirements.txt            # 将当前pip环境中安装的所有Python库记录下来
pip install -r requirements.txt        # 根据requirements.txt安装Python库，同步pip环境
  - 可以把requirements.txt中不眼熟的库删掉，因为它们可能会被其它库附带安装。
  - 使用requirements.txt并不能解决依赖库冲突的问题：假设库A需要下载库B的2.0版，而库B需要下载库C的3.0版，则安装库B之后，库C就升到了3.0版，导致库A可能运行出错。
## 一些第三方库。
- autopep8：用于将Python代码自动排版成PEP8风格。
- pylint：用于检查Python代码的语法、代码风格。
- 
## 
## 
## 
 
♢ virtualenv
## virtualenv：Python的第三方库，用于创建Python的虚拟环境。
- 安装：pip install virtualenv
- 使用virtualenv模块可以给每个Python项目创建一个虚拟环境（实际上是拷贝一份Python解释器），给它们分别安装Python的第三方库，隔离它们的运行环境。
- 用法：
  - 进入一个Python项目的目录，输入以下命令。它会创建一个名为.venv的文件夹，将系统Python解释器的安装目录拷贝进去（默认只会拷贝pip、setuptools、wheel三个包）。
virtualenv .venv
        -p C:\Users\Leo\AppData\Local\Programs\Python\Python37\Python.exe
# 指定要使用的Python解释器（默认使用安装virtualenv的那个）
  - 输入以下命令进入该虚拟环境的终端，此时使用pip命令安装的第三方库都会保存在.venv文件夹中。
.venv\Scripts\activate.bat
  - 输入以下命令退出该虚拟环境的终端。
deactivate
## 
## 
## 
 
其它知识
pass 和 ...
## pass在Python中是一个关键字，可用于填补语句块的空缺。
- 例：
>>> def fun1():
...     pass
...
## 省略号...在Python中是一个属于ellipsis类的单例对象Ellipsis，其布尔值为True。
>>> ...
Ellipsis
>>> type(...)
<class 'ellipsis'>
>>> bool(...)
True
- ...可以替代pass填补语句块的空缺。
>>> def fun1():
...     ...
...
- ...可以用于赋值。
>>> x = ...
>>> x
Ellipsis
  - 而pass是一个关键字，不能用于赋值。
>>> x = pass
SyntaxError: invalid syntax
- 当对象中的某个元素是对自身的循环引用时，会被解释器替代为...。
>>> list1 = [1, 2, 3]
>>> list1.append(list1)
>>> list1
[1, 2, 3, [...]]
>>> list1[3]
[1, 2, 3, [...]]
>>> list1[3][3]
[1, 2, 3, [...]]
  - 但直接用list1赋值时，不会造成循环引用。
>>> list1 = [1, 2, 3]
>>> list1 = [1, 2, 3, list1]
>>> list1
[1, 2, 3, [1, 2, 3]]
## 
## 
## 
 
内置函数
## Python解释器启动时会自动导入builtins模块，它提供了一些内置函数。
## 
## 
## 
 
关于底层
## def id(object) -> int
- 功能：返回对象的唯一ID。
  - 在CPython中是把对象的内存地址转换成十进制，作为ID。
- 例：
>>> id(1)
140706485723792
>>> x = 1; id(x)
140706485723792
## def help(object)
- 功能：返回对象的帮助文档（包括Python的帮助文档、源代码的说明文档）
- 例：
>>> help(id)
Help on built-in function id in module builtins:...
>>> x=1; help(x)
Help on int object:...
## def callable(object) -> bool
- 功能：判断一个对象是否可以调用（是否为函数名或类名）。
- 例：
>>> callable(10)
False
>>> callable(int)
True
## def globals() -> dict
- 功能：返回一个字典，包含所有全局变量。
- 例：
>>> globals()
{'__name__': '__main__', '__doc__': None, '__package__': None, '__loader__': <class '_frozen_importlib.BuiltinImporter'>, '__spec__': None, '__annotations__': {}, '__builtins__': <module 'builtins' (built-in)>}
## def locals() -> dict
- 功能：返回一个字典，包含当前作用域的所有局部变量。
- 例：
>>> def fun1():
...     x = 1
...     print(locals())
... 
>>> fun1()
{'x': 1}
## 
## def repr(obj) -> str
- 功能：返回对象的__repr__()方法的返回值。
- 当对象A在终端被打印时，显示的值就是 print(A.__repr__())
- 例：
>>> repr(3.14)
'3.14'
>>> repr(int)
"<class 'int'>"
>>> repr('Hello')        # 如果对象本来就是字符串类型，则会加上引号
"'Hello'"
>>> repr(b'Hello')
"b'Hello'"
## 
## 
 
关于执行代码
## def exec(src, globals=..., locals=...) -> None
- 功能：执行一段代码。
- 例：
>>> exec("1+2")
>>> exec("a=0")
>>> a
0
- 执行时可以访问外部变量：
>>> a = 1
>>> exec("print(a)")                        # 默认使用当前作用域的可用变量
1
>>> exec("print(a)", {"a":2})                # 可以给定变量
2
>>> exec("print(a)", globals(), locals())    # 传入当前的全局变量、局部变量
1
## def eval(src, globals=..., locals=...) -> object
- 功能：执行一段代码，返回其结果。
- 例：
>>> eval("1+2")
3
>>> eval("int")                    # 返回值是某个对象的引用，不是单纯的字符串
<class 'int'>
>>> eval("print('hello')")        # 返回值可以来自stdout
hello
>>> eval("a = 1")                    # 不能执行赋值语句
    a = 1
      ^
SyntaxError: invalid syntax
>>> eval("print(1);print(2)")        # 只能执行一条语句，返回一个结果
Traceback (most recent call last):
  File "<stdin>", line 1, in <module>
  File "<string>", line 1
    print(1);print(2)
            ^
SyntaxError: invalid syntax
## def compile(src, filename, mode) -> code
- 功能：将字符串编译成code对象，可以被exec()或eval()执行。
- 例：
>>> code = compile("print(1+2)", '<string>', "eval")
>>> eval(code)
3
## 
## 
## 
 
关于类
## class type(object) -> className
- 功能：返回对象的类型（即类名）。
- 例：
>>> type(1)
<class 'int'>
>>> type(int)        # 一般的类实际上是type类的实例
<class 'type'>
>>> type(object)
<class 'type'>
## def isinstance(object, type) -> bool
- 功能：判断一个对象是否是某个类的实例。
- type参数可以是一个类名，或者一个包含多个类名的元组。
- 例：
>>> isinstance(1.0, int)
False
>>> isinstance(1.0, (int, float))
True
## def issubclass(cls, another_cls) -> bool
- 功能：判断一个类是否是某个类的子类或同一个类。
- another_cls参数可以是一个类名，或者一个包含多个类名的元组。
- 例：
>>> class Test(int):
...     pass
... 
>>> issubclass(Test, int)
True
>>> issubclass(Test, Test)
True
>>> issubclass(Test, (float, str))
False
## class super(type, object) -> superclass
- 功能：获取一个对象的父类。
- type是一个类名，object是该类或其子类的一个实例。例如，
- 例：
>>> super(int, 1)            # 获取int类在实例1的MRO列表中的下一个父类
<super: <class 'int'>, <int object>>
- 下例是调用父类的构造方法：
>>> class Test(int):
...     def __init__(self):
...         super(Test, self).__init__()    # 在Python3中可将super(Test, self)简写为super()
...
>>> Test()
0
## 
## 
## 
 
关于类的成员
## 反射：根据类的成员的名称字符串，获得它的引用。
- 使用反射可以让Python程序在运行时更加动态。
## def dir(object=...) -> list of strings
- 功能：查看对象的所有成员，返回一个字符串列表。
- 不输入object参数时，返回当前作用域的所有可用标识符。
- 例：
>>> dir(1)
['__abs__', '__add__', '__and__', '__bool__', '__ceil__', '__class__', '__delattr__', '__dir__', '__divmod__', '__doc__', '__eq__', ...]
>>> dir()
['__annotations__', '__builtins__', '__doc__', '__loader__', '__name__', '__package__', '__spec__']
## def getattr(object, name:str, default=...) -> attribute
- 功能：获取对象的某个成员。如果不存在则报错，或者返回default参数。
- 例：
>>> getattr(str(), "encode")
<built-in method encode of str object at 0x000002ACBA2F7CE0>
>>> getattr(str(), "len")
AttributeError: 'str' object has no attribute 'len'
## def hasattr(object, name:str) -> bool
- 功能：判断对象是否拥有某个成员。
- 实际上是调用getattr()并捕捉异常。
- 例：
>>> hasattr(str(), "encode")
True
>>> hasattr(str(), "len")
False
## def setattr(object, name:str, value) -> None
- 功能：设置对象的某个成员，实际上是更改它的引用。
- 例：
>>> class Test:
...     def fun1(self):
...         print("this is fun1")
... 
>>> def fun2():
...     print("this is fun2")
... 
>>> t = Test()
>>> setattr(t, "fun1", fun2)        # 相当于t.fun1 = fun2
>>> t.fun1()
this is fun2
## def delattr(object, name:str) -> None
- 功能：删除对象的某个成员。
- 例：
>>> delattr(str(), "encode")
AttributeError: 'str' object attribute 'encode' is read-only
## 
## 
## 
 
关于迭代
## class range(stop: int) -> iterable
class range(start: int, stop: int, step: int=...) -> iterable
- 功能：生成一个等差数列。从start开始、到stop结束（不包含stop所在位），步进值为step。这些参数可以是负数。
- 例：
>>> range(5)                    # range()的返回值不是列表，要像迭代器一样遍历
range(0, 5)
>>> list(range(5))            # 生成一个在 [0, 5) 区间的等差数列
[0, 1, 2, 3, 4]
>>> list(range(1, 5))            # 生成一个在 [1, 5) 区间的等差数列
[1, 2, 3, 4]
>>> list(range(-1, -10, -2))    # 生成一个在 [-1, -10) 区间、步进值为-2的等差数列
[-1, -3, -5, -7, -9]
- 以下情况中，range()生成的等差数列为空。
>>> list(range(0))
[]
>>> list(range(-1))
[]
>>> list(range(5, 1))
[]
>>> list(range(1, 10, -2))
[]
## class enumerate(iterable, start=0) -> iterator
- 功能：枚举一个可迭代对象，返回一个迭代器。每个迭代的元素是一个元组 (index, iterable[index]) 。
- 常用于生成带序号的序列。
- 例：
>>> list(enumerate("Hello"))
[(0, 'H'), (1, 'e'), (2, 'l'), (3, 'l'), (4, 'o')]
## def sorted(iterable, key: callable=None, reverse=False) -> list
- 功能：将一个可迭代对象中的所有元素进行排序，放在一个list中返回。
- 默认直接比较各个元素的大小，可以通过key参数生成一个值再比较大小。
- 默认reverse=False，按升序排序，即后一项比前一项大。
- 例：
>>> list1 = [3, 2, 4, 5]
>>> sorted(list1)
[2, 3, 4, 5]
>>> sorted(list1, key=lambda x:-x)
[5, 4, 3, 2]
>>> sorted(list1, reverse=True)
[5, 4, 3, 2]
- 对字典进行排序：
>>> dict1 = {1:'c', 2:'b', 3:'a'}
>>> sorted(dict1)                                        # 对key进行排序
[1, 2, 3]
>>> sorted(dict1.items(), key=lambda x: x[1])            # 按value进行排序
[(3, 'a'), (2, 'b'), (1, 'c')]
>>> dict(sorted(dict1.items(), key=lambda x: x[1]))        # 排序后再转换成dict
{3: 'a', 2: 'b', 1: 'c'}
## def zip(*iterable) -> iterable[tuple]
- 功能：返回一个生成器，每次迭代取出各个iterable的第n项元素，组成一个元组返回。
- 例：
>>> zip(range(5))
<zip object at 0x7fa35d9d7fc8>
>>> list(zip(range(5)))
[(0,), (1,), (2,), (3,), (4,)]            # 每次迭代的返回值是一个元组
>>> list(zip(range(5), "Hellooo"))        # zip()可以迭代n次，n等于最短的那个可迭代对象的可迭代次数
[(0, 'H'), (1, 'e'), (2, 'l'), (3, 'l'), (4, 'o')]
>>> list(zip(*zip(range(5), "Hellooo")))        # zip(* )是zip的逆过程，可实现二维矩阵的转置
[(0, 1, 2, 3, 4), ('H', 'e', 'l', 'l', 'o')]
## def map(func, *iterable) -> iterable
- 功能：返回一个生成器，每次迭代会取出各个iterable的第n个元素，传给func函数执行，返回函数的返回值。
- 例：
>>> map(print, range(3))
<map object at 0x7fa35e250dd8>
>>> list(map(print, range(3)))
0
1
2
[None, None, None]
- map()比zip()更灵活、功能更强。例如用它们实现二维矩阵的转置：
>>> list(zip([1, 2, 3, 4], [5, 6, 7]))
[(1, 5), (2, 6), (3, 7)]
>>> list(map(lambda x, y: (x, y), [1, 2, 3, 4], [5, 6, 7]))
[(1, 5), (2, 6), (3, 7)]
## 
## 
## 
 
关于计算
## def len(object) -> int
- 功能：返回对象包含的元素个数，由对象的内置方法__len__()决定。
- 例：
>>> len("Hello")
5
>>> len([1, 2, 3])
3
>>> len({1:None, 2:None, 3:None})
3
## def abs(n)
- 功能：返回n的绝对值。
- 例：
>>> abs(-1)
1
>>> abs(-1.0)
1.0
## def round(number, digits=0) -> number
- 功能：将一个数字的小数部分四舍五入，只保留指定位数。
- 例：
>>> round(123.456)
123
>>> round(123.456, 2)
123.46
>>> round(123.456, 5)        # 保留的位数比实际位数多时，不会有影响
123.456
>>> round(123.456, -2)    # 保留-2位小数
100.0

def max(iterable, *_args, key: Callable) -> value
def max(arg1, arg2, *_args, key: Callable) -> value
- 功能：找出多个arg中最大的那个。
- 基于比较运算符 > 比较大小。
例：
>>> max()                                    # 必须传入参数
TypeError: max expected 1 arguments, got 0
>>> max(1)                                    # 只传入一个参数时，它必须是可迭代对象
TypeError: 'int' object is not iterable
>>> max([1, 2, 3])
3
>>> max(1, 2)
2
>>> max('a', 1)
TypeError: '>' not supported between instances of 'int' and 'str'
>>> max('a', 'b')
'b'‘
- 如果传入了key参数，max()不会直接比较arg1>arg2，而是比较key(arg1)>key(arg2)。
例：找出列表中出现频率最高的数字
>>> _list = [1, 2, 3, 2]
>>> max(set(_list), key=_list.count)
2

例：找出字典中value最大的key
>>> d = {'a': 1, 'b': 2, 'c': 3}
>>> max(d, key=d.get)
'c'

- min()函数的原理与max()类似，只不过是找出最小值。

## def sum(iterable, start=0) -> value
- 功能：将可迭代对象中的各个元素相加求和。
- 例：
>>> sum(1)
TypeError: 'int' object is not iterable
>>> sum([1, 2, 3])
6
## def all(iterable) -> bool
- 功能：如果iterable中各个元素的bool值都是True，则返回True。
- 例：
>>> all([0])
False
>>> all([1, 2, False])
False
- 例外：如果iterable为空，则也返回True。
>>> all([])
True
## def any(iterable) -> bool
- 功能：如果iterable中有任意一个元素的bool值为True，则返回True。
- 例：
>>> any([])
False
>>> any([0])
False
>>> any([0, 1, 2])
True
## 
## 
## 
 
常用模块
关于系统
♢ os
## os：Python的标准库，用于调用系统的API。
>>> import os
>>> os.name                    # 返回当前系统的接口类型，取值为'posix'或'nt'
'nt'
>>> os.abort()                # 终止Python解释器，且没有返回值
## 关于环境变量。
>>> os.environ.get("PATH")    # os.environ返回一个字典，包含当前的环境变量，可直接读写
'C:\\Windows\\system32;C:\\Windows;C:\\Windows\\System32\\Wbem;...
>>> os.environ["DEBUG"] = "true"
## 关于进程。
>>> os.getpid()            # 获得当前进程的pid
18516
>>> os.getppid()            # 获得当前进程的父进程的pid
6484
>>> os.getlogin()            # 获得当前登录的用户名
'Will'
## 关于执行命令。
- os.system(cmd)：创建一个shell（属于当前进程的子进程），执行一条命令，并返回命令的返回码(int类型）。
  - 例如：
>>> os.system("echo hello")
hello            # 命令的stdout会输出到当前进程中
0                # 命令正常结束时的返回码为0
  - 可根据返回值是否为0来判断进程是否正常结束：
if not os.system("..."):
    print("done")
- os.popen(cmd, mode="r", buffering=-1)：在系统shell中执行一条命令，并以文件流的形式返回其stdout。
  - 读取模式可以是'r'或'w'。
  - buffering=-1表示采用系统默认的缓冲方式。
  - os.system()会阻塞当前进程，一直等到命令执行结束。而os.popen()是异步执行命令，如果用p.read()等方法进行交互，也会阻塞当前进程。
  - 例如：
with os.popen("ipconfig") as p:
    result = p.read()
## 关于文件路径。
>>> os.path.split('D:/1/2.py')        # 将一个文件路径分割成目录名和文件名
('D:/1', '2.py')
>>> os.path.split("D:/1/2.py/")        # 最后一个路径分隔符的右侧内容会被视作文件名
('D:/1/2.py', '')
>>> os.path.split("/")                # 处理根目录时，不会分割
('/', '')
>>> os.path.split("")
('', '')

>>> os.path.dirname("D:/1/2.py")        # 返回path的目录名
'D:/1'
>>> os.path.basename("D:/1/2.py")        # 返回path的文件名
'2.py'
>>> os.path.sep                        # 获得当前系统的路径分隔符
'\\'
>>> os.path.join('D:/1', '2.py')        # 用当前系统的路径分隔符，把目录名和文件名合成一个路径
'D:/1\\2.py'
>>> os.path.join('D:/1', 'test', '2.py')    # 可以输入多项参数，一起合并
'D:/1\\test\\2.py'
>>> os.path.abspath(".")                # 返回path的绝对路径
'D:\\1'
>>> os.path.relpath("D:/1", "D:/")        # 返回"D:/1"对于"D:/"的相对路径
'1'
>>> os.path.normpath("D:/1/")            # 将一个path正常化（并不会判断它是否有效），
'D:\\1'                                # 它会自动转换成当前系统的路径分隔符，并去掉path末尾的路径分隔符
>>> os.path.normpath("D://\\1////")    # 即使有多余的路径分隔符，也会自动处理
'D:\\1'
>>> os.path.normpath("")                # 如果输入的path是空字符串，则返回'.'
'.'


例：基于路径分隔符分割path
>>> path = 'D:/1/2.py'
>>> os.path.normpath(path).split(os.path.sep)
['D:', '1', '2.py']

## 获取目录信息。
>>> os.getcwd()                        # 获得当前的工作目录
'D:\\1\\'
>>> os.chdir("D:\\")                    # 切换到指定工作目录
- >>> os.listdir("D:\\")                # 列出指定目录下的所有文件和文件夹
['.vscode', '1.py', '__pycache__']        # 包括隐藏文件，但不包括 . 和 .. 两个特殊文件
  - os.listdir()不能列出子目录下的文件，而且遇到异常时（比如无权限访问某个目录）会立即中断。
- >>> os.walk(".", onerror=print)        # 列出指定目录下，各个目录中的文件和文件夹，返回一个生成器
<generator object walk at 0x000001CC520EBA98>
>>> for i in os.walk(".", onerror=print):
>>>     print(i)
>>>
('.', ['res', 'utils', '__pycache__'], [1.py', '__init__.py'])
('.\\res', ['img'], [])
('.\\res\\img', [], ['9.jpg', 'logo.ico'])        # 生成器的每项元素为：目录、该目录下的子目录名、文件名
  - os.walk()默认会忽略遇到的异常，应该传入onerror参数，记录遇到的异常。
## 获取文件信息。
>>> os.path.exists("D:\\1")        # 判断文件是否存在
True
>>> os.path.isfile("D:\\1")        # 判断是否为普通文件
False
>>> os.path.isdir("D:\\1")        # 判断是否为目录
True
>>> os.path.getsize("D:\\1")        # 返回文件的大小（占多少字节）
4096
>>> os.path.getctime("D:\\1")        # 返回文件的创建时间
1546567973.6038435
>>> os.path.getatime("D:\\1")        # 返回文件的最后访问时间
1562806458.460649
>>> os.path.getmtime("D:\\1")        # 返回文件的最后修改时间
1562806458.460649
## 管理文件和目录。
>>> os.link(src, dst)                    # 创建硬链接，如果该文件已存在就会报错
>>> os.symlink(src, dst)                # 创建符号链接（不能在Windows上使用），如果该文件已存在就会报错
>>> os.rename(src, dst)                # rename a file or directory
>>> os.remove("D:\\1\\1.py")            # 删除文件
>>> os.mkdir("D:\\1")                    # 创建目录，若该目录已存在则抛出FileExistsError异常
>>> os.rmdir("D:\\1")                    # 删除目录（当目录不为空时会报错）
>>> os.makedirs("1/2/3")                    # 递归创建多层目录，若该目录已存在则报错
>>> os.makedirs("1/2/3", exist_ok=True)    # 若该目录已存在则不报错
- 给上述函数输入的path既可以是绝对路径，也可以是相对路径。
## 
## 
## 
 
♢ sys
## sys：Python的标准库，提供了一些与Python解释器进行交互的方法。
- 例：
>>> import sys
>>> sys.path                # 查看搜索模块时采用的所有路径，第一个''的作用是指向当前目录
['','C:\\Users\\Will\\AppData\\Local\\Programs\\Python\\Python37-32\\Python37.zip', 'C:\\Users\\Will\\AppData\\Local\\Programs\\Python\\Python37-32\\DLLs', 'C:\\Users\\Will\\AppData\\Local\\Programs\\Python\\Python37-32\\lib', 'C:\\Users\\Will\\AppData\\Local\\Programs\\Python\\Python37-32', 'C:\\Users\\Will\\AppData\\Roaming\\Python\\Python37\\site-packages', 'C:\\Users\\Will\\AppData\\Local\\Programs\\Python\\Python37-32\\lib\\site-packages', 'C:\\Users\\Will\\AppData\\Local\\Programs\\Python\\Python37-32\\lib\\site-packages\\win32', 'C:\\Users\\Will\\AppData\\Local\\Programs\\Python\\Python37-32\\lib\\site-packages\\win32\\lib','C:\\Users\\Will\\AppData\\Local\\Programs\\Python\\Python37-32\\lib\\site-packages\\Pythonwin']
>>> sys.exit(1)            # 退出程序，并返回一个值
>>> sys.exit(1)
- >>> sys.getsizeof('a')    # 返回对象占用的内存大小
50
>>> sys.getsizeof('ab')
51
## 可以对stdin、stdout、stderr进行操作。
>>> sys.stdout
<_io.TextIOWrapper name='<stdout>' mode='w' encoding='utf-8'>
>>> sys.stdout.write("hello")
hello5
>>> sys.stdout.flush()
- 下例是重定向stout、stderr：
>>> f = open("stdout.txt", "w")
>>> sys.stdout = f
>>> sys.stderr = f
>>> print("hello")
>>> raise RuntimeError("testing...")
  - 如果想恢复原本的stdout、stderr，需要先备份：
>>> __stdout__, __stderr__ = sys.stdout, sys.stderr
## 
## 
## 
 
♢ shutil
## shutil：Python的标准库，提供了一些拷贝文件的方法。
- 例：
>>> import shutil
>>> shutil.copy("D:/1.txt", "D:/1")            # 拷贝源文件，保存到目标目录下
'D:/1\\1.txt'                                # 执行成功之后会返回目标路径
>>> shutil.copy("D:/1.txt", "./1/2.txt")        # 拷贝源文件，保存为目标文件（目标文件已存在时会自动覆盖）
'./2.txt'

拷贝时的目标目录需要已经存在，否则容易出错。
如果目标目录"D:/1"已存在，则源文件会被保存为"D:/1/1.txt"；
如果"D:/1"不存在，或者为文件，则源文件会被保存为"D:/1"，即自动重命名为文件1；
如果目标路径为"./1/2.txt"，且上一级目录'./1/'不存在，则会直接报错，无法拷贝。


>>> shutil.copytree("D:/1", "D:/2")            # 拷贝源目录，保存为目标目录（目标目录已存在时会报错）
'D:/2'
>>> shutil.move("D:/1", "D:/2")                # 移动文件或目录
'D:/2'
## 
## 
## 
 
♢ psutil
## psutil：Python的第三方库，用于查看系统的硬件信息、运行状态。
- 安装：pip install psutil
- 查看进程的信息。
>>> psutil.pids()                    # 返回所有进程的pid
[0, 4, 88, 120, 140, 344, 412, 532, 612, 628, 728, 800, 808, ……]
>>> psutil.pid_exists(0)            # 查看某个pid的进程是否还在运行
True
>>> psutil.Process(0)                # 得到某个进程的引用，从而可以访问该进程的各种方法
psutil.Process(pid=0, name='System Idle Process', started='2019-06-21 18:25:21')
>>> p = psutil.Process(4500)        # 使用psutil.Process(os.getpid())可获得当前进程的引用
>>> p.status()                    # 返回进程的状态
'running'
>>> p.terminate()                    # 终止进程
>>> p.name()                        # 返回进程的名字
'BaiduNetdisk.exe'
>>> p.exe()                        # 返回进程的可执行文件的路径
'C:\\Users\\Leo\\AppData\\Roaming\\baidu\\BaiduNetdisk\\BaiduNetdisk.exe'
>>> p.cwd()                        # 返回进程当前的工作目录
'C:\\Windows\\System32'
>>> p.cmdline()                    # 返回进程的启动命令
['C:\\Users\\Leo\\AppData\\Roaming\\baidu\\BaiduNetdisk\\BaiduNetdisk.exe']
>>> p.create_time()                # 返回进程的创建时间（为UTC时间戳）
1561193118.0
>>> p.username()                    # 返回启动该进程的用户名
'LEO\\Leo'
>>> p.terminal()                    # 返回启动该进程的终端
AttributeError: 'Process' object has no attribute 'terminal'
>>> p.cpu_percent(1)                # 阻塞1秒，然后返回这段时间内该进程的CPU使用率
15.6
>>> p.memory_info()                # 返回进程的内存使用信息
pmem(rss=63967232, vms=60678144, num_page_faults=554783977, peak_wset=107614208, wset=63967232, peak_paged_pool=809056, paged_pool=751528, peak_nonpaged_pool=109032, nonpaged_pool=66736, pagefile=60678144, peak_pagefile=62353408, private=60678144)
>>> p.connections()                # 查看进程使用的所有网络连接
[pconn(fd=-1, family=<AddressFamily.AF_INET: 2>, type=1, laddr=addr(ip='10.135.149.134', port=56855), raddr=addr(ip='153.37.235.47', port=5287), status='ESTABLISHED'), pconn(……]
>> p.open_files()                    # 查看进程打开的所有文件
[popenfile(path='C:\\Users\\Leo\\AppData\\Local\\Temp\\baidu\\BaiduYunGuanjia\\at_monhavior-shm', fd=-1), popenfile(……]
>>> p.num_threads()                # 查看进程启动的线程数
42
>>> p.threads()                    # 列出该进程启动的所有线程
[pthread(id=17336, user_time=2161.453125, system_time=12109.109375), pthread(……]
>>> p.parent()                    # 返回父进程的引用
psutil.Process(pid=4940, name='explorer.exe', started='2019-06-22 16:18:53')
>>> p.children()                    # 列出所有子进程
[psutil.Process(pid=1524, name='BaiduNetdiskHost.exe', started='2019-06-22 16:45:19'), psutil.Process(pid=9536, name='BaiduNetdiskHost.exe', started='2019-06-22 16:45:20')]
- 查看CPU的信息。
>>> psutil.cpu_count()                            # 查看CPU的核数（默认为逻辑核数）
8
>>> psutil.cpu_count(logical=False)                # 查看CPU的物理核数
4
>>> psutil.cpu_percent()                            # 查看所有CPU的平均使用率（从上一次调用到目前为止）
7.2
>>> psutil.cpu_percent(interval=1, percpu=True)    # 阻塞1秒，然后返回这段时间的各个CPU使用率
[20.6, 7.7, 10.8, 20.0, 12.3, 4.6, 10.8, 4.6]
>>> psutil.cpu_times_percent()                    # 查看CPU各方面的使用率（像Linux的uptime命令）
scputimes(user=3.2, system=4.0, idle=92.5, interrupt=0.2, dpc=0.2)
>>> psutil.cpu_stats()
scpustats(ctx_switches=3346114770, interrupts=2451502960, soft_interrupts=0, syscalls=2114761291)
- 查看内存的信息。
>>> psutil.virtual_memory()                        # 虚拟内存（像Linux的free命令，单位为bytes）
svmem(total=8424906752, available=2264326144, percent=73.1, used=6160580608, free=2264326144)
>>> psutil.swap_memory()                            # swap
sswap(total=15404228608, used=9708523520, free=5695705088, percent=63.0, sin=0, sout=0)
- 查看磁盘的信息。
>>> psutil.disk_partitions()                        # 查看各个磁盘分区的信息
[sdiskpart(device='C:\\', mountpoint='C:\\', fstype='NTFS', opts='rw,fixed'), sdiskpart(device='D:\\', mountpoint='D:\\', fstype='NTFS', opts='rw,fixed')]
>>> for x in psutil.disk_partitions():                # 提取磁盘分区的device名字
...     print(x[0])
...
C:\
D:\
>>> psutil.disk_usage("D:")                        # 查看指定磁盘分区的使用率
sdiskusage(total=295923871744, used=237350260736, free=58573611008, percent=80.2)
>>> psutil.disk_io_counters()                        # 查看磁盘IO的总量
sdiskio(read_count=1898598, write_count=1444576, read_bytes=131522050560, write_bytes=137437140480, read_time=1106, write_time=980)
- 查看网络的信息。
>>> psutil.net_if_addrs()                            # 查看所有网卡的地址
{'以太网': [snicaddr(family=<AddressFamily.AF_LINK: -1>, address='34-64-A9-15-EF-A9', netmask=None, broadcast=None, ptp=None), snicaddr(family=<AddressFamily.AF_INET: 2>, address='192.168.10.172', netmask='255.255.255.0', broadcast=None, ptp=None), snicaddr(family=<AddressFamily.AF_INET6: 23>, address='fe80::7c60:86c4:a3e2:c668', netmask=None, broadcast=None, ptp=None)], ……}
>>> for k, v in psutil.net_if_addrs().items():        # 提取网卡的mac地址
...     for item in v:
...         address = item[1]
...         if '-' in address and len(address) == 17:
...             print(address)
...
34-64-A9-15-EF-A9
>>> psutil.net_if_stats()                        # 查看所有网卡的信息（像Windows的ipconfig -all命令）
{'以太网': snicstats(isup=False, duplex=<NicDuplex.NIC_DUPLEX_FULL: 2>, speed=0, mtu=1500), 'Loopback Pseudo-Interface 1': snicstats(isup=True, duplex=<NicDuplex.NIC_DUPLEX_FULL: 2>, speed=1073, mtu=1500), 'WLAN': ……}
psutil.net_connections(kind="tcp")
>>> psutil.net_connections()                    # 查看所有网络连接的信息（像Linux的ss命令）
[sconn(fd=-1, family=<AddressFamily.AF_INET: 2>, type=2, laddr=addr(ip='0.0.0.0', port=49665), raddr=(), status='NONE', pid=3800), sconn(……]
>>> psutil.net_connections(kind="tcp")            # 只查看TCP类型的网络连接的信息
[sconn(fd=-1, family=<AddressFamily.AF_INET: 2>, type=1, laddr=addr(ip='10.135.149.134', port=57878), raddr=addr(ip='211.97.82.37', port=443), status='CLOSE_WAIT', pid=1524), sconn(……]

## 
## 
## 
## 
 
♢ platform
## platform：Python的标准库，用于获取当前运行平台的信息。
- 关于Python解释器。
>>> import platform
>>> platform.architecture()[0]    # 返回Python解释器的位数
'64bit'
>>> platform.python_version()        # 返回Python解释器的版本
'3.7.3'
- 关于操作系统。
>>> platform.system()                # 返回操作系统的名字（在Linux系统上是返回'Linux')
'Windows'
>>> platform.platform()            # 返回操作系统的具体名字
'Windows-10-10.0.17763-SP0'
>>> platform.machine()            # 返回CPU的架构类型
'AMD64'
>>> platform.processor()            # 返回CPU的具体名字
'Intel64 Family 6 Model 158 Stepping 10, GenuineIntel'
>>> platform.node()                # 返回该主机在网络中的名字
'Leo'
- 以上函数的返回值大多为str类型。如果没有确定的答案，则返回空字符串。
## 
## 
## 
 
关于时间
♢ time
## time：Python的标准库，用于获取时间。
- 获取UTC时间的时间戳：
>>> import time
>>> time.time()
1544593113.593077
  - 使用time模块获取的时间戳总是UTC时间，这样通用性强。
  - UTC时间是世界标准时间，记录从1970年1月1日开始的原子时秒长。
  - UTC时间属于0时区，与格林威治时间（GMT）相同。北京时间属于UTC+8时区。
  - 通过time.time()获取时间的延迟很小，不足1ms。
- 获取UTC时间的struct_time元组：
>>> time.gmtime(time.time())            # 将时间戳转换成struct_time元组
time.struct_time(tm_year=2019, tm_mon=5, tm_mday=31, tm_hour=4, tm_min=40, tm_sec=52, tm_wday=4, tm_yday=151, tm_isdst=0)
>>> time.gmtime().tm_year                # 不输入参数时，默认使用time.time()
2019
  - 可以访问struct_time元组中的任意属性。其中，tm_isdst表示是否是夏令时（DST）。
- 获取本地时间的struct_time元组：
>>> time.localtime(time.time())        # 将UTC时间的时间戳转换成本地时间的struct_time元组
time.struct_time(tm_year=2019, tm_mon=5, tm_mday=31, tm_hour=12, tm_min=46, tm_sec=15, tm_wday=4, tm_yday=151, tm_isdst=0)
>>> time.localtime().tm_year            # 不输入参数时，默认使用time.time()
2019
## struct_time元组。
- 将struct_time元组转换成时间戳（会自动从本地时区转换成UTC时区）：
>>> time.mktime((2019,2,21,14,10,45,3,52,0))
1545878778.0                # 得到的时间戳没有小数部分
  - 如果给time.mktime()输入的年份早于1970年就会报错。
  - time.mktime()在转换时会自动计算本地时区与UTC时区的差值，如下：
>>> time.mktime(time.localtime()) - int(time.time())
0.0
>>> time.mktime(time.gmtime()) - int(time.time())
-28800.0
- 将struct_time元组转换成指定格式的字符串：
  - struct_time元组不包含毫秒，因此生成的字符串中不包含毫秒。
>>> time.strftime("%Y%m%d-%H:%M:%S", time.localtime())
'20181212-13:52:43'
- 将指定格式的字符串转换成struct_time元组：
>>> time.strptime("20181212-13:52:43", "%Y%m%d-%H:%M:%S")
time.struct_time(tm_year=2018, tm_mon=12, tm_mday=12, tm_hour=13, tm_min=52, tm_sec=43, tm_wday=2, tm_yday=346, tm_isdst=-1)
## time模块还可暂停当前线程、获取程序的运行时间。
- 暂停当前线程：
>>> time.sleep(3)
  - 让线程保持等待时，调用sleep()函数比空语句pass更好。
while 1:
    pass                # 在这个死循环中，线程会不停地跳转while循环，占用CPU
while 1:
    time.sleep(1)        # 在这个死循环中，线程会被被挂起，不会占用CPU
- 获取程序的运行时间：
>>> time.perf_counter()            # 返回程序的运行时间，在终端里则是打开Python编辑器后的时间
16.795266047
# 运行程序时可以用time.perf_counter()截取多个时间节点，计算它们的差值就可以知道程序的运行时间
>>> time.process_time()
0.078125
>>> time.thread_time()
0.078125
## 
## 
## 
 
♢ datetime
## datetime：Python的标准库，基于time模块封装了一些API，适合处理日期、切换时区、计算两个日期的差或和。
- 时区要用pytz模块选择：
>>> import pytz
>>> pytz.all_timezones_set        # 返回所有可用时区名的集合
LazySet({'Europe/Tirane', 'Asia/Phnom_Penh', 'America/New_York',...
>>> pytz.timezone("UTC")            # 返回某个时区名对应的时区对象
<UTC>
- 获取当前时间的datetime对象：
>>> from datetime import datetime                # 从datetime模块导入datetime类
>>> datetime.utcnow()                            # 获取UTC时间，返回一个datetime对象
datetime.datetime(2019, 5, 30, 9, 2, 2, 512089)
>>> datetime.now()                            # 获取本地时间
datetime.datetime(2019, 5, 30, 17, 2, 3, 632104)
- 转换时区：
>>> from datetime import timezone
>>> import pytz
>>> datetime.now(tz=pytz.timezone("UTC"))                # 获取指定时区的时间
datetime.datetime(2019, 5, 30, 8, 58, 21, 426129, tzinfo=<UTC>)
>>> datetime.now().astimezone(pytz.timezone("UTC"))        # 将datetime对象转换到指定时区
datetime.datetime(2019, 5, 30, 9, 46, 17, 373527, tzinfo=<UTC>)
## datetime对象。
- datetime对象包含了年、月、日、时、分、秒以及时区信息。
>>> d = datetime.now()
>>> print(d.year, d.month, d.day)
2019 5 30
>>> print(d.hour, d.minute, d.second, d.microsecond)
17 5 25 630753
>>> d.replace(hour=12)            # 修改datetime对象的值
datetime.datetime(2019, 5, 30, 12, 5, 25, 630753)
- 与时间戳的转换：
>>> d.timestamp()                    # 将datetime对象转换成时间戳（不会自动转换成UTC时区）
1559207573.719928
>>> datetime.fromtimestamp(1559207573.719928, tz=pytz.timezone("UTC"))
# 将时间戳转换成datetime对象
datetime.datetime(2019, 5, 30, 9, 12, 53, 719928, tzinfo=<UTC>)
- 与字符串的转换：
  - 与time.strftime()相比，datetime能用 %f 输出微妙。
>>> d.strftime("%Y%m%d-%H:%M:%S.%f")            # 将datetime对象转换成指定格式的字符串
'20190530-17:12:53.505080'
>>> datetime.strptime('20190530-17:12:53', "%Y%m%d-%H:%M:%S")
datetime.datetime(2019, 5, 30, 17, 12, 53)        # 将指定格式的字符串转换成datetime对象
- datetime对象支持加减法运算：
>>> from datetime import timedelta                # 从datetime模块导入timedelta类
>>> datetime.now() - datetime.utcnow()            # 两个datetime对象相加减，会生成timedelta对象
datetime.timedelta(seconds=28800)
>>> datetime.now() + timedelta(hours=10)        # 一个datetime对象可以与timedelta对象相加减
datetime.datetime(2019, 5, 31, 3, 23, 20, 397415)
>>> timedelta(milliseconds=100).total_seconds()    # 获取timedelta对象的秒值
0.1
## 
## 
## 
 
♢ apscheduler
## apscheduler：Python的第三方库，用于执行定时任务。
- 安装：pip install apscheduler
- 原理：当一个任务到达触发时刻时，就创建一个子线程来运行它。
- 例：
from apscheduler.schedulers.blocking import BlockingScheduler
from datetime import datetime, timedelta

schedule = BlockingScheduler()        # 创建一个任务表，它在运行时会阻塞当前线程

# 添加一个定时任务，只会执行一次
schedule.add_job(func=print, args=('hello',), kwargs=None, trigger='date', next_run_time=datetime(2012, 10, 1, 0, 0, 0))

# 添加一个周期性任务，每隔一段时间就执行一次
schedule.add_job(func=print, args=('hello',), trigger='interval', seconds=3)

# 添加一个日常循环任务，在每天的12:30执行一次
schedule.add_job(func=print, args=('hello',), trigger='cron', hour=12, minute=30)

schedule.start()            # 启动任务表
schedule.get_jobs()        # 返回一个列表，包含所有待执行的任务（不包含已经失效的任务）
schedule.shutdown()        # 终止任务表

- 关于add_job()方法。
  - trigger参数表示任务的触发方式。
  - 可传入max_instances参数，控制任务的运行实例数量。默认为1。
  - 对于'interval'类型的任务，可使用以下参数控制任务的间隔时间：
weeks(int)    间隔几周
days(int)    间隔几天
hours(int)    间隔几小时
minutes(int)    间隔几分钟
seconds(int)    间隔多少秒
start_date(datetime or str)    开始日期
end_date(datetime or str)    结束日期
  - 对于'cron'类型的任务，可使用以下参数控制任务的启动时刻：
year、month、week、day_of_week（取值为0~6）、hour、minute、second、start_date、end_date
- 删除任务：
job = scheduler.add_job(func=print, args=('hello',), trigger='interval', seconds=3)
job.remove()
## 
## 
## 
 
♢ celery
## celery：Python的第三方库，是一个分布式的任务队列，常用于执行大量的异步任务、定时任务。
- 安装：pip install celery
- 原理：用户将任务保存到broker服务器。而worker会从broker服务器提取任务并执行，然后将执行结果保存到backend服务器。
  - broker、backend服务器可以采用RabbitMQ，也可以采用Redis。
  - celery采用分布式架构，可以有多个worker。
- 任务有以下几种状态：
  - PENDING    ：等待被执行。
  - STARTED    ：已被启动，正在执行。
  - RETRY    ：发生异常，正在重新执行。
  - SUCCESS    ：执行成功。
  - FAILURE    ：执行失败。
## 例：
- 创建异步任务：
>>> import celery
>>> cel = celery.Celery(backend='redis://127.0.0.1:6379/1', broker='redis://127.0.0.1:6379/2')
    # 可以加上密码，例如'redis://:123456@127.0.0.1:6379/1'
    # 此时只是创建客户端，等执行实际操作时才会连接到broker
>>> @cel.task            # 使用装饰器添加任务
... def fun1(*args):        # 函数在第一次添加到celery时就固定了，不能再重新定义
...     print(b)
... 
>>> fun1('hello')                    # 正常调用该函数
hello
>>> task = fun1.delay('hello')    # 异步执行该函数（这会将任务发送到broker），用delay()方法传入参数
>>> task
[2019-10-28 16:00:35,998: WARNING/MainProcess] <AsyncResult: c399d950-c16e-4912-8d19-624393abf1ef>
>>> result = celery.result.AsyncResult(id=task.id, app=cel)        # 获取任务的result
>>> result.status                    # 查看任务状态
[2019-10-28 16:01:01,766: WARNING/MainProcess] 'PENDING'
- 运行worker有两种方法。
  - 在终端执行以下命令：
celery worker
--app task1            # 指定任务所在的.py文件
--loglevel info
--logfile <file>        # 指定日志文件的保存路径（默认输出到stdout）
  - 或者在python中执行主函数：
cel.worker_main()
- 创建定时任务：
>>> result = fun1.apply_async(args=('hello',), kwargs=None, countdown=10)
>>> result.status
'PENDING'
- 设置周期性任务：
cel.conf.beat_schedule = {
    'schedule1': {
        'task': 'task1.fun1',                # 把task1.py文件中的fun1()函数添加成任务
        'args': ('hello',)                    # 输入参数
        'schedule': timedelta(seconds=2),    # 间隔时间
    },
    'schedule2': {
        ...
    },
}
## 
## 
## 
 
关于数据
♢ random
## random：Python的标准库，用于生成随机数。
- random模块生成的随机数不适合用作安全加密，想生成密码时，使用os.urandom()更安全。
- 例：
>>> import random
>>> print(random.randint(1, 10))        # 生成一个指定范围的int型随机数（这里是闭区间[1,10]）
3
>>> print(random.randrange(1, 100, 2))    # 生成一个从1到100、步进值为2的随机整数
5
>>> print(random.uniform(1.1, 5.4))    # 生成一个指定范围的float型随机数（上下限可以是浮点数）
5.254084551261407
>>> random.shuffle([0, 1, 2, 3])        # 将列表中元素的顺序打乱
>>> random.choice("01")                # 从序列中随机选取一项元素
0
## 
## 
## 
 
♢ string
## string：Python的标准库，提供了一些常用的字符集合。
- 关于数字。
>>> import string
>>> string.digits                # 全部数字
'0123456789'
>>> string.hexdigits            # 全部十六进制数字
'0123456789abcdefABCDEF'
>>> string.octdigits            # 全部八进制数字
'01234567'
- 关于字母。
>>> string.ascii_letters        # 全部字母
'abcdefghijklmnopqrstuvwxyzABCDEFGHIJKLMNOPQRSTUVWXYZ'
>>> string.ascii_lowercase    # 全部小写字母
'abcdefghijklmnopqrstuvwxyz'
>>> string.ascii_uppercase    # 全部大写字母
'ABCDEFGHIJKLMNOPQRSTUVWXYZ'
- 其它。
>>> string.whitespace            # 所有空白字符
' \t\n\r\x0b\x0c'
>>> string.punctuation        # 所有标点符号
'!"#$%&\'()*+,-./:;<=>?@[\\]^_`{|}~'
>>> string.printable            # 所有可打印字符（等于digits + letters + whitespace + punctuation）
'0123456789abcdefghijklmnopqrstuvwxyzABCDEFGHIJKLMNOPQRSTUVWXYZ!"#$%&\'()*+,-./:;<=>?@[\\]^_`{|}~ \t\n\r\x0b\x0c'
## 
## 
## 
 
♢ collections
## collections：Python的标准库，提供了一些容器类。
- 可迭代对象、迭代器。
>>> from collections.abc import Iterable, Iterator
>>> isinstance("Hello", Iterable)
True
>>> isinstance(iter("Hello"), Iterator)
True
## 
## 
 
关于调试
♢ traceback
## traceback：Python的标准库，用于获取stack的信息。
- 例：
import traceback
try:
    ...
except :                                # 使用时不需要实例化异常类
    traceback.print_exc()                # 打印出完整的异常信息
    list1 = traceback.format_exc()        # 保存异常信息
## 
## 
## 
## 
## 
## 
## 
 
♢ inspect
## inspect：Python的标准库，提供了一些查询对象属性、查看堆栈的方法，常用于调试。
## 判断对象的类型。
- def ismodule(object) -> bool
  - 功能：判断对象是否为模块名。
  - 例：
>>> from inspect import ismodule
>>> ismodule(inspect)
True
- def isclass(object) -> bool
  - 功能：判断对象是否为类名。
  - 例：
>>> a = int
>>> isclass(a)
True
- def ismethod(object) -> bool
  - 功能：判断对象是否为某个实例的普通方法或类方法名。（根据该对象是否具有__func__属性）
  - 例：
>>> class Test(int):
...     def fun1(self):
...         pass
...
>>> ismethod(Test().fun1)
True
>>> ismethod(Test.fun1)        # 必须是实例的方法
False
>>> ismethod("".encode)        # 不能为built-in类的实例的方法
False
- def isfunction(object) -> bool
  - 功能：判断对象是否为用户定义的函数名（非built-in）。
  - 例：
>>> isfunction(isfunction)
True
>>> isfunction(lambda : ...)        # 可以是匿名函数
True
>>> isfunction(len)                # 不可以是内置函数
False
>>> isfunction("".encode)        # 不可以是方法
False
- def isbuiltin(object) -> bool
  - 功能：判断对象是否为built-in的函数或方法名。
  - 例：
>>> inspect.isbuiltin(len)
True
>>> inspect.isbuiltin("".encode)
True
- def isroutine(object) -> bool
  - 功能：判断对象是否为函数名或方法名。
  - 例：
>>> inspect.isroutine(len)
True
>>> inspect.isroutine("".encode)
True
- def isgenerator(object) -> bool
  - 功能：判断对象是否为生成器。
  - 例：
>>> isgenerator((x for x in range(5)))
True
## 查看对象的定义。
- def getfile(object: object) -> str
  - 功能：返回定义该对象的.py文件的绝对路径。
  - 例：
>>> getfile(getfile)
'C:\\Users\\Will\\AppData\\Local\\Programs\\Python\\Python37\\lib\\inspect.py'
>>> getfile(int)
TypeError: <module 'builtins' (built-in)> is a built-in class
- def getsourcelines(object) -> (List[str], int)
  - 功能：获取一个对象的源代码，返回一个list（包含每行代码字符串）、行号。
  - 例：
>>> getsourcelines(getfile)
(['def getfile(object):\n', '    """Work out which source or compiled file an object was defined in."""\n', '    if ismodule(object):\n',...'], 642)
- def signature(callable, *, follow_wrapped=True) -> Signature
  - 功能：查看函数的一些属性，返回一个Signature对象。
  - 例：
>>> def fun1(a, b: str, c: int = 0):
...     pass
...
>>> sign = signature(fun1)
>>> sign
<Signature (a, b: str, c: int = 0)>
>>> sign.parameters                # 获取函数的形参列表（与定义处一致），返回一个dict类对象
mappingproxy(OrderedDict([('a', <Parameter "a">), ('b', <Parameter "b: str">), ('c', <Parameter "c: int = 0">)]))
  - 可以模拟给函数形参赋值：
>>> arguments = sign.bind(1, b=2)                # 正常传参，要传入所有必需参数
>>> arguments.arguments                        # 显示被赋值的那些参数
OrderedDict([('a', 1), ('b', 2)])
>>> arguments.args
(1, 2)
>>> arguments.kwargs
{}
>>> sign.bind(1).arguments
TypeError: missing a required argument: 'b'
>>> sign.bind_partial(1).arguments            # 只传入部分参数
OrderedDict([('a', 1)])
## 
## 
## 
 
♢ logging
## logging：Python的标准库，用于记录日志。
- logging模块定义了以下几种日志级别：
  - DEBUG    ：最详细的日志信息，比如记录程序的执行进度。
  - INFO        ：用户需要关注的关键信息。
  - WARNING    ：一些警告。
  - ERROR    ：严重的错误，导致某些功能无法实现。
  - CRITICAL    ：致命的错误，导致程序不能运行。
- 这几种级别的日志的重要性依次递增。
  - 通常用配置文件为程序指定一个日志级别，程序会记录下不低于该级别的所有事件。
  - 在程序开发阶段时，通常使用DEBUG或INFO级别，获取最详细的日志。在程序发布阶段时，通常使用WARNING、ERROR或CRITICAL级别，从而简化日志数量、降低IO压力。
- 日志（log）用于记录程序运行时发生的某些事件。
  - 日志中的一条事件通常包含重要级别、发生时间、发生位置、具体描述等信息。
  - 通常根据重要性的不同将事件分为几种级别（level），方便整理和筛选。

将每行日志保存成JSON格式（不加换行、缩进）可以方便后期解析日志。如下：
{"date":"2018-01-01 01:01:01", "level": "WARNING", "message": "There is something wrong."}


## 使用简单的函数记录日志（只能使用默认的日志器root logger）：
- logging.basicConfig(**kwargs)：对root logger进行基本配置（该函数只在第一次调用时有效）。
  - root logger默认日志级别为WARNING，将日志输出到sys.stderr。
- logging.debug(msg)：记录一条DEBUG级别的事件到root logger。
  - 同理，还有logging.info()、logging.warning()、logging.error()、logging.critical()
- 例如：
import logging
import time
time_str = time.strftime("_%Y%m%d", time.localtime())
fileName = "test"+time_str+".log"
logging.basicConfig(filename=fileName, filemode='a', level=logging.DEBUG,
                    format="%(asctime)s %(levelname)s %(threadName)s: %(message)s",
                    datefmt="%Y-%m-%d %H:%M:%S")
# 这里设置了将日志输出到指定文件、日志级别、事件字符串的格式、asctime的格式
logging.debug("test...")
# 输出的日志内容为：2019-02-19 17:22:02 - DEBUG - MainThread: test...
- logging.log(level, msg, *args, **kwargs)        # 记录一条level级别的日志
- logging模块提供了一些可嵌入到事件字符串中的字段，包括：
  - %(asctime)s        ：当前的格式化时间。
  - %(name)s            ：当前日志器的名称。
  - %(levelname)s    ：当前日志器的日志级别的名称。
  - %(message)s        ：事件字符串的内容。
  - %(pathname)s        ：当前程序文件的绝对地址。
  - %(filename)s        ：pathname的文件名部分，包含后缀名。
  - %(module)s        ：pathname的文件名部分，不包含后缀名。
  - %(lineno)d        ：当前代码所在行号。
  - %(funcName)s        ：当前代码所在函数名。
  - %(process)d        ：当前的进程ID。
  - processName        ：当前的进程名称。
  - %(thread)d        ：当前的线程ID。
  - %(thread)s        ：当前的线程名称。
## 使用基本的日志类记录日志：
- logger类        ：日志器。
  - 程序将事件传给日志器，日志器会将日志交给处理器，处理器会将日志内容格式化后再输出到某个地方。
  - 日志器的名称可以用 . 分隔成多个层级，每个 . 之后的logger是之前的logger的子级。例如：A.B.C，当C收到一条日志时，会将它传递给A和B。
- handler类    ：处理器，将日志输出到某个地方。
  - 一个日志器可以连接多个处理器。
- filter类        ：过滤器，过滤日志。
  - 例如：logger.addFilter()、logger.removeFilter()
- formatter类    ：格式器，控制输出的每行日志格式。
- 例如：
import logging
import time

filename = "test" + time.strftime("_%Y%m%d", time.localtime()) + ".log"
handler = logging.FileHandler(filename)        # 创建一个处理器
handler.setLevel(logging.INFO)                # 设置处理器的日志级别
formatter = logging.Formatter(
    fmt="{asctime} {levelname:5} {threadName:15} --> {message}",
    datefmt="%Y-%m-%d %H:%M:%S", style='{')
handler.setFormatter(formatter)                 # 设置该handler的格式器

console_handler = logging.StreamHandler()      # 创建一个StreamHandler
console_handler.setFormatter(formatter)
console_handler.setLevel(logging.INFO)

logger = logging.getLogger(name=__file__)        # 创建一个日志器
logger.setLevel(logging.DEBUG)                # 设置日志器的级别
logger.addHandler(handler)                      # 为该日志器添加一个处理器
logger.addHandler(console_handler)

logger.debug("test...")                        # logger对象也有logging.debug()等方法
  - 调用logging.getLogger()时，如果不设置name，就返回默认的root logger。如果设置的name与已有的logger相同，则返回那个logger的引用。
## 
## 
## 
 
♢ pytest
## pytest：Python的第三方库，是一个开源的Python单元测试框架。
- 安装：pip install pytest
- pytest的基本用法如下：
  - 将单元测试的脚本命名为 test_*.py 或 *_test.py 。
  - 将单元测试的函数命名为 test_* 。
  - 将单元测试的类命名为 Test* ，且该类不能定义__init__()方法。
  - 如下：
def fun1(x):
    return x**2

class TestClass:
    def test_fun1_1(self):
        assert fun1(1)

    def test_fun1_2(self):
        for i in range(100):
            assert fun1(i) > 0
- 命令：
pytest [file_or_dir]...    # 让pytest执行指定的测试脚本
-q        # 用一行显示所有测试脚本的测试结果
-v        # 详细地显示每个测试函数的测试结果
    -s        # 显示测试用例的stdout
  - 不指定测试脚本的话，pytest会自动在当前目录及其子目录中搜集单元测试的脚本来执行（搜集过程是import这些脚本）。
- 执行pytest之后的显示内容如下：
D:\1\test_Python>pytest
======================== test session starts ========================
platform win32 -- python 3.7.2, pytest-4.3.1, py-1.8.0, pluggy-0.9.0
rootdir: D:\1\test_Python, inifile:
collected 2 items                                                                                   

test_.py .F                                                          [100%]

  - 测试脚本后，绿色的 . 表示一个测试函数pass了，红色的 F 表示一个测试函数fail了，蓝色的 [100%] 表示pytest的测试进度。
  - 红色的 E代表一个抛出的异常，即源代码没有捕捉到的异常。
## pytest支持传统的单元测试风格：定义setup()、teardown()函数，pytest运行测试函数前会自动调用setup()进行测试前的准备工作，运行测试函数后会自动调用teardown()进行测试后的清理工作。
- 按作用区域分级：
  - setup_module()、teardown_module()        ：执行每个测试模块的前后被调用。
  - setup_function()、teardown_function()    ：执行每个测试函数的前后被调用。
  - setup_class()、teardown_class()        ：执行每个测试类的前后被调用。
  - setup_method()、teardown_method()        ：执行每个测试类中的测试方法的前后被调用。
  - setup()、teardown()                    ：执行每个测试类中的测试函数的前后被调用。
- 例如：
  - 定义如下测试类：
import pytest

class TestClass:
    def setup_class(self):
        self.result = []
        self.result.append("setup_class")

    def teardown_class(self):
        self.result.append("teardown_class")
        with open("1.txt", 'w') as f:
            f.writelines('\n'.join(self.result))    # 记录测试方法的运行结果

    def setup_method(self):
        self.result.append("setup_method")

    def teardown_method(self):
        self.result.append("teardown_method")

    def test_1(self):
        self.result.append("test_1")

    def test_2(self):
        self.result.append("test_2")
- 输入命令pytest进行测试，在1.txt中可看到测试结果如下：
setup_class
setup_method
test_1
teardown_method
setup_method
test_2
teardown_method
teardown_class
## 用with pytest.raises()可以判断源代码是否抛出了某个异常。如果抛出了，则pass；如果没抛出，则fail。
import pytest

def fun1():
    raise KeyboardInterrupt

def test_fun1():
    with pytest.raises(KeyboardInterrupt):
        fun1()
## pytest还提供了装饰器 @pytest.fixture，用于标记一个fixture函数，只要把它的函数名作为形参传入测试函数，pytest就会在进行测试时自动调用它。
- 直接使用该装饰器的例子：
@pytest.fixture(scope="function")        # 相当于@pytest.fixture
def fun1(request):
    print("fun1")

def test_1(fun1):                        # 传入fixture函数的函数名
    assert 0
  - scope = 'function' 表示在运行某个测试函数时调用fixture函数。scope可取值为"function"（默认该值）、
- 给fixture函数传入参数的例子：
@pytest.fixture(params=[1, 2, 3], ids=['a', 'b','c'])
def fun1(request):            # fixture函数通过request参数获取装饰器的一些信息
    print(request.param)
    assert request.param == 0

def test_1(fun1):
    pass
  - 这里执行test_1()时会调用三次fun1()——即测试三次。每次传入一个参数，并给test_1()记上一个id，即test_1[a]、test_1[b]、test_1[c]。
  - 如果没有给装饰器设置参数ids，pytest会自动生成数字编号，即test_1[1]、test_1[2]、test_1[3]。
## pytest的可用插件。
- pytest-cov：用于统计测试覆盖率，即每个py文件中的源代码被测试用例执行到的百分比。
- pytest-django：用于执行Django项目目录下的测试用例。
## 
## 
## 
 
关于运行
♢ argparse
## argparse：Python的标准库，用于处理启动脚本时输入的命令行参数。
- 输入命令行参数时通常有两种形式：
D:\1\test_Python>python test.py --test            # 只输入选项名
D:\1\test_Python>python test.py --test     1        # 输入选项名，并输入该选项的参数
  - 选项名通常还可使用简写（如果程序支持这种操作的话），比如--test/-t。
- 例如，在test.py中保存以下内容：
import argparse
parser = argparse.ArgumentParser(description="This script is use to test.")
# description是该脚本的说明信息，使用选项--help/-h时会显示出来
parser.add_argument("--test", "-t", help="just for test", action="store_true")
    # help是该选项的说明信息，使用选项--help/-h时会显示出来
    # action="store_true"表示当输入选项--test/-t时（不需要输入其值）会将args.test的值置为true
parser.add_argument("--level", "-l", type=int, default=0)
    # default=0表示该选项的默认值是0，而且限制输入值为int型

, required=True)
非必须参数才设置默认值

args = parser.parse_args()        # 将启动脚本时输入的命令行参数解析并保存到args中
print(args.test)                    # 获取选项test的值
print(args.level)                # 获取选项level的值
- 然后，在终端测试启动该脚本：
  - argparse会自动生成选项--help/-h的相应内容，可直接使用：
D:\1\test_Python>python test.py –h
usage: test.py [-h] [--test] [--level LEVEL]
This script is use to test.
optional arguments:
  -h, --help            show this help message and exit
  --test, -t            just for test
  --level LEVEL, -l LEVEL
  - 这里使用选项--test/-t时不需要输入其值。
D:\1\test_Python>python test.py --test
True
0
  - 这里使用选项--level/-l时需要输入该选项的值，除非不使用该选项（会用默认值）。
D:\1\test_Python>python test.py
False
0

D:\1\test_Python>python test.py --level
usage: test.py [-h] [--test] [--level LEVEL]
test.py: error: argument --level/-l: expected one argument

D:\1\test_Python>python test.py --level 1
False
1
## 
## 
## 
 
♢ pyinstaller
## pyinstaller：Python的第三方库，用于将Python脚本打包成可执行文件。
- 安装：pip install pyinstaller
- 例：
pyinstaller  D:\1\1.py     # 打包成一个文件夹，包含一堆运行库
-F                # 打包成一个可执行文件，体积较大
-w                # 启动程序时只显示GUI窗口，不打开一个终端窗口（针对Windows、MacOS的选项）
-p ./utils        # 指明寻找模块的路径（如果找不到该模块的话）
--icon 1.ico        # 设置程序的图标
  - 基于64位的Python解释器打包的可执行文件不能在32位的电脑上使用，但反之可以兼容。
  - 使用-w选项的话，如果启动程序失败，就看不到报错信息了。
  - build目录下的warn-*.txt文件中记录了找不到的模块，但那些模块可能不需要导入。
- 打包之后，会在当前目录下生成两个文件夹。
  - build：保存打包过程中的一些信息。
  - dist：保存打包结果。
- 
## 
## 
## 
 
其它模块
♢ functools
## functools：Python的标准库，提供了一些功能函数、装饰器。
## 
## class partial(func, *args, **keywords)
- 功能：给函数传入一些参数，装饰成一个新函数。又称为偏函数。
- 例：
>>> import functools
>>> def fun1(a, b, c=0, d=0):
...     print(a, b, c, d)
... 
>>> fun1_new = functools.partial(fun1, 1, 2, c=3)
>>> fun1_new
functools.partial(<function fun1 at 0x7f58aa51aa60>, 1, 2, c=3)
>>> fun1_new()
1 2 3 0
>>> fun1_new('c')            # 此时传入的位置参数会被赋值给参数c
TypeError: fun1() got multiple values for argument 'c'
>>> fun1_new(c='c')        # 以关键字的形式传入参数，就不会报错重复赋值
1 2 c 0
## 
## 
## 
 
进程和线程
## 进程：程序运行时的最小单位。
- 系统启动一个程序时，会为它创建至少一个进程，然后在该进程中运行至少一个线程。
进程像一个容器，用于容纳线程，线程才是实际干活的单位。
进程中第一个运行的线程称为主线程。

每个进程都可以创建子进程，它们是平级关系，属于同一个进程组。
当一个进程组中的所有进程都终止时，系统才会终止该进程组。

每个线程都可以创建子线程，它们是从属关系，属于同一个进程。
当一个线程终止时，系统会自动终止它的所有子线程。
当一个进程中的主线程终止时，系统就认为该进程已终止。

- 进程之间的通信媒介。
  - 文件
  - 管道
  - 共享内存
## 线程。
- 系统会为每个进程分配一个独立的资源空间，为每个线程分配CPU占用时间。
  - 同一进程中的各个线程会共享该进程的全部资源，共用一个堆（因此可通过全局变量进行通信），但是有各自的栈。
- 使用多线程的优点是，可以利用CPU的空闲时间（比如在一个线程等待IO时，运行其它线程）。
  - 线程数过多会导致切换线程的开销过大，得不偿失。
  - CPU在切换进程时，不仅需要切换运行的线程，还需要切换内存、堆栈等资源。比在同一个进程中切换线程的开销更大。
- CPU的运行速度远快于磁盘、网络等IO速度，因此在进行IO操作时，经常会浪费CPU的等待时间。
  - 同步IO：在执行IO操作时程序保持等待，即同步运行。
  - 异步IO：在执行IO操作时程序转去执行其它操作，即异步运行。
- 线程之间的通信媒介。
  - 全局变量
  - 
- 线程之间的通信方式。
  - 轮询（poll）：主线程循环去检查子线程的状态，这会浪费一些主线程的时间，
  - 回调（callback）：子线程执行结束后调用主线程的一个函数或方法。
## 创建子进程、子线程时，可以把它们设置成daemon，即后台运行。（此daemon不是指守护进程）
- Python创建的子进程、子线程默认是非daemon。
- 创建一个daemon之后，就不必考虑如何让它结束。
  - 当一个进程组中的所有非daemon进程结束时，系统会自动终止所有daemon线程，然后结束该进程组。
  - 当一个进程中的所有非daemon线程结束时，系统会自动终止所有daemon线程，然后结束该进程。
## 结束子线程的方法。（对子进程同理）
- 由主线程控制何时停止子线程。
  - 永远不要强制杀死子进程，应该让它自己自愿结束，清理自己占用的资源。因为子线程可能正在执行一些不宜中断的操作，比如拿到了某个资源的锁、打开了某个文件还没有关闭、创建了孙线程还没有关闭。
  - 当主进程异常终止时（比如被kill -9），子进程就会变成没人管的孤儿进程。
- 把子线程设置成daemon，当主进程退出时它们就会被系统自动终止。
- 让子线程自己判断是否要结束运行。
  - 这样子线程的独立性强。
- 等子线程处理完所有业务，运行结束。
  - 这需要事先确定子线程不会无限运行。
## 线程安全：运行多线程时，多个线程的运行顺序无法确定（这取决于CPU的调度），因此要考虑以下问题。
- 一个线程在执行任务时可能被其它线程打断。
  - 可以阻塞其它线程，先让该线程运行完该任务。
- 一个线程在访问共享资源时，该资源可能被其它线程修改。
  - 可以给该资源上锁，保证同时只被一个线程访问。
## CPython早先引入了GIL（Global Interpreter Lock，全局解释锁）机制。
- 为了保证多线程之间不冲突，同一时间只有一个线程拿到GIL运行，当该线程暂时不用执行字节码时（比如等待IO响应时）就会把GIL传递给其它线程，或者隔一小段时间后解释器会抢走这个GIL给其它线程（这可能中断正在执行的某个任务，所以以防万一，还是要加锁来保证线程安全）。
- 由于GIL机制，CPython程序同时只能使用CPU的一个核。因此，处理IO密集型任务时，用多线程能提高效率；处理CPU密集型任务时，用多进程或协程才能提高效率。
## 
## 
## 
 
♢ threading
## threading：Python的标准库，用于创建多线程。
## 第一种创建线程的方法：直接调用类Thread()。
- class Thread(group=None, target=None, name=None, args=(), kwargs=None, daemon:bool)
  - 功能：定义一个线程。
  - group是线程组（目前尚未实现），target是要在线程中运行的函数，name是线程名，args是传递给线程函数的参数（必须是tuple型）。
  - 调用Thread.run()方法时，会在系统中创建该进程，分配资源，并调用Thread.start()方法开始运行。
  - 例：
>>> import threading
>>> def fun1(string):
...     print(string)
...
>>> t1 = threading.Thread(target=fun1, args=("Hello",))
>>> t1.start()        # 启动线程
Hello
  - Thread.start()方法会在系统中创建一个进程，分配资源，并调用Thread.run()方法。
  - Thread.run()方法定义了该线程的运行内容（即运行target函数）。
  - 每个线程只能调用一次start()方法，否则会报错。
- 查看线程的信息。
>>> t1.getName()        # 获得线程的名字
'Thread-1'
>>> t1.setName("t1")    # 设置线程的名字
>>> t1.isAlive()        # 判断线程是否正在运行
False
- 关于daemon线程。
>>> t1.isDaemon()                # 判断t1是否为daemon线程
>>> False
>>> t1.setDaemon(True)        # 将t1设置成daemon线程（必须在线程启动之前设置daemon属性）
RuntimeError: cannot set daemon status of active thread
- 阻塞线程。
>>> t1.join()            # 使CPU只运行该线程，阻塞其它线程的运行
>>> t1.join(3)            # 使CPU只运行该线程，最多持续3秒（t1可能提前运行结束）
- 关于多线程。
>>> threading.current_thread()        # 返回当前所在的线程对象
<_MainThread(MainThread, started 140176114464576)>
>>> threading.current_thread().getName()
'MainThread'
>>> threading.active_count()            # 返回当前运行的线程总数
2
>>> threading.enumerate()                # 列出当前运行的所有线程对象
[<_MainThread(MainThread, started 140176114464576)>, <Thread(Thread-1, started 140175977273088)>]
  - 调试运行时，会创建几个额外的线程。
## 第二种创建线程的方法：继承threading.Thread类，重载其run()方法。
- 例：
>>> class myThread(threading.Thread):
...     def __init__(self, *args, **kwargs):
...         super().__init__(*args, **kwargs)    # 先调用super().__init__()进行初始化，再进行修改
...         self.name = kwargs.get("name")
...     def run(self):
...         print("Hello!")
...
>>> t1 = myThread(name="t1")
>>> t1.start()
Hello!
## 线程的锁。
- threading.Lock()：互斥锁。获得后使系统只运行当前线程，阻塞其它线程的运行。
>>> lock = threading.Lock()
>>> lock.acquire()        # 请求获得锁，这会阻塞当前线程，直到请求成功
True
>>> flag1 = True
>>> lock.release()        # 释放锁
  - 互斥锁同一时间只能被一个线程获得。
  - 死锁：线程请求获得锁时，锁一直没有释放，导致线程一直在等待。
例如：如果一个线程在获得锁之后没有释放就再调用acquire()方法，就会一直等待获得锁，陷入死锁。
- threading.RLock()：可重入锁。
  - 可重入锁可以重复获得，只不过调用了多少次acquire()就得调用多少次release()才能完全释放该锁。
>>> rlock = threading.RLock()
>>> rlock.acquire()
True
>>> rlock.acquire()
True
>>> rlock.release()
>>> rlock.release()
>>> rlock.release()
RuntimeError: cannot release un-acquired lock
## 定时任务。
- class Timer(interval, function, args=None, kwargs=None)
  - 功能：定义一个线程，在interval秒之后执行function函数。
  - 只不过是延迟启动一个线程，不适合处理大量的、频繁的定时任务。
  - 例：
>>> t = threading.Timer(3.0, print, ('hello',))
>>> t.start()        # 启动线程
>>> hello

>>> t.cancel()        # 取消该进程
## 
## 
## 
 
♢ queue
## queue：Python的标准库，用于创建线程间通信的队列。
- queue模块提供了三种队列，都是基于生产者-消费者模式，自身实现了线程锁，是线程安全的。
## class Queue(maxsize: int)
- 功能：创建一个先进先出队列（FIFO）。
  - maxsize表示该队列的最大容量，当maxsize<=0时容量为无限大。
- 例：
>>> from queue import Queue
>>> q = Queue(10)
>>> q.qsize()            # 返回队列此时的大小（不可靠，队列的大小可能转瞬就变）
0
>>> q.empty()            # 判断队列是否为空
True
>>> q.full()                # 判断队列是否满了
False
- Queue.put(item, block=True, timeout=None)
  - 功能：往队列中写入一个元素（可以是任意类型）。
  - 当队列满了时，写入操作会一直阻塞，直到队列中有元素被消费掉。
如果block=False，则不阻塞，直接抛出queue.Full异常。
如果输入了timeout参数，则最多阻塞timeout秒，然后抛出异常。
  - 例：
>>> q.put(0)
>>> q.put("Hello", block=False)
>>> q.put([1, 2, 3], timeout=1)
- Queue.get(block=True, timeout=None)
  - 功能：从队列中取出一个元素。
  - 当队列为空时，读取操作会一直阻塞，直到队列中写入了新元素。
如果block=False，则不阻塞，直接抛出queue.Empty异常。
如果输入了timeout参数，则最多阻塞timeout秒，然后抛出异常。
  - 例：
>>> q.get()
0
>>> q.get(block=False)
'Hello'
>>> q.get(timeout=1)
[1, 2, 3]
## class LifoQueue(maxsize=0)
- 功能：创建一个后进先出队列（LIFO）。
- LifoQueue继承自Queue类，因此可使用同样的方法进行操作。
## class PriorityQueue(maxsize: int)
- 功能：创建一个优先级队列（Priority）。
  - 基于heapq模块的heappush()和heappop()实现，只不过加上了线程锁。
- PriorityQueue也继承自Queue类，因此可使用同样的方法进行操作。
  - 不同之处在于，写入的元素需要实现__lt__()方法，从而可以被sorted()排序。
- 例：
class Item:
    def __init__(self, priority, data):
        self.priority = priority
        self.data = data
    
    def __lt__(self, other):
        return self.priority < other.priority

>>> from queue import PriorityQueue
>>> q = PriorityQueue()
>>> q.put(Item(1, "one"))
>>> q.put(Item(3, "three"))
>>> q.put(Item(2, "two"))
>>> q.get().data
'one'
>>> q.get().data
'two'
>>> q.get().data
'three'
## 
## 
## 
 
♢ multiprocessing
## multiprocessing：Python的标准库，用于创建多进程。
- class Process(group=None, target=None, name=None, args:Iterable, kwargs:Mapping[Any, Any], daemon:bool)
  - 功能：定义一个进程。
  - 例：
>>> import multiprocessing
>>> p = multiprocessing.Process(target=print, args=('hello',))
>>> p
<Process(Process-1, initial)>
>>> p.start()
>>> hello
  - 进程的方法。
>>> p.is_alive()
False
>>> p.join(1)
>>> p.terminate()        # 强制终止进程
>>> p.terminate()        # 重复终止不会报错
  - 进程的属性。
>>> p.daemon
False
>>> p.exitcode
0
>>> p.name
'Process-1'
>>> p.pid
2798
## 进程池：用于限制进程的最大运行数量。当进程池满了时，新增的进程会被挂起，直到进程池有空位时才开始运行。
- 例：
>>> pool = multiprocessing.Pool(2)            # 创建一个大小为2的进程池（默认等于CPU核数）
>>> for i in range(5):
...     pool.apply_async(fun1, (i,))        # 往进程池中添加进程
... 
0
1
2
3
4
>>> pool.close()        # 关闭进程池，不能再加入进程了
>>> pool.join()        # 阻塞当前进程，等pool里的进程运行结束（需要先调用close()方法）
- def apply_async(func, args=(), kwds={}, callback=None, error_callback=None)
  - 功能：异步地创建进程。
  - 调用apply_async()函数会立即完成，不会等子进程运行结束，不会阻塞当前进程。
## 进程之间的通信方式（Inter-Process Communication，IPC）。
- multiprocessing模块提供了进程之间通信的队列Queue类，用法与queue模块相同。
>>> q = multiprocessing.Queue()
>>> q.put("hello")
>>> q.get()
'hello'
## 
## 
## 
 
♢ asyncio
## 协程：即协同程序，又称为异步函数。是指系统在执行某个函数时中断，转去运行另一个函数。
- 协程可以达到多线程并行工作的效果，但它依然是在一个线程内运行，不用担心线程安全，而且比切换线程的开销小很多。
- 协程常用于实现异步IO。
## Python中可以用async关键字创建协程，使用await关键字实现异步工作。
- Python的协程是通过生成器实现的。
- await只能在async函数中使用。
  - await只能调用实现了__await__()方法的对象。
## asyncio：Python的标准库，提供了异步IO的方法。
>>> import asyncio
>>> async def fun1(n):
...     for i in range(n):
...         await asyncio.sleep(1)        # 表示这里要等待1秒的IO，让解释器去执行event_loop中的其它协程
...         print(i)
... 
>>> loop = asyncio.get_event_loop()    # 创建事件循环
>>> loop.run_until_complete(fun1(5))    # 开始事件循环
0
1
2
3
4
- async函数不能直接使用，直接调用会返回一个coroutine对象。
>>> fun1(5)
<coroutine object fun1 at 0x7f79d8348a40>
- 可以在event_loop中加入多个任务。
>>> tasks = [asyncio.ensure_future(fun1(i)) for i in [2, 3, 3]]
>>> loop.run_until_complete(asyncio.wait(tasks))
0
0
0
1
1
1
2
2
({<Task finished coro=<fun1() done, defined at <stdin>:1> result=None>, <Task finished coro=<fun1() done, defined at <stdin>:1> result=None>, <Task finished coro=<fun1() done, defined at <stdin>:1> result=None>}, set())
## 
## 
## 
 
访问文件
## 类Unix平台、Web使用正斜杠 / 作为路径分隔符，而Windows使用反斜杠 \ 作为路径分隔符（在字符串中出现时要转义或者加上前缀r）。
- Python访问某个路径时可以用正斜杠也可以用反斜杠，比如"C:/"、"C:\\"、r"C:\"。
## 访问文件的方式。
- 二进制流
  - 所有文件都是以二进制的形式存储的，因此以二进制的形式可以直接读写所有文件。
- 字符流：以字符为单位读写文件。
  - 需要先读取文件的二进制内容，再按某种编码方式转换成字符流。
## 序列化（serialization）：将数据转换成可传输、可存储的数据类型的过程。
- 序列化时，一般先将数据转换成XML、JSON等通用的文本格式，再按某种编码格式转换成二进制形式。
- 反序列化是指相反的过程。
## 
## 
## 
 
打开文件
## 访问文件时，首先要用open()打开文件创建一个指向文件的变量f，然后就能调用f的各个方法。
- def open(file, mode='r', encoding=None, newline=None)
  - 功能：打开文件，返回一个文件流对象，可以对它进行读写。
  - 参数encoding表示编码格式（只在text mode下有效）。
不指定encoding时会尝试用utf-8、gbk等常见的编码格式解析文件内容。
  - 参数newline表示换行符（只在text mode下有效）。
读取文件时，如果newline=None，则会把文件中的'\r'、'\n'、'\r\n'都识别成换行符，统一转换成'\n'之后再返回。如果指定了newline，则只会识别这种换行符。
写入文件时，如果newline=None，则会把待写入字符串中的'\n'都转换成当前系统的默认换行符再写入文件。如果指定了newline=''或'\n'，则不会进行转换。如果指定了其它字符作为newline，则会把字符串中的'\n'都转换成该字符。
  - 例：
f = open("1.txt",'r')
for line in f:            # 用for语句遍历文本时，每次读取一行，相当于file.readline()
print(line, end="")
f.close()                # 要记得用 close() 方法关闭文件
  - 打开文件时访问指针会放在文件的开头，每次读写操作都会使访问指针移动位置，读取一行就移动一行。（用for语句遍历也会移动）读取到文件末尾后就读取不出内容了。
- 用with关键字可以进行上下文管理。如下，当Python解释器执行完with语句块或者抛出异常时，会自动调用f.close()完成清理。
with open("1.txt") as f:
    for line in f:
        print(line)
  - 相当于：
try:
    f = open("1.txt")
    ...
finally:
    f.close()
- 打开文件的模式。
  - r是只读模式，w是只写模式，实际上默认是rt、wt模式。
  - t是text mode(文本模式）。
  - a是追加模式，打开文件后指针放在文件末尾。（r和w打开文件后指针都放在文件开头，因此会覆盖原文件）
  - rb是以只读模式打开成二进制文本，wb是以只写模式写入成二进制文本，ab是以追加模式写入成二进制文本。
  - r+、w+、a+、rb+、wb+、ab+是读写模式。
## 文件类型对象的常用方法。
- 读取文件。
  - f.read(n=-1)                # 最多读取n个字节，返回一个字符串。如果n为负则读取所有字节
  - f.readline(n=-1)            # 读取一行，返回一个字符串（包括换行符'\n'）。最多读取n个字节
  - f.readlines(n=-1)        # 读取所有行，返回一个字符串列表。最多读取n个字节
- 写入文件。
  - f.write(str)                # 写入一个字符串，返回写入的长度
  - f.writelines(sequence)    # 写入一个字符串的序列（该序列中的元素必须都是字符串，且要自己加上换行符）
例：
>>> with open("1.txt",'w') as f:
...     f.writelines(["Hello\n","world\n",'!'])
...
>>> with open("1.txt") as f:
...     f.read()            # 读取文件的全部内容
...     f.seek(0)
...     f.readlines()        # 读取文件的全部内容
...
'Hello\nworld\n!'
0
['Hello\n', 'world\n', '!']
- f.flush()        # 刷新缓冲区，把缓冲区的数据立即写入文件
- f.next()            # 返回文件下一行的内容
- f.tell()            # 返回文件指针当前的位置（int类型的值），即位于第几个字符
- f.seek(offset: int, whence: int = 0)        # 设置文件指针的位置
  - offset表示开始的偏移量，即第几个字符（如果汉字采用同一编码，一个汉字也只占一个字符大小）。
  - whence是可选参数，值为0表示从文件开头开始偏移，值为1表示从当前位置开始偏移，值为2表示从文件末尾开始偏移。
## 
## 
## 
 
编码格式
## 以下编码格式是代表某种字符集，规定了一个字符在存储时的二进制值是什么。
- Unicode（统一码、万国码）：给多国语言的字符规定了唯一编号（但并没有规定它们存储时的二进制值是什么）。
  - Unicode编码是4个16进制数，通常加上前缀“U+”或“\u”，写成文本的话就占6个字节。因此Unicode编码并不实用。
  - Unicode可以容纳多种主要语言的字符码，但是表示ASCII码字符时，高字节全为零，浪费了存储空间，比如'A'表示成“U＋0041”。

如果一个字符的编码值超过一个字节，则称为宽字符。
- UTF-8：一种基于Unicode的编码格式，但更实用。
  - UTF-8的编码长度可变（可用1~6个字节），比如存储ASCII码字符时只用1个字节，存储中文字符时用3个字节，这样比Unicode编号更节省存储空间。
  - 与UTF-8同系列的还有UTF-16、UTF-32。
- BIG5：一种流行的中文繁体编码格式。
- GBK：一种流行的中文简体编码格式。
  - GBK是GB2312的超集，字符更多。
  - GBK将中文、英文字符都用2个字节存储。
- ISO-8859-1：属于单字节编码，只收录了英语、希腊语、阿拉伯语等字符，向下兼容ASCII码。
  - 它用到了单字节的所有编码，因此使用ISO-8859-1处理其它编码格式的字节流时并不会有遗漏。
## 以下编码格式不是代表某种字符集，只是对采用ASCII码的字符串进行处理，以便于网络传输。
- URLencode：将字符串转换成URL格式。
  - 如果有键值对参数，把每对参数用 = 连接、键值对之间用 & 分隔。
  - 按照RFC 3986规范：只保留数字、英文字母和十一种符号（ ~@$&=+,;:/? ），其它字符都转换成百分号 %加两位16进制编码。比如空格要转换成 %20。
- Base64：将字符串转换成最多64种字符。
  - 转换原理：每次从原数据中取出3个字节，拆分成4组，每组6个bit。然后在每组之前补上00凑成8个bit，最终得到了4个有64种可能取值的字符。如果原数据末尾不足3个字节，则用1个或2个 = 补齐。
  - 标准的Base64表包含了26个大写字母、26个小写字母、10个数字、2个特殊字符 + / ，主要用于转义非ASCII字符、不可打印的ASCII字符。
- Quoted-printable（可打印字符引用编码）：将字符串转换成只剩可打印字符。
  - 转换原理：将原数据中的每个非可打印字符用两个十六进制数表示，并加上等号 = 作为前缀。另外，每行最多有76个字符，超过该长度则插入 = 作为分行符。比如 "=" 要转换成 "=3D"。
  - 常用于编码邮件内容。
## 打开文件时，如果采用的编码格式与其实际编码格式不一致，得到的字符串就会出现乱码。
- Python中用open()打开一个文件时会自动猜测其编码格式，但最好指定按某个编码格式打开该文件，如下：
open(path, 'r', encoding="utf-8")
- 编程时，源文件一般采用utf-8编码，于是Python自动按utf-8格式打开源文件。但是源文件中可能包含中文注释，当Python读取到这一行时就会出错。
- 如果只需要拷贝文件的数据，以二进制形式打开文件最简单，这样就不用考虑编码格式的问题。
## 
## 
## 
 
♢ chardet
## chardet：Python的第三方库，用于检测bytes对象采用的字符集编码格式。
- 其原理是通过比对各种字符集的特征字符来猜测编码格式。
  - 检测的数据量太少就容易猜错。
  - 不能处理string对象，因为string已经是按Unicode格式编码了。
- 例：
>>> chardet.detect(b"Hello, world!")
{'encoding': 'ascii', 'confidence': 1.0, 'language': ''}    # confidence表示可信度，这里是100%
>>> chardet.detect("你".encode("GBK")))
{'encoding': None, 'confidence': 0.0, 'language': None}
>>> chardet.detect("你好".encode("GBK"))
{'encoding': 'TIS-620', 'confidence': 0.3598212120361634, 'language': 'Thai'}
>>> chardet.detect("你好，欢迎来到这里！".encode("GBK"))
{'encoding': 'GB2312', 'confidence': 0.99, 'language': 'Chinese'}
  - 最好把GB2312也当做GBK编码解码，以防chardet把GBK识别成GB2312。
- 也可以使用chardet直接检测一个文件，如下：
>>> f=open(path, 'rb')
>>> chardet.detect(f.read())["encoding"]
'GB2312'
## 
## 
## 
 
♢ base64
## base64：Python的标准库，提供了Base64格式的编码、解码方法。
- 用法：
>>> import base64
>>> b = base64.b64encode('hello'.encode())        # 从其它的bytes类型转换成Base64编码的bytes类型
>>> b
b'aGVsbG8='
>>> base64.b64decode(b)
b'hello'
## 
## 
## 
 
♢ quopri
## quopri：Python的标准库，提供了Quoted-printable格式的编码、解码方法。
- 用法：
>>> import quopri
>>> quopri.encodestring(b"hello world!==\r\n")
b'hello world!=3D=3D\r\n'
>>> quopri.decodestring(b"hello world!=3D=3D\r\n")
b'hello world!==\r\n'
## 
## 
## 
 
♢ pickle
## pickle：Python的标准库，可以将Python中任意类型的对象序列化成二进制形式。
- 没有保存成XML、JSON等通用的文本格式，因此只能被Python读取。
- 序列化：
>>> import pickle
>>> class Test:
...     a = 1
...     b = 2
... 
>>> data = pickle.dumps(Test())        # 序列化
>>> data
b'\x80\x03c__main__\nTest\nq\x00)\x81q\x01.'
>>> with open('dumps', 'wb') as f:
...     f.write(data)
... 
24
- 反序列化：
>>> with open('dumps', 'rb') as f:
...     data = f.read()
... 
>>> data
b'\x80\x03c__main__\nTest\nq\x00)\x81q\x01.'
>>> pickle.loads(data)                # 反序列化
<__main__.Test object at 0x7f82d2495710>
## 
## 
## 
 
文本处理
♢ fnmatch
## fnmatch：Python的标准库，可使用shell风格的通配符匹配字符串。
- def fnmatch(string, pattern) -> bool
  - 功能：判断string是否与pattern匹配。
  - 例：
>>> import fnmatch
>>> fnmatch.fnmatch("1.txt", "*.txt")
True
>>> fnmatch.fnmatch("1.txt", "?.txt")
True
>>> fnmatch.fnmatch("1.txt", "1.txt")
True
## shell风格的通配符。
- *    ：匹配零个或任意个字符。
- ?    ：匹配单个字符。
- [abc]：匹配abc中的任意一个字符。
- [a-z]：匹配a~z范围内的任意一个字符。
## 
## 
## 
 
正则表达式
## 正则表达式（regular expression）是由普通字符和特殊字符（称为元字符）组成的文字模式（pattern），用于匹配字符串中符合描述的片段。
- 正则表达式只能用于查找字符串的某个片段，不能进行增、删、改，这些功能应该由各种语言中的字符串处理函数实现。
- 普通字符：泛指没有声明为元字符的所有字符。包括非打印字符，比如：
  - \r    ：匹配回车符。
  - \n    ：匹配换行符。
  - \t    ：匹配制表符。
  - \f    ：匹配换页符。
  - \s    ：匹配任何空白字符。
  - \S    ：匹配任何非空白字符。
- 元字符
  - .    ：用于匹配除换行符 \n 以外的任何字符。
  - \    ：用于标记一个转义字符或向后引用（前提是匹配到了多个子串）。
  如果要匹配元字符所占符号，需要加上反斜杠进行转义。比如 \\ 匹配 \ 。
      \d        匹配一个数字，相当于[0-9]。
      \D        匹配一个非数字，相当于[^0-9]。
      \w        匹配一个字母、数字、下划线，相当于[A-Za-z0-9_]。
      \W        匹配一个非字母、数字、下划线的字符，相当于[^A-Za-z0-9_]。
  - |    ：表示匹配前面的元素或后面的元素。例如 (go.*\b)|(bed\b)。
  - ()    ：用于构成元素组。
>>> re.findall(r"(as)asd","asasd")    # 有小括号时，只会返回小括号内元素组的匹配结果
['as']
>>> re.findall(r"((as)as)","asasd")    # 有多个小括号时，它们的匹配结果会分别返回
[('asas', 'as')]
>>> re.findall(r"(as)|(d)","asasd")
[('as', ''), ('as', ''), ('', 'd')]
# 只要 | 前后有一个元素匹配成功，就返回一个值，因此另一个元素的返回值一定为空
  - []    ：用于构成字符集。例如，[Pp]ython匹配Python或Python。
      如果 . 在中括号内，则只匹配小数点字符 . ，相当于 \. 。
      如果 ^ 在中括号内的开头位置，表示不匹配中括号内的元素。例如[^0-9]表示不匹配数字。
      中括号表达式只匹配单个字符，例如"[A-Za-z]"匹配"good"中的"g"、"o"、"o"、"d"。
      如果要在中括号内匹配连字符 - ，需要用 \- 转义，或放在要匹配的字符范围之外，比如"-0-9-"。
  - {}    ：用于构成限定符表达式。
## 元字符中的限定符。
- 限定符用于限定前面一个元素的匹配次数。
  - *    ：匹配前面的元素任意次（包括0次）。
  - +    ：匹配前面的元素至少一次。
  - ?    ：匹配前面的元素至多一次。
>>> re.findall(".*3","123123123")            # *、+ 是贪心模式，会尽量匹配最多次
['123123123']
>>> re.findall(".*?3","123123123")            # 把 ? 放在 * 、+ 限定符之后，就会变成非贪心模式
['123', '123', '123']
- 用 { } 可以标记一个限定符表达式。
  - {n}        ：匹配n次。
  - {n,}        ：匹配至少n次。
  - {n,m}    ：匹配至少n次、至多m次。（要求n、m都是非负整数，且n<=m。另外，逗号前后不能随便加空格）
  - 例如：
>>> str1="bed"
>>> re.findall(r"e{2}",str1)
[]
>>> re.findall(r"e{2}","beeeed")
['ee', 'ee']
>>> re.findall(r"e{2,}","beeeed")
['eeee']
- 例如：
<.*>            匹配从 < 到 > 之间的所有内容。
[1-9][0-9]    不匹配个位数，只匹配两位数。比如匹配"120"中的"12"，匹配"1200"中的"12"、"00"。
[1-9][0-9]*    不匹配 0 ，匹配任意正整数，即左边第一位只能是1~9，右边可以是任意位0~9。
[1-9][0-9]?    只匹配1~9、10~99，适合用于匹配常见的数字，相当于[1-9][0-9]{0,1}。
[0-9]{1,4}    匹配至少一位、至多4位0~9。比如匹配"120000"中的"1200"和"00"。
## 元字符中的定位符。
- 定位符用于将正则表达式对齐到字符串的边界位置。
  - ^    ：匹配字符串的开始位置。
  - $    ：匹配字符串的结束位置。
  - \b    ：匹配单词的前边界或后边界，可以是单词与空格、()、\n等特殊字符之间的位置。
  - \B    ：匹配非单词边界，即其它的任何边界。
>>> re.findall(r"\bp","--Python")
['p']
>>> re.findall(r"\Bp","--Python")
[]
>>> re.findall(r"\bp","123Python")
[]
>>> re.findall(r"\Bp","123Python")
['p']
- 不能用限定符修饰定位符，因为边界位置只能有一个。
- 例如：
"\bgo"        匹配"good"、"very good"中的"go"，不匹配"verygood"。
            如果把\b换成空格，即改成" go"，则不会匹配"good"。
"\Bgo"        匹配"verygood"中的"go"，不匹配"very good"。
"\bgo.*\b"    匹配"good girl"中的"good girl"。可看做匹配go之后再匹配*个任意字符，匹配*个后才截止。
            （实际上不会截止，不会考虑到\b）
## 
## 
## 例子。
- ^[A-Za-z]\w{7,19}$
检验一个密码，必须以字母开头，可包含字母、数字和下划线，长度为8~20位。
如果匹配结果为[]，说明该字符串不符合要求。
- ^[\u4e00-\u9fa5]*$
检验一个中文名，只能使用汉字。由于用 ^ 和 $ 限定了头尾位置，所以不能出现任何非汉字的字符。
    例如，它匹配"中国"，但不匹配"中国1"、"中1国"。
- 检验一个时间字符串。
>>> str1=r"([0-1]?[0-9]|2[0-3])h:([0-5][0-9])m:([0-5][0-9])s"
>>> re.findall(str1,"12/14/18   14h:24m:08s")
[('14', '24', '08')]
- 收集时间数据，当数值超过时分秒的正常范围时也提取，当缺少数值时才不提取。
>>> re.findall(r"(\d{1,2})h:(\d{1,2})m:(\d{1,2})s","12/14/18    h:18m:16s")
[]                # 因为没有用到 | ，所以只要有一个地方不匹配，结果就为空
## 
## 
 
♢ re
## re：Python的标准库，用于按正则表达式检索字符串。
- 一般的字符串处理调用字符串的方法即可，遇到复杂的匹配处理时再考虑使用正则表达式。
## re.compile(pattern[, flags])
- 生成一个正则表达式对象。
  - 常见的flags：
re.A：当pattern为str类型时，使 \b、\B、\d、\D、\w、\W 只匹配ASCII字符。
默认情况下，会匹配任何Unicode字符。因此设置re.A才是标准的正则匹配。

re.I：不区分大小写。
re.S：允许 . 匹配任何字符，包括换行符 \n 。

  - flags可以取多个值，用 | 隔开。
- 正则表达式对象具有match()、search()、findall()等方法，它们的形参类似于 .findall(self, string, pos=None, endpos=None)，可以设置检索的起始位置和结束位置。
- 例如：
>>> pattern1=re.compile(".*", re.I|re.S)
>>> pattern1
re.compile('.*', re.I|re.S)
>>> pattern1.findall("Hello!",2,4)
['ll', '']

>>> re.findall(r'\w', 'Hello你好')
['H', 'e', 'l', 'l', 'o', '你', '好']
>>> re.findall(r'\w', 'Hello你好', re.A) 
['H', 'e', 'l', 'l', 'o']

## re.findall(pattern, string, flags=0)
- 检索整个字符串，将所有匹配的子串组成一个list返回。
- 例如：
>>> re.findall(r"\d", "asAS\n")            # 匹配失败时返回一个空list
[]
>>> re.findall("(h)ell(o)","hello")        # 如果同一次匹配得到多个结果，则组成一个元组
[('h', 'o')]
>>> re.findall(r".", "asAS\n")            # 匹配单个字符，每个占list中的一项
['a', 's', 'A', 'S']
>>> re.findall(r".*", "asAS\n")            # 匹配整个字符串，但不匹配换行符 \n
['asAS', '', '']
>>> re.findall(r".*", "asAS\n", re.S)        # 匹配整个字符串，包括换行符 \n
['asAS\n', '']
## re.match(pattern, string, flags=0)
- 从字符串的开头开始匹配。相当于正则表达式前面加上了 ^ ，如果第一个字符不匹配就匹配失败。
## re.search(pattern, string, flags=0)
- 返回第一个成功匹配的match对象，匹配失败则返回None。
- 例如：
>>> result = re.search("as", "aisAS")
>>> type(result)
<class 'NoneType'>
>>> result = re.search("as", "aisAS", re.I)    # 使用re.I标识符
>>> result
<re.Match object; span=(3, 5), match='AS'>
>>> result.span()                            # 得到匹配的切片位置
(3, 5)
- 使用group()方法可以提取检索到的多个组。
>>> re.search("as(AS)","asasAS").groups()        # 返回各个组的匹配结果
('AS',)
>>> re.search("(as)(AS)ooo","asasASooo").group()# 返回整个正则表达式的匹配结果，等价于group(0)
'asASooo'
>>> re.search("(as)(AS) ooo","asasASooo").group(1)    # 返回第一个组的匹配结果
'as'
>>> re.search("(as)(AS)","asasAS").group(2)        # 返回第二个组的匹配结果
'AS'
>>> re.search("(as)(AS)","asasAS").group(3)
IndexError: no such group
## re.sub(pattern, replace, string, count=0, flags=0)
- 将string中匹配的部分换替换成replace。
  - 最多替换count次，count等于0时表示次数不限。


# 会替换匹配的整个字符串，而不管元素组。如下：
>>> re.findall(r'(l)\w', 'Hello World')
['l', 'l']
>>> re.sub(r'(l)\w', '*', 'Hello World')
'He*o Wor*'
>>> re.findall(r'((l)\w)', 'Hello World')
[('ll', 'l'), ('ld', 'l')]
>>> re.sub(r'((l)\w)', '*', 'Hello World')
'He*o Wor*'

## re.split(pattern, string[, maxsplit=0, flags=0])
- 用匹配的子串将string分割成多项，以list的形式返回。
  - 最多分割maxsplit次，maxsplit等于0时表示次数不限。
- 例如：
>>> re.split(r"\W+", "www.baidu.com")
['www', 'baidu', 'com']
## 例子。
- re.sub(r"# .*$",'', line)            # 删除某行的注释
- >>> re.sub('(\d{4})-(\d{2})-(\d{2})', r'\2/\3/\1', '2018-12-27')        # 修改时间的格式
'12/27/2018'                        # 这里用\2、\3、\1引用匹配结果中的第2、3、1个子串
## 
## 
## 
 
表格
♢ csv
## 将数据保存成表格时，可保存为CSV类型或Excel类型。
- CSV（Comma Separated Values，逗号分隔值）文件以纯文本的形式存储表格数据。
  - csv文件并没有明确的格式规定，不同来源的csv文件不一定能互通。
  - Python访问csv文件时可以像文本文件一样直接读写，例如f.write("path,content,total pings\n")，也可以导入内置的csv模块。
- xlsx文件是专有格式，只能用Excel软件打开，修改不自由。
  - 用Excel软件也可以直接打开 csv文件，还可以把 .xlsx文件保存成 csv文件。
  - 可使用第三方的xlrd和xlwt模块读写xlsx文件，其中xlrd用于读取（只读，不能修改），xlwt用于写入。
  - 还可使用读写功能都具备的openpyxl模块。
- 当csv文件的风格符合以下要求时，在Excel中显示的内容才会与xlsx文件一致。
  - 每行数据以换行符 '\r\n' 分隔，每行的各个字段以英文逗号 , 分隔。
  - 单个字段中如果出现了英文逗号、英文双引号，要用英文双引号把这个字符串包住，还要在其中的每个双引号前加上一个双引号进行转义。
  - 例如，用Excel编辑xlsx文件，写入如下三个单元格（每格之间用Tab分隔）：
1    A,B    A,"B"
用Excel将它保存为csv文件，用notepad++打开后的显示内容为：
1,"A,B","A,""B"""
用Python读取该csv文本，实际上每行末尾还有换行符（除非是最后一行）：
>>> with open("test.csv", newline="") as f:
...     f.read()
...
'1,"A,B","A,""B"""\r\n'
## csv：Python的标准库，用于读写csv文件。
- 写入的方法如下。
>>> import csv
>>> data = [["Hello world!"], [1, 2, 3, 4, 5], {'a': 1, 'b': 2, 'c': 3}]
>>> with open("test.csv", 'w', newline='') as f:# 设置newline=''，避免写入文件时自动转换换行符
...     csv_writer = csv.writer(f)                # 在文件流f上创建一个csv写入器
...     csv_writer.writerow("Hello")            # 写入一行，输入必须是可迭代对象
...     csv_writer.writerows(data)                # 写入多行，输入必须是可迭代对象
...
  - 检查保存结果：
>>> with open("test.csv") as f:
...     f.read()
...
'H,e,l,l,o\nHello world!\n1,2,3,4,5\na,b,c\n'
  - 用notepad++打开该文件，显示为：
H,e,l,l,o        # 直接拿一个字符串作为一行，转换成csv格式时就会被拆散成单个字符
Hello world!
1,2,3,4,5
a,b,c            # 这种情况下，字典只被保存了键名
- 读取的方法如下。
>>> with open("test.csv", 'r') as f:
...     csv_reader = csv.reader(f)        # 在一个可迭代对象（比如文件流、list）上创建csv阅读器
...     for line in csv_reader:        # 迭代csv_reader的内容
...             print(line)
...
['H', 'e', 'l', 'l', 'o']
['Hello world!']
['1', '2', '3', '4', '5']
['a', 'b', 'c']
  - 也可用csv.reader()直接解析csv格式的字符串：
>>> [i for i in csv.reader(["a,b,c\n"])]
[['a', 'b', 'c']]
## 用csv.writer()写入csv文件时，还可以选择csv风格，如下。
- csv.writer()的定义为csv.writer(fileobj [, dialect='excel']），其中dialect='excel'表示默认转换成excel的风格。
- 查看现有的所有dialect：
>>> csv.list_dialects()
['excel', 'excel-tab', 'unix']
  - 'excel'的定义为：
class excel(Dialect):
    delimiter = ','                # 一行中每个字段的分隔符
    quotechar = '"'                # 引用号，用于引用一个字段（避免被当作多个字段处理）
    doublequote = True            # 使用引用号时是否在字段的前后都加上引用号，还是只在前面加上引用号
    skipinitialspace = False        # 忽略分隔符delimiter之后的空格
    lineterminator = '\r\n'        # 分行符
    quoting = QUOTE_MINIMAL        # 控制何时使用引用号quotechar
# quoting 的取值：QUOTE_ALL表示引用所有字段，QUOTE_MINIMAL表示只引用包含特殊字符的字段
register_dialect("excel", excel)
  - 'excel-tab'与'excel'的区别在于：delimiter = '\t'
  - 'unix'与'excel'的区别在于：lineterminator = '\n'，quoting = QUOTE_ALL
- 自定义dialect的方法如下：
>>> class myDialect(csv.excel):
...     delimiter='|'
...
>>> csv.register_dialect("myDialect", myDialect)            # 登记自定义的dialect
>>> with open("test.csv", 'w', newline='') as f:
...     csv_writer = csv.writer(f, dialect='myDialect')        # 选择使用自定义的dialect进行写入
...     csv_writer.writerows(data)
...
>>> csv.unregister_dialect("myDialect")                    # 删除自定义的dialect
## csv模块还可专门读写字典格式的数据。
## 
## 
## 
 
♢ openpyxl
## openpyxl：Python的第三方库，用于读写xlsx/xlsm文件。
- 安装：pip install openpyxl
- 一般操作流程为：先打开Workbook（即工作簿），再定位Worksheet（即工作表），然后操作Cell（即单元格）。
- 如果要在Excel中插入图片，需要用到pillow库。
## 创建一个Excel表格。
>>> from openpyxl import Workbook        # 从openpyxl模块导入Workbook类，用于创建和写入表格
>>> wb=Workbook()                        # 创建一个工作簿对象
>>> wb.sheetnames                        # 列出所有工作表的名字，新创建的工作簿只有一个默认工作表
['Sheet']
>>> ws=wb.create_sheet("sheet1", 0)    # 在第一个位置插入新工作表。如果不指定位置就默认在最后插入
>>> #ws.title="Sheet1"                # 设置工作表的名字
>>> wb.save("1.xlsx")                    # 把工作簿保存为一个xlsx文件
>>> wb.close()                        # 关闭对该文件的占用，但该文件的内容仍然保留在内存中可以读取
- 保存工作簿时，如果存在同名文件，会直接覆盖而不会提醒。如果其它程序正在使用该文件就无法保存。
## 打开一个现有的Excel表格。例如，在工作表"Sheet1"中有如下数据。
 
>>> from openpyxl import load_workbook        # 从openpyxl模块导入load_workbook类
>>> wb=load_workbook("1.xlsx")
>>> wb.sheetnames
['Sheet1', 'Sheet2', 'Sheet3']
>>> ws1=wb[wb.sheetnames[0]]                # 用工作表的名字作为工作簿的键值，可得到该工作表对象的引用
>>> ws1
<Worksheet "Sheet1">
>>> ws1.max_row                            # 获得工作表的最大行数
4
>>> ws1.max_column                        # 获得工作表的最大列数
3
- def load_workbook(filename, read_only=False, keep_vba=KEEP_VBA, data_only=False, guess_types=False, keep_links=True)用于打开一个由filename指定的工作簿。
  - keep_vba=KEEP_VBA    表示保留所有Visual Basic元素。
  - data_only=False        表示当单元格中存在公式时，获得原本的公式，不会只读取公式的计算结果。（每次用Excel打开工作簿时会自动计算公式）
  - guess_types=False    表示读取单元格时，不猜测其数据类型。
  - keep_links=True        表示保留与外部工作簿的链接。
## 读写工作表的值。
- 遍历工作表：
>>> for row in ws1:                        # 遍历工作表的每行，ws1相当于ws1.rows
...     print(row)
...
(<Cell 'Sheet1'.A1>, <Cell 'Sheet1'.B1>, <Cell 'Sheet1'.C1>)
(<Cell 'Sheet1'.A2>, <Cell 'Sheet1'.B2>, <Cell 'Sheet1'.C2>)
(<Cell 'Sheet1'.A3>, <Cell 'Sheet1'.B3>, <Cell 'Sheet1'.C3>)
(<Cell 'Sheet1'.A4>, <Cell 'Sheet1'.B4>, <Cell 'Sheet1'.C4>)
>>> for row in ws1:                        # 遍历每行
...     for cell in row:                    # 遍历每行的单元格
...         print(cell.value, end="\t")        # 取得每个单元格的值
...     print('\n')
...
1       2       3

4       5       6

None    None    None                        # 单元格为空时，返回的值为None

10      11      12

>>> for row in ws1.values:                # 使用工作表的values属性遍历所有单元格的值
...     print(row)
...
(1, 2, 3)
(4, 5, 6)
(None, None, None)
(10, 11, 12)
>>> for x in range(1,11):                    # 通过cell方法遍历一个10行10列的区域，range从1开始
...     for y in range(1,11):
...             ws1.cell(x, y).value
...
（显示略）
- 工作表对象支持索引，用行名、列名或单元格的名字作为工作表的键值，从而访问指定的单元格。
>>> ws1['A']                    # 获得A列所有不为空的单元格的引用
(<Cell 'Sheet1'.A1>, <Cell 'Sheet1'.A2>, <Cell 'Sheet1'.A3>, <Cell 'Sheet1'.A4>)
>>> ws1['1']                    # 获得第1行所有不为空的单元格的引用
(<Cell 'Sheet1'.A1>, <Cell 'Sheet1'.B1>, <Cell 'Sheet1'.C1>)
>>> ws1['A1']                # 获得A1单元格的引用
<Cell 'Sheet1'.A1>
>>> ws1['A1'].value            # 通过单元格的 value 属性获得其值
1
>>> ws1['A1']=2                # 给单元格赋值时不需要指定 value 属性
- 工作表对象支持切片，可以访问某个范围的单元格。
>>> ws1['A1':'B2']
((<Cell 'Sheet1'.A1>, <Cell 'Sheet1'.B1>), (<Cell 'Sheet1'.A2>, <Cell 'Sheet1'.B2>))
- 使用工作表对象的 cell() 方法可以操作一个指定单元格，其原型为def cell(row, column, value=None)。
>>> ws1.cell(2,3)
<Cell 'Sheet1'.C2>
>>> ws1.cell(2,3,12)            # 通过 cell() 方法给单元格赋值
<Cell 'Sheet1'.C2>
>>> ws1.cell(2,3).value        # 使用cell()方法时，即使没有赋值，也会在内存中创建一个单元格，其值为None
12
>>> ws1.cell(2,3).coordinate    # 获得该单元格的坐标
'C2'
## 使用只读或只写模式可以节省占用的内存。
- 用wb = Workbook(write_only=True)可以创建一个只写的工作簿，它的内存开销很小。
  - 它不会创建一个默认的工作表，必须要主动创建。
  - 它只能通过 append() 写入数据。例如：
>>> from openpyxl.worksheet.write_only import WriteOnlyCell
>>> from openpyxl.styles import Font
>>> cell = WriteOnlyCell(ws, value="hello world")
>>> cell.font = Font(name='Courier', size=36)
>>> ws.append([cell, 3.14, None])
  - 这个被创建的只写工作簿只能被保存一次，否则会报错。（可以再创建一个新的）
## 其它笔记。
- 用工作表的append()方法可以在工作表后附加一个可迭代的对象，比如tuple、list、dict、range、generator，也可附加某个或某些单元格。例如：
>>> column1=ws1['A']
>>> ws1.append(column1)
>>> for i in ws1.values:
...     print(i)
...
(1, 2, 3, None)
(4, 5, 12, None)
(None, None, None, None)
(10, 11, 12, None)
(1, 4, None, 10)        # 附加一列会变成一行加在工作表的末尾，这里多出来一列，空白的单元格也会被创建
- 给单元格赋值时，可以输入Excel的公式，例如：ws1["D4"] = "=SUM(A1:C4)"
- 设置行高和列宽的方法：
ws1.column_dimensions['A'].width = 90        # 只写的表格要在写入内容之前设置列宽
ws1.row_dimensions[1].height = 20
- openpyxls提供了多种设置单元格样式的类。例如，下方是使用Font类。
from openpyxl.styles import Font
font1 = Font(name='Calibri',        # 字体
            size=11,                # 字号
            bold=False,            # 加粗
            italic=False,            # 斜体
            underline='None',        # 下划线
            color='FF000000'        # 字体颜色
            ...)
ws1['A1'].Font=font1
ws1['A2'].Font=font1
- 调用以下函数可以转换列的数字序号和字母序号。
>>> from openpyxl.utils import get_column_letter, column_index_from_string
>>> get_column_letter(2)
'B'
>>> column_index_from_string('AA')
27
## 
## 
## 
 
XML
## XML（可扩展标记语言）：一种保存结构化数据的文本格式，常用于不同编程语言之间的通信。可读性较差。
## 语法。
- 用 <!-- ... --> 声明注释。
- 可以在第一行声明XML的版本：
<?xml version='1.1' encoding='UTF-8'?>
- XML中的空格、换行符不会被忽略。
- 每个元素是用一对标签包住的值，格式如下：
<tag>value</tag>
  - tag、value都是字符串类型，但是不必加引号作为定界符。
  - 例：
<student>
<id>1</id>
<name>one</name>
</student>
- 标签用尖括号标记，必须成对出现。
  - 前一个标签称为开始标签，前一个标签称为结束标签。
  - XML的标签要区分大小写。
  - 可以在开始标签中加上属性。属性是键值对格式，值必须要用双引号包住。如下：
<note date="20191001" time="12:00">
Hello World
</note>
- 一个元素的value可以嵌套一个或多个子元素，构成层级结构。
  - 最外层的tag称为根元素。
## 
## 
## 

 
♢ xml
## xml：Python的标准库，用于解析XML格式的文本。
- 例：
>>> from xml.etree import ElementTree
>>> item = ElementTree.Element("test")        # 创建一个元素
>>> item
<Element 'test' at 0x7fe42c2d1e08>
>>> item.set("date", "20191001")            # 设置一个属性（没有该属性则添加）
>>> item.set("time", "12:00")
  - 查看元素的信息。
>>> item.tag            # 标签名，str型
'test'
>>> item.text        # 标签包住的文本（不是子元素），str型
'Hello World'
>>> item.attrib        # 标签中的属性，dict型
{'date': '20191001', 'time': '12:00'}
  - 关于子元素。
>>> sub = ElementTree.Element("sub")
>>> sub.text = "..."
>>> item.append(sub)        # 添加一个子元素（可以添加多个）
>>> item.append(sub)
>>> list(item)            # 列出所有子元素（item是可迭代对象）
[<Element 'sub' at 0x7efd36b9a278>, <Element 'sub' at 0x7efd36b9a278>]
>>> item.find("sub")        # 根据tag名查找一个子元素，返回第一个匹配的，没找到则返回None
<Element 'sub' at 0x7fe4247fb278>
>>> item.findall("sub")    # 根据tag名查找所有匹配的子元素，没找到则返回[]
[<Element 'sub' at 0x7fe4247fb278>, <Element 'sub' at 0x7fe4247fb278>]
>>> item.remove(sub)        # 删除一个子元素
>>> item.clear()            # 删除text、子元素、attrib
  - 与字符串的转换。
>>> ElementTree.tostring(item, encoding="utf-8").decode()    # 从XML对象转换成字符串
'<test />'                # 一个空的元素，只有tag名
>>> with open("1.xml") as f:
...   root = ElementTree.XML(f.read())        # 从字符串中解析出XML对象
... 
>>> root                    # 返回的是根元素
<Element 'flow-definition' at 0x7fe42c2f1a98>
## 
## 
## 
 
JSON
## JSON（JavaScript Object Notation）：一种保存结构化数据的文本格式。
- JSON原本是JavaScript的对象表示格式，后来发展成为一种独立于语言和平台的文本格式，常用于不同编程语言之间的通信。
- JSON、XML、YAML都是纯文本格式，用于保存、传输数据，方便程序使用。而HTML是用于显示数据给用户看。
## 语法。
- 用 // 声明单行注释。
- JSON中的数据采用键/值（key/value）对的格式表示，每个键值对之间用逗号隔开。
  - 键名放在双引号中，然后通过冒号连接其value。例如，JSON中的 "name" : "菜鸟教程"相当于JavaScript 中的name = "菜鸟教程"。
- key必须是字符串类型，而且不能重复。
- value可以是以下类型。
  - Number    ：整数或浮点数。
  - Boolean    ：取值为true 或 false。
  - String    ：用双引号包住。
  - Array    ：用中括号包住，有序地存储多个键值对。
  - Object    ：用花括号包住，无序地存储多个键值对。
  - null
- 例：
{
"id":1,
"enabled":true,
"payload": [
{ "name":"菜鸟教程" , "url":"m.runoob.com" }, 
{ "name":"google" , "url":"www.google.com" }, 
]
}
## 
## 
## 
 
♢ json
## json：Python的标准库，用于解析JSON格式的文本。
- def dumps(obj, skipkeys=False, ensure_ascii=True, check_circular=True, allow_nan=True, cls=None, indent=None, separators=None, default=None, sort_keys=False) -> str
  - 功能：将Python基本数据类型的对象转换成JSON格式的字符串。
  - 例：
>>> import json
>>> json.dumps(True)
'true'
>>> dict1={'a': 1, 'b': 2, 'c': 3}
>>> json.dumps(dict1)
'{"a": 1, "b": 2, "c": 3}'
  - ensure_ascii=True表示将输出的字符转换成ASCII码。
>>> json.dumps("你好")
'"\\u4f60\\u597d"'                            # Unicode字符会直接保存成显示的Unicode编码
>>> json.dumps("你好", ensure_ascii=False)        # 不转换ASCII码，继续使用Python的Unicode编码
'"你好"'
>>> json.dumps("你好", ensure_ascii=False).encode()
b'"\xe4\xbd\xa0\xe5\xa5\xbd"'
  - indent=None参数表示输出时不换行、不缩进。
>>> print(json.dumps(dict1, indent=4))        # 输出时换行，且缩进为4个空格
{
    "a": 1,
    "b": 2,
    "c": 3
}
- def loads(s, ...) -> object
  - 功能：将JSON格式的文本转换成Python的基本数据类型的对象。
  - s是一个str、bytes或bytearray对象，包含JSON格式的文本。
  - 例：
>>> json.loads("true")
True
>>> json.loads('{"你好":1}')
{'你好': 1}
>>> json.loads(json.dumps(dict1, indent=4))
{'a': 1, 'b': 2, 'c': 3}
>>> with open("test.json") as f:
...     jsons = json.loads(f.read())
...

## 使用json.dumps()时，会将Python中的基本数据类型转换成JSON中的数据类型。如下：
int, long, float —> number
str, unicode —> string
list, tuple —> array
dict  —> object
True  —> true
False —> false
None  —> null
## 
## 
## 
 
YAML
## YAML（/ˈjæməl/）：一种保存结构化数据的文本格式，比JSON更简单。
- YAML格式的文件的后缀名为 .yaml 或 .yml 。
## 基本语法。
- 用 # 声明单行注释。
- 用缩进（通常为两个空格，不能用Tab）表示层级关系。
- 可以在一个文件中写多个YAML文档，每个文档用 --- 声明开始、用 ... 声明结束。如下：
  ```yaml
  ---
  debug: true
  env: ‘test’
  server:
    - 10.0.0.1
    - 10.0.0.2
  ...

  ---
  debug: false
  env: ‘production’
  server: [10.0.0.1, 10.0.0.2]
  ...
  ```

- 区分大小写。
- 包含两种数据结构：
  - 键值对：以 : 连接。
  - 数组：写成 [x, x, x] 的格式，或者写成多行，每个元素以 - 开头。
- 常量的数据类型可以是：int、float、bool、null（用 ~ 表示）、string。
字符串可以用双引号包住，也可以用单引号包住（此时不能转义字符），甚至不用引号包住（此时YAML允许包含空格）。
- 例：
server:
    - name: www.test.com
    - ip: 192.168.0.1
DEBUG: true
  - 相当于Python中的["server":["name": "www.test.com", "ip": "120.168.117.22"], "DEBUG": "true"]


yaml模块
pip install pyyaml

写：
>>> data = {"k1": "v1", "k2": "v2"}
>>> yaml.dump(data, Dumper=yaml.CDumper)       # 从dict类型转换成YAML格式的字符串
'k1: v1\nk2: v2\n'
>>> with open("test.yml", 'w') as f:
...     yaml.dump(data, f, Dumper=yaml.CDumper)      # 转换成YAML格式并写入文件
...

读取：
>>> with open("test.yml") as f:
...     yaml.load(f.read(), Loader=yaml.CLoader)
...
{'k1': 'v1', 'k2': 'v2'}

## 
## 
 
Markdown
## Markdown是一种对纯文本进行简单排版的标记语言，可以被对应的Markdown编辑器识别并渲染显示。
- Markdown格式的文件的后缀名为 .md 。
- 其基本语法为：
  - 在文本中插入一个空行，显示时就会换行。
  - 输入多个空格时，只会显示一个空格。
  - 输入多个空行时，只会显示一个空行。
  - 在一个空行后输入三个减号 --- ，会显示成一条水平分隔线。
- Markdown兼容HTML的语法。
## Markdown的特殊语法。
- 标题：以井号 # 加空格开头。
  - 一个#是一级标题（最高级，是文档标题，一个文档中只能有一个），六个#是六级标题。
# 一级标题
## 二级标题
...
###### 六级标题
- 无序列表：每行以星号 * 、减号 – 或加号 + 加空格开头。
  - 可以在行首加上缩进，从而显示出多个层级。
* sentence
* sentence
  - sentence
  - sentence
    + sentence
    + sentence
- 有序列表：每行以阿拉伯数字加小数点加空格开头。
1. sentence
2. sentence
3. sentence
- 引用
  - 以大于号 > 开头时，会显示成单行引用。
  - 段首以四个以上的空格开头时，会显示成一个缩进的区块。
- 代码
  - 在字符串前后加上一个反引号 ` ，会加亮显示。如下：
请在终端输入命令`ls -l`
  - 在前后各加上三个反引号 ``` ，会显示成代码块。
  - 如果在开头加上编程语言的名称，就会显示成对应的颜色风格。如下：
```Python
print("hello")
```
- 链接
[一个超链接](https://www.baidu.com)
<https://www.baidu.com>

![一张图片](1.png)
![一张居中且限制尺寸的图片](1.png#pic_center =60x60)
- 斜体和粗体：在前后各加上星号 * 或下划线 _ ，如下：
普通字体
*斜体*，_斜体_
**粗体**，__粗体__
***斜粗体***，___斜粗体___
~~删除文本~~
- 表格
key|Value
-|-
a|1
b|2
c|3
- 扩展语法
[TOC]            # 显示目录
x^2^                # 上标
H~2~O            # 下标
==Notice==        # 高亮显示
## 
## 如果要显示MarkDown语法中的保留字符，则需要用反斜杠转义，如下：
\<  \*  \#
## 
 
数学分析
♢ decimal
## decimal：Python的标准库，用于进行极其精确的小数运算。
- 将float对象直接转换成Decimal对象会有误差，应该先将float对象转换成字符串，再转换成Decimal对象。
>>> from decimal import Decimal
>>> Decimal(0.1)
Decimal('0.1000000000000000055511151231257827021181583404541015625')
>>> Decimal("0.1") + Decimal("0.2")
Decimal('0.3')
- Decimal对象可以直接转换成字符串。
>>> str(Decimal("0.1"))
'0.1'
- Decimal对象的有效位数默认为28。
>>> from decimal import Decimal, getcontext
>>> getcontext().prec
28
>>> getcontext().prec = 4            # 设置有效位数
>>> Decimal("0.1") / 3
Decimal('0.03333')
>>> Decimal("0.1234567") / 1        # 超出有效位数时，会自动四舍五入
Decimal('0.1235')
## 
## 
## 
 
♢ math
## math：Python的标准库，提供了开方、正弦、阶乘等基本的数学函数。
## 
## 
## 
## 
## 
## 
## 
## 
## 
## 
 
♢ NumPy
## 
## 
## 
## 
## 
## 
## 
## 
## 
## 
## 
 
♢ sympy
## 
## 
## 
## 
## 
## 
## 
## 
## 
## 
## 
 
♢ matplotlib
## Matplotlib：Python的第三方库，仿制了许多matlab的绘图函数。
- 安装：pip install Matplotlib
- 例：
from matplotlib import pyplot, image

img = image.imread(r"C:\Users\Leo\Desktop\IMG_1.jpg")
p1=pyplot.imshow(img)
pyplot.show()        # 用matplotlib的绘图板显示该图片
pyplot.axis("off")    # 不显示绘图板上的坐标线
- 创建图像实例：
plt.figure("test1")        # 创建一个图像窗口，并设置其标题名
f1 = plt.figure("test1")    # 再创建一个图像窗口
# 如果该窗口与test1重名，则不会新建该窗口，而是返回同一个实例的引用
plt.close()                 # 关闭当前的figure，这会销毁这个对象
plt.close(f1)            # 关闭指定的figure
plt.close("all")            # 关闭所有figure
plt.cla()                # 对当前figure中的所有坐标轴执行axes.cla()，清除其中的图像
plt.clf()                 # 清除当前figure中的所有坐标轴
## 绘制折线图。
import matplotlib.pyplot as plt

plt.title("Simple Plot")        # 设置图像窗口的标题名
plt.xlabel("X", fontsize=16)    # 设置x轴的名字及其字体大小
plt.ylabel("Y")
# plt.axis([0, 10, 0, 1])        # 设置x轴和y轴的长度（如果设置了，显示时窗口比例会固定，否则会自动调整）
# plt.tick_params(axis="both", labelsize=10)  # 选择显示两条坐标轴，并设置坐标轴数字的大小

list1 = range(1, 11)
list2 = range(11, 21)
line1 = plt.plot(list1, list2, label="test1")# 绘制一条折线，list1、list2分别表示各个点的x轴、y轴坐标
plt.plot(list2, list1, label="test2", linewidth=3, color="blue")  # 绘制第二条折线
plt.plot(list1, list2, linestyle="-", marker="*")    # 把线型改为''，即可绘制散点图
# 可选参数：
# label        ：线条的标签名
# linewidth    ：线条的宽度
# color        ：线条的颜色，可使用十六进制的颜色值，比如"# 008000"
# linestyle    ：线型
# marker        ：每个点的标记符号

plt.legend()                    # 创建图例（图例是图像上的说明信息，这里是提取每个折线的label）
# plt.legend("upper left")    # 将图例放在图像的左上方

# plt.grid(True)        # 显示网格线

plt.savefig("test1.png")    # 保存图像

plt.show()          # 显示该图像

- plt.show()会阻塞线程，可使用plt.ion()打开交互模式，执行plt.plot()时就会立即显示图像，但是显示一瞬间之后就会消失，因此要用plt.pause()维持图像的显示，如下：
plt.ion()
last_dot = [0, 0]
for i in range(100):
    new_dot = [i, random.randint(0,10)]    # 设置当前点的坐标
    plt.plot([last_dot[0], new_dot[0]], [last_dot[1], new_dot[1]], color="blue")
            # 每次循环绘制的是一条新线段，颜色随机，这里给它们设置统一的颜色
    last_dot = new_dot
    plt.pause(0.1)
  - 或者关闭交互模式再用plt.show()持续显示图像，如下：
plt.ion()
plt.plot(list1, list2, label="test1")
plt.ioff()    # 关闭交互模式
plt.show()
## 
## 
## 绘制动态图：https://blog.csdn.net/rumswell/article/details/11731003
## mpl_toolkits库用于绘制三维图，参考：https://blog.csdn.net/chi_wawa/article/details/68062506
## 
## 
 
图片处理
## 电子图片的基本属性。
- 分辨率。
  - 可以用（水平像素数×垂直像素数）表示，即图片的长宽是多少个像素点。
  - 也可以用DPI（Dots Per Inch）、PPI（Pixels Per Inch）表示，即每英寸内有多少个像素点。
- 位深度：指图片中的每个像素点用几个二进制位表示。这些二进制位有多少种取值，就能存储多少种颜色。
  - 位深度可取值为1、4、8、16、24、32。
  - 位深度为1 bit时，只能存储黑白两种颜色。
  - 位深度为8 bit时，可以存储256种颜色。
  - 位深度为24 bit时，可以存储2563种颜色。
- 颜色模式。
  - 黑白图    ：位深度为1 bit，由一排排0、1的二进制位组成。
  - 灰度图    ：位深度为8 bit，只有一个灰度通道，用0~256表示黑色、白色以及中间的254种灰色。
 灰度图转换成黑白图时，通常选择128作为阙值，如果一个像素点的灰度值大于等于阙值，则记作1（即白色），否则计0（即黑色）。
  - 索引颜色    ：位深度为8 bit，将图中的颜色数减少到256种以内，把它们记在一个调色板上，然后记录图中的每个像素点采用编号0~256中的哪种颜色。这样能减少图片体积，但是能表示的颜色数量有限。
  - RGB        ：位深度为24 bit，又称为真彩色，有RGB三个通道，每个通道占8 bit。
  - RBGA        ：位深度为32 bit，多了一个描述透明度的Alpha通道，每个通道占8 bit。
  - CMYK        ：位深度为32 bit，印刷时采用的颜色模式，有CMYK四个通道。
CMYK印刷品是通过反光来显示的，而RGB图片是通过主动发光来显示的，两者存在不可避免的色差。
- 图片体积：即图片占用的存储空间。
  - 比如一张分辨率为1080×720、位深度为24 bit的图片，其理论体积为：1080×720×(24/8)≈2.2MB。
- 压缩方式。
  - 不压缩：不压缩图片的体积，直接保存原图。
  - 无损压缩：可以压缩图片的体积，且压缩时没有损失图片的任何质量。
  - 有损压缩：可以压缩图片的体积，但压缩时降低了图片的质量。压缩率越高，画质越差。
## 图片格式。
图片格式    JPG/JPEG    PNG    GIF    BMP
位深度    最高为24 bit    最高为32 bit    最高为8 bit，画质差    最高为32 bit
图片体积    较小    较大    很小    很大
能否压缩    有损压缩，压缩率可以很高
（通过舍弃一些不影响人眼观看的细节，来压缩体积）    无损压缩，压缩率低    无损压缩，压缩率高    不压缩
能否透明    不能    能
（在RGB通道之外加了一个Alpha通道，用0~256表示透明度）    能
（但是不能控制透明度，要么完全透明要么不透明）    不能
总结    适合保存色彩丰富、却要压缩体积的图片    适合保存色彩丰富、又不限制体积的图片、透明图层    适合保存色彩简单、而体积很小的图片。不仅可以存储单张图片，还支持用多帧组成动画    体积很大，不适合在网络传输
- JPG/JPEG的保存方式有两种：
  - Baseline JPEG：按行保存，显示时从上向下逐行显示。
  - Progressive JPEG：按深度保存，显示时从模糊逐渐变清晰。
- SVG：可缩放的矢量图形（Scalable Vector Graphics），基于XML语言，可通过编程进行动态显示。
  - 矢量图又称为向量图，存储一些描述图像形状的矢量函数，可以无损压缩，也可以无限放大而不失真。
  - 缺点是显示时要进行计算，占用CPU。
- RAW：专业相机导出的图片格式，存储了原始的图片信息。
## 图片的元数据（Metadata）保留在图片的文件属性中，记录了图片的作者、日期、标签等信息。
- 常见的几种元数据标准：
  - EXIF标准：常用于数码相机的照片。
  - IPTC标准
  - XMP标准：由Adobe公司定义，保存在图像头部的XML文段中，可用于JPEG、PNG、GIF、PSD、TIFF、MOV、MP3、MPEG2、MPEG4、AVI、FLV、SWF等多种格式的文件。
## 
## 
## 

 
♢ pillow
## pillow：Python的第三方库，用于图像处理。
- 安装：pip install pillow
- pillow继承自Python2的图像处理库PIL（python Imaging Library）。
- 打开图片：
from PIL import Image

img = Image.open(r"C:\Users\Leo\Desktop\IMG_1.jpg")


img.show()             # 调用系统默认的看图软件查看该图片（此时该图片被缓存为bmp格式）
img.save(r"C:\Users\Leo\Desktop\1.jpg", format="JPEG", quality=95)  # 保存图片

# img.close()
# 调用Image.open时，pillow会读取图片文件的内容并自动关闭文件。但某些格式的图片不会自动关闭，需要用户主动关闭


  - 如果不注明保存格式，则默认保存为初始格式。
  - 如果不指定quality，则默认值为75，会对图片进行压缩、降低质量。95已经是最佳质量，100会增加很多图片的体积却没有明显改善质量。

- 查看图片的信息：
>>> img.size      # 返回图片的尺寸，是一个元组(width,height)
(1328, 1741)
>>> img.format    # 返回图片的格式
'JPEG'
>>> img.bits        # 返回图片的位深度
8
>>> img.mode      # 返回图片的颜色模式
'RGB'
- 修改图片的尺寸：
img.thumbnail((200, 300))            # 降低图片的分辨率（不能升高），而且是修改原图

_img = img.resize((4000,4000))    # 重新设置图片的分辨率，返回一个新图片
- 转换图片的颜色模式：
_img = img.convert("RGB")        # 这会返回一个新图片
  - 可选的颜色模式：1（二进制黑白图）、L（灰度图）、P（索引颜色）、RGB、RGBA、CMYK。
  - PNG格式保存直接保存为JPEG格式会报错，需要先把PNG图片从RGBA模式转换成RGB模式。
- 分离颜色通道：
r,g,b = img.split()
r.show()
- 复制、粘贴：
_img = img.copy()                        # 返回图片的一个副本
_img = img.crop((10,20,300,400))        # 返回图片中从点(10,20)到点(300,400)之间的矩形区域的拷贝
img.paste(_img, (0,0))                # 将图片_img粘贴到当前图片中，左上角对齐到点(0,0)
- 加入图片的全部像素点，返回一个二维序列：
>>> data = img.load()
>>> data[0,0]                        # 可以直接访问每个像素点
(0, 0, 0)
>>> data[0,0]=(255,0,0)
- 合并两张图片，返回一个新图片：
_img = Image.blend(img1, img2, 0.2)
# 这里，img1为（1-0.2）的透明度，img2为0.2的透明度
# 如果两张图片的尺寸或颜色模式不一致，就会报错
_img = Image.blend(img1, img2, mask)
        # 这里，两张图片使用mask决定透明度，mask是一张同样尺寸的图片，可以为1、L、RGBA模式
- 顺时针旋转图片指定角度，返回一个新图片：
img.rotate(30).show()
img.rotate(30, expand=True).show()            # 扩展图片的尺寸，以容纳旋转后的图片
## 原创绘画。
- 创建画布
img = Image.new("RGB", (300,300), (255,255,255))    # 新建一个图像，指定颜色模式、尺寸、填充色
- 添加文字
from PIL import ImageFont

font = ImageFont.truetype(r"C:\Users\Leo\Desktop\Asterix-Regular.ttf", 24)  # 选择一种字体
_str = "hello"
draw.text(xy, _str, fill, font)        # 从指定坐标处开始，添加一段文字
  - 生成验证码的方法：创建一个图片，随机给每个像素点设置颜色，然后添加四个随机字母，最后用模糊滤镜处理该图片。
## filter类提供了一些图像滤镜。
from PIL import ImageFilter
_img = img.filter(ImageFilter.CONTOUR)    # 返回一个经过CONTOUR滤镜处理后的图像
- 可选的滤镜包括：BLUR（均值模糊）、CONTOUR（提取轮廓）、EDGE_ENHANCE（边界增强）、EMBOSS（浮雕）、FIND_EDGES（提取边界）、SMOOTH（平滑）、SHARPEN（锐化）。
## 
## 
## 
 
图片相似度
## 图片相似度。
- 用MD5等加密哈希算法可以判断两张图片是否为同一文件，但不能判断两张图片的相似度。
- 判断图片相似度的哈希算法通常采用以下策略：
  - 缩小图片的分辨率、减少颜色通道数，以便简化分析。
  - 按某种算法计算出每张图片的哈希值（又称为特征值），再根据两个哈希值的汉明距离判断图片的相似度。
  - 相似度 = 1 - ( 汉明距离/哈希值长度 )
- 汉明距离（Hamming Distance）：两个长度相同的字符串之间，不同的对应位的数量（异或运算）。
## 衡量图片哈希算法的指标。
- 能否识别图像相似、只是有细节差异的图片。
- 能否识别图像相似、但分辨率不同的图片。
- 能否识别图案相似、只是颜色不同的图片。
- 处理图片的耗时。
- 判断相似度的准确性。
## 平均哈希算法（average Hash，aHash）
- 步骤：
1.    将图片缩小到8×8分辨率。（这样就只需考虑64个像素点）
2.    将图片转换成灰度图。（这样就只需考虑一个颜色通道）
3.    计算64个像素点的灰度平均值。
4.    将每个像素点的灰度值与平均值作比较，如果大于或等于平均值则计1，否则计0。最后得到一个64位的哈希值。
- 特点：
  - 不能考虑图片细节的差异，适合计算缩略图的哈希值。
  - 不能适应图片分辨率的变化。将同一张图片放大、缩小，aHash值会变化很大。
## 梯度哈希算法（difference，dHash）
- 步骤：
1.    将图片缩小到9×8辨率。
2.    转换成灰度图。
3.    比较每对相邻像素点的灰度值，如果前一个像素点的灰度值大于等于后一个像素点则记1。否则计0。最后得到一个64位的哈希值。
比如[254, 254, 255, 253]经过计算之后得到[1, 0, 1]。
- 
## 感知哈希算法（perception Hash，pHash）：基于离散余弦变换（DCT）。
- 步骤：
1.    将图片缩小到指定分辨率。
2.    转换成灰度图。
3.    计算灰度图的DCT变换，得到一个32×32的DCT矩阵。可以只取矩阵左上角的8×8部分，计算其平均值。
4.    将每个像素点的灰度值与平均值作比较，如果大于或等于平均值则计1，否则计0。最后得到一个64位的哈希值。
- 特点：
  - 能考虑图片细节的差异。
  - 计算比较慢。
  - 还能计算音频，视频文件的哈希值。
## 小波哈希算法（wavelet Hash，wHash）：基于离散小波变换（DWT）。
- 
- 
## 内容特征法
- 原理：
  - 如果两张图片的黑白轮廓相似，那么它们的内容可能也相似。
  - 在色阶0~255中选择一个阙值，把图片从灰度图转换成黑白图。
- 
## SIFT算法
- 
- 
  - 能适应图片分辨率的变化。
  - 能适应图片的旋转。
## 
## 
## 
## 
## 
 
GUI软件
♢ tkinter
## tkinter（全名为Tk Interface）是Python的标准GUI包，可以兼容类Unix系统、Windows系统，显示经典桌面风格的GUI界面。
- tkinter通过回调函数来响应事件。
- 编写了基于tkinter的脚本之后，可用pyinstaller打包成可执行文件。
## 显示窗口。
- 创建一个窗口的代码如下：
import tkinter

w1 = tkinter.Tk()                      # 创建一个窗口类（在终端执行该命令时会立即显示窗口）
w1.title("mainWindow")                # 设置窗口的标题

w1.geometry("500x300+0+0")            # 设置窗口的尺寸和坐标，格式为widthxheight+x+y
w1.resizable(width=True, height=True)    # 设置宽度、高度是否可变
w1.minsize(500, 300)                    # 设置窗口的最小尺寸

w1.mainloop()                          # 进入主循环
  - 运行mainloop()时会阻塞当前线程，保持窗口的显示，检测到用户的操作就执行相应的动作。
  - mainloop()必须在创建它的线程中运行，在其它线程中调用会使程序崩溃。
  - 运行mainloop()时，tkinter会抓住一些不重要的异常，即使它们发生了也不会使GUI关闭，只会将报错信息显示在终端上。
- 窗口类有一个attributes()方法，功能很强大，如下：
w1.attributes("-topmost", True,     # 使该窗口置顶
                   # "-fullscreen", True,  # 使该窗口为全屏
                   # "-disabled", True,    # 使该窗口无法操作（用户对它的点击、输入统统无效）
                   # "-toolwindow", True,  # 使该窗口为toolwindow
                   # "-alpha", 0.9,        # 设置该窗口的透明度，0代表完全透明，1代表完全不透明
                   )
  - 设置窗口全屏时不会显示窗口的边框，因此不能点击标题栏上的关闭按钮来关闭它。
  - 设置窗口disable之后，按alt+F4也关闭不了它。
  - 尝试了同时设置窗口topmost、fullscreen、disable，结果发现关闭不了它，连任务管理器都不能调出来。最后，新建了一个win10桌面，打开DOS窗口，用taskkill命令才关闭了该窗口。
## 
## 
## 
 
控件
## 显示控件（widget）。
- 在tkinter中，每个控件都有三种布局方法：pack()、grid()、place()。例如：
  - pack()方法。
L1.pack()                # 将该控件直接放到窗口上，让它自己调整位置
L1.pack(side="top")        # 设置该控件在窗口的位置，可选top、bottom、left、right
L1.pack(fill='y')        # 设置该控件在某一方向填满窗口，可选none、x、y、both
  - grid()方法。
略
  - place()方法。
L1.place(width=10, height=20, x=10, y=20)        # 设置该控件在父容器中的宽度、高度、坐标
L1.place(relwidth=0.5, relheight=0.5, relx=0.2, rely=0.2)    # 设置相对宽度、高度、坐标
  - 可随时调用三种方法来修改控件的位置，但是调用另一种布局方法时可能会毁掉之前的设置。
  - 每个控件在创建时要指定父容器（master），创建后要调用一个布局方法放到窗口中才能显示。例如：
tkinter.Label(w1, text="one", bg="pink").pack()    # 可以在创建该控件的同时打包
- 窗口、控件都可用destroy()方法销毁，这会同时销毁掉以它为父容器的其它控件。例如：
w1.destroy()
## tkinter提供了多种控件，常用的如下。
- Label：标签。可显示文本或图片。
L1 = tkinter.Label(master=w1, text="label1", fg="#FFF",
                     bg="#000", bd=10, font=("Arial", 12), width=10, height=5)
L1.pack()
L1["text"] = "Hello"    # 修改label的显示内容
  - 输入的参数中，text是要显示的文本（默认居中对齐），fg是前景色（即文本的颜色），bg是后景色（用三个十六进制数或已有的颜色名设定一种颜色，不设置的话就没有颜色，是透明的），bd是边框的宽度。
  - tkinter只支持PNG、GIF、PGM、PPM格式的图片，用以下函数导入：
img = tkinter.PhotoImage(file=r"C:\Users\Will\Desktop\1.png", width=200, height=100)
tkinter.Label(w1, image=img).pack(side="left")

- Frame：框架。用于包装一堆控件，作为它们的master。
F1 = tkinter.Frame(w1)
F2 = tkinter.Frame(F1)
tkinter.Label(F2, text="one").pack()
tkinter.Label(F2, text="two").pack()
F2.pack()
F1.pack()
- Button：按钮。
B1 = tkinter.Button(master=w1, text="close", command=B1.destroy)
B1.pack()
B1.flash()        # 让按钮在未激活与激活的外观之间闪烁几次
  - button控件可以将一个函数名赋值给command，当button被触发（即鼠标左键按下再松开）时就会执行该函数。
  - 可以用lambda函数作为command参数，如下：
B1 = tkinter.Button(w1, text="close", command=lambda: print("closing..."))
- Checkbutton：复选按钮。
Check1_var = tkinter.IntVar()        # 创建一个可及时刷新的变量，用于保存复选按钮的状态（1或0）
Check1 = tkinter.Checkbutton(w1, text = "run", variable = Check1_var)
Check1.pack()

Check1.select()        # 设置为选中状态
Check1.deselect()    # 设置为不选中状态
Check1.toggle()        # 在选中与不选中状态之间切换
Check1.invoke()        # 调用此方法相当于模拟用户点击一次复选按钮

Check1_var.get()        # 通过变量Check1_var获得复选按钮的状态
- Entry：输入框。只能让用户输入一行文本。
E1_var = tkinter.Variable()        # 创建一个可及时刷新的变量，用于保存输入框的文本内容
E1 = tkinter.Entry(w1, textvariable=E1_var)
E1.pack()

def get_entry():
    line=E1_var.get()+'\n'        # 获取输入框的文本内容
    T1.insert("end",line)

B1 = tkinter.Button(w1, text="Entry", command=get_entry)
B1.pack()
- Text：文本框。可以让用户输入多行文本，可以插入文本、图片、按钮，甚至当做网页浏览器使用。
T1=tkinter.Text(w1)
T1.pack()
T1.insert("1.0", "Hello\n")    # 在指定位置插入一个字符串，这个位置可以是第几行或已命名的特殊位置
T1.delete("1.2","end")        # 删除从第一行第2个字符到文本末尾之间的内容

T1.config(state="disabled")    # 使文本框不可编辑（用户和程序都不可以对它编辑）
T1.config(state="normal")        # 使文本框可编辑

B1 = tkinter.Button(w1, text="UP") 
T1.window_create("end", window=B1)        # 插入按钮

img = tkinter.PhotoImage(file=r"C:\Users\Will\Desktop\scene.png")
T1.image_create("end", image=img)        # 插入图片

## messagebox：消息框，不需要设定master，可以直接显示，但是同时只能显示一个消息框，关闭之后才会显示下一个。
from tkinter import messagebox        # 从tkinter包中导入messagebox模块

# 显示一个信息框，只有一个“确定”按钮
messagebox.showinfo(title="OK", message="operation completed!")
messagebox.showwarning("warning")
messagebox.showerror("error")

# 显示一个询问框，有“确定”、“取消”两个按钮，被用户点击后分别返回True、False
if messagebox.askokcancel("ask", "即将开始更新，确定or取消"):
    messagebox.showerror("更新失败！")

# 显示一个询问框，有“是”、“否”、“取消”三个按钮，被用户点击后分别返回True、False、None
messagebox.askyesnocancel("ask","是or否or取消")

# 显示一个询问框，有“是”、“否”两个按钮
messagebox.askyesno("ask","是or否")
## 
## 
## 
 
绑定事件
## 每个控件都可以用方法bind()在某个事件上绑定一个函数，一旦该事件发生就调用该函数，并将一个event对象传给函数。例如：
# 在L1的<ButtonPress-1>事件上绑定一个函数print()
L1.bind("<ButtonPress-1>", print)

# 在L1的<Enter>事件上绑定一个用lambda定义的简单命令
L1.bind("<Enter>", lambda event: print(L1["text"]))

- event对象描述了一个事件的多种信息，使用时自行提取event的属性即可。例如：
E1 = tkinter.Entry(w1, text='')
E1.pack()

def check_status(event):
    print(event)
    print(event.keysym)

E1.bind("<Key>", check_status)

# 运行该程序，按下Esc键，终端的显示如下：
<KeyPress event state=Mod1 keysym=Escape keycode=27 char='\x1b' x=289 y=53>
Escape

- 常用的event如下：
<ButtonPress-1>        鼠标左键按下
<ButtonRelease-1>    鼠标左键释放
<Double-Button-1>    鼠标左键双击
# 把上面三个事件名中的1改成2、3，就变成了鼠标滚轮、鼠标右键

<Enter>                鼠标移入该控件
<Leave>                鼠标离开该控件
<Motion>                鼠标在该控件上方移动
<B1-Motion>            在该控件上方按住鼠标左键的前提下，移动鼠标
<FocusIn>            该控件得到焦点（比如用户按Tab切换到它）
<FocusOut>            该控件失去焦点

<Key>                按住任意按键（注意是“按住”，如果用户一直按着，就会反复触发）
# 可以按下任意按键，用.bind("<Key>", print)查看该event的内容，其中就包括键名和键值
# 如果按下字母按键时被中文输入法挡住，程序可能会读取到异常的键值，导致程序出错
<Key-Return>            按住回车键
<Key-y>                输入小写的y
<Key-Y>                输入大写的Y（比如按Shift+Y输入，后切换大小写）
<Shift-Y>            在按住Shift的前提下，按住Y

<Configure>            窗口的大小改变

  - 可以自定义event，需要在前后各加两个尖括号，例如：
E1.bind("<<myEvent>>", print)
- 每个控件都可以用event_generate()方法主动生成一个事件，例如：
E1.bind("<Key-Return>", print)
E1.event_generate("<Key-Return>", when="tail")        # when="tail"是为了让该事件按顺序排队
  - 如果事件是<Key>类型，当焦点不在该控件上时，生成一个事件该控件也不会有反应。
  - 可以使用方法after(self, ms, func=None, *args)让tkinter在指定毫秒后执行某函数（这是tkinter内置的方法，如果使用time.sleep实现该功能就会阻塞线程）。
- bind()方法不输入参数则返回绑定的事件元组，可以用unbind()解绑一个事件。例如：
>>> E1.bind("<<myEvent>>", print)
'15615600print'
>>> print(E1.bind())
('<<myEvent>>',)
>>> E1.unbind("<<myEvent>>")
>>> print(E1.bind())
()
  - 对窗口进行绑定，例如w1.bind()，会绑定其中的所有子控件。
## 
## 
## 
 
♢ PyQt5
## PyQt5：Python的第三方库，使得Python可以调用Qt5的大部分API。
- 安装：pip install PyQt5==5.10 PyQt5-sip==12.7.0
  - PyQt5-sip库用于让PyQt调用Qt的C++ API。
- 例：
from PyQt5.QtWidgets import QApplication, QWidget
import sys

app = QApplication(sys.argv)    # 每个Qt程序在启动时首先要创建一个QApplication对象，可以输入参数
w = QWidget()                # 创建主窗口
w.show()                        # 显示窗口

sys.exit(app.exec())            # 进入app的主循环，一旦app结束就终止程序

- Qt是一个GUI软件开发框架，基于C++，兼容Windows、Linux、MacOS、iOS、Android。
  - Qt5重构了底层模块，不兼容Qt4。
- 控件：指UI上显示的各种对象，比如窗口、按钮。
  - 通常先创建一个顶级窗口，再以它为父控件，创建其它控件。
  - 当父控件被销毁时，它的所有子控件都会被自动销毁。
  - 多个控件可以叠加显示在同一位置，后显示的控件会显示在上层。
## 
## 
## 
## 
## 
 
Qtcore模块
## 
## 
## 
## QTimer类：定时器。
- QTimer(parent: QObject = None)
- 例：
>>> timer = QTimer(w)                            # 创建一个定时器
>>> timer.timeout.connect(lambda:print(1))        # 绑定timeout信号
<PyQt5.QtCore.QMetaObject.Connection object at 0x000001EA668E9668>
>>> timer.setInterval(1000)                    # 设置触发timeout信号的间隔时间（单位为毫秒）
>>> timer.start()                                # 启动定时器（定时器会一直运行，循环触发timeout信号）
1                                            # 可以用timer.start(1000)，在启动时设置间隔时间
1
1
>>> timer.stop()                                # 停止定时器）
>>> timer.start()                                # 可以再次启动
1
1
1
- 下例是设置定时任务，定时器触发一次timeout信号之后就自动停止。
>>> QTimer.singleShot(1000, lambda:print(1))
1
## 
## 
## QThread类：多线程。
- 用法：自定义一个类，继承QThread类，并重载run()方法。
- 与Python自带的Threading模块相比，QThread创建的线程可以方便地使用信号进行通信。但依然受到GIL的限制。
## 
## 
## 
 
处理事件
## 为了让Qt程序处理用户触发的事件，可以设置信号与槽函数，也可以重载控件的某种事件的处理函数。
## 信号与槽函数：将控件的某个信号绑定到一个槽函数。
- 例：
w = QWidget()
b = QPushButton("Close", w)
b.clicked.connect(w.close)        # 将一个信号对象与一个槽函数绑定
b.clicked.disconnect(w.close)        # 解绑（如果不存在该绑定关系则报错）

  - 当用户单击按钮时，按钮控件会发送click信号给所有与之绑定的槽函数，从而对该事件做出响应。
  - 一个信号对象可以绑定多个槽函数。
  - 可以将一个信号对象与另一个信号对象绑定，即前一个信号发生时会触发后一个信号。
b2 = QPushButton("Button2", w)
b2.clicked.connect(b.clicked)
- 例：
from PyQt5.QtWidgets import QApplication, QWidget
from PyQt5.QtCore import pyqtSignal

class MyWindow(QWidget):
    _signal = pyqtSignal(str)        # 自定义一个信号，它的形参列表要与其槽函数一致

    def __init__(self):
        super().__init__()
        self._signal.connect(self._slot)
        self._signal.emit("testing...")    # 可以用emit()方法主动发送某种信号

    def _slot(self, string):
        print(string)
        print(self.sender())        # 在槽函数中，可以用self.sender()方法返回信号的发送者的引用

## 常见的信号对象。
- clicked
- 
- 
- 
- 
- 
## 重载控件的某种事件的处理函数。
- 例：
class Example(QWidget):
    def __init__(self):
        super().__init__()
    def keyPressEvent(self, event):
        if event.key() == Qt.Key_Escape:        # 如果用户按下Esc键，则关闭窗口
            self.close()
- 
## 常见的事件处理函数。
- def keyPressEvent(self, event):
    print(event.key())        # 获取用户按下的按键键值，比如按键A的键值是65（不受大小写的影响）
- def mouseMoveEvent(self, event):
    print(event.pos())        # 获取鼠标在窗口内的相对坐标
    print(event.globalPos())    # 获取鼠标在窗口内的全局坐标
  - 默认当用户按住鼠标并移动时才会触发mouseMoveEvent事件。如果设置self.setMouseTracking(True)，则只要用户在窗口范围内移动鼠标，就会触发mouseMoveEvent事件。
- 
## 
## 

 
QTime类
## QTime类。
- 例：
>>> time = QTime.currentTime()        # 获取当前时间
>>> time
PyQt5.QtCore.QTime(22, 8, 3, 113)        # 一个QTime对象包含时、分、秒、毫秒四项参数
>>> time.hour()
22
>>> time.minute()
8
>>> time.second()
3
>>> time.msec()
113
>>> time.toPyTime()                    # 转换成datetime对象
datetime.time(22, 8, 3, 113000)
>>> time.toString()                    # 转换成字符串
'22:08:03'
## QDate类。
- 例：
>>> date = QDate.currentDate()
>>> date.year()
2019
>>> date.month()
10
>>> date.day()
9
>>> date.dayOfWeek()                    # 获取周几
3
>>> date.toPyDate()
datetime.date(2019, 10, 9)
## QDateTime类。
- 例：
>>> datetime = QDateTime.currentDateTime()
>>> datetime
PyQt5.QtCore.QDateTime(2019, 10, 9, 22, 19, 14, 330)
>>> datetime.toTime_t()            # 转换成时间戳
1570630754
>>> datetime.toPyDateTime()        # 转换成datetime对象
datetime.datetime(2019, 10, 9, 22, 19, 14, 330000)
- PyQt获取的时间默认为本地时间。
>>> datetime_UTC = QDateTime.currentDateTimeUtc()        # 获取UTC时区的时间
>>> datetime.timeZone().id()                            # 查看时区
PyQt5.QtCore.QByteArray(b'Asia/Shanghai')
>>> datetime.toUTC()                                    # 转换成UTC时间
PyQt5.QtCore.QDateTime(2019, 10, 9, 14, 19, 14, 330, PyQt5.QtCore.Qt.TimeSpec(1))
>>> datetime_UTC.toLocalTime()                        # 转换成本地时间
PyQt5.QtCore.QDateTime(2019, 10, 9, 22, 19, 14, 330)
>>> datetime_UTC.toLocalTime().toLocalTime()            # 重复转换也不会出错，该操作有幂等性
PyQt5.QtCore.QDateTime(2019, 10, 9, 22, 19, 14, 330)
## 
## 
## 
 
QtWidgets模块
QApplication类
## QApplication类：用于创建Qt应用（它采用单例模式）。需要导入：from PyQt5.QtWidgets import QApplication
- app = QApplication.instance()
  - 功能：返回Qt应用的引用，总是返回一个单例对象。
- app.closeAllWindows() -> None
  - 功能：关闭所有窗口。
- app.quit() -> None
  - 功能：终止Qt应用。
- 
  - 功能：
- 
  - 功能：
- 
  - 功能：
- 
  - 功能：

## 
## 
## 
## 
## 
 
QWidget类
## QWidget类：用于创建普通窗口。需要导入：from PyQt5.QtWidgets import QWidget
- QWidget是所有窗口的基类，是QDialog、QMainWindow、QFrame的父类。
- w = QWidget(parent: QWidget = None)
  - 功能：创建一个窗口。
  - 如果它没有父控件，它就会成为唯一的顶级窗口。
- w.show() -> None
  - 功能：显示控件。
  - 父控件在第一次显示时会初始化布局，将它的各个子控件也显示出来。如果在父控件初始化之后才加入子控件，则需要主动调用子控件的show()方法。
- w.close() -> bool
  - 功能：关闭控件的显示（但并没有销毁）。
  - 如果成功关闭显示，或者该控件本来就没有显示，则返回True。
- 
- 
## 窗口的特有方法。
- w.setWindowTitle(str) -> None
  - 功能：设置窗口的标题。
- w.setWindowIcon(QIcon) -> None
  - 功能：设置窗口的图标。
  - 例：
from PyQt5.QtGui import QIcon
w.setWindowIcon(QIcon(r"C:\Users\Leo\Pictures\1.jpg"))
- w.isMaximized() -> bool
  - 功能：判断窗口是否被最大化了。
  - 窗口最大化时不一定是全屏，比如限制了窗口最大尺寸时，不能填满屏幕。
- w.isMaximized() -> bool
  - 功能：判断窗口是否被最小化了。
## 控件的通用方法。
- w.setFocus() -> None
  - 功能：使控件得到焦点。
- w.setEnabled(bool) -> None
  - 功能：设置控件是否可以被用户操作，这会影响到它的所有子控件。
- w.isActiveWindow() -> bool
  - 功能：判断控件是否获得了屏幕焦点。
- w.isVisible() -> bool
  - 功能：判断控件现在是被show()显示了，还是被close()关闭显示了。
- w.setToolTip(str) -> None
  - 功能：设置提示语。当鼠标悬停在该控件上方时就会立即显示。
  - 例：
w.setToolTip("This is a tip.\n")                            # 支持转义字符
w.setToolTip("这是一个提示。")                                # 支持Unicode字符
w.setToolTip('This is a <font color="red">tip</font>.')        # 支持HTML语法
  - 可定义ToolTip的字体：
from PyQt5.QtWidgets import QToolTip
from PyQt5.QtGui import QFont
QToolTip.setFont(QFont("微软雅黑", 12))
w.setToolTip('This is a <font color="red">tip</font>.')
- 
  - 功能：
- 
  - 功能：
- 
  - 功能：
- 
## 
## 
## 
## 
 
QMainWindow类
## QMainWindow类：用于创建包含菜单栏、工具栏、状态栏的经典风格的窗口。
- w = QMainWindow(parent: QWidget = None)
  - 功能：创建一个主窗口。
## 菜单栏。
- menubar = w.menuBar()
  - 功能：第一次调用将创建菜单栏，重复调用将返回菜单栏这个单例对象的引用。
- menubar.addMenu(str) -> QMenu                # 输入名字
menubar.addMenu(QIcon, str) -> QMenu        # 输入图标和名字
menubar.addMenu(QMenu) -> QMenu            # 输入一个QMenu对象
  - 功能：加入一个菜单。
  - 可以在一个菜单中嵌套另一个菜单，称为子菜单。例：
file_menu = menubar.addMenu("File")
sub_menu = file_menu.addMenu("Recent Files...")
- QMenu.addAction(str) -> QAction
QMenu.addAction(QIcon, str) -> QAction
QMenu.addAction(QAction) -> QAction
  - 功能：在某个菜单下加入一个动作（按钮）。
  - 下例是定义一个普通的动作：
from PyQt5.QtWidgets import QAction

# 定义动作
exit_action = QAction(QIcon(r'C:\Users\Leo\Pictures\1.jpg'), "Exit", w)
exit_action.setShortcut("Ctrl+Q")                        # 设置快捷键
exit_action.setStatusTip("Exit the application.")        # 设置显示在状态栏的提示
exit_action.triggered.connect(app.quit)                # 绑定到一个槽函数

menubar = w.menuBar()
file_menu = menubar.addMenu("File")        # 创建菜单
file_menu.addAction(exit_action)            # 添加动作
  - 下例是定义一个勾选的动作：
def debug_mode(state):        # 触发该槽函数时，会传入一个参数，表示当前按钮是否被勾选
    if state:
        w.statusBar().showMessage("Debug mode is enabled")
    else:
        w.statusBar().showMessage("Debug mode is disabled")

debug_action = QAction("Debug mode", w, checkable=True)
debug_action.setChecked(True)        # 设置按钮初始的状态是否被勾选
debug_action.triggered.connect(debug_mode)

menubar = w.menuBar()
fileMenu = menubar.addMenu("fileMenu")
fileMenu.addAction(debug_action)
- QAction(parent: QWidget = None) -> QAction
QAction(str, parent: QWidget = None) -> QAction
QAction(QIcon, str, parent: QWidget = None) -> QAction
  - 功能：定义一个动作。
## 上下文菜单：即右键菜单。
- 定义上下文菜单需要重载contextMenuEvent()方法。如下：
class MyWindow(QMainWindow):
    def contextMenuEvent(self, event):
        contextMenu = QMenu(self)
        open_action = contextMenu.addAction("open")
        quit_action = contextMenu.addAction("quit")

## 工具栏：显示一些常用的动作，便于使用。
- 例：
w.exit_tool = w.addToolBar("Exit")
w.exit_tool.addAction(exit_action)
## 状态栏。
- statuebar = w.statusBar()
  - 功能：第一次调用将创建状态栏，重复调用将返回状态栏这个单例对象的引用。
- statuebar.showMessage(str, msecs: int = 0)
  - 功能：在状态栏中显示一行字符串。默认永久显示，输入msecs参数可设置最大显示时长。
## 
## 
## 
 
坐标、尺寸
## 坐标。
- w.pos() -> QPoint
  - 功能：查看控件的坐标，返回一个QPoint对象。
  - 例：
>>> w.pos()
PyQt5.QtCore.QPoint(639, 237)
>>> pos = w.pos()
>>> pos.x()
639
>>> pos.y()
237
  - 顶级窗口的坐标代表其左上角相对于屏幕左上角的距离，子控件的坐标代表其左上角相对于父控件左上角的距离。
  - 顶级窗口的坐标可以移动到屏幕之外，子控件的坐标可以移动到父控件的显示区域之外。
>>> w.mapToGlobal(w.pos())        # 从局部坐标转换成全局坐标（即加上当前控件的坐标）
PyQt5.QtCore.QPoint(1279, 512)
>>> w.mapFromGlobal(w.pos())        # 从全局坐标转换成局部坐标（即减去当前控件的坐标）
PyQt5.QtCore.QPoint(-1, -38)
- w.move(int, int) -> None            # 输入横坐标x、纵坐标y（单位为pixel）
w.move(QPoint) -> None            # 输入一个QPoint对象
  - 功能：移动控件到指定坐标。
## 尺寸。
- w.size() -> QSize
  - 功能：查看控件的尺寸，返回一个QSize对象。
  - 例：
>>> w.size()
PyQt5.QtCore.QSize(640, 480)
>>> size = w.size()
>>> size.width()
640
>>> size.height()
480
- w.resize(int, int) -> None        # 输入宽度width、高度height（单位为pixel）
w.resize(QSize) -> None            # 输入一个QSize对象
  - 功能：调整控件的尺寸。
  - 控件的尺寸不能设置为0或负数，否则控件会被关闭显示。
  - 控件的尺寸不能超过屏幕的可用显示范围，即使用resize()设置了更大的尺寸也不会生效，即使用户用鼠标拖动窗口边框也不能变得更大。
- w.adjustSize() -> None
  - 功能：根据控件需要显示的内容，自动调整尺寸。
- 设置最大尺寸。
w.setMaximumHeight(int) -> None
w.setMaximumWidth(int) -> None
w.setMaximumSize(int, int) -> None
w.setMaximumSize(QSize) -> None
- 设置最小尺寸。
w.setMinimumHeight(int) -> None
w.setMinimumWidth(int) -> None
w.setMinimumSize(int, int) -> None
w.setMinimumSize(QSize) -> None
- 设置固定尺寸。
w.setFixedHeight(int) -> None
w.setFixedWidth(int) -> None
w.setFixedSize(int, int) -> None
w.setFixedSize(QSize) -> None
  - 可以在程序运行时随时改变窗口的尺寸，但是如果设置了固定尺寸，用户就不能再拖动窗口的边界了，只能由程序改变。
## 几何属性。
- w.geometry() -> QRect
  - 功能：查看控件的几何属性，返回一个QRect对象。
  - 例：
>>> w.geometry()
PyQt5.QtCore.QRect(640, 275, 640, 480)
>>> geometry = w.geometry()
>>> geometry.x()            # QRect对象兼容QPoint对象、QSize对象的属性和方法
640
>>> geometry.y()
275
>>> geometry.width()
640
>>> geometry.height()
480
- w.setGeometry(int, int, int, int) -> None        # 输入x、y、width、height
w.setGeometry(QRect) -> None                    # 输入一个QRect对象
  - 功能：设置控件的几何属性。
  - QRect对象提供了一些移动控件的方法，但不会影响到原控件。可以先修改QRect对象，再把它应用到原控件。
>>> geometry = w.geometry()
>>> geometry.right()                # 同理还有left()、top()、bottom()
1279
>>> geometry.moveRight(1000)        # 同理还有moveLeft()、moveTop()、moveBottom()
>>> geometry.topLeft()            # 同理还有topRight()、bottomLeft()、bottomRight()、center()
PyQt5.QtCore.QPoint(361, 275)        # 返回一个QPoint对象
>>> geometry.moveTopLeft(geometry.center())
# 同理还有moveTopRight()、moveBottomLeft()、moveBottomRight()、moveCenter()
>>> w.setGeometry(geometry)        # 把QRect对象应用到原控件
## 获取桌面的尺寸信息。
- 获取桌面窗口的实例：
>>> from PyQt5.QtWidgets import QDesktopWidget
>>> desktop = QDesktopWidget()
- 它兼容QWidget的部分方法，可像QWidget一样查看尺寸：
>>> desktop.size()
PyQt5.QtCore.QSize(1920, 1080)
- 它的特有方法：
>>> desktop.availableGeometry()                # 查看桌面的可用显示范围（略小于屏幕尺寸，因为要减去边框）
PyQt5.QtCore.QRect(0, 0, 1920, 1030)
## 
## 
 
布局
## 设置控件的位置时，使用布局方法比使用绝对坐标更好，因为使用布局方法可以适应窗口的伸缩变化，而且在不同平台上的显示效果都一致。
- 不可以直接将多个水平布局、垂直布局组合在一起，但可以将一个布局嵌套成另一个布局中的元素。
- 给一个控件设置了布局之后，只能在该布局的基础上进行修改，不能换成另一个布局。
## QHBoxLayout类：用于实现水平布局（Horizontal Layout），使多个控件在水平方向均匀排列。
## QVBoxLayout类：用于实现垂直布局（Vertical Layout），使多个控件在垂直方向均匀排列。
- 例：
from PyQt5.QtWidgets import QApplication, QWidget, QPushButton, QHBoxLayout, QVBoxLayout
import sys

app = QApplication(sys.argv)
w = QWidget()
w.show()
button1 = QPushButton("One")
button2 = QPushButton("Two")

hbox = QHBoxLayout()            # 创建一个水平布局（即一行空间）
hbox.addStretch(1)            # 添加一个拉伸因子（拉伸因子会尽可能地挤占空白空间）
hbox.addWidget(button1)        # 添加控件（这些空间会按添加的先后顺序排列）
hbox.addWidget(button2)

vbox = QVBoxLayout()            # 创建一个垂直布局（即一列空间）
w.setLayout(vbox)            # 采用该布局（之后再修改该布局时，会立即生效）
vbox.addStretch(1)
vbox.addLayout(hbox)            # 添加一个布局作为元素
  - 拉伸因子的值越大，挤占空间的优先级越高。
## QGridLayout类：用于实现网格布局，将空间分成多行多列，将控件放在某个格子内，或者占据多个格子。
- 例：
from PyQt5.QtWidgets import QApplication, QWidget, QPushButton, QGridLayout
import sys

app = QApplication(sys.argv)
w = QWidget()
w.show()

grid = QGridLayout()
w.setLayout(grid)
grid.setSpacing(10)        # 设置每个格子的间距

button1 = QPushButton("Send")
grid.addWidget(button1)                # 添加一个控件，默认使用垂直布局
grid.addWidget(button1, 0, 0)            # 添加一个控件，放在第0行、第0列
textEdit1 = QTextEdit()
grid.addWidget(textEdit1, 1, 0, 2, 2)    # 添加一个控件，占据从第1行、第0列到第2行、第2列之间的格子

- 下例是添加一些按矩阵排列的控件：
positions = [(i, j) for i in range(5) for j in range(4)]
names = ['Cls', 'Bck', '', 'Close',
         '7', '8', '9', '/',
         '4', '5', '6', '*',
         '1', '2', '3', '-',
         '0', '.', '=', '+']
for position, name in zip(positions, names):
    if name == '':
        continue
    button = QPushButton(name)
    grid.addWidget(button, *position)
## 
## 
## 
 
控件
按钮
## QPushButton类：普通按钮。
- QPushButton(parent: QWidget = None)                # 只输入父控件，则显示一个空白按钮
QPushButton(str, parent: QWidget = None)            # 输入显示内容、父控件
QPushButton(QIcon, str, parent: QWidget = None)        # 输入图标、显示内容、父控件
- 例：
>>> button = QPushButton("Quit", w)
>>> button.clicked.connect(QApplication.instance().quit)    # 将按钮按下的信号绑定到一个槽函数
>>> button.text()                                # 返回按钮的名字
'Quit'
- 可以让普通按钮保持在“按下”或“未按下”状态。
def changeState(pressed):
    if pressed:
        print("On")
    else:
        print("Off")

button.setCheckable(True)                        # 使普通按钮可以保持状态
button.clicked[bool].connect(changeState)        # 绑定信号
button.toggle()                                # 切换状态
## QToolButton类：点击时不会显示虚线边框。
## QCheckBox类：勾选按钮。有“选中”、“未选中”两种状态。
- QCheckBox(parent: QWidget = None)
QCheckBox(str, parent: QWidget = None)
- 例：
def changeState(self, state):
    if state == Qt.Checked:
        print("On")
    else:
        print("Off")

>>> checkBox = QCheckBox("On", w)
>>> checkBox.stateChanged.connect(changeState)        # 将状态改变的信号绑定到一个槽函数
>>> checkBox.isChecked()                            # 判断是否被选中了
True
>>> checkBox.setChecked(True)                        # 设置状态
>>> checkBox.toggle()                                # 切换状态
## QRadioButton类：单选按钮。
## 
## 
## 
## 
## 
## 
## 
## 
## 
## 
## 
## 
## 
 
关于输入
## QLineEdit类：单行输入框，用于输入一行字符串。
- QLineEdit(parent: QWidget = None)
QLineEdit(str, parent: QWidget = None)        # str参数表示输入框的初始内容
- 例：
>>> lineEdit = QLineEdit(w)
>>> lineEdit.show()
>>> lineEdit.setText("hello")            # 设置输入框的内容
>>> lineEdit.text()                    # 获取输入框的内容
'hello'
>>> lineEdit.setMaxLength(10)            # 设置输入内容的最大长度
>>> lineEdit.setReadOnly(True)        # 使输入框变成只读
>>> lineEdit.setEchoMode(QLineEdit.Password)        # 使输入框的内容按密文显示
- 常用信号：
lineEdit.textChanged.connect(...)            # 当输入框的内容改变时（不管是被用户改变，还是被程序改变）
lineEdit.editingFinished.connect(...)        # 当用户输入结束时（比如按下回车、焦点从输入框移动到其它控件）
lineEdit.selectionChanged.connect(...)        # 当用户的选中范围改变时（没有选中范围时不会触发）
## QTextEdit类：多行输入框，用于输入多行字符串，可以插入富文本。
- QTextEdit(parent: QWidget = None)
QTextEdit(str, parent: QWidget = None)
- 当输入的字符串行数过多时，会自动显示一个垂直滚动条。
- 例：
>>> textEdit = QTextEdit(w)
>>> textEdit.show()
>>> textEdit.toPlainText("Hello")            # 设置输入框的纯文本内容
>>> textEdit.toPlainText()                # 获取输入框的纯文本内容（QTextEdit对象没有text()方法）
'Hello'
>>> textEdit.setHtml("<h1>标题一</h1>")    # 设置输入框的html内容
>>> textEdit.toHtml()                        # 获取输入框的html内容
'<!DOCTYPE HTML PUBLIC "-//W3C//DTD HTML 4.0//EN" "http://www.w3.org/TR/REC-html40/strict.dtd">\n<html><head><meta name="qrichtext" content="1" /><style type="text/css">\np,...
>>> textEdit.clear()                        # 清空输入框
- 关于插入文本：
>>> textEdit.append("Hello")                    # 在末尾附加内容（这会新起一行）
>>> from PyQt5.QtGui import QTextCursor
>>> textEdit.moveCursor(QTextCursor.Start)        # 将光标移动到最前面
>>> textEdit.moveCursor(QTextCursor.End)        # 将光标移动到最后面
>>> textEdit.insertPlainText("Hello")            # 在光标处插入纯文本
>>> textEdit.insertHtml("<h1>标题一</h1>")        # 在光标处插入html
- 下例是将stdout、stderr重定向到textEdit。
from PyQt5.QtWidgets import QApplication, QWidget
from PyQt5.QtCore import QObject, pyqtSignal
from PyQt5.QtGui import QTextCursor

class EmittingStream(QObject):
    output = pyqtSignal(str)      # 定义output信号，接收一个str参数
    def write(self, text):
        self.output.emit(str(text))
    def flush(self):
        pass

class MyWindow(QWidget):
    def __init__(self):
        super().__init__()
        self.log_view = QTextEdit(self)

        # 重定向stdout、stderr，让它们触发output信号，并把信号绑定到logger槽函数
        sys.stdout = EmittingStream(output=self.logger)    
        # sys.stderr = sys.stdout        # 重定向stderr的话，程序就不能捕捉异常，容易崩溃

    def logger(self, text):
        """ 接收log信号的槽函数，用于记录日志 """
        self.log_view.moveCursor(QTextCursor.End)
        self.log_view.insertPlainText(text)

# 尝试发送stdout、stderr
print("hello")
raise RuntimeError("testing...")

## QComboBox类：下拉列表。
- QComboBox(parent: QWidget = None)
- 例：
>>> combo = QComboBox(w)
>>> combo.show()
>>> combo.addItem("One")        # 添加一个选项（只是显示一个str）
>>> combo.addItem("Two")
>>> combo.currentText()        # 获取当前的选项
'One'
- 常用信号：
def onActivated(text):
    print(text)

combo.activated[str].connect(onActivated)
## QScrollBar类：滚动条，用于拖动显示区域。
## QSlider类：滑动条，用户可以通过拖动滑动条来调整某个数值。
- QSlider(parent: QWidget = None)
QSlider(Qt.Orientation, parent: QWidget = None)
  - Qt.Orientation有水平、竖直两种显示方向，默认是Qt.Vertical，可设置成Qt.Horizontal。
- 例：
>>> slider = QSlider(Qt.Horizontal, w)            # 创建一个水平显示的滑动条
>>> slider.show()
>>> slider.setValue(100)                        # 设置值（取值范围为0~99，超出范围则设置成最大/小值）
>>> slider.value()
99
- 常用信号：
def changeValue(value):
    print(value)
slider.valueChanged[int].connect(changeValue)    # 绑定取值改变的信号（取值范围为0~99）
## QCalendarWidget类：日历。用于让用户方便地选择一个日期。
- QCalendarWidget(parent: QWidget = None)
- 例：
def getDate(date):    # 传入的date参数是QDate对象
    print(date.toString())

calendar = QCalendarWidget(w)
calendar.show()
calendar.clicked[QDate].connect(getDate)
## 
## 
## 
## 
## 
## 
## 
## 
## 
 
关于输出
## QLabel类：标签，用于显示一个只读的字符串。
- QLabel(parent: QWidget = None)
QLabel(str, parent: QWidget = None)
- 例：
>>> label = QLabel("hello", w)
>>> label.show()
## QProgressBar类：进度条。
- QProgressBar(parent: QWidget = None)
- 例：
>>> progressBar = QProgressBar(w)
>>> progressBar.show()
>>> progressBar.setValue(100)        # 设置进度值。取值范围为0~100
>>> progressBar.value()
100
>>> progressBar.setValue(99.99)    # 小数部分的值会被舍去
>>> progressBar.value()
99
## 
## 
## 
## 
## 
## 
## 
## 
## 
## 
## 
## 
## 
## 
 
关于布局
## QFrame类：框架，用于将多个控件组合在一起。
## QSplitter类：分割器。插入到控件之间，从而用户用户拖动控件的边界。
- QSplitter(parent: QWidget = None)
QSplitter(Qt.Orientation, parent: QWidget = None)
- 例：
from PyQt5.QtWidgets import QApplication, QWidget, QFrame, QHBoxLayout, QSplitter
from PyQt5.QtCore import Qt
import sys

app = QApplication(sys.argv)
w = QWidget()

frame1 = QFrame(w)
frame1.setFrameShape(QFrame.StyledPanel)    # 设置frame的主题，以支持QSplitter
frame2 = QFrame(w)
frame2.setFrameShape(QFrame.StyledPanel)
frame3 = QFrame(w)
frame3.setFrameShape(QFrame.StyledPanel)

splitter1 = QSplitter(Qt.Horizontal)        # 创建一个水平方向的分割器splitter1
splitter1.addWidget(frame1)                # 用splitter1分割topleft和topright
splitter1.addWidget(frame2)

splitter2 = QSplitter(Qt.Vertical)
splitter2.addWidget(splitter1)
splitter2.addWidget(frame3)

hbox.addWidget(splitter2)
## 
## 
## QTableView
## QListView
## QTreeView
## QListWidget
## QTableWidget
## QTabWidget
## QStackedWidget
## QDockWidget
## 
## 
## 
## 
## 
 
对话框
## QDialog类：所有对话框窗口的基类。
## QInputDialog类：输入对话框。
- 例：
text, ret = QInputDialog.getText(w, "Input Dialog", "Please input your name:")
if ret:
    print("Your name is:" + text)
  - text存储用户输入的文本，ret是一个bool值，表示用户是否点击了Yes按钮。
## QFontDialog类：选择字体的对话框。
- 例：
font, ret = QFontDialog.getFont()
if ok:
    lable.setFont(font)
## QColorDialog类：选择颜色的对话框。
- 例：
color = QColorDialog.getColor()
if color.isValid():
    w.setStyleSheet("QWidget {{ background-color: {} }}".format(color.name()))
## QFileDialog类：选择文件的对话框。
- 选择一个文件：
filename, _filter = QFileDialog.getOpenFileName(w, "Open file", ".", "*.py")
                    # 输入参数：父控件、窗口名、打开的目录、筛选的文件名
                    # 返回的filename和_filter都是str型
if filename:
    with open(filename, "r") as f:
        textEdit.setText(f.read())
- 选择多个文件：
filenames, _filter = QFileDialog.getOpenFileNames(w, "Open files", ".", "*.py")
                    # 返回的filenames是一个字符串列表
- 选择保存文件的路径：
>>> QFileDialog.getSaveFileName(w, "Save to", ".", "*.py")
('D:/1/move_files/src/1.py', '*.py')
- 选择一个目录：
>>> QFileDialog.getExistingDirectory(w, "Open file", ".")
'D:/1'
## QMessageBox类：消息框，用于通知用户某个消息。
- 提问框：有Yes、No两个选项。
>>> reply = QMessageBox.question(w, "标题...", "内容...")
>>> reply == QMessageBox.Yes
True
>>> reply == QMessageBox.No        # 当用户点击No选项或关闭按钮时，返回值为QMessageBox.No
False
- 提示框：只有一个Ok选项。
>>> reply = QMessageBox.information(w, "标题...", "内容...")
>>> reply == QMessageBox.Ok        # 当用户点击Ok选项或关闭按钮时，返回值为QMessageBox.Ok
True
- 警告框：只有一个Ok选项。
>>> reply = QMessageBox.warning(w, "标题...", "内容...")
>>> reply == QMessageBox.Ok
True
- 错误框：只有一个Ok选项。
>>> reply = QMessageBox.critical(w, "标题...", "内容...")
>>> reply == QMessageBox.Ok
True
## 
## 
## 
## 
## 
## 
## 
 
QtGui模块
## QFont类：用于选择字体。
- 例：
>>> from PyQt5.QtGui import QFont
>>> QFont("微软雅黑", 12)        # 输入字体名、字号
<PyQt5.QtGui.QFont object at 0x0000023BE20F9358>
## QColor类：用于选择颜色。
- QColor(int, int, int, alpha: int = 255)
  - 前三个参数代表RGB三个通道的值（取值为0~255），alpha参数表示不透明度。
- 例：
>>> from PyQt5.QtGui import QColor
>>> color = QColor(0, 0, 255)            # 选择颜色
>>> color.name()                        # 返回颜色的十六进制值
'#0000ff'
>>> color.isValid()                    # 判断是否为有效的颜色值
True
  - 可以单独访问red、green、blue、alpha通道。
>>> color.alpha()
255
>>> color.setAlpha(0)
## QIcon类：用于导入图片。
- 例：
>>> from PyQt5.QtGui import QIcon
>>> QIcon(r"C:\Users\Leo\Pictures\1.jpg")
<PyQt5.QtGui.QIcon object at 0x0000023BE1C45C18>
## QPixmap类：用于显示图片。
- 例：
>>> pic = QPixmap(r"C:\Users\Leo\Pictures\1.jpg")
>>> label = QLabel(w)
>>> label.setPixmap(pic)            # 用图片填充label
>>> label.show()
>>> w.adjustSize()
## QPainter类：用于绘画。
## 
## stylesheet：样式表。
- 子控件会自动继承父控件的stylesheet，为了避免这种情况，应该注明stylesheet的作用对象，如下：
QMainWindow{                            # 作用于QMainWindow类对象
background-color: rgb(255, 255, 0);
color: rgb(255, 85, 0);
}
QMainWindow:mainwindow{                # 只作用于mainwindow对象
background-color: rgb(255, 255, 0);
color: rgb(255, 85, 0);
}
- 
## 
## 
 
♢ pyqt5-tools
## pyqt5-tools：Python的第三方库，提供了Qt的一些工具。
- 安装：pip install PyQt5-tools==5.10.1.1.3
  - 这些工具安装在Python/Scripts目录下，并且注册在环境变量PATH中，可以输入工具名直接调用。
- 
- 
## designer：用于设计Qt的GUI界面，生成.ui文件。
- 用法：用designer.exe启动，或在命令行输入designer启动。
## 
## 
## 
## 
## 
## pyuic5：用于将.ui文件转换成.py文件。
- 用法：
pyuic5 mainwindow.ui -o mainwindow_ui.py
- 可以将.ui文件转换成.py文件之后再导入，如下：
import sys
from PyQt5.QtWidgets import QApplication, QMainWindow
from mainwindow_ui import Ui_MainWindow

class MyWindow(QMainWindow, Ui_MainWindow):  # 多继承，QMainWindow是基类，Ui_MainWindow用于配置
    def __init__(self):
        super().__init__()
        self.setupUi(self)

app = QApplication(sys.argv)
w = MyWindow()
w.show()
sys.exit(app.exec())
- 也可以直接导入.ui文件（但这样不能打包到exe文件中），如下：
from PyQt5 import uic

class MyWindow(QMainWindow):                # 不继承
    def __init__(self):
        super().__init__()
        uic.loadUi("mainwindow.ui", self)    # 调用其setupUi()方法
## pyrcc5：用于将.qrc文件转换成.py文件，便于打包。
- 用法：
pyrcc5 resource.qrc -o resource.py
- 导入图片等资源文件的方法有两种：
  - 使用文件路径直接导入，但这样必须将资源文件与程序打包到同一个文件夹发布。
  - 把资源文件记录到.qrc文件中（使用designer的资源窗口），再转换成.py文件，然后在主脚本中导入。如下：
import resource
QIcon(r":resource/img/logo.ico")    # 使用冒号:加文件路径导入图片，该路径必须与.qrc文件中的一致
## 
## 用pyinstaller打包PyQt程序。
1.    写好程序，能用Python解释器成功启动。
2.    将.qrc文件转换成.py文件，然后在主脚本中导入。
3.    到源代码目录下，执行：
pyinstaller mainwindow.py -w -i resource/img/logo.ico
  - 如果启动失败，就先不用-w选项，在终端启动，可以看到报错信息。
4.    将源代码目录下的.ui文件、resource目录都拷贝到dist目录下，因为程序打包时没有集成它们，还需要按相对路径导入。
## 
## 
## 
## 
## 
## 
## 
## 
 
designer
## 
## 
## 按F4进入信号-槽的设置模式
可以自定义signal或slot，等导入该ui文件时再定义相应的方法。

## 在designer中导入图片等资源时，要先点击Resource菜单，创建一个.qrc文件，用于记录导入的所有资源。
- 也可以直接导入文件路径。
## 
## 自定义widget，做成插件后便可以显示在designer左侧的widget列表中，也可以通过“promoted widget”功能导入。
https://www.xdbcb8.com/archives/1675.html
https://ilmvfx.wordpress.com/2016/02/16/use-promoted-widgets-in-qt-designer/
## 
## 
## 
## 
## 
## 
 
软件原理
设计模式
## 设计模式的根本目的是解耦、提高效率。
## Python作为动态语言，其设计模式的实现方法与Java等静态语言不同。有些设计模式Python用自身的语法就可以实现。
## 
## 面向对象编程（Object Oriented Programming，OOP）
## 
## 
- 模块化设计：把可以独立实现的功能分离成一个个模块。
  - 高内聚：将每个功能需要用到的代码都封装到模块中，使模块内部尽量不依赖外部。
  - 低耦合）：让模块与外部的各种联系尽可能地少。
- 单一职责原则    ：每个模块只做它应该做的事，少管闲事，且能独立地把自己的事做好。
- 开闭原则        ：每个模块对扩展开放、对修改关闭。
- 依赖抽象原则    ：每个模块依赖于外部的抽象接口，而不是具体细节。
- 组合优于继承    ：如果两个类之间是is a的关系，应该用继承进行管理，否则使用组合更好。
  - 组合和继承都能实现对象的多态性、提高代码的复用性，但组合能避免类之间的耦合。
  - 继承会加深父类与子类的耦合，破坏子类和父类的封装（导致它们的成员混合在一起）。
## 测试驱动的开发：先规划开发需求、编写测试用例，再开始开发代码。
## 
- 发布/订阅（publish/subscribe）模式：消息的发布者（Publisher）会把消息发送到代理（Broker），由代理接受订阅者（Subscriber）的订阅请求并发布消息。
  - Publisher可以同时是Subscriber。
  - 代理可以是一台设备或一个应用程序。
  - 从客户端/服务器模式来看，Publisher和Subscriber都是客户端（Client），Broker则是服务器（Server）。
- 观察者模式与发布/订阅模式很像，但是观察者模式中被观察对象会直接将消息发送给各个观察者，不存在代理。
## 
## 
## MVC模式：
Model（模型）：负责读写数据库
View（视图）：负责从Model读取数据，显示给用户
Controller（控制器）：从View读取用户的输入信息，向Model发送数据。
## 
## 
## 

 
软件开发
## 编程要有计划，清楚自己的进度。一般分为以下五步：
- 分析需求
  - 要实现什么功能、达到什么效果。
- 分析流程
  - 分析程序的运行流程、逻辑、框架。
- 分离模块
  - 实现常见的功能时先去网上找找有没有现成的，避免重复造轮子。首先理解其用法，其次理解其思路。
  - 不要随便重构代码，这要花费很大代价，除非实在不能向下兼容。
- 编写代码
  - 先想象出代码是什么样子，再把它编写出来。
  - 假设异常总是可能出现，考虑好怎么处理各个环节的异常。
  - 埋头苦干一段时间之后就放松一下，检查进度、宏观规划。
  - 做好规划，不要做无用功，不要重复劳动，不要做错方向。
  - 先规划，再行动；继续规划，继续行动。
  - 软件的性能、可维护性、用户体验、稳定性、安全性需要均衡考虑，比如银行系统最看重安全性。
- 测试验证
  - 编程时尽量多调试，改动大一点或超过一段时间就调试一次。
## 防错方法。
- 将一个复合功能分解成多个基础模块，便于单独修改和单元调试。
  - 一个独立的模块被调用时应该不信任外部的输入，先判断输入是否合法。外部调用该模块时应该不信任它的输出，先判断返回值是否合法。
  - 给每块代码插入一些排错语句有利于调试排错，但是会使得代码变得臃肿、增加程序运行时的开销。
  - 折中的方法是，在程序开发测试阶段多插入一些排错语句，然后逐步确保这些环节不会有错、删除排错语句，让程序相信自己内部的数据，只是严格审查外部输入。
- 排查程序错误时，首先保证能重现错误，然后估计可能出错的代码，逐步排查，缩小嫌疑范围。
  - 可以经常使用断言来检测程序某些环节的变量是否合法。
- 及时处理每个异常可以避免打断程序的运行，但也可能导致忽略重要的异常。
- 在C语言中调用API时，先确定哪个API会创建内存、这块内存又要用哪个API释放。
## 软件的版本号。
- 主版本号.子版本号[.修订版本号[.编译版本号]]
  - 当不再兼容某些旧API时，将主版本号递增（同时将之后的版本号复位为0）。
  - 当修改了API但依然兼容所有旧API时，将子版本号递增。
  - 当修改了某些代码但没有修改API时，将修订版本号递增。
  - 编译版本号表示对同一代码做的不同编译，通常用于在不同平台上发布。
- 几种软件版本名。
  - α（alpha）    ：只是一个初步完成品，通常有很多bug，只用于内部测试，不对外发布。
  - β（beta）    ：消除了严重错误，可以提供给部分用户试用，即公开测试。
  - RC(Release Candidate)    ：候选发布版，如果没有问题就成为release版本。软件在正式发布前可能有多个RC版本。
  - release        ：正式发布的版本，可以提供给所有用户使用。
  - standard        ：标准版，提供了软件的基本功能，满足一般用户的需求。
  - professional    ：专业版，包含一些标准版没有的高级功能，满足专业用户的需求。
  - enterprise    ：企业版，用户可以使用该软件的所有功能。
## 软件开发模式。
- 瀑布开发：严格按照分析需求、设计规划、编程、集成、测试的步骤开发软件，完成上一阶段之后再专心执行下一阶段。
  - 发布周期长，当需求变化时难以做出调整。
- 迭代开发：通常每几周迭代一次，每次只设计和实现软件的一部分功能，提交给客户之后再根据新的需求进行下一次开发。
  - 发布周期短，能适应需求的变化。
- 螺旋开发：结合瀑布开发和迭代开发，先实现软件的重要功能，然后评估风险，确保软件变得稳定之后再实现其它功能，逐渐展开。
  - 有利于抵抗风险。
- 敏捷开发：以需求为核心，一边发布软件的新版本，一边进行开发迭代。
  - 发布周期短，开发、测试效率高，能更好地适应需求的变化。
## 在需求已确定的情况下，软件的开发流程大致分为：编程、构建、集成（将新代码集成到旧代码中）、测试、交付、部署。
- 持续集成（Continuous Integration，CI）：快速完成从编程到集成的周期。
  - 目前流行的CI方案：用Git、GitLab编写好源代码，用Jenkins构建、测试，最后做成Docker镜像，上传到Harbor仓库。
- 持续部署（Continuous Deployment，CD）：快速完成从编程到部署的周期。
  - 目前流行的CD方案：从Harbor仓库拉取镜像，用Rancher部署到k8s集群。
- 持续交付（Continuous Delivery，CD）：快速完成从编程到交付的周期。
## 
## 
## 
## 
 
软件测试
## 测试步骤。
- 熟悉项目
- 分析需求
  - 分析需求后才能清楚测试目标，提高测试的覆盖率。
- 编写测试计划
  - 测试应该有计划地进行。
  - 测试计划不能一劳永逸，不可能测试出完美的软件，也不能停止测试。
- 编写测试用例
  - 编写测试用例是为了方便以后的重复测试，因此不应该对需求多变的功能编写测试用例。
  - 不要害怕遇到bug，bug早晚会出现，一定会出现，越早解决越好。
  - 测试用例要尽量简单，尽量只测试一种功能，便于排查。
  - 先测一下错误的情况，证明测试用例可以发现错误。
  - 常见的测试用例：某种对象的增删查改以及使用、某种信息的查看和设置、某种输入的多种可能……
- 准备测试环境
- 开始测试
  - 测试时先故意让软件出错，证明该测试方法可以发现错误。
  - 测试应该以用户需求为核心，测试的目的是为了提高用户的使用体验，而不是找出多少bug。
- 输出测试报告
  - 描述测试环境、bug的复现步骤
## 根据测试目标进行分类。
- 功能测试：基于黑盒测试。比如软件能否成功运行、能否实现应有的功能、是否与预期状态一致、抓包是否正常。
  - 冒烟测试：检查软件能否达成一些基本要求，这是进行其它测试的前提。适合做成自动化测试。
先测试软件能否在简单情况下跑通，再测试软件能否在复杂情况下跑通。
  - 异常测试：软件的容错性如何、运行出错时怎么定位错误，比如是否会输出日志。
- 性能测试：测试影响用户体验的性能，比如软件或服务器的响应速度、对系统资源的消耗量。
  - 负载测试（load testing）：测试几种不同负载情况下，软件的运行状态。比如一百个连接数、一千个连接数有什么区别。
  - 压力测试（stress testing）：逐渐增加负载压力，找到软件的最大承受能力。从而确定软件的能力上限。
  - 极限测试：加到最大负载压力，测试软件在极限情况下能坚持多久。从而确定软件有多少能力可以透支。
  - 容量测试：通过测试找到软件的最大容量。比如数据库的最大存储量。
  - 稳定性测试：测试在某种程度的负载压力下，软件长时间运行的稳定性。比如连续运行时tps能保持稳定。
  - 高可用性：测试软件能否长时间运行，一直提供可靠服务。
- 兼容性测试：测试对不同平台的兼容性、不同平台之间能否正常通信。
- 安全性测试：测试软件对用户访问权限的控制、对数据的保护等方面。
  - SQL注入测试
## 软件测试的其它分类。
- 根据能否自动测试分为：
  - 手动测试
  - 自动测试：主要用于一些经常重复执行的测试用例。
- 根据是否运行程序分为：
  - 静态测试：不运行程序，检查源代码、说明文档等内容。
  - 动态测试：运行程序，检查程序的运行状态。
- 根据是否了解源代码分为：
  - 白盒测试：阅读源代码，理解软件的运行逻辑，找出软件内部的问题。
  - 黑盒测试：不阅读源代码，分析程序的外部特征。
  - 灰盒测试：综合使用白盒测试和黑盒测试。
- 根据软件的开发阶段分为：
  - 单元测试：测试软件中的一个模块。
  - 集成测试：将单个模块集成到软件中，看能否组装在一起。
  - 系统测试：测试整个软件系统，一般在生产环境中运行。
  - 验收测试：由用户测试验收。
  - 回归测试：旧代码被修改后要重新测试，检查软件是否照常。
## 测试用例的设计方法。
- 等价类划分法：将软件的输入值分成多个集合，每个集合选出一个代表来输入。
  - 比如测试布尔值时，True、False属于有效等价类，除此之外的数字、字符串等集合都是无效等价类。可以取一个数字、一个字符串来测试输入，也可以考虑更详细的情况，比如数字0和1、数字混合字符串等、特殊字符。
- 边界值分析法：已知软件输入值的有效范围时，测试输入这个范围的边界值，看它是否正常。
  - 比如一年里，1月和12月是边界值，软件可能没有正确处理边界值。
- 错误推测法：已知软件可能出错的情况时，故意测试这些情况下软件的运行状态。
- 流程分析法：验证软件的运行流程是否符合预期，比如正常运行流程、出现异常时的处理流程。
- 评定表法：已知软件的判断逻辑时，将所有判断逻辑整理成一个评定表，然后依次测试软件能否实现这些判断逻辑。
  - 比如当输入为数字时软件应该怎么做，当输入为字符串时软件应该怎么做。
- 正交分析法：将影响软件运行的各个输入变量、环境变量整理成表（尽量是互不相干的变量），就得到了大量变量组合，分析每个变量组合对软件的影响。这样测试的覆盖率高。
- 模糊测试：测试各种意外的情况、随机的输入，看能否发现漏洞。
## bug的严重程度。
- 致命错误    ：不能实现重要功能、有重大隐患，必须立即处理。
- 严重错误    ：没有实现次要功能、性能较差。
- 一般错误    ：一些不太重要的问题、某些方面的缺陷，允许延后处理。
- 不重要    ：通常为说明文档的描述错误。
- 建议        ：一些优化的建议。
## 其它概念。
- 测试覆盖率：表示测试用例的有效性。
  - 可分为：覆盖了多少条语句（即执行了它们）、覆盖了多少种可能的输入、覆盖了多少种可能的运行情况。
  - 一味地追求测试覆盖率会增加测试成本，可以适当地关注没被测试覆盖的地方。
- 
## 
## 
## 
 
软件运维
## 运维方式。
- 手工运维：由运维人员手工完成，效率低。
- 自动化运维：基于专家系统的规则，编写程序来自动完成一些常见的运维工作。
- DevOps：即Development（开发）+ Operations（运维），鼓励开发部门和运维、测试等部门紧密联系合作，提高运维、测试的效率（比如使用自动化测试工具、自动化运维工具）。
- AIOps：智能运维，通过人工智能达到比自动化运维更好的效果。
  - 智能运维与自动化运维相比，在处理问题时，不依赖于专家系统的已知规则，而是能通过机器学习，从海量运维数据中自动总结规则。
- 
- 
## 发布新版本的方式。
- 直接发布：将所有服务器都停掉，部署了新版本之后再启动服务。
  - 过程简单，但是服务会中断一段时间。
- 蓝绿发布：部署一套独立的新版本服务器（称为蓝组），把用户流量转移到新服务器上，等确定正常之后，再回收旧版本的服务器（称为绿组）。
  - 过程与蛮力发布一样简单，但是需要两倍的服务器资源。
  - 如果新版本有问题，可以立即回滚到旧版本。
- 金丝雀发布：先更新少部分服务器，等确定正常之后，再更新所有服务器。
  - 在国内又称为灰度发布。
  - 如果测试耗时太久，可以先进行粗略测试，然后灰度发布，在生产环境中进行详细测试。
- 滚动发布：逐步更新服务，比如每次更新10%的服务器。
  - 如果发现异常，可以回滚到上一阶段，但不能直接回滚到旧版本。
## 
## 
## 其它概念。
- 可扩展性：系统的性能可以提高。
  - 垂直扩展：通过增强单个系统的能力来提高性能。
  - 水平扩展：通过增加系统实例的数量来提高性能。
- 
## 
## 
## 
## 
## 
## 
 
算法
## 算法是指解决问题的方法，是编程的核心。
- 数据结构和算法都是独立于编程语言的概念，选择好的数据结构和算法可以提高程序运行的效率。
- 算法可以用伪代码、流程图等方法描述。
- 一个算法应该具备以下特点：
  - 有输入和输出
  - 可行性：可以通过编程实现。
  - 确定性：每一步操作的含义都是确定的。对于一种输入，只会得到一种输出值。
  - 有穷性：执行的操作数是有限的，会在一段时间内完成。
## 评价算法性能的主要标准是时间复杂度和空间复杂度。
- 空间复杂度：算法运行时占用的内存大小。
- 时间复杂度：算法的运行时间。
  - 忽略计算机硬件性能的差异，因为算法的运行时间与算法中简单操作的次数成正比，一般设问题规模为n，用简单操作的次数f(n)来表示算法的时间复杂度。
  - 简单操作包括各种运算、流程转向、返回值、输入和输出等。
  - 如下，for语句中i<n循环了n+1次，i++、s+=b循环了n次。另外每次进行i>=n的比较后都要选择执行循环体还是结束循环，这个流程转向也是一个简单操作。综上，该for语句的简单操作次数为4n+2，整个函数的时间复杂度为f(n)=4n+4。
int sum(int b, int n){
int i, s = 0;            // 定义语句int i不算简单操作
for(i=0; i<n; i++)
s += b;            // 复合赋值运算符也只算一次简单操作
return s;
}
  - 一般只考虑算法时间复杂度的数量级（order），但不是以十进制作为一个数量级，而是当两个数相除的极限值不是无穷小0或无穷大∞时就属于同一级。例如上述算法的数量级可简记为O(n)，其它常见的数量级还有O(2n)、O(n2)、O(n!)等。特别地，O(1)表示时间复杂度为常数，即与问题规模n无关。
- 
## 
## 基本算法。
- 递归：定义函数时，在函数体中调用该函数本身。
  - 递归通常是让函数一次只处理一个步骤或一个层级的事务，然后调用函数自己，传入本次的处理结果，去处理下一个事务。
  - 由于每次调用都会创建参数的副本，递归层次变多时占用内存就会过大。
  - 递归的算法复杂度可能较高。
  - 当递归层数太多时会导致栈溢出，因为编译器要多次将运行时的上下文入栈保存。
- 动态规划法：像递归一样处理一系列类似的事务，但是存储每个事务的处理结果，以便于在遇到处理过的事务时直接复用。
- 遍历：逐个访问集合中的所有元素。
- 迭代：反复执行某一段代码，以逐渐达到某个目的。
  - 编程时有两种方法可实现迭代：使用循环、使用递归。
## 
## 
## 
## 把一些算法做成自己的库
## 
## 
## 待做的算法


实现等差数列求和公式

判断任意一个数是否是质数


递归求利率
int sum(int start,float rate,int n)
每次调用函数只计算一次利率，n极大时可以求出自然常数

分别用递归法和动态规划法求斐波那契数列的第a项数
动态规划时，从底层（即n=1）开始计算，逐步计算到顶层（即n=a），用数组保存每项的值

递归可用于按递推公式求数列，

错序排列
n个有序的元素应有n!个不同的排列，如若一个排列使得所有的元素不在原来的位置上，则称这个排列为错排
找出规律，用递归求

## 
## 
## 
## 
## 
## 
## 
## 
## 
## 
## 
## 
## 
## 
## 
## 
 
数据结构
## 数据：对客观事物的符号表示，。
- 数据元素：数据的基本单位。
- 数据对象：一部分数据元素的集合。
- 各种编程语言都定义了自己的数据类型，一般分为简单类型和结构类型两种，像C语言中的基本数据类型与结构体。
  - 简单类型的数据都是无法细分的单位，而结构类型的数据是由简单类型或结构类型的数据组成的。
- 数据结构：指数据、数据之间的关系。
  - 可以表示成二元组的形式，比如B=(K，R)，其中B代表一个数据结构，K是数据的有限集，R是数据之间的关系的有限集。
  - 也可以表示成三个方面的内容：逻辑结构、存储结构（物理结构）、数据的运算。
## 逻辑结构是从实际问题中抽象出来的结构，用于反映数据之间的逻辑关系。以下是四种基本的逻辑结构：
- 集合结构：所有节点属于一个集合。
- 线性结构：节点之间只存在一对一的关系，可以依次连成一条线，有且仅有一个头节点、一个尾节点。
- 树型结构：节点之间存在一对多的关系。
- 图状（网状）结构：节点之间存在多对多的关系。
## 存储结构是逻辑结构在计算机中的存储形式。
- 顺序存储结构：节点们的存储地址连续，并且存储顺序与逻辑顺序一致。
  - 比如数组，其元素之间的逻辑关系为线性结构，存储时采用顺序存储结构。
- 链式存储结构：节点们的存储地址不必连续，分散存储，只是可以用一条线串联起来。
- 索引存储结构
- 散列存储结构
## 常见的数据结构。
- 线性表：一组存储地址连续的元素，存储顺序也与逻辑顺序一致。
  - 典型的例子就是数组。
- 栈(stack)：一种线性结构，只能在一端（称为栈顶）移入（PUSH）、移出（POP）元素，因此读写顺序为先进后出(First-In Last-Out，FILO)。
  - 栈的基本操作包括入栈、出栈、读栈顶元素。
- 堆(heap)：一种完全二叉树，读写顺序任意。
- 队列：一种线性结构，只能在一端移出元素（称为队首）、在另一端移入元素（称为队尾），因此读写顺序为先进先出（First-In First-Out，FIFO）。
- 链表：像数组，但是属于链式存储结构，每个节点包含一个指向下一个节点的指针。
  - 顺序存储可以访问任意节点，而链表只能从第一个节点开始逐个访问。
  - 例：
typedef struct Node{
    int id;
    struct Node *next;            // 只有一个指向下一个节点的指针，称为单向链表
    // struct Node *last;            // 加上指向上一个节点的指针，就变成了双向链表
};
Node *n = malloc(sizeof(Node));    // 创建一个节点
n->id = 0;
n->next = NULL;                    // 初始化
- 树：除了根节点（有且仅有一个）以外的其它节点都有且仅有一个前件即父节点，除了叶子节点以外的其它节点都有一个或多个后件即子节点。一个节点的子节点的个数称为该节点的度，叶子节点的度为0。所有节点中最大的一个度记作树的度。树中某个节点的深度是指从根节点（深度为1）往下到该点的层数，高度是指从叶子节点（高度为1）往上到该点的层数。
- 二叉树：每个节点最多有两个子节点，称为左子树和右子树。二叉树中度为0的节点总是比度为2的节点多一个。满二叉树中除了叶子节点以外的其它节点都有两个子节点，完全二叉树中除了最底下两层以外的其它节点都有两个节点、且叶子节点都集中在最底层的左侧。故满二叉树一定是完全二叉树，而完全二叉树不一定是满二叉树。完全二叉树实际上是使按层遍历的结果与满二叉树相同。
- 图：如果两个节点相邻，就画上一条连接的线段，称为边。
- 
## 
## 
## 字节序：存储多个字节时的顺序。分为大端和小端两种。
- 大端模式（Big Endian）：先存储数据的高字节（即大端）。这样内存的起始地址存储着最高的字节，看起来像字符串从左往右的阅读顺序，更常用。
- 小端模式（Little Endian）：先存储数据的低字节（即小端）。
## 
## 
## 
 
查找算法
## 
## 相关概念。
- 遍历：依次访问一个集合中的每个元素。
- 
## 
## 二叉树的遍历方法有四种：
- 按层遍历：按从上到下、每一层从左到右的顺序遍历。图中的结果是abcdfeg。
- 前序遍历：先访问父结点，再访问左子树，最后访问右子树。图中的结果是abdefgc。
- 中序遍历：先访问左子树，再访问父结点，最后访问右子树。图中的结果是debgfac。
- 后序遍历：先访问左子树，再访问右子树，最后访问父结点。图中的结果是edgfbca。分析时，a为父结点，往左子树看，b、d也是父结点，e是右子树，是这一层优先级最高的了。往上一层看d是左子树，b还是父结点，所以d的优先级最高。b右下方的f也是父结点，再往下看g是左子树。回来往上看f是右子树，b是左子树，c是右子树。
 
## 顺序查找是从线性表的第一个元素开始逐个与特定元素比较，若相等则查找成功。采用链式存储结构的线性表或无序的线性表都只能使用顺序查找。
## 二分法查找是先将线性表的中间元素与特定元素比较，若相等则查找成功，若中间元素较小则在线性表的后半部分重复该操作，若中间元素较大则在线性表的前半部分重复该操作。二分法仅适用于采用顺序存储结构的、非递减排列的有序线性表。设线性表长度为n，最坏的情况下要比较log2n次。
## 
## 
## 
## 
## 
## 
## 
## 
## 
## 
## 
 
排序算法
## 
## 
## 
## 冒泡排序法是从表头开始，逐个比较相邻元素的大小，若前者大于后者，则互换位置，最终使得最大项在线性表的末尾，循环该操作，每次循环都使当前的最大项移到表末，而下一次循环就少比较一次。最坏的情况下要比较n(n-1)/2次。"冒泡"一词是形容最大的元素会像水泡一样慢慢浮到线性表的顶端。
## 快速排序法一般取线性表的第一个元素与其它元素比较排序，使得左边的元素都小于等于它，右边的元素都大于它，然后对两边元素不停重复该操作。
## 冒泡排序法和快速排序法都属于交换类排序法。
## 
## 
## 
## 
## 
## 
## 