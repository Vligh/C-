[TOC]

#### CLion一个工程文件下执行多个.cpp文件

①在setting下，Plugins搜索C/C++ Single File Execution插件进行安装

②安装成功后，在想要执行的.cpp文件下，右键点击最后一行![image-20220825210254270](C:\Users\admin\AppData\Roaming\Typora\typora-user-images\image-20220825210254270.png)

#### 为什么要使用 **using namespace std;** ?

有些名字容易冲突，所以会使用命名空间的方式进行区分，具体来说就是加个前缀。比如C++标准库里面定义了vector容器，自己也可以写个vector类；这样名字就冲突了。于是标准库里的名字都加上std::的前缀，必须使用std::vector来引用。同理，自己的类也可以加个自定义的前缀。但是经常写全名会很繁琐，所以在没有冲突的情况下可以写一句using namespace std;，接下去的代码就不用写前缀直接写vector了。std是标准库函数使用的命名空间，是standard(标准)的缩写。

+ 默认情况下，int、short、long都是带符号的，即 signed。

+ 枚举类型：如果一个变量只有几种可能的值，可以定义为枚举(enumeration)类型。所谓“枚举”是指将变量的值一一列举出来，变量的值只能在列举出来的值的范围内。

  enum 枚举名{

  ​			标识符[=整型常数],

  ​			标识符[=整型常数],

  .....

  ​			标识符[=整型常数]

  } 枚举变量;

  如果枚举没有初始化，即省掉"=整型常数"时，则从第一个标识符开始。

  例：定义了一个颜色枚举，变量c的类型为color。最后，c被赋值为“blue”。

  enum color {red, green, blue} c;

  c = blue;//这里的c就等于2。

  默认情况下，第一个名称的值为0，往后依次加1，如果有初始值，在其初始值后的值同理依次加1.

  enum color {red, green = 5, blue} ;//这里red=0，blue=6

  可以这样用enum color { red, green, blue } col;  color  c = red;

+ 转义字符 \,\a 警报铃声  \b 退格键   \f换页符   \n 换行符  \r 回车  \t水平制表符  \v 垂直制表符

+ 定义成const后的变量，程序对其只能读不能修改。

#### 宏定义与const区别

<img src="C:\Users\admin\AppData\Roaming\Typora\typora-user-images\image-20220125180229526.png" alt="image-20220125180229526" style="zoom: 80%;" />![image-20220125180254658](C:\Users\admin\AppData\Roaming\Typora\typora-user-images\image-20220125180254658.png)

<img src="C:\Users\admin\AppData\Roaming\Typora\typora-user-images\image-20220125180254658.png" alt="image-20220125180254658" style="zoom:80%;" />

#### 修饰符类型

<img src="C:\Users\admin\AppData\Roaming\Typora\typora-user-images\image-20220125181052363.png" alt="image-20220125181052363" style="zoom:80%;" />

#### 存储类

extern存储类是用来在另一个文件中声明一个全局变量或函数。

<img src="C:\Users\admin\AppData\Roaming\Typora\typora-user-images\image-20220126140913550.png" alt="image-20220126140913550" style="zoom:67%;" />

#### 几个数学函数

`#include <valarray>`

double  **pow**(double  x, double  y)该函数返回x的y次方

double  **sqrt**(double) 返回参数的平方根

int **abs**(int) 返回整数的绝对值

double **fabs**(double) 返回浮点数的绝对值

**log函数**也能用详细：

①以e为底：`log(n)`   ②以10为底：`log10(n) `   ③以m为底：`log(n)/log(m)`

#### 随机数

两个相关函数，rand()该函数只返回一个伪随机数。生成随机数前必须先调用strand()。

srand((unsigned) time(NULL));

rand() % 10 + 1;//随机数从1开始，区间个数为10，即在1到10之间的随机数[1,10]。

#### 指针

是一个变量，其值为另一个变量的地址，即内存位置的直接地址。

int var = 20；

int  *p；

p = &var；

var等于20，p是var-20的地址，*p是20

int  x =  5；

int&  y = x；

这里y等于5，&y为x=5的地址<img src="C:\Users\admin\AppData\Roaming\Typora\typora-user-images\image-20220206133530628.png" alt="image-20220206133530628" style="zoom: 80%;" />

**这里再做一下解释**:

```c++
int x = 5;
int &y = x;
int z = x;
cout<<y<<"\n";
cout<<z<<"\n";
cout<<&x<<"\n";
cout<<&y<<"\n";
cout<<&z;
```

输出结果为如下，结果显示x=y=z=5，y的地址和x的地址一样即5这个数字的地址有两个标识x和y，而z的地址是另外一个地址。

<img src="C:\Users\admin\AppData\Roaming\Typora\typora-user-images\image-20220212165214608.png" alt="image-20220212165214608" style="zoom:80%;" />

#### 日期&时间

需要引用<ctime>头文件。

<img src="C:\Users\admin\AppData\Roaming\Typora\typora-user-images\image-20220206135617853.png" alt="image-20220206135617853" style="zoom:80%;" />

​		结果：<img src="C:\Users\admin\AppData\Roaming\Typora\typora-user-images\image-20220206135639335.png" alt="image-20220206135639335" style="zoom:80%;" />

#### 输入输出

<img src="C:\Users\admin\AppData\Roaming\Typora\typora-user-images\image-20220206140102389.png" alt="image-20220206140102389" style="zoom:80%;" />

还有输入运算符`>>` 默认会忽略空格，遇到空格就认为输入结束。

#### 结构体

```c++
struct Books{
	char title[50];
	char author[50];
	char subject[100];
	int book_id;
} book;
```

这里定义了一个Books 的结构体，初始化了变量book。

book.title来访问book里的title成员。

还有定义指向结构的指针：

```c++
struct Books  *book1;
book1->title;//这里来访问title成员
```

typedef关键字

```c++
typedef struct Books{
	char title[50];
	char author[50];
	char subject[100];
	int book_id;
}Books;
```

现在可以直接使用Books来定义Books类型的变量，而不需要使用struct关键字。如Books  Book1;

也可以使用typedef关键字来定义非结构类型：

```c++
typedef long int *pint32;
pint32 x,y,z;
```

x,y,z都是指向长整型long int 的指针。

+ 范围解析运算符::

如果想要定义类中的成员函数，可以直接在类内部定义，或者使用**范围解析运算符::**

```c++
class Box{
	public:
		double length;//长度
		double breadth;//宽度
		double height;//高度
		double getVolume(void);//返回体积
};
Ⅰ直接在类内部定义
class Box{
    public:
		double length;//长度
		double breadth;//宽度
		double height;//高度
		double getVolume(void)//返回体积
        {
            return length*breadth*height;
        }
};
Ⅱ在类外部使用范围解析运算符::
double Box::getVolume(void){
    return length*breadth*height;
}
```

+ protected成员

这种成员可以在派生类(即子类)中可访问。`class SmallBox:Box //SmallBox是派生类`

继承时不声明默认是private继承

+ 友元函数

类的友元函数是定义在类外部，但有权访问类的所有私有成员和保护成员，需要在类定义中该函数原型前使用关键字**friend**。

+ 重载函数和重载运算符

在该作用域声明的函数或方法具有相同的名称但它们的参数列表和定义不同。

```c++
class printData{
	public:
    	void print(int i){
            cout<<"整数为:"<<i<<endl;
        }
   		void print(double f){
            cout<<"浮点数为:"<<f<<endl;
        }
    	void print(char c[]){
            cout<<"字符串为:"<<c<<endl;
        }
};
//调用
printData pd;
pd.print(5);//
pd.print(20.2);
char c[] = "Hello C++";
pd.print(c);
```

#### 动态内存

栈：在函数内部声明的所有变量都将占用栈内存

堆：程序总未使用的内存，在程序运行时可用于动态分配内存。

<img src="C:\Users\admin\AppData\Roaming\Typora\typora-user-images\image-20220206155316346.png" alt="image-20220206155316346" style="zoom:80%;" />

动态二维数组实例如上。

+ memset函数，void *memset(void *str,int c,size_t n)复制字符c(一个无符号字符)到参数str所指向的前n个字符。

  声明`void *memset(void *str,int c,size_t n)`参数str--指向要填充的内存块；c--要被设置的值，该值以int形式传递，但是函数在填充内存块时使用该值的无符号字符形式；n--要被设置为该值的字符数。返回一个指向存储区str指针。

<img src="C:\Users\admin\AppData\Roaming\Typora\typora-user-images\image-20220208170201186.png" alt="image-20220208170201186" style="zoom:80%;" />

#### sstream头文件，数据类型转换，int->string且string->int同理

```c++
#include<iostream>
#include<string>
#include<sstream>
using namespace std;

string toString(int a){
    stringstream ss;
    ss<<a;//将int类型的值放入输入流中;如果是string转int这里将string类型的变量输入给ss;
    string ans;
    ss>>ans;//从ss中抽取前面插入的int类型的值，赋给string类型;
    		//如果是string转int这里将ss中抽取的值给ans;
    return ans;
}

//如果要多次转换，每次都要将ss清空:ss.clear()语句，原因不清楚，实践得出。
```

#### set常用方法

```  C++
begin()   返回指向第一个元素的迭代器
end()     返回指向迭代器的最末尾处(即最后一个元素的下一个位置)
clear()   删除set容器中的所有元素
empty()   判断set容器是否为空
max_size()返回set容器能容纳的元素的最大限值
size()    返回当前set容器的元素个数
rbegin()  返回的值和end()相同
rend()    返回的值和rbegin()相同
```

+ set特点：①set中的元素都是排序好的，set中的元素都是唯一的没有重复的。②不能通过set的迭代器去修改set元素，原因是修改元素会破坏set组织，当对容器中的元素进行插入或删除时，操作之前的所有迭代器在操作之后依然有效。

**set定义及初始化**

使用之前必须加相应容器的头文件:`include <set>`set属于std命名域的，因此需要通过命名限定，例如using std::set;

```c++
set<int> a;//定义一个int类型的集合a
//set<int> a(10); //错误,未定义这种构造函数
//set<int> a(10,2); //错误,未定义这种构造函数
set<int> b(a);//定义并用集合a初始化集合b
set<int> b(a.begin(),a.end());//将集合a中的所有元素作为集合b的初始值
/*还可以使用数组直接初始化向量*/
int n[] = {1,2,3,4,5};
list<int> a(n,n+5);//将数组n的前5个元素作为集合a的初值。
```

**基本操作**

+ 容器大小:`st.size();`
+ 容器最大容量:`st.max_size();`
+ 容器判空:`st.empty();`
+ 查找键key的元素个数:`st.count(key);`
+ 插入元素`st.insert(4)`
+ 删除元素`st.erase(4)//删除特定的元素`，`st.clear()//清空所有元素`
+ 查找键key:`st.find(key)` 存在则返回该元素，否则set.end():st.find(key);

<img src="C:\Users\admin\AppData\Roaming\Typora\typora-user-images\image-20220209164108331.png" alt="image-20220209164108331" style="zoom: 80%;" />

+ 遍历元素

```c++
set<int>::iterator it;//这是指针
for(it = st.begin();it != st.end();it++)
	cout<<*it<<endl;
```

#### continue语句

continue语句类似于break语句，不是强制终止，continue会跳过当前循环，开始下一个循环。

![img](https://www.runoob.com/wp-content/uploads/2014/09/c-continue-statement-works.jpg)

#### npos

它等于size_type类型可以表示的最大值，用来表示一个不存在的位置，例如string::npos,  container_type::size_type。

std::string的查找函数①find②rfind③find_first_of等都是返回string::size_type类型的值。

**人话**:npos可以表示string的结束位子，是string::type_size类型的，也就是find()返回的类型。**find函数在找不到指定值的情况下会返回string::npos.**

```c++
int idx = str.find("abc");
if(idx == string::npos)
```

上面代码,idx类型定义为int是错误的，它必须定义为string::size_type。因为string::size_type描述的是size，所以为无符号整数类型，缺省配置器**以size_t作为size_type**.

####  二分法

在查找的数据结构要有序:

<img src="C:\Users\admin\AppData\Roaming\Typora\typora-user-images\image-20220220151701875.png" alt="image-20220220151701875" style="zoom:80%;" />

#### sort函数

sort(first,last)；头函数`<algorithm>`；对容器或普通数组中[first,last)范围内的元素进行排序，默认**升序**排序。

这里first和last是指针类型，比如，num[10]对这个数组排序，sort(num,num+10)这样才对，sort(0,10)这样不对。

#### 移位运算符(左乘右除)

<<左移:按二进制形式把所有的数字向左移动对应的位数，高位移出(舍弃)，低位的空位补零。

例如:3<<2,是将数字3左移2位。人话:**左移一位相当于乘以2的一次方**，左移n位相当于乘以2的n次方。

\>>右移:**右移一位相当于除2**，右移n位相当于除以2的n次方。

#### 递归

一个例子机器人走方格，有一个X*Y的网格，一个机器人只能走格点且只能向右或向下走，要从左上角走到右下角。设计一个算法，计算机器人有多少种走法。给定两个正整数int x, int y,请返回机器人的走法数目。保证x+y小于等于12.

<img src="C:\Users\admin\AppData\Roaming\Typora\typora-user-images\image-20220221163537968.png" alt="image-20220221163537968" style="zoom:80%;" />

```c++
//DP公式:f(x,y)=f(x,y-1)+f(x-1,y)
int Num_Walk(int x,int y){
	if(x==1||y==1) return 1;
	return Num_Walk((x-1),y)+Num_Walk(x,(y-1));
}
```

也可以使用迭代的方式来实现

<img src="C:\Users\admin\AppData\Roaming\Typora\typora-user-images\image-20220221165954302.png" alt="image-20220221165954302" style="zoom:80%;" />

初始化可以使用二维数组，

```c++
//迭代方式
int m,n,ans;
cin>>m>>n;
int square[m+1][n+1];
for (int i = 1; i < m+1; ++i) {
    square[i][1] = 1;
}
for (int j = 1; j < n+1; ++j) {
    square[1][j] = 1;
}
for (int i = 2; i < m+1; ++i) {
    for (int j = 2; j < n+1; ++j) {
        square[i][j] = square[i-1][j]+square[i][j-1];
        ans = square[i][j];
    }
}
cout<<ans<<endl;
```

#### dfs深度优先搜索/bfs广度优先算法

dfs一条路走到黑，bfs能走的都走一遍。

dfs算法如下，一个数独题(9*9方格)：

<img src="C:\Users\admin\AppData\Roaming\Typora\typora-user-images\image-20220223174723008.png" alt="image-20220223174723008" style="zoom:67%;" />

<img src="C:\Users\admin\AppData\Roaming\Typora\typora-user-images\image-20220223174308179.png" alt="image-20220223174308179" style="zoom:67%;" />

深度优先遍历，在树和图中常见，先序遍历，中序遍历，后序遍历，都是。

树的深度优先搜索在二叉树的特例下，就是二叉树的先序遍历操作。

再来张图:

<img src="C:\Users\admin\AppData\Roaming\Typora\typora-user-images\image-20220407162222024.png" alt="image-20220407162222024" style="zoom: 67%;" />

#### getchar();//用来吸收回车键

它会在输入缓冲区顺序读入一个字符(包括空格、回车和Tab)

#### %s%d%c基本概念和用法

https://blog.csdn.net/myyllove/article/details/79574582

| **%d**  | **十进制有符号整数** |
| ------- | -------------------- |
| **%u**  | **十进制无符号整数** |
| **%f**  | **浮点数**           |
| **%s**  | **字符串**           |
| **%c**  | **单个字符**         |
| **%lf** | **double浮点数**     |
| **%f**  | **浮点数**           |

printf("%02d",a)表示变量a采用右对齐方式输出，如果a为2，则输出02，如果a为10，输出10.

可以在%和字母之间加上小写字母l，表示输出的是长型数，%ld 输出long整数，%lf 输出double浮点数

可以在%和字母之间插入数字表示最大长宽。%3d表示输出3位整型数，不够3位右对齐，%9.2f表示输出浮点数，其中小数点2位整数6位，小数点占一位，不够9位右对齐。%8s表示输出8位字符的字符串，不够8个字符右对齐。

如果用浮点数表示字符或整型量的输出格式，小数点后数字代表最大宽度，小数点前数字代表最小宽度。例如:%6.9s表示一个长度不小于6且不大于9的字符串。如大于9，则第9个字符以后的内容将被删除。

可以控制输出左对齐或右对齐，在%和字母之间加入“-”号说明输出为左对齐，否则右对齐。例如:%-7d表示输出7位整数左对齐。

```c++
double average;
printf("%.2lf", average);//输出保留两位小数
```



#### string字符串详解

```c++
string s = "http://c.biancheng.net";
int len = s.length();
cout<<len<<endl;
//输出结果为22，string末尾没有‘\n’字符，
//所以length()返回的是字符串的真实长度，而不是长度+1
```

1.插入字符串insert

`string& insert(size_t pos,const string& str);` 原型

```c++
string s1,s2;
s1 = "123456";
s2 = "aaa";
s1.insert(3,s2);
cout<<s1<<endl;
//结果为123aaa45
```

2.删除字符串erase

`string& erase (size_t pos = 0, size_t len = npos);` 原型,**pos表示要删除的子字符串的起始下标，len表示要删除子字符串的长度**。**如果不指明len，那么直接删除从pos到字符串结束处的所有字符**(此时len = str.length - pos)

```c++
string s1,s2,s3;
s1 = s2 = s3 = "123456"
s2.erase(3);//下标为3及后面都删除
s3.erase(3,2);//下标3往后两个删除
cout<<s1<<endl;//123456
cout<<s2<<endl;//123
cout<<s3<<endl;//1236
```

3.提取子字符串

`string substr (size_t pos = 0, size_t len = npos) const;` **pos为要提取的子字符串的起始下标**，**len为要提取的子字符串的长度**。如果pos越界则抛出异常，len越界会提取从pos到字符串结尾处的所有字符。

```c++
string s1 = "first second third";
string s2;
s2 = s1.substr(6,6);
cout<<s1<<endl;//first second third
cout<<s2<<endl;//second
```

4.查找字符串

1)find() 原型不写了，s1.find(s2,5);意义是在s1的第5个位置查找有无s2，有则返回下标,如果没找到则返回无穷大的数。

2)rfind()和find类似，s1.rfind(s2,6);意义是在s1中找s2，最多找到s1的下标为6的位置，有则返回下标，没有则返回无穷大的数

3)find_first_of()函数，用于查找子字符串和字符串共同具有的字符在字符串中首次出现的位置。

```c++
string s1 = "first second third";
string s2 = "asecond";
int index = s1.find_first_of(s2);//3
```

这里例子中s1和s2共有的字符是‘s’，该字符首次在s1中出现的下标是3，所以返回3.

#### Tips:四舍五入

![image-20220225184846039](C:\Users\admin\AppData\Roaming\Typora\typora-user-images\image-20220225184846039.png)

上面pass=5,n=7,excel=3,要求百分号前四舍五入。

#### 最大公约数gcd

```c++
int gcd(int m,int n){
	if(n==0) return m;
	return gcd(n,m%n);
}
int gcd(int a,int b){
    while(a!=b){
        if(a>b)a=a-b;
        else b=b-a;
    }return a;
}
```

#### 并查集Disjoint Set

在一些有N个元素的集合应用问题中，通常在开始时让每个元素构成一个单元素的集合，然后按一定顺序将属于同一组的元素所在的集合合并，期间要反复查找一个元素在哪个集合中。并查集是一种树型的数据结构，用于处理一些不相交集合的合并及查询问题。常常在使用中以森林来表示。

举个栗子 : 判断亲戚关系

输入n个人，m个亲戚关系，询问p对亲戚关系。

9 7 1 // 2 4 // 5 7 // 1 3 // 8 9 // 1 2 // 5 6 //2 3 //1 9,最后问1 9是否是亲戚关系。

初始状态:{1}{2}{3}{4}{5}{6}{7}{8}{9}

输入关系，分离集合

(2,4) {2,4}{1} {3} {5} {6} {7} {8} {9}

(5,7) {2,4} {5,7} {1} {3} {6} {8} {9}

(1,3) {1,3} {2,4} {5,7}{6} {8} {9}

(8,9) {1,3} {2,4} {5,7} {8,9}{6}

(1,2) {1,2,3,4} {5,7} {8,9}{6}

(5,6) {1,2,3,4} {5,6,7} {8,9}

(2,3) {1,2,3,4} {5,6,7} {8,9}

判断亲戚关系 (1,9) ,因为1 9 不在同一集合内，所有输出"NO"

下面不一样，找父节点,集合中自己定义的父节点

<img src="C:\Users\admin\AppData\Roaming\Typora\typora-user-images\image-20220227160018118.png" alt="image-20220227160018118" style="zoom:67%;" />

#### &号

n&1，判断奇偶数，n为奇数时结果为1，n为偶数是结果为0.

n&1\==1   < == >  n%2==1.

#### char转换为int(char to int)

```c++
char a = '0';
int a1 = int(a);//48
int a2 = a-48;//0
int a3 = a-'0';//0
```

同理，int转char，是+48.

有个库函数`itoa(int,char *,int)`三个参数，第一个是需要char->int中的int，第二个参数为char，第三个int参数为想要转换后几进制的数。头文件为`<stdlib.h>`.

#### 一个数字取出单个数字或取出前几位后几位

```c++
int x=2020,four,three,two,one;
four = x/1000;//取千位的数字
three = (x/100)%10;//取百位的数字
two = (x/10)%10;//取十位的数字
one = x%10;//取个位的数字

%是取出后几位，/是取出前几位
比如4659/10=465取出了前三位。4659%10=9取出最后一位。
```

#### STL-vector

一个数组必须要有固有的长度，在开一个数组时，这个长度就被静态的确定下来了，但是vector却是数组的plus版，对于一个数据来讲，往vector里存多少数据，vector的长度就有多长。

实际上vector的实现方式是基于倍增思想的:假如vector的实际长度为n,m为vector当前的最大长度，那么加入一个元素的时候，先看一下，假如当前的n=m，则再动态申请一个2m大小的内存。反之，在删除的时候，如果n>=m/2,则再释放一半的内存。

##### vector容器的声明

vector容器存放在模板库:`#include<vector>`里，使用前需要先开这个库。vector容器的声明遵循C++STL的一般声明原则:容器类型<变量类型>名称.例:

```c++
#include<vector>
vector<char> vec;
vector<int> vec1;
vector<pair<int,int>> vec2;
vector<node> vec3;
struct node{...}
vector<int> a(10,1);//定义了10个整数元素的向量，且给出每个元素的初值为1
```

##### vector容器的使用方法

| 用法                                   | 作用                                                         |
| -------------------------------------- | ------------------------------------------------------------ |
| vec.begin(),vec.end()                  | 返回vector的首、尾**迭代器**                                 |
| **vec.front(),vec.back()**             | 返回vector的首、尾**元素**                                   |
| **vec.push_back()**                    | **从vector末尾加入一个元素**                                 |
| vec.size()                             | 返回vector当前的长度(大小)                                   |
| **vec.pop_back()**                     | **从vector末尾删除一个元素**                                 |
| vec.empty()                            | 返回vector是否为空，1为空，0为不空                           |
| vec.clear()                            | 清空vector                                                   |
| vec.erase(vec.begin()+1,vec.begin()+3) | 删除vec中第1个(从第0个算起)到第二个元素，也就是说**[vec.begin()+1 , vec.begin()+3 )** |

vector容器支持**随机访问**，可以像数组一样使用[]来取值。不是所有的STL容器都有这个性质。初始化时[]下标不能使用，只有在vector中有值(初始化后)才可以使用[].

#### STL-queue

##### queue容器说明

队列先进先出，`#include<queue>`声明遵循c++STL的一般声明原则:容器类型<变量类型> 名称

```c++
#include <queue>
queue<int> q;
queue<char> q1;
```

| 用法                    | 作用                                |
| ----------------------- | ----------------------------------- |
| **q.front(), q.back()** | 返回queue的首尾**元素值**           |
| **q.push()**            | 从queue末尾加入一个元素             |
| **q.size()**            | 返回queue当前的长度(大小)           |
| **q.pop()**             | 从queue删除第一个元素，不返回元素值 |
| **q.empty()**           | 返回queue是否为空，1为空，0为不空   |

queue不支持随机访问，就是不能像数组一样任意取值，queue不能用clear()清空，清空queue必须一个一个弹出。queue不支持遍历，所以没有begin()end()函数。

#### STL-deque

双端队列，deque<int\>  deq

| 用法                           | 作用                                 |
| ------------------------------ | ------------------------------------ |
| **deq.size()**                 | 容器大小                             |
| deq.max_size()                 | 容器最大容量                         |
| deq.resize()                   | 更改容器大小                         |
| **deq.empty()**                | 容器判空                             |
| **deq.push_front(const T& x)** | **头部添加元素**                     |
| **deq.push_back(const T& x)**  | **末尾添加元素**                     |
| **deq.pop_back()**             | 末尾删除元素                         |
| **deq.clear()**                | 清空元素                             |
| **deq.front()**                | **访问第一个元素或deq[1],deq.at(1)** |

| **deq.back()**                            | **访问最后一个元素**    |
| ----------------------------------------- | ----------------------- |
| **deq.pop_front()**                       | 头部删除元素            |
| deq.insert(iterator it, int n,const T& x) | 任意位置插入n个相同元素 |
| deq.insert(iterator it, const T& x)       | 任意位置插入元素        |

#### STL-priority_queue优先队列

| q.size()  | 元素个数          |
| --------- | ----------------- |
| q.empty() | 是否为空          |
| q.push(k) | 在q的末尾插入k    |
| q.pop()   | 删除q的第一个元素 |
| q.top()   | 返回q的第一个元素 |

```c++
priority_queue<int> q;
int tmp;
char c;
while((cin>>tmp).get(c)){//10 8 12 14 6 3
	q.push(tmp);
	if(c=='\n')break;
}
while(!q.empty()){
	cout<<q.top();//14 12 10 8 6 3
	q.pop();
}
//q.top()是堆中最大值
```

从大到小排序。

#### STL-set

set容器的功用就是维护一个集合，其中元素满足**互异性**两两不同，**升序排序**，头文件`#include<set>`

##### set容器的使用

```c++
s.empty();//函数返回当前集合是否为空，空返回1，非空返回0
s.size();//返回当前集合的元素个数
s.clear();//清空
s.insert(k);//向集合中加入元素k
s.erase(k);//删除集合中的元素k
```

#### STL-stack

stack容器存放在模板库:`#include<stack> ` 里。

```c++
#include<stack>
stack<int> st;
stack<char> st;
stack<pair<int,int>> st;
stack<node> st;
struct node{...};
```

##### stack使用方法

| 用法           | 作用                                             |
| -------------- | ------------------------------------------------ |
| **st.top()**   | 返回stack的栈顶元素                              |
| **st.push()**  | 从stack栈顶加入一个元素(st.push(a); 压入元素a)   |
| **st.size()**  | 返回stack当前的长度                              |
| **st.pop()**   | 从stack栈顶弹出一个元素(移除栈顶元素值 st.pop()) |
| **st.empty()** | 返回stack是否为空，1为空，0为不为空              |

#### unordered_map

##### 查找是否存在key find

map.**find**(target) 如果容器中存在以target为key时，返回指向该key的迭代器，否则指向map.end()。如果获得该key的迭代器，可以通过此迭代器,**it->first和it->second获取键值对**。

##### 查找key对应的value值：

①**[]** 像取数组一样，map[1] 取key值为1的value。但是如果没有key值为1时，则向当前容器添加以目标元素为键的键值对

②**at()** 操作，和[]一样，但是如果遇到没有key值为1时，会自动抛出异常不会添加键值对。

##### 添加键值对 insert emplace

①将pair类型的键值对元素添加到容器中

`map.insert(pair<int,int>(nums[i],i))` 

②emplace 比insert插入效率更高。

`map.emplace(nums[i],i)` 

#### STL-map 

***感觉对map操作使用迭代器比较好一点，迭代器展示的信息更直观点。*** 

| map.begin()      | 指向map头部的迭代器                                          |
| ---------------- | ------------------------------------------------------------ |
| map.end()        | 指向map尾部的迭代器                                          |
| map.find(target) | map.**find**(target) 如果容器中存在以target为key时，返回指向该key的迭代器，否则指向map.end()。如果获得该key的迭代器，可以通过此迭代器,**it->first和it->second获取键值对**。 |
| map.erease(it)   | 删除it迭代器指向的元素                                       |
| map.size()       | map中元素个数                                                |



##### 根据value找到key

```c++
for (map<int,int>::iterator it=mm.begin(); it !=mm.end(); ++it) {
    if (it->second==q.top()){
        ans.push_back(it->first);
        break;
    }
}//从头往后找，直到找到第一个map->value等于val的值，得到迭代器，即可,
 //但是如果有多个key的value一样则会出现问题，多次找到的key为同一个第一个出现的key
```

#### STL-priority_queue\<int> q

优先队列，保存顺序为降序，大的在前，小的在后。

| q.push(k) | push进k值，会进行排序操作                              |
| --------- | ------------------------------------------------------ |
| q.size()  | 大小                                                   |
| q.top()   | 是整个堆里面的最大值，返回优先级队列中第一个元素的引用 |
| q.pop()   | 移除第一个元素                                         |
| q.empty() | 队列为空为1，否则0                                     |



#### 质数(素数)判断

```c++
bool isPrime(int n){
    //判断是否是质数，依次除以比自己小的数，看有无余数，如果都有余数则为质数
    //如果有(没有余数)的情况就不为质数
    for (int i = 2; i < n; ++i) {//这里如果有一次能除尽就会进入if语句返回false说明不是质数
        if (n%i==0)return false;
    }return true;
}
```

#### break语句只跳过上一层循环

#### 遇上需要处理的数字很长很大时，可以考虑用unsigned long long

如，在棋盘上放麦子，64格，第一格1个，第二格2个，第三格4格...问需要多少麦子。

观察规律，到第二格需要1+2=3，2^2^ -1 = 3，到第三格需要1+2+4=7，2^3^ -1=7.那么到第64格需要2^64^ -1粒。

```c++
#include <valarray>//pow函数需要头文件valarray
unsigned long long temp;
temp = pow(2,64)-1;
cout<<temp;
```

+ pow(x,y), pow函数是返回x^y^ . 

#### 求最大公约数(最小公倍数=两整数的乘积/最大公约数)

(1)辗转相除法

有两整数a和b:①a%b得余数c ②若c=0，则b为两数的最大公约数 ③若c!=0，则a=b，b=c，回去执行①

例如:27/15余12  15/12余3  12/3余0，因此，3为最大公约数

```c++
int gcd(int a,int b){
	return b==0?a:gcd(b,a%b);
}
```

(2)相减法

有两整数a和b:①若a>b,则a=a-b;②若a<b,则b=b-a;③若a=b，则a(或b)为两数的最大公约数④若a!=b,回去执行①

例如，27-15=12 (15>12) 15-12=3 (12>3) 12-3=9 (9>3) 9-3=6 (6>3) 6-3=3(3==3) 3为最大公约数

```c++
while(a!=b){
	if(a>b) a=a-b;
	else b=b-a;
}//跳出while循环后a或b就是最大公约数
```

#### 返回数组指针，用int *变量名接收

```c++
int* sort(int series[n]){
    for (int i = 0; i < n; ++i) {
        for (int j = i+1; j < n; ++j) {
            if (series[j]<series[i]){
                int temp;
                temp=series[j];
                series[j]=series[i];
                series[i]=temp;
            }
        }
    }return series;
}
int main(){
	int *n;
	n = sort(数组);
}
```

#### 回文字符串-翻转后是否和自己相同

#### 贪心算法-每一步都是局部最优解

平面分割，20条直线和20个圆最多能把平面分成多少块。

<img src="https://dn-simplecloud.shiyanlou.com/courses/uid1459416-20210322-1616388232231" alt="图片描述" style="zoom:80%;" />

```c++
#include <bits/stdc++.h>
using namespace std;
int a[30][30]={0};
int main()
{
    a[0][0]=1;
    for(int i = 1; i <= 20; i++)
    {
        a[i][0]=a[i-1][0]+i;//这里先处理没有加入圆的情况
        for(int j = 1; j <= 20; j++)
        {
            a[i][j]=a[i][j-1]+2*(i+j-1);
        }
    }
    cout << a[20][20];
    return 0;
}
```

#### 有关小数点后几位精度的题

```c++
/*黄金分割率，0.618034，
 * 1 3 4 7 11 18 29 47..称为鲁卡斯队列，后面每一项都是前两项的和
 * 1/3 3/4 ...会越来越接近黄金分割率，计算哪一项的四舍五入达到了0.618034的精度
 * 输出分子/分母  比如 29/47
 * 思想：第一次到达这个精度，应该这个值在0.6180335到0.6180344之间
 * 1364/2207
 * */
#include <iostream>
using namespace std;
int main() {
    float a=1,b=3,c;
    for (long long i = 1; i<100; ++i) {
        c = a+b;
        a=b;
        b=c;
        if (a/b>=0.6180335&&a/b<=0.6180344){
            cout<<a<<"/"<<b;
            break;
        }
    }
    return 0;
}
```

#### 万能头文件 bits/stdc++.h

#### 背包问题

01背包问题

有N件物品和一个容量为V的背包。第i件物品的费用是c[i]，价值是w[i]。求解哪些物品装入背包可使这些物品的费用不超过背包容量且价值最大。

```c++
/*f[i][j]表示只看前i个物品，总体积是j的情况下，总价值最大是多少。
result = max{f[n][0~V]}
f[i][v]:
1.不选第i个物品，f[i][j] = f[n-1][v];
2.选择第i个物品，f[i][j] = f[n-1][j-c[i]]+w[i];
f[i][j] = max{1.2.}
*/
```

<img src="C:\Users\admin\AppData\Roaming\Typora\typora-user-images\image-20220324170427027.png" alt="image-20220324170427027" style="zoom: 80%;" />

#### cin的一点总结

[C++中关于输入cin的一些总结 - Mini_Coconut - 博客园 (cnblogs.com)](https://www.cnblogs.com/mini-coconut/p/9041925.html)

cin>>可以连续从键盘读取想要的数据，以空格、tab或换行作为分隔符，即碰到分隔符，表示一个输入的结束。当cin>>从缓冲区中读取数据时，若缓冲区中第一个字符是空格、tab或换行这些分隔符，cin>>会将其忽略并清除，继续读取下一个字符，若缓冲区为空，则继续等待。但是如果读取成功，**字符后面的分割符是残留在缓冲区的，cin>>不做处理。**

`getline(cin,str)`这样输入空格也会读取记录到str中，但是换行还是就意味结束。

#### 初始化多行string变量

①<img src="C:\Users\admin\AppData\Roaming\Typora\typora-user-images\image-20220324185340543.png" alt="image-20220324185340543" style="zoom:80%;" />

**在每行后面加上 \ 反斜杠**

②<img src="C:\Users\admin\AppData\Roaming\Typora\typora-user-images\image-20220324185601113.png" alt="image-20220324185601113" style="zoom:80%;" />

**每行两侧加上 " "号**

#### 后缀表达式

( (15 / ( 7-(1+1) ) ) * 3) - ( 2 + (1 + 1) ) -----> 15  7  1  1  +  -  /   3  *  2  1  1  +  +  -   

用栈实现后缀表达式的运算:

① 从左往右扫描下一个元素，直到处理完所以元素

② 若扫描到操作数则压入栈，并回到①；否则执行③

③ 若扫描到运算符，则弹出两个栈顶元素，执行相应的运算，运算结果压回栈顶，回到①(先弹出的是“右操作数”)

###### 子串分值

<img src="C:\Users\admin\AppData\Roaming\Typora\typora-user-images\image-20220325201350921.png" alt="image-20220325201350921" style="zoom:80%;" />![image-20220325201438833](C:\Users\admin\AppData\Roaming\Typora\typora-user-images\image-20220325201438833.png)

<img src="C:\Users\admin\AppData\Roaming\Typora\typora-user-images\image-20220325204806303.png" alt="image-20220325204806303" style="zoom:80%;" />



#### long long可以支持19位

long long的最大值：9223372036854775807   一共19位。

long long的最小值：-9223372036854775808   一共19位。

比如其中一题，要求100个数(有三位四位的)相乘后末尾有几个零。这100个数相乘肯定溢出了，所以可以加判定条件，当相乘的数大于十几位时(小于19位时，提前)，就模%十几位(模的十几位可以是10位14位15位或其他位数)，来保证相乘数在long long支持的位数范围内。

```c++
long long temp=1,ans=0;
    for (int i = 0; i < 100; ++i) {
        int n;
        cin>>n;
        temp = temp*n;
        while (temp%10==0){
            ans++;
            temp = temp /10;
        }
        temp = temp % 100000000000000;//10^14
    }
    cout<<ans;
    return 0;
```

#### 迪杰斯特拉算法

该算法用于求图中某一顶点到其余各顶点的最短路径。设有两个集合T和S，S中存放已经找到的最短路径的顶点，T存放剩下的顶点，需要三个辅助数组，dist[],path[]和set[].

dist[v_i]表示v_0到v_i最短路径长度，初态：若从v_0到v_i有边，则dist[v_i]为边上的权值，否则置dist[v_i]=∞

path[v_i]保存v_0->v_i最短路径上v_i的前一个顶点，假设最短路径上顶点为v_0,v_1...v_i-1,v_i,则path[v_i]=v_i-1, paht[]初态：如果有v_0到v_i的边则path[v_i]=v_0,否则path[v_i]=-1;

set[]标记数组，set[v_i]=0表示v_i在T中，没有被并入最短路径，反之同理，初态：set[v_0]=1,其余0.

执行过程：

①从通往当前剩余顶点(**剩余节点这个怎么判断：看set[u]的值，为0则表示是剩余节点**)的路径dist[]**选出最小值**，假设为dist[v_u],将set[v_u]=1，表示当前新并入的顶点为v_u.

②循环扫描各顶点，对各顶点进行以下检测：

​	假设当前检测v_j,检测v_j是否被并入S中，看set[v_j]是否等于1.如果set[v_j]=1，什么都不做；如果set[v_j]=0，则比较dist[v_j]和dist[v_u]+w(w:<v_u,v_j>的权值)(dist[v_j]旧路，dist[v_u]+w新路)，**如果dist[v_u]+w < dist[v_j]则用新的路径长度来更新旧的路径，并把v_u并入路径中，set[v_u]=1**,且作为路径v_j之前的那个顶点，否则什么都不做。

③**对①②循环执行n-1次，n为图顶点个数**，即可得到v_0到其余所有顶点的最短路径。

#### ceil()函数向上取整 cmath头文件 

ceil(double num); 对num向上取整，如ceil(15.08) 结果是16，ceil(15) 还是等于15

#### 快速排序

<img src="C:\Users\admin\AppData\Roaming\Typora\typora-user-images\image-20220403173413729.png" alt="image-20220403173413729" style="zoom:80%;" />

例如:19 , 97 , 9 , 17 ,1 , 8排序，选取第一个数19为轴开始

<img src="C:\Users\admin\AppData\Roaming\Typora\typora-user-images\image-20220403173559776.png" alt="image-20220403173559776" style="zoom: 33%;" />

选择L了第一步不动(不检测L指向的值)，第一步检测R指向的值，如果R对应的值大于轴值则不动，如果小于轴值移动到L位置，直到L和R重叠在一起，L和R指向同一位置，则轴赋给这个位置。L和R交替检测L向后移动R向前移动，如果当前检测不需要移动，则继续当前的L或R的检测，直到L和R指向同一位置。

<img src="C:\Users\admin\AppData\Roaming\Typora\typora-user-images\image-20220403174033334.png" alt="image-20220403174033334" style="zoom:67%;" />

再循环检测轴左右两边的序列，直到完成。

#### 1e6=1*10^6=1000000.0浮点数的一种写法

##### double的最大值和最小值:1.79769e+308(1.79769\*10\^308)-----2.22507e-308(2.22507*10\^-308)

最大1.7*10\^308，最小\*10\^-308

#### 1既不是质数(素数)也不是和数(和数指自然数中除了能被1和本身整除外，还能被其他数(0除外)整除的数)

(Test)SweepRobot    

#### 无序容器(unordered_set哈希表、unordered_map键值对)

unordered_set容器可以做哈希表，无序set容器，set容器会自动对存储的数据进行排序，而unordered_set容器不会。

unordered_set容器性质:

1. 不再以键值对的形式存储数据，而是直接存储数据的值。
2. 容器内部存储的各个元素的值都互不相等，且不能修改。
3. 不会对内部存储的数据进行排序。

用法：

```c++
unordered_set<int> uset;
```

| 成员方法      | 功能                                                         |
| ------------- | ------------------------------------------------------------ |
| begin()       | 返回指向容器中第一个元素的正向迭代器                         |
| end()         | 返回指向容器最后一个元素的正向迭代器                         |
| empty()       | 若容器为空，true，不为空，false                              |
| size()        | 返回容器元素个数                                             |
| **find(key)** | **查找key的元素，如果能找到，返回一个指向该元素的迭代器；反之指向容器最后一个元素之后位置的迭代器**（找不到key元素时，返回end()迭代器） |
| count(key)    | 查找key值元素的个数                                          |
| emplace()     | 添加一个新元素，效率比insert()高                             |
| insert()      | 添加元素                                                     |
| erase()       | 删除指定元素                                                 |
| clear()       | 清空容器                                                     |

unordered_map是键值对<key,value>类型的元神，其中 各个键值对的值不允许重复。键值对是无序的。

![image-20220828211529375](C:\Users\admin\AppData\Roaming\Typora\typora-user-images\image-20220828211529375.png)

#### INT_MIN 理论最小值

#### 单引号 ’ ‘ 和双引号  “ ” 俩不一样，单引号引注单个字符的是char型，而双引号是string

#### 当需要循环输入数字以回车结束循环时

```c++
vector<int> num;
int temp;
char c;//用char型接收是否为回车'\n'
while((cin>>temp).get(c)){//检查是否接收为回车'\n'
	num.push_back(temp);
    if(c=='\n')break;//如果接收为回车则跳出循环
}
```

```c++
if(cin.get()=='\n')break; //有个弊端会吃掉一个输入，导致第一个输入无法使用
//或者
if((cin>>str).get()=='\n')break;  
```

#### 需要以 ] 右括号结束输入

```c++
vector<int> nums;
int num;
for(int i=0;;i++){
	if(getchar()==']')break;//如果getchar从输入缓冲区读取一个字符，如果是 ] 则break
	cin>>num;//输入到num
	if(to_string(num)=="["||to_string(num)==",")continue;
	nums.push_back(num);
}
for(int i=0;i<nums.size();i++){
	cout<<nums[i]<<" ";
}
```

#### swap函数交换两个变量的内容

##### vector<vector<int\>\>  向二维数组添加元素：res.push_back({nums[i],nums[j],nums[k]});用{}大括号

## 字符串

##### 判断字符串中的空格直接`==' '` 空个格就表示空格。

对string增加空间用resize : `s.resize(s.size()+2)`

### KMP

KMP主要应用到字符串匹配上，当出现字符串不匹配时，可以知道一部分之前已经匹配的文本内容，可以利用这些信息避免从头再去做匹配。如何记录已经匹配的文本内容，是KMP的重点，也是next数组肩负的重任。

##### 1.什么是前缀表

next数组就是一个前缀表。前缀表是用来回退的，记录了模式串和主串不匹配的时候，模式串应该从哪里开始重新匹配。例子，在aabaabaafa中查找是否出现过一个模式串：aabaaf。

![KMP详解1](https://code-thinking.cdn.bcebos.com/gifs/KMP%E7%B2%BE%E8%AE%B21.gif)

前缀表：**记录下标i之前(包括i)的字符串中，有多大长度的相同前缀后缀**。

##### 2.最长公共前后缀？

**前缀指不包含最后一个字符的所有以第一个字符开头的连续子串**。**后缀是指不包含第一个字符的所有以最后一个字符结尾的连续子串**。

”最长相等前后缀“相当于“最长公共前后缀”这个需要理解。比如，字符串a的最长相等前后缀为0，字符串aa的最长相等前后缀为1.字符串aaa的最长相等前后缀为2.

##### 3.一定要用前缀表？

前缀表可以帮助上次匹配的位置，并跳过去。模式串指向f，如图：

<img src="C:\Users\admin\AppData\Roaming\Typora\typora-user-images\image-20220920210016776.png" alt="image-20220920210016776" style="zoom:50%;" />

然后找到下标2，指向b，继续匹配：

<img src="C:\Users\admin\AppData\Roaming\Typora\typora-user-images\image-20220920210108916.png" alt="image-20220920210108916" style="zoom:50%;" />

理解：**下标5之前这部分的字符串（也就是字符串aabaa）的最长相等的前缀和后缀字符串是子字符串aa，因为找到了最长相等的前缀和后缀，匹配失败的位置是后缀子串的后面，那么需要找到与其相等的前缀的后面从新匹配就可以了**。

##### 4.如何计算前缀表

<img src="C:\Users\admin\AppData\Roaming\Typora\typora-user-images\image-20220920210713426.png" alt="image-20220920210713426" style="zoom: 50%;" />

长度为前一个字符的子串a，最长相同前后缀的长度为0，（注意字符串的**前缀是指不包含最后一个字符的所有以第一个字符开头的连续子串**；**后缀是不包含第一个字符的所有以最后一个字符结尾的连续子串**。）

<img src="C:\Users\admin\AppData\Roaming\Typora\typora-user-images\image-20220920210953616.png" alt="image-20220920210953616" style="zoom:50%;" />

长度为前2个字符的子串aa，最长相同前后缀的长度为1.

<img src="C:\Users\admin\AppData\Roaming\Typora\typora-user-images\image-20220920211247531.png" alt="image-20220920211247531" style="zoom:50%;" />

长度为前3个字符的子串aab，最长相同前后缀的的长度为0.

以此类推：长度为前4个字符的子串aaba，最长相同前后缀的长度为1.长度为前5个字符的子串aabaa，最长相同前后缀的长度为2，长度为前6个字符的子串aabaaf最长相同前后缀的长度为0.

那么把求得最长相同前后缀的长度就是对应前缀表的元素，如图：

<img src="C:\Users\admin\AppData\Roaming\Typora\typora-user-images\image-20220920211725060.png" alt="image-20220920211725060" style="zoom:67%;" />

模式串与前缀表对应位置的数字表示就是：**下标i之前（包括i）的字符串中，有多大长度的相同前后缀**。

利用前缀表找到字符不匹配的时候指针应该移动的位置：

![KMP精讲2](https://code-thinking.cdn.bcebos.com/gifs/KMP%E7%B2%BE%E8%AE%B22.gif)

找到不匹配的位置，要看它前一个字符的前缀表的数值是多少。前一个字符的前缀表的数值是2，把模式串下标移动到下标2的位置继续匹配。

##### 5.前缀表和next数组

![image-20220920213443522](C:\Users\admin\AppData\Roaming\Typora\typora-user-images\image-20220920213443522.png)

##### 6.使用next数组来匹配

**以下我们以前缀表统一减一之后的next数组来做演示**。

有了next数组，就可以根据next数组来 匹配文本串s，和模式串t了。

注意next数组是新前缀表（旧前缀表统一减一了）。

匹配过程动画如下：

<img src="https://code-thinking.cdn.bcebos.com/gifs/KMP%E7%B2%BE%E8%AE%B24.gif" alt="KMP精讲4"  />

##### 7.构造next数组

```c++
void getNext(int* next, const string& s)
```

构造next数组其实就是计算模式串s，前缀表的过程。三步：

​		1.初始化  	2.处理前后缀不相同的情况   	3.处理前后缀相同的情况。

**1.初始化：**

定义两个指针i和j，**j指向前缀末尾位置**，**i指向后缀末尾位置**。

然后还要对next数组进行初始化赋值，如下：

```c++
int j = -1;
next[0] = j;
```

j为什么要初始化为-1那，因为之前说过，前缀表要统一减一的操作仅仅是其中一种实现，这里先给j初始化为-1，下文有j不初始化为-1的代码。

next[i]表示i（包括i）之前最长相等的前后缀长度（其实就是j）所以初始化next[0] = j.

**2.处理前后缀不相同的情况**

因为j初始化为-1，那么i就从1开始，进行s[i]与s[j+1]的比较。

遍历模式串s的循环下标i要从1开始，代码：

```c++
for(int i=1;i<s.size();i++)
```

如果s[i]与s[j+1]不相同，就是遇到前后缀末尾不相同的情况，就要向前回退。

next[j]就是记录着j（包括j）之前的子串的相同前后缀长度。

那么s[i]与s[j+1]不相同，就要找j+1前一个元素在next数组里的值（就是next[j]）。

所以，处理前后缀不相同的情况下代码：

```c++
while(j>=0 && s[i]!=s[j+1]){//前后缀不相同了
	j = next[j];//向前回退
}
```

**3.处理前后缀相同的情况**

如果s[i]与s[j+1]相同，就同时向后移动i和j说明找到了相同的前后缀，同时还要将j（前缀的长度）赋给next[i]，next[i]要记录相同前后缀的长度。

```c++
if(s[i] == s[j+1]){//找到相同的前后缀
	j++;
}
next[i] = j;
```

整体构建next数组：

```c++
void getNext(int* next,const string& s){
	int j=-1;
	next[0] = j;//初始化next数组的第一位
	for(int i=1;i<s.size();i++){
		while(j>=0 && s[i]!=s[j+1]) j = next[j];//前后缀不同向前回退
		if(s[i] == s[j+1]) j++;//找到相同的前后缀
		next[i] = j;//将j（前缀长度）赋给next[i]
	}
}
//next数组的值不减1
void getNext(int* next,const string& s){
    int j = 0;
    next[0] = 0;
    for(int i = 1;i<s.size();i++){
        while(j>0&&s[i]!=s[j]){//前后缀不相同,要保证j大于0，下面有j-1作为下标的操作
        	j = next[j-1];//注意，要找前一位的对应的回退位置了
        }
        if(s[i] == s[j]){
            j++;
        }
        next[i]=j;
    }
}
```

![KMP精讲3](https://code-thinking.cdn.bcebos.com/gifs/KMP%E7%B2%BE%E8%AE%B23.gif)

##### 8.使用next数组来做匹配

在文本串s中，找是否出现过模式串t。

定义两个下标j指向模式串起始位置，i指向文本串起始位置。

那么j初始值依然为-1，**依然因为next数组里记录的起始位置为-1**。

i就从0开始，遍历文本串，代码：

```c++
for(int i=0;i<s.size();i++)
```

接着就是s[i]与t[j+1]（因为j从-1开始的）进行比较。

如果s[i]与t[j+1]不相同，j就要从next数组里寻找下一个匹配的位置。

```c++
while(j>=0 && s[i]!=t[j+1]){
	j = next[j];
}
```

如果s[i]与t[j+1]相同，那么i和j同时向后移动，

```c++
if(s[i] == t[j+1]){
	j++;//i的增加在for循环里
}
```

如何判断在文本串s里出现了模式串t那，如果j指向了模式串t的末尾，那么就说明模式串t完全匹配文本串s里的某个子串了。

目的是要在文本串中找到模式串出现的第一个位置(从0开始)，所以返回当前在文本串匹配模式串的位置i减去模式串的长度，就是文本串字符串中出现模式串的第一个位置。

```c++
if(j == (t.size() - 1)){
	return (i-t.size()+1);
}
```

那么使用next数组，用模式串匹配文本串的整体代码:

```c++
int j = -1; // 因为next数组里记录的起始位置为-1
for (int i = 0; i < s.size(); i++) { // 注意i就从0开始
    while(j >= 0 && s[i] != t[j + 1]) { // 不匹配
        j = next[j]; // j 寻找之前匹配的位置
    }
    if (s[i] == t[j + 1]) { // 匹配，j和i同时向后移动
        j++; // i的增加在for循环里
    }
    if (j == (t.size() - 1) ) { // 文本串s里出现了模式串t
        return (i - t.size() + 1);
    }
}
```

```c++
//整体代码
class Solution {
public:
    void getNext(int* next, const string& s) {
        int j = -1;
        next[0] = j;
        for(int i = 1; i < s.size(); i++) { // 注意i从1开始
            while (j >= 0 && s[i] != s[j + 1]) { // 前后缀不相同了
                j = next[j]; // 向前回退
            }
            if (s[i] == s[j + 1]) { // 找到相同的前后缀
                j++;
            }
            next[i] = j; // 将j（前缀的长度）赋给next[i]
        }
    }
    int strStr(string haystack, string needle) {
        if (needle.size() == 0) {
            return 0;
        }
        int next[needle.size()];
        getNext(next, needle);
        int j = -1; // // 因为next数组里记录的起始位置为-1
        for (int i = 0; i < haystack.size(); i++) { // 注意i就从0开始
            while(j >= 0 && haystack[i] != needle[j + 1]) { // 不匹配
                j = next[j]; // j 寻找之前匹配的位置
            }
            if (haystack[i] == needle[j + 1]) { // 匹配，j和i同时向后移动
                j++; // i的增加在for循环里
            }
            if (j == (needle.size() - 1) ) { // 文本串s里出现了模式串t
                return (i - needle.size() + 1);
            }
        }
        return -1;
    }
};
```

#### 大顶堆和小顶堆

大顶堆顶节点比孩子节点都大，小顶堆顶节点比孩子节点都小。本身是一个二叉树的结构。

堆本身是一种非线性结构，堆就是利用完全二叉树的结构来维护的一维数组。

#### string删除最后一位

```c++
string ss;
cin>>ss;//123456
ss.erase(ss.end()-1);//12345
cout<<ss<<endl;
ss.pop_back();//1234
cout<<ss<<endl;
```

**①ss.erase( ss.end ( ) -1 );**

**②ss.pop_back();** 这个语法可能有的编译器没有

#### 二叉树

##### **满二叉树**：

如果一颗二叉树只有度为0和度为2的节点，并且度为0的节点在同一层上。

![image-20220928211959547](C:\Users\admin\AppData\Roaming\Typora\typora-user-images\image-20220928211959547.png)

##### **完全二叉树** ：

在完全二叉树中，除了最底层节点可能没填满外，其余每层节点数都达到最大值，并且最下面一层的节点都集中在该层最左边的若干位置。若最底层为第 h 层，则该层包含 1~ 2^(h-1)  个节点。

![image-20220928212121758](C:\Users\admin\AppData\Roaming\Typora\typora-user-images\image-20220928212121758.png)

之前的优先队列其实是个堆，堆就是完全二叉树，同时保证父子节点的顺序关系。

##### **二叉搜索树** ：

前面介绍的树，都没有数值的，而二叉搜索树是有数值的了，**二叉搜索树是一个有序树**。

- 若它的左子树不空，则左子树上所有结点的值均小于它的根结点的值；
- 若它的右子树不空，则右子树上所有结点的值均大于它的根结点的值；
- 它的左、右子树也分别为二叉排序树

![image-20220928212338907](C:\Users\admin\AppData\Roaming\Typora\typora-user-images\image-20220928212338907.png)

##### 平衡二叉树：

又被称为AVL（Adelson-Velsky and Landis）树，且具有以下性质：它是一棵空树或它的左右两个子树的高度差的绝对值不超过1，并且左右两个子树都是一棵平衡二叉树。

![image-20220928212447667](C:\Users\admin\AppData\Roaming\Typora\typora-user-images\image-20220928212447667.png)

**C++中map、set、multimap，multiset的底层实现都是平衡二叉搜索树**，所以map、set的增删操作时间时间复杂度是logn，注意我这里没有说unordered_map、unordered_set，底层实现是哈希表。

##### 二叉树的存储方式：

**二叉树可以链式存储，也可以顺序存储。**

那么链式存储方式就用指针， 顺序存储的方式就是用数组。

顾名思义就是顺序存储的元素在内存是连续分布的，而链式存储则是通过指针把分布在散落在各个地址的节点串联一起。

![image-20220928212828460](C:\Users\admin\AppData\Roaming\Typora\typora-user-images\image-20220928212828460.png)

![image-20220928212840119](C:\Users\admin\AppData\Roaming\Typora\typora-user-images\image-20220928212840119.png)

用数组来存储二叉树如何遍历的呢？

**如果父节点的数组下标是 i，那么它的左孩子就是 i \* 2 + 1，右孩子就是 i \* 2 + 2。**

但是用链式表示的二叉树，更有利于我们理解，所以一般我们都是用链式存储二叉树。

**所以大家要了解，用数组依然可以表示二叉树。** 

##### 二叉树的遍历方式：

二叉树主要有两种遍历方式：

1. 深度优先遍历：先往深走，遇到叶子节点再往回走。
2. 广度优先遍历：一层一层的去遍历。

- 深度优先遍历
  - 前序遍历（递归法，迭代法）
  - 中序遍历（递归法，迭代法）
  - 后序遍历（递归法，迭代法）
- 广度优先遍历
  - 层次遍历（迭代法）

![image-20220928213043365](C:\Users\admin\AppData\Roaming\Typora\typora-user-images\image-20220928213043365.png)

最后再说一说二叉树中深度优先和广度优先遍历实现方式，我们做二叉树相关题目，经常会使用递归的方式来实现深度优先遍历，也就是实现前中后序遍历，使用**递归**是比较方便的。

**前中后序遍历**的逻辑其实都是可以**借助栈使用非递归的方式来实现**的。

而**广度优先遍历**的实现一般**使用队列来实现**，这也是队列先进先出的特点所决定的，因为需要先进先出的结构，才能一层一层的来遍历二叉树。

##### 二叉树的定义：

```c++
struct TreeNode{
	int val;
	TreeNode *left;
	TreeNode *right;
	TreeNode(int x):val(x),left(NULL),right(NULL){}//没看懂
}
```

#### 二叉树的迭代遍历

##### 先序遍历，中左右，

每次先处理的是中间节点，那么先将根节点放入栈中，然后将右孩子加入栈，再加入左孩子。为什么要先加入 右孩子，再加入左孩子呢？ 因为这样出栈的时候才是中左右的顺序。

![二叉树前序遍历（迭代法）](https://tva1.sinaimg.cn/large/008eGmZEly1gnbmss7603g30eq0d4b2a.gif)

```c++
class Solution {
public:
    vector<int> preorderTraversal(TreeNode* root) {
        stack<TreeNode*> st;
        vector<int> result;
        if (root == NULL) return result;
        st.push(root);
        while (!st.empty()) {
            TreeNode* node = st.top();                       // 中
            st.pop();
            result.push_back(node->val);
            if (node->right) st.push(node->right);           // 右（空节点不入栈）
            if (node->left) st.push(node->left);             // 左（空节点不入栈）
        }
        return result;
    }
};
```

##### 中序遍历，左中右

先序遍历时，**要访问的元素和要处理的元素顺序是一致的，都是中间节点。** 但是中序遍历不是这样的，是**处理顺序和访问顺序是不一致的。** 

那么**在使用迭代法写中序遍历，就需要借用指针的遍历来帮助访问节点，栈则用来处理节点上的元素。**

![二叉树中序遍历（迭代法）](https://tva1.sinaimg.cn/large/008eGmZEly1gnbmuj244bg30eq0d4kjm.gif)

````c++
class Solution {
public:
    vector<int> inorderTraversal(TreeNode* root) {
        vector<int> result;
        stack<TreeNode*> st;
        TreeNode* cur = root;
        while (cur != NULL || !st.empty()) {
            if (cur != NULL) { // 指针来访问节点，访问到最底层
                st.push(cur); // 将访问的节点放进栈
                cur = cur->left;                // 左
            } else {
                cur = st.top(); // 从栈里弹出的数据，就是要处理的数据（放进result数组里的数据）
                st.pop();
                result.push_back(cur->val);     // 中
                cur = cur->right;               // 右
            }
        }
        return result;
    }
};
````

##### 后序遍历，左右中

只需要调整一下先序遍历的代码顺序，就变成中右左的遍历顺序（入栈时先入左节点这样出栈时左节点后出来，变成中右左了），然后在反转result数组，输出的结果顺序就是左右中了，如下图：

![前序到后序](https://img-blog.csdnimg.cn/20200808200338924.png)

```c++
class Solution {
public:
    vector<int> postorderTraversal(TreeNode* root) {
        stack<TreeNode*> st;
        vector<int> result;
        if (root == NULL) return result;
        st.push(root);
        while (!st.empty()) {
            TreeNode* node = st.top();
            st.pop();
            result.push_back(node->val);
            if (node->left) st.push(node->left); // 相对于前序遍历，这更改一下入栈顺序 （空节点不入栈）
            if (node->right) st.push(node->right); // 空节点不入栈
        }
        reverse(result.begin(), result.end()); // 将结果反转之后就是左右中的顺序了
        return result;
    }
};
```

#### 递归算法<font color=#871F78>三要素</font>

①**确定递归函数的<font color=#871F78>参数</font>和<font color=#871F78>返回值</font>font>**：确定哪些参数是递归过程中需要处理的

②**确定<font color=#871F78>终止条件</font>**：如果没有终止条件操作系统的内存栈必然会溢出

③**确定<font color=#871F78>单层递归逻辑</font>**：确定每层递归需要处理的信息。

#### if语句里面的判定条件计算机是有计算顺序的，前面的条件先运算再运算后面的条件

```c++
if ((!st.empty())&&((s[i]==')'&&st.top()=='('))){//先判断st栈是否为空，再运算括号是否匹配
	st.pop();
}
```

