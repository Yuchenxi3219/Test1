# 《JAVA学习笔记》

##   1.java基本程序设计结构

```java
public class FirstSample
    public static void main (String[] args){
    System.out.println("helloworld");
}
```

### 1.1 基本结构

* public 是**访问权限修饰符**,用于控制程序的其他部分对这段代码的访问级别:==*public,protected,default,private*==。

* | 修饰符      | 当前类 | 同一包内 | 子孙类(同一包) | 子孙类(不同包) | 其他包 |
  | ----------- | ------ | -------- | -------------- | -------------- | ------ |
  | `public`    | Y      | Y        | Y              | Y              | Y      |
  | `protected` | Y      | Y        | Y              | Y              |        |
  | `default`   | Y      | Y        | Y              |                |        |
  | `private`   | Y      |          |                |                |        |

* class代表**类**，java中的全部程序内容都包含在类中。

* FirstSample是程序名，*字母开头，推荐使用驼峰命名法*

* System.out是一个对象，其中.println是他的一个方法。

* 注释：1. //   2. /* */  3. /** */（*第三种会自动生成文档*）

### 1.2 数据类型

* java作为一种强类型语言，必须为每一个变量声明一种类型。

* 1 bit = 一个0或者一个 1;

* | 整数类型     | 浮点类型      | 字符                    | boolean           |
  | ------------ | :------------ | ----------------------- | ----------------- |
  | byte：1字节  | float：4字节  | char(可以做运算)：2字节 | true/false：1字节 |
  | short：2字节 | double：8字节 |                         |                   |
  | int：4字节   |               |                         |                   |
  | long：8字节  |               |                         |                   |

* *长整型：xxx+L; 二进制：**0b**+xxx；八进制：**0**+xxx；十六进制：**0x**+xxx*

  ```java
  在java中改变进制的方法
  比如：
  010：10这个数字的8进制
  0x10 :10这个数字的16进制
  0b10：10这个数字的2进制
  
  tips:任意进制到10进制的转换
  
  系数*进制（2、8、16）^顺序（0、1、2、3...）之和
  
  比如0x23转成10进制：
  3*16^0+2*16^1=35
  
  10进制转换成任意进制
  
  十进制的数字不断除以进制（2，8，16）得到的余数倒着写
  
  比如：343转为16进制
  342/16 商为 21，余数为6
  21/16 商为1，余数为5
  1/16 商为0，余数为1
  所以16进制的343是156
  
  快速转换；8421表
  2进制转换成10进制：
  10100
  =0*2^0+0*2^1+1*2^2+0*2^3+1*2^4=20
  
  2进制快速转换成8进制：（421，421，421）
  10100
  =0*1+1*2，0*1+0*2+1*4=2，4=24
  
  2进制快速转换成16进制：（8421，8421，8421）
  10100
  =1*1，0*1+0*2+4*1+0*8=1，4=14
  -----------------------------------------------------------------------
  位运算:1 / 0     
  &:"按位与" :两个同为1的时候才为1
      例如:3:0b00000000000000000000000011
          4:0b00000000000000000000000100
              
  |:"按位或":两个只要有一个1就是1
  
  ^:"按位抑或":一个数据对相同数据抑或两次值不变(3^4^4 = 3)
      
  ~:"按位取反":~3 = -4 , ~-4 = 3 
  ```

  

* 绝大多数程序都会采用double而非float，若是用float则在浮点数数值后面+F，*如：3.33F*,**double精度是float双倍**

### 1.3变量

* java所有的变量都有类型，同时起变量名称时，*区分大小写；字母开头；由字母 数字 _ $组成*

* 声明一个变量之后，必须要用赋值语句对其进行**显式初始化**

* 相同的变量名字不可以重复定义,**嵌套定义要注意"可下不可上"**

* 大**驼峰**主要用于类名,如:StudentOne,小驼峰主要用于变量名如:max和方法名:getName()

* ```java
  int TheNumberOfSheep=1000;//给变量赋值
  ```

* **常量**：*1.用final来定义；2.只能被赋值一次，被赋值之后不可修改；3.变量名全大写*

* ```java
  public static final int NUMBER=999;//static:静态修饰符，作用于类。public让这个NUMBER常量其他类也可以使用了
  ```

* **运算符** :（+ - * / %）

  * ```java
    10/3;//3
    ----------------------------------------
    10.0/3; //3.333333335
    20/3.0;//3.333333335
    ----------------------------------------
    double d = 5/2; // 2.0
    ```

  * ASCII码表:字节到字符的对应关系 :'a' =97 ; 'A'=97-32=65; 0=48;

  * **String+**任何数据都变成新的String (类似牛皮糖)

    ```java
    "5+5"+5+5//输出为5+5=55
    -------------------------------------------------    
     public class test {
        public static void main(String[] args) {
            char c = 'a';
            int n =10;
            String s = "hello";
    
            System.out.println(c+n+s);//107hello
            System.out.println(c+s+n);//ahello10
            System.out.println(c+(n+s));//a10hello
            System.out.println(s+n+c);//hello10a
            System.out.println(s+(n+c));//hello107
        }
    }
    ```

  * **++/--**, a++, ++a 单独使用时候都一样 ( **++a:先自增,再参与操作(输出也算操作)/a++:先操作,再自增 **)

* **数值类型的转换**:

  * 强制类型转换: 

    ```java
    double x =234.21345;
    int y =(int)x;//将double的x强制转换成int类型的y的格式
    -------------------------------------------------------------
    float f = 12;//输出12.0,因为是int--float,小转大
    float f = 12.5;//错误,这里是double--float,大转小,需要float f = (float) 12.5;或12.5F
    --------------------------------------------------------------
    long num = 123;//正确,int--long
    long num =12342323432567;//错误,超出int范围,需要强制转换,12342323432567L
    ```

  *   隐式类型转换:

    * byte--short--int--long--float--double 	          	

      ​           char-- 

    * **byte,short,char**都会**自动转换成int**再转换; 

      ```java
      byte a = 3;
      byte b = 4;
      byte c = =a +b;//错误,需要强制转换,因为3 4这里计算时都是int类型
      byte c =(byte)(a+b);//正确
      byte d = 3+4;//正确,常量优化机制,自动判断在不在范围内
      ```

* **赋值运算符**：**+=，-=，*=，/=，%=**  ，此类扩展赋值运算符，**底层自带强转**.

* **二元运算符**：x+=6 // x=x+6,  还有*=，%=   (+=是右结合运算符，所以a+=b+=c 其实是a+=(b+=c)), +=优先级低于三元运算符.

* **三元运算符**，x<y?x:y   **//x,y一定要有明确的结果,不可以是输出语句,并且x,y类型要统一**,

* **关系运算符**：**（比较基本数据类型的值的时候，比较的是值本身）用来检测相等，!=用来检测不相等 如： 3!=4  值为true**
* **逻辑运算符**：*&&：与，||：或，！：非*，按照短路求值。

* **枚举类型（enum）**:相当于一一举例，包含有限个值

  ```java
   enum animal{dog,cat,fish};
   Animal a =Animal.dog;
  ```

### 1.4字符串

* String类的**substring**方法：从较大的类里面提取一个子类，例如：

  ```java
  String x = "abcdefg";
  String y =x.substring(0,4);//y的字符串就是"abcd"(不包括第4个)
  ```

* 新的String可以由两个老的String**直接拼接**；若其中有非字符串的，则自动转换成字符串，例如：

  ```java
  String x ="dog";
  String y = "cat";
  String z = x+y;//直接相加
  ------------------------------------
  int a = 10;
  String b ="abc"+a;//b为"abc10"，（在System.out中很多见）
  ```

* String类的对象为不可变字符串；**字符串常量池**：编译器让字符串共享。(只有字符串常量是共享的，通过各种方法重新产生的新的字符串不是共享的，如substring等)

* 用**equals**（不区分大小写可以用*equalsIgnoreCase*）检测字符串是否相等（而非==）；同时字符串比较的时候完全可以字符串变量和字符串字面量比较，例如：

  ```java
  "abc".equals(X)//字面量和变量比较
  ```

* **“”**：（一个Java对象，长度0，内容空）和 **null**：（String变量存放null表示还没有任何对象和该变量相关联），既不是空串又不是null的检查方法：

  ```java
  if(Str.length()!=0&&Str!=null)
  ```

* **StringBuilder**:字符串构建器，builder.append():添加内容，builder.toString():转成String字符串

###  1.5 输入和输出

* 输入：**构造Scanner这个类的对象**：//Scanner定义在java.util包里面（而非基本的java.lang），需要导包

  ```java
  Scanner sc = new Scanner(System.in);
  String x =sc.nextLine();//nextline处理带有空格的输入内容，next处理不带空格的输入内容，整数：nextInt,浮点：nextDouble
  ```

* 输出：**格式化输出：printf**，

  ```java
  public class test2 {
      public static void main(String[] args) {
          String name = "zhangsan";
          int age = 23;
          double dollar =25.78332435;
          System.out.printf("%s,%d,%f",name,age,dollar);
      }
  }//输出的结果是zhangsan,23,25.78332435(参数与%的说明符一一对应,这个要注意顺序对应)
  ·--------------------------------------------------------------------------------------------------------
  String message =String.format("%s,%d,%f",name,age,dollar);
  //用格式化方法直接创造字符串的时候，可以用静态的format方法，作用于String类
  ```

* **文件的输入和输出**：暂时没太懂，后面学习。。

***********

### 1.6 控制流程

* **块（block）**：大括号里面的若干条java语句，用以控制变量的作用域。一个块可以嵌套在另一个块里面，嵌套的块里面不同声明一样的变量。独立的块可以声明一样的变量。

* **for/while（不明确循环次数的）/do...while**(do...while是让代码先运行一次，再检测)。for支持迭代，例如：

  ```java
  for(int i =0;i<100;i++){...};
  /*int i = 0:初始化计数器 ,初始语句只执行一次!,无论是int i =1;还是sout语句
    i<100:检测循环的次数
    i++:计数器更新*/
  ```

  ```java
  public class While {//珠峰例子
      public static void main(String[] args) {
          int i = 0;//定义计数器,定义在循环体外面
          double p =0.1;
          double zf =8844430;
          while (p<=zf){
             p=p*2;
             i++;
          }
          System.out.println(i);//可以直接打印计数器
  
          int c = 0;
          double p1 =0.1;
          double zf2 =8844430;
          for (int j = 1; p1<=zf2 ; j++) {//死循环格式是for(;;)
              p1*=2;
              c++;
          }
          System.out.println(c);//fori的计数器在循环结束后消失,所以要单独定义计数器//for循环也可把计数器定义在外面
      }
  }
  
  ```

  * **跳转控制语句**:

    * continue; :跳过一次循环

    * break; :终止循环,**就近原则,终止掉最近的循环**

    * 两者都可以通过**标签**结束整个循环

      ```java
      package day03.practice;
      
      import java.util.Scanner;
      
      public class Break {//最大公约数和最小公倍数例子
          public static void main(String[] args) {
              Scanner sc = new Scanner(System.in);
              System.out.println("输入 a ");
              int a = sc.nextInt();
              System.out.println("输入 b ");
              int b = sc.nextInt();
              
              int min = a > b ? b : a;//最大公约数肯定是小于min
              int max = a > b ? a : b;//最公倍数肯定是小于max
              
              int x = -1;//此处定义x就是为了后面接收i.并且只输出x一次即可
              for (int i = 1; i < min; i++) {
                  if ((a %i  == 0) && (b % i == 0)) {
                      x = i;//因为最后一个是想要输出的值
                  }
              }
              System.out.println(x);
      //----------------------------------------------------------------------------------------
              for (int i = max; i < a * b; i++) {//最小公倍数
      
                  if ((i % a == 0) && (i % b == 0)) {
                      System.out.println(i);
                      break;//因为第一个是想要输出的值,后面不需要输出,就直接break
                  }
              }
      
          }
      }
      //1.for循环(计数条件是min/max)里面嵌套if判断(条件是&&);
      //2.i出了大括号就没了,注意在大括号前新建变量x,在大括号里面用i给x赋值,x除了大括号还在,还能输出;
      //break直接终止循环;
      ```

* **switch**语句：

  * 执行相匹配的case**(**(...)里面可以是**byte**/**short**/**int**/**char**/**String**/**枚举** **)**,不能是浮点数
  * (case的值**不允许重复**,必须**是常量**,不能是变量)直到遇到break,若无匹配则直接运行default。default位置是**灵活**的
  * （在switch中使用枚举常量的时候，格式遵循switch的格式，不必再指明枚举名如:直接case dog；而非case Animl.dog）

* **带有标签的break**：直接给嵌套循环一个标签（abc）,用break abc;直接跳出这个循环。**continue**：跳到最内层循环的首部。

* **BigInteger/BigDecimal**：java.math的***大数值类***，实现任意精度的整数运算/浮点运算。用的是**add、multiply*方法**

### 1.7数组

* **数组**：储存同一类型值的集合，动态初始化（*int [] x =new int [100]）/静态初始化(int [] x ={1,2,3,4,5,6}*)定义数组。数值数组元素的初始值是0，布尔数组是false，对象数组是null。Java允许数组长度为0。

  * 创建数组对象是在内存中开辟**一块连续内存空间**,数组名中引用的是这块连续空间的首地址; 
    * *[I@10f87f48* : [:表示当前是数组类型,I:当前数组容器中存储的数据类型,10f87f48:十六进制内存地址
    * **char类型**数组打印出来的不是地址值(println方法打印出来的是空格) 
  * 数组长度一经确定无法改变;

* **遍历数组**的三种方法：fori , foreach , Arrays.toString,例如：

  ```java
   package test;
  
  import java.util.Arrays;
  
  public class test2 {
      public static void main(String[] args) {
          int[] arr = {1, 2, 3, 4, 5, 6};
          for (int y : arr) {
              System.out.println(y);
          }//foreach
          for (int i = 0; i <arr.length ; i++) {
              System.out.println(arr[i]);
          }//fori
          String s = Arrays.toString(arr);//将数组以显示参数传入
          System.out.println(s);
      }//Arrays.toString
  }
  ```

*  public static void main(String[] args)，String[] args是字符串数组，其中args也可以改成别的单词，不固定，也就是命令行参数。

* 数组的排序：**Arrays.sort() **方法：例如书中83页程序示例*（涉及到到数组的思想，防止新定义数组元素重复可能性的方法，Math.random() 方法*）：

  ```java
  import java.util.Arrays;
  import java.util.Scanner;
  
  public class test2 {
      public static void main(String[] args) {
          Scanner sc = new Scanner(System.in);
          System.out.println("输入想从多少个(n)数值中抽取?");
          int n = sc.nextInt();
          int[] numbers = new int[n];
          for (int i = 0; i < n; i++) {
              numbers[i] = i + 1;
          }//将1到n的每一个数字都塞进了numbers数组里面
          System.out.println("输入抽取数值的个数(k)");
          int k = sc.nextInt();
          int[] result = new int[k];//定义一个个数是k的数组result
          for (int i = 0; i < k; i++) {
              double random = Math.random();//Math.random会返回一个0-1之间的随机浮点数
              int r = (int) (random * n);//将返回的随机浮点数强制转换成int，就相当于随机返回了个0到50直接的整数
              result[i] = numbers[r];//若随机得到的整数是r==5,那么number[]==5，这里为什么多此一举弄个number[]数组呢，而不是直接将r塞进result数组里面？就是因为返回的r是一个固定值，但是也有可能这此和下一次随机返回的r值相同，比如r都是5，为了避免这个问题，直接将r放进number[]数组中做下标，然后对number[r]进行操作就行
              numbers[r] = numbers[n - 1];
              n--;//关键步骤，为了避免随机数字r产生重复，每次在number[r]用完之后，重新将这个number[r]坑位上面的数字用numbers[n-1]的值赋值，同时n--，让这次的numbers[n-1]的值下次不会再出现
          }
          Arrays.sort(result);//对result这个数组进行升序排序
          for (int x : result) {
              System.out.println(x);//用foreach遍历数组result
          }
      }
  }
  ```

  * 数据交换:
    * 1,定义新变量temp
    * 2.抑或法:a = a^ b ; b =a^b; a=a^b;   三步交换a b
    * 3.数学加减推理 a=10,b=20; a=a+b=30; b=a -b=30-20 =10; a=a-b=20; 

  * 数组反转:

    * 把原数组里面的元素反转.==核心思想是用temp变量接收数据==,两种方法如下所示:

    ```java
    package com.YuChenXi.day07.parctice;
    
    import java.util.Arrays;
    
    public class ShuZuJiaoHuan {//反转数组的两种方法
    
        public static void main(String[] args) {
            int[] arr = {1, 2, 3, 4, 5, 6, 7, 8, 9};
            int[] arr1 = {1, 2, 3, 4, 5, 6, 7, 8, 9, 10};
            
            for (int a = 0, b = arr.length - 1; a < b; a++, b--) {
                int temp = arr[a];
                arr[a] = arr[b];
                arr[b] = temp;
            }//定义变量a,b.用a++,b--法,结束条件是a<b
    
    
            for (int i = 0; i < arr1.length / 2; i++) {
                int temp = arr1[i];
                arr1[i] = arr1[arr1.length - i - 1];
                arr1[arr1.length - i - 1] = temp;
            }//不用新定义变量,直接fori,但是注意结束长度条件是数组长度的一半
    
            
            System.out.println(Arrays.toString(arr));
            System.out.println(Arrays.toString(arr1));
        }
    }
    ```

* **二维数组:**

  * 1.**int[] [] arr** , new int[2] [3] : 2个数组元素,每个元素可以装3个元素 
  * 2.存取元素的方式:
    * 二维数组在储存一维数组的时候是存储的**内存地址**
    
    * arr[0] [1]=999; (存储格式)
    
    * ==提前创建好的一维数组放进二维数组==:
    
      * 如果已经创建好的一维数组的元素数量超过了二维数组的预设的宽度,将一维数组塞进二维数组后,也是能将一维数组越界的元素输出(因为是**内存地址的替换**,已经引用的是新的一维数组了,而非二维数组创建时产生的一维数组)
    
        ```java
        int[]arr = {1,2,3,4};
        int[][]arr2=new int[2][2];
        arr2[1]=arr;
        //输出得:arr2[1][3]=4;创建的时候也可以直接 int[][]arr2=new int[2][];
        ```
    
      * 静态初始化:new int [] [] {{1,2,3},{4,5,67},{},{6}}

### 1.8 数组高级

#### 1.81 二分查找数组元素的索引

* 前置条件是数组里面的==元素是按照大小顺序排列的==
* 思路:
  * 把数组第一个索引定义为min,最后一个索引定义为max,中间值是middle=(min+max)/2
  * 将arr[middle]与要查找的元素x进行比较,如果x>arr[middle]大,进入middle后半部分进行查找,反之在前半部分查找
  * 如果是在后半部分,max值不变,min=middle值+1,再计算middle,将x和arr[middle]进行比较
  * 如果是在前半部分,min值不变,max=middle值-1,再计算middle,将x和arr[middle]进行比较
  * 重复直到x==arr[middle],获得middle值为数组索引.
  * 如果数组中没有要查询的元素,二分法继续进行的最终结果就是min>max,此时代表找不到在该数组里面找不到x值,流程结束,返回-1举例:

* 举例：

```java
package com.AdvancedCode.Day05;

public class AdvancedArrErFenFaTest {
    public static void main(String[] args) {
        int[] arr = {4, 5, 6, 7, 8, 9, 10, 11, 12, 13, 14, 15, 16, 17, 18, 19, 23, 45, 67, 99, 233, 445};
        System.out.println("输入元素在数组中的索引位置是:"+seek(arr, 14));
    }

    public static int seek(int[] arr, int x) {
        int min = 0;
        int max = arr.length-1;
        while (min <= max) {//注意,如果一个不断减小的max的值小于不断增大的min值得时候,证明已经找不到了
            int middle = (min + max) / 2;//注意这个随时变动的middle要定义在循环里面
            if (x > arr[middle]) {
                min = middle + 1;

            } else if (x < arr[middle]) {
                max = middle - 1;

            } else if (x == arr[middle]) {
                return middle;
            }
        }
        return -1;
    }
}
```

#### 1.82 数组的冒泡排序

* 针对元素大小顺序打乱的数组进行元素排序的方法
* 思路:

  * 用判断if(arr[i]>arr[i+1]),true则两者i 和i+1 索引上的数值交换,一直循环让最大的数到数组最右边(类似于冒泡到水面)
  * 将除去了最右边的数剩下的元素看成一个新的数组,再冒泡,新数组最右边的元素也是新数组里面最大的数
  * 重复步骤2,完成数组排序

* 举例：

```java
package com.AdvancedCode.Day05;

import java.util.Arrays;
import java.util.Random;

public class AdvancedArrMaoPaoTest {
    public static void main(String[] args) {
        int[] arr = getInts();
        int[] arr2 = Arrays.copyOf(arr, 10);
        y(arr);//方法1
        x(arr2);//方法2
    }

    public static int[] getInts() {
        int[] arr = new int[10];
        int c = 0;
        Random r = new Random();
        for (int i = 0; i < arr.length; i++) {
            arr[i] = r.nextInt(51);
        }
        System.out.println(Arrays.toString(arr) + "-----");
        return arr;
    }

    public static void y(int[] arr) {
        int a =0 ;
        for (int i = 0; i < arr.length - 1; i++) {
            if (arr[i] > arr[i + 1]) {
                int temp;
                temp = arr[i];
                arr[i] = arr[i + 1];
                arr[i + 1] = temp;
                a++;
                if (i == 0) {
                    i--;
                } else {
                    i = i - 2;
                }

            }
        }
        System.out.println("运行了"+a+"次");
        System.out.println(Arrays.toString(arr));
    }

    public static void x( int [] arr) {
        int c = 0;
        for (int i = 0; i < arr.length-1; i++) {//关键步骤
            for (int j = 0; j < arr.length - 1 - i; j++) {
                if (arr[j] > arr[j + 1]) {
                    int temp;
                    temp = arr[j];
                    arr[j] = arr[j + 1];
                    arr[j + 1] = temp;
                    c++;
                }
            }
        }
        System.out.println("运行了" + c + "次");
        System.out.println(Arrays.toString(arr));
    }
}
```

#### 1.83 递归

* 思路：
  * 递归思想就是不断把返回的值又重新调用到方法里面(在方法体内部再调用方法)
  * 最后必须有个结束标志(递归的出口)
  * 方法被重复调用的时候,下一个参数要比前一个参数更加靠近递归出口
* 举例：

```java
package com.AdvancedCode.Day05;

public class AdvancedArrDiGuiTest {
    public static void main(String[] args) {//用递归求10的阶乘
        int i = getmultipy(10);
        System.out.println(i);
    }

    public static int getmultipy(int x){
        if (x==1){
            return x;
        }else{
            x=x*getmultipy(x-1);
        }
        return x;
    }
}
```

#### 1.85 快速排序

* 思路：
  * 先取数组中间元素p
  
  * 数组左右两端L,R一起查找，循环条件是（L<R）。arr[L]如果比p小，左侧索引L++；arr[R]如果比p大，R--。如果两者if都不成立。arr[L]与arr[R]**元素互换**。(所以这个方法要有三个参数：arr[], int left, int right；并且在方法一开始就要把left赋值给L，right赋值给R。要保证实参的纯洁性) 
  
  * 不断递归循环步骤二，相当于p左右两边不断裂变，不断有元素交换
  
  * 直到L==R的时候，证明到头了，设置L++和R--，作为递归的结束条件。
  
    ```java
    package com.AdvancedCode.Day05;
    
    import java.util.Arrays;
    
    public class AdvancedArrKuaiPaiTest {
        public static void main(String[] args) {
            int[] arr = {21, 12, 23, 1, 14, 37,999, 30, 38};
           /*   {2, 12, 23, 1, 14*, 37, 30, 38, 21, 50};
                {2, 12, 23], 1, 14*, 37, 30, 38, 21, 50};
                 {2, 12, 14, 1, 23*, 37, 30, 38, 21, 50};
             */
           m(arr,0,arr.length-1);
            System.out.println(Arrays.toString(arr));
        }
    
        public static void m(int[] arr, int left, int right) {
            int l = left;
            int r = right;
            int p = arr[(left + right) / 2];//中轴值
            int temp=0;
    
            while (l < r) {//while循环终止条件是左边索引一定是小于右边索引,这样才能确保是把数组根据中轴值切割成两部分
                while (arr[l] < p) {//找出左边大于中轴值的时候才跳出循环,不然就一直找
                    l++;
                }
                while (arr[r] > p) {
                    r--;
                }
    
                temp=arr[l];
                arr[l]=arr[r];
                arr[r]=temp;//让左边两边找得的数据进行交换
    
            }
    
         if(l==r){
                l++;
                r--;
            }//这步骤是为了下面两个步骤限制条件,当l==r的时候,指针已经指到最边上了,已经不需要继续操作了,直接l++,r--让下面两个的if条件不成立(作为递归的结束条件)
    
          if(left<r){//递归左边
                m(arr,left,r);
            }
    
            if (right>l){//递归右边
                m(arr,l,right);
            }
        }
    }
    ```
  
    

## 2.对象与类

### 2.1 概述

* **类（class）**：

  *  构造（construct）*对象*的模板，类构造对象的过程叫做创建类的*实例*（instance）,java库提供上千个类可供使用，自己也可以创建新的类。
  * *在java中，没有类就无法做任何事情*
  * *（并不是所有类都有面向对象的特征，如Math类，只封装了功能，没有数据，不可生成对象以及初始化实例域）。*

* **封装**：类似于黑盒，关键在于不可以让类中的**方法**访问其他类的**实例域**（对象中的数据（成员变量）），==程序仅仅通过**对象的方法**和**对象的数据**进行**交互**==。此对象发生的变化其他对象不知道。

  * **private**:*只能在本类当中被访问*.用方法来**set/get方法调用**域值(例如可以对进行if检查再选择是否调用方法,更加灵活)
  
* **对象**：对象的三个特性：

  * 1.行为（可以给对象施加哪些方法）；

  * 2.状态（施加方法后对象怎么响应）；对象间彼此方法的调用形成联系
  * 3.对象的标识（对象自己的唯一的身份）。

### 2.2 对象的构造

####  2.21 构造器

* **构造器（constructor）**：特殊的方法，用来构造以及初始化对象。（1.构造器与类同名；2.构造器可以有多个参数；3.一个类可以有多个构造器；4.构造器没有返回值（连void都没有）；5构造器总是伴随着new）==成员变量有初始化值,局部变量没有,必须先赋值,再使用==

  ```java
  Student Stu1 = new Student();//本质上是new Student()就已经创建了一个新的对象了，将这个新对象存放到一个对象变量Stu1中。Stu1没有包含一个对象，只是引用了一个对象。(强,软,弱,虚引用)
  Student Stu2;
  Stu2=Stu1;//引用同一个内存地址
  Stu1=null;Stu2=null;//对象没有被引用了,成为了!垃圾!,垃圾回收器空闲的时候会将它回收. 
  ```

* **自定义类**:  构造一个Employee类

  ```java
  public class Employee{
      private String name;
      private double salary;//实例域(类中方法外,有默初始化认值),在堆内存.(局部变量在栈内存,没有默认初始化值)
      
      public Emloyee(String x,double y){
          name=x;
          salary=y;
      }//构造器
      public void xxx(){
          System.out.println(name+salary)//成员方法
      }
  }
  ```

  **隐式参数/显示参数**：例如

  ```java
  xxx.yyy()//xxx这个对象调用yyy方法
  ---------------------------------------
  private int number;
  ,,,
  public void yyy(int x){
      int y = this.number+x;
  }//这里的int x是显式参数，有一个xxx被省略掉了，也可用this代替
  
  ```

  **封装**：*1.一个private的数据域，2.公有的域访问器（get）/工有的域修改器（）*（一个方法可以访问所属类的所有对象的私有域）

  **final实例域**：将实例域定义为final后，不可被修改，也没有set更改器方法。例如：

  ```java
  class Empolyee{
      private final String name;
      ...
  }
  ```

####  2.23 静态static

##### 2.231 静态域

* *静态域*：如果将域定义为static:(静态域/静态方法都可以直接用*类名.调用*,也可以*创建对象调用*)

  * 1.则==这个类**所有的对象都共享(可以作为判断条件)**一份这个静态域,如果静态域被更改,那么其他对象也会共享更改后的静态域==。
  * 2.这个静态域本质是属于类，不属于任何对象, ==随着类的加载而加载,**优先于对象存在**==。**static优先于其他非static域/方法加载,所以无法用static调用其他域/方法**,**但是可以调用其他静态**.
  * 3.可以直接 **类名.静态方法**名进行调用(对象名调用=方式依旧保留)
  * 4.静态方法里面不能用this,super(没有对象...)
  
  ```java
  class Empolyee{
      private static int nextId=1;//静态域
      private int id;//实例域
      ...
  }
  ```

##### 2.232 静态常量

* *静态常量*：在类中定义静态常量，可以直接通过类调用这个常量，例如：

  ```java
  public class Math{
      public static final double PI=314..........;
      ...
  }
  ```

  调用的时候直接Math.PI即可。

##### 2.234 静态方法

* *静态方法*:不能向对象实施操作的方法，直接用类调用（或者说静态方法没有隐式参数）

  在两种情况下需要使用静态方法：

  * 1.一个方法不需要访问对象状态，其需要的参数都式通过显示参数,**没有this关键字**                                                  
  * 2.==**一个静态方法只能访问类的静态域/方法**==（**静态优先加载,非静态需要创建对象才能使用** ,静态方法不能访问实例域，因为它不能操作对象，但是它可以访问静态域，因为静态域是属于类的）
  * 3.**非静态方法可以访问静态域/方法**(很好理解,如果可以调用非静态方法的时候,说明对象都已经创建好了,那么当然类已加载完毕,静态域/方法也都加载好了)

* **程序清单4-3**例子如下，涉及到*Employee类的构造，其中包括静态域、实例域、有参构造器、成员方法、访问器方法（包括静态）。对象数组的构建、foreach遍历（直接e.setid这种形式对数组内所有对象使用方法）*

```java
import java.util.Arrays;
import java.util.Scanner;

public class test2 {
    public static void main(String[] args) {
        Employee[] staff = new Employee[3];
        staff[0] = new Employee("Tom", 100);
        staff[1] = new Employee("Jack", 300);
        staff[2] = new Employee("Max", 500);
        for (Employee e : staff) {
            e.setid();
            System.out.println("id" + e.getId() + " " + "name " + e.getName() + " " + "salary " + e.getSalary());
        }//把每个成员都遍历出来，并且id++
        int n = Employee.getNextid();
        System.out.println("Nextid is " + n);
    }

}

class Employee {
    private static int nextid = 1;
    private String name;
    private double salary;
    private int id;

    public static int getNextid() {
        return nextid;
    }

    public String getName() {
        return name;
    }

    public double getSalary() {
        return salary;
    }

    public int getId() {
        return id;
    }

    public Employee(String x, double y) {
        name = x;
        salary = y;
        id = 0;
    }

    public void setid() {
        id = nextid;
        nextid++;
    }

    public static void main(String[] args) {
        Employee e = new Employee("zhangsan", 200);
        System.out.println("name " + e.getName() + " " + "salary " + e.getSalary());
    }//可以单独运行这一段
}

```

#### 2.24 方法参数和重载

* 方法的注意事项:
  * 方法与方法是平级关系,**不能嵌套定义**,包括主方法.
  * 方法可以**嵌套调用**,要注意参数的定义位置
  * **方法的调用过程**
    * 没被调用的时候在**方法区**的字节码文件.class中储存
    * 调用的时候进入**栈内存**运行
  * 形式参数:(int num); 实际参数: (*num*: 10);
  * 方法=方法的声明+方法的实现
  * **return:**
    * 1.return代表着方法的结束,**void可以写return**,但是不能带数据,只是表示方法的结束,后面不能再写代码;
    * 2.有返回值的时候,必须有return返回返回值,**返回内容可以是变量**;
    * **一个方法只能返回一个返回值**;多个结果可以打包成一个数组

* **方法参数：**java**都是按值(*数据值/地址值*)调用**(原先变量的自己的值不会改变)，表示方法接收的是调用者提供的值

  * 如果**传递的引用数据类型,传递的是内存地址**,如果在方法里面有改动,引用内存地址的对象变量都会改变. (根本不同在于**会不会对堆里面的值做改变**,如果在方法里面使得堆里面数据改变,主方法里面的引用类型的对象的值也会改变),如下例:

    ```java
    package com.YuChenXi.day06.practice;
    
    import java.util.Arrays;
    
    public class TestStack {
        public static void main(String[] args) {
            int[] arr = {1,2,3,4};
                test(arr);//调用方法后也会发生数据改变
            System.out.println(Arrays.toString(arr));//只改变了第一次
        }
    
        public static void test (int[]x){
            x[0]=0;//此方法传递的地址值,此处已经对堆内存的该地址值的数据进行了改变
            System.out.println("直接更改"+x[0]);
            x=new int[]{1,23,4,56};
            x[0]=1000;
            System.out.println("在test方法里面重新让x引用新的数组对象"+x[0]);
        }
    }
    ```

  * 方法不能修改一个基本数据类型的参数（值/布尔型）

  * 方法可以改变*对象参数*的状态

  * 方法不能让对象参数引用新的对象

* **重载 :** 如果同一个类中有多个方法，***名字*相同，但是*参数* (个数,类型,顺序) 不同**(方法名和参数构成了方法的签名)，则构成了重载。(和返回值没有关系)

  * 原则:**参数类型符合就近原则,如果类型不能完全一致,就按照 byte-short-int-long的顺序往上提升调用方法,但是如果混淆就会报错**

  * 如果编写类的时候，没有写构造器，则系统默认一个无参构造
  * 如果写了构造器，那么必须也得写一个无参构造

#### 2.25 显示域的初始化、初始化块(代码块)

* **显示域的初始化：**

  * 通过构造器的重载，可以用多种形式设置类的实例域的初始状态，每个构造器都是一个途径。
  * 实例域的初始值不一定是非得是常量，也可以是方法的返回值。

* 用**this**调用同一个类的另一个构造器（这个除了表示隐式参数以外的第二个用法）。注意：this要在构造器里面第一行

* **初始化块：**初始化数据域的第三种方法（第一种是在构造器中设置值，第二种在声明中直接赋值）

  * 形式：==位置在类中方法外; 分为静态代码块(类中方法外), 构造代码块(类中方法外) ,局部代码块(方法中定义)==

    ```java
    {//构造代码块,位置在类中方法外
        id=nextId;
        nextId++;
    }//就是直接在类中加一个代码块，首先会运行这个初始化块，再运行构造器的主体部分,(这个就是构造代码块,每次创建对象都会运行,而且是在构造器之前)
    
    static
    {
     Random x = new Random();
     nextId=x.nextInt(1000);
    }//静态初始化块的格式(区别于构造代码块,静态代码块只执行一次)
    ```

  * 程序4-5例子

  ```java
  public class ConstructorTest {
      public static void main(String[] args) {
          Employee[] staff = new Employee[3];
          staff[0]=new Employee("张三",3000);
          staff[1]=new Employee(4000);//调用了另一个构造器
          staff[2]=new Employee();
  
          for (Employee e:staff) {
              System.out.println("name="+e.getName()+",id="+e.getId()+",salary="+e.getSalary());
          }
      }
  }//在Employee这个类里面使用了静态初始化块，随机生成一个0-99的静态域nextid，这个Employee类生成的对象都共用这一个静态的nextid数值。
  
  class Employee {
      private static int nextid;
      private int id;
      private String name = "";
      private double salary;
  
      static {
          Random generator = new Random();
          nextid = generator.nextInt(100);
      }
  
      {
          id = nextid;
          nextid++;
      }
  
      public Employee(String name, double salary) {
          this.name = name;
          this.salary = salary;
      }
  
      public Employee(double s) {
          this("Employee#" + nextid, s);//调用第一个构造器，"Employee#" + nextid因为牛皮糖效应自动成了String类的参数
      }
  
      public Employee(){
  
      }
  
      public int getId() {
          return id;
      }
  
      public String getName() {
          return name;
      }
  
      public double getSalary() {
          return salary;
      }
  }
  
  ```

#### 2.26 final 关键字

* final可以修饰类/变量/方法/域

* 被final修饰的类是最终类,不可以被继承

* ==被final修饰的方法不可以被覆盖==

* 被final修饰的变量

  * 基本数据类型:只能在第一次被赋值,不能被再次赋值,(常量)

  * 引用数据类型:**变量**的引用对象的内存地址值不能被更改,但是对象的域值可以改变

    ```java
    final Student stu=new Student();
    stu =new Student();//这里就错了,stu已经被final修饰,和之前的对象地址值绑定在一起了
    ```

  * 用**final修饰域值**得时候,有两个选择:

    * 声明变量的时候就赋值
    * **在构造器里面赋值**:在创建对象的时候可以对final域赋值,增加了灵活性.(但是要确保所有的构造器都有给final域赋值的能力,如果有一个可能无法给它赋值,编译就无法通过)

### 2.3 分包/分类思想

#### 2.31 分类

* 将复杂的代码块分散在各个类里面,便于专人干专事同时提高代码的可读性和维护性
* 此处是分为 Data (数据), Service(业务逻辑) ,controller(用户交互) ,entry(提供main方法)

#### 2.23 分包

* package,本质是文件夹,字母都是小写
* 一般都是 **com.xxx.其他包名**
*  类和package声明紧密相连
* **类与类的访问:**
  
  * 同一个包下面,直接访问
  * 不同包下面
    * 1.import导包
    
    * 2.通过全类名(包名+类名)访问(比如java.lang.String),**多个包下面有==相同的类名称==**,**用此方法加以区分**
    
    * ```java
      import java.util.*;//*:通配符,直接通过*把until包的直接类全部导入
      //java.lang.* 这个包是自动存在的,这就是为什么System.out可以直接使用的原因
      ```

##  3 .继承

### 3.1 继承

#### 3.11继承的格式

* **继承**：“is-a”关系是继承的明显特征：如Manager is a Employee. 继承的关键词是extends

* 已经存在的类是**超类**，如Employee，新派生出来的类是**子类**，如Manager，子类继承了超类的域和方法，并且封装了更多数据，拥有更多功能。

  ```java
  public class Manager extends Employee{
      private double bonus;
      public void setbonus(double bonus){
          this.bonus=bonus;//新添加的私有域和方法
      }
  }
  
  ```

#### 3.12 覆盖方法

* **覆盖方法(override)**：对于从超类继承下来的有些方法在子类不一定适用，在子类中需要写新的方法将其覆盖

* 覆盖注意事项：@override是注解,可以用来检测是否是正确的覆盖.

  * 1.方法名相同；2.参数类型相同；3.返回类型兼容（允许子类覆盖方法的返回类型为原返回类型的子类型，比如原返回类型为Employee，覆盖方法返回类型可以为Manager）
  * 4.==超类的**私有方法**不可覆盖==(因为超类的私有方法是子类访问不到的,连覆盖的的机会都不给)
  * 5.==超类**的静态方法**不可以被覆盖==,如果子类的有个静态方法和超类一样,可以看做是把超类的静态方法隐藏了(可以有,但并非覆盖)
* 6.子类的覆盖方法的**访问权限**要大于等于父类(例如:父类方法是protected,子类就必须是protected/public)
  
* 注意：子类的get方法不能直接**访问超类的私有域（private）,需要调用超类自己的get方法（它是public的），调用方法:使用super.关键字。（如super.getSalary()）** *超类的private域其实也是被子类继承下来了,就是不能直接调用*

#### 3.13 子类构造器

* 子类构造器：由于子类的构造器也不能直接访问超类的私有域，必须用在子类构造器里面用**super（)**来调用超类的构造器。==**如果不调用超类构造器,那么就自动启动超类的默认构造器(系统隐藏了super(),()里面是空的,就像超类的默认构造一样,是隐藏默认的),想在子类使用父类的有参构造器就必须super(...)**==
* 注意：**super( x,y);** //这个是调用超类构造器的格式，意思就是调用超类里面有x , y 显示参数的那个构造器。
* 注意：super( )；必须位于子类构造器里面**第一行**。
* **this**的三个用途:
  * 1.表示隐式参数,
  * 2.也可以解决局部变量和域的重名问题,和对象变量的打印地址都是一样的,所以本质也就是所在类对象的引用
  * 3.调用该类的其他构造器，如：this("Employee#" + nextid, s);//调用第一个构造器  ）
* **super**的两个用途:
  * 1.调用超类的方法 
  * 2.调用超类的构造器
  * 3.如果超类的方法/域都是public,那么在子类对象中直接调用即可**,如果是私有的/重名(*重名的情况因为就近原则,会调用子类的域/方法*)的,那么就要使用super.xxx/super.xxx( )**

###  3.2 多态

#### 3.21 多态

* **多态**：一个对象变量（如 x）可以指示多种实际类型(如 Manager类,Employee类)的现象,其中，*程序中任何出现超类对象的地方，都可以用子类对象置换*。（ 运行是时候自动选择调用哪个方法的现象叫做**动态绑定**。）

  程序5-123例子

  ```java
  package example5_123;
  
  public class ManagerTest {
      public static void main(String[] args) {
          Manager boss = new Manager("Jack", 9000);
          boss.setbonus(2000);
          Employee[] staff = new Employee[3];
          staff[0] = boss;//父类的对象可以用子类代替
          staff[1] = new Employee("Mike", 2000);
          staff[2] = new Employee("Bob", 2500);
          for (Employee e : staff) {
              System.out.println("姓名"+e.getName()+" "+"薪水" + e.getSalary());
          }//多态的重要用途:提高代码的扩展性
  
      }
  
  }
  
  class Employee {
      private String name;
      private double salary;
  
      public Employee() {
  
      }
  
      public Employee(String name, double salary) {
          this.name = name;
          this.salary = salary;
      }
  
      public String getName() {
          return name;
      }
  
      public void setName(String name) {
          this.name = name;
      }
  
      public double getSalary() {
          return salary;
      }
  
      public void setSalary(double salary) {
          this.salary = salary;
      }
  
      public void raiseSalary(double x) {
          double raise = salary * x / 100;
          salary += raise;
      }
  }//超类
  
  class Manager extends Employee {
      private double bonus;
  
      // public Manager() {}
  
      public Manager(String name, double salary) {
          super(name, salary);//调用超类构造器
          bonus = 0;//在构造器里面把bonus初始化
      }
  
      @Override
      public double getSalary() {
          return bonus + super.getSalary();
      }//覆盖超类的getSalary方法// 这也是多态实现的前提条件之2,就像绳索一样,让子类对象被超类统一控制
  
      public void setbonus(double x) {
          bonus = x;
      }//新定义一个方法给bonus赋值，可控性强
  }//子类
  ```

* Java语言中，**对象变量**是**多态**的，一个Employee对象变量可以引用Employee对象，也可以引用任何Employee类的子类的对象，如Manager对象，Executive对象等。

  * 超类对象不能赋予子类对象变量
  * 子类数组的引用可以转换成超类数组的引用
  
* 多态中的构造器/域/方法访问特点:

  * **构造器:和继承一样,**子类通过super访问超类的构造器

  * 域:用超类对象变量引用子类对象后,用对象访问的域值是**超类的域值**
  * 方法:用超类对象变量引用子类对象后,用对象访问的方法是**子类的方法,**==两者不同的根本原因是:方法是有覆盖的,域是无法覆盖的==

* ==**多态的三个前提条件**==:

  * 1.有继承/实现关系
  * 2.子类覆盖了超类方法
  * 3.超类对象变量引用了子类对象
  
* 多态的好处和弊端:

  * 好处:提高了代码的扩展性:让超类/接口统一调度子类
  * 劣处:无法直接方法子类特有的方法(这个可以通过**转型(3.33)**改善:)
    * ==多态中的转型==:**向下转型:从超类类型转换成子类类型(确保被转型的对象是真正的子类对象,本质是复原,不可虚报瞒报,要保持类型统一).**格式是Zi z = (Zi) f;   向上转型就是超类对象变量引用了子类对象
    * **可以用==instanceof==检查类型是否统一**

#### 3.32 Java方法的调用过程

* **Java方法的调用过程**
* 1.如果x.f(y), x是A类的对象,A的超类是B。编译器会列举所有A类里面的f方法以及A类的超类里面所有的public的f方法。（获取名字）
  * 2.重载解析，找出和y相符的参数类型的方法。（获取参数类型）
  * 3.如果是private,final,static,构造器方法，编译器就会准确知道调用哪个方法（静态绑定）。普通方法的调用是动态绑定，依赖于隐式参数的实际类型。
  * 4.动态绑定时，编译器会调用与实际类型最合适的那个类的方法（先在x的类A里面寻找f，再在超类B里面寻找f，以此类推）。如果是super.f(y)，则直接在超类里面寻找。


#### 3.33 强制类型转换

* **强制类型转换**

  * 转换原因：暂时忽略对象类型，使用对象的全部功能。
  * 转换方法：和数据类型的强制转换一样，如 Manager boss=(Manager)  staff[0] (程序5-123例子中，staff[0]是Employee的对象变量，引用的是子类Manager对象，现在用强制类型转换将其**复原**成Manager类)

### 3.3 抽象类

* 抽象类（abstract）是用于派生其他类的基类，如person类，animal类，本身无法被具体描述，不能被实例化(**但是有构造方法**)。实现前提是继承性.

  ```java
  public abstract class Person{
      ...
      public abstract String getDescription();
  }
  ```

  * 抽象类的抽象方法没有主体体，它是为了标记**多态**而存在，充当着占位的角色，它的具体实现在子类之中。==抽象类里面是有构造器的(区别于接口),为了子类实例化==
* 包含抽象方法的类必须为抽象类，但是如果类没有抽象方法，也可以标记抽象。
  * 可以定义抽象类的对象变量，但是只能引用**非抽象子类**的对象，如 Person p = new Student();
  * **abstract不能修饰**:域 ,构造器, 私有方法 ,final方法/类 ,静态方法 (==因为静态方法不能被覆盖,且有方法体==)

###  3.4 Object类

#### 3.41 equals

* Object类：所有类的祖宗类。如果一个类没有明确指出超类，那么这个类的超类就是Object类。//java中只有基本类型的值不是对象（数值，字符，布尔类型），其他都是对象
* **equals方法**：Object类的equals方法用来判断两个对象是否具有相同的引用。**这里将equals方法覆盖，用以判断两个对象状态的相等性**。
  * ==注意:String类已经将equals方法覆盖,会有一个instanceof检查参数是不是String类型,如果不是String,直接返回false==
* 1.首先要进行初步检测，若是this**==*otherObjectl return true;（因为这直接证明了两者的地址值相等，两个对象有着相同的引用）
  * 2.检测otherObject是否为**null** 
  * 3.用getClass**检测类**是否相同
  * 4.鉴于前三者检测都已经部署，第四步是将otherObject**类型转换**other。（转换成被比较的类，便于实行第五步）
  * 5.将两者对象的**每个域**进行检测。对于域中的对象值，比如String 类的name,可以用Objects.equals(name,other.name)进行比较。

#### 3.42 hashcode

* **hashcode方法**

  * hashcode（散列码）方法定义在Object类中， 每个对象都有自己的hashcode，其值为对象的储存地址。两个相等的对象散列也是相等的。

    * 字符串的散列码是由其内容导出的

    * null安全方法，如果参数为null,则返回0

    * Objects.hash方法，是对各个参数调用散列码，并且将他们组合在一起，如：

      ```java
      Objects.hash(name,salary);
      ```

#### 3.43 toString

* **toString方法**

  * 对象+一个字符串，那么java会自动调用toString方法。 *Object的toString是直接打印类名和散列码*

    可以将Object类的toString方法覆盖，大多数格式都是 **类名**加上方括号括起来的**域值**，如：

    ```java
     return getClass().getName()+"[name="+name+",salary="+salary+"]";
    ```

  * 子类可以直接调用super.toString方法

  * 数组对象要用Arrays.toString( )方法打印整个数组。不能直接toString,否则就和普通对象一样打印出了散列码

    * 这本书强烈建议定义自己的toString方法

```java
package example5_8910;

import java.util.Objects;

public class EqualsT {
    public static void main(String[] args) {
        Employee jack1 = new Employee("jack",100);
        Employee jack2=jack1;
        Employee jack3 = new Employee("jack",100);
        Employee mike =new Employee("mike",200);
        System.out.println("jack1==jack2:"+(jack1==jack2));//jack1==jack2:true
        System.out.println("jack1==jack3:"+(jack1==jack3));//jack1==jack3:false...==对于引用类型只能比较地址，每个对象的地址都是不同的(hashcode初始就等于地址值，但是hashcode后期可以修改，但是地址值不会变的)
        System.out.println("(jack1.equals(jack3)):"+(jack1.equals(jack3)));//(jack1.equals(jack3)):true...用覆盖了的equals方法来比较
        System.out.println("jack1.equals(mike):"+jack1.equals(mike));//jack1.equals(mike):false
        System.out.println(mike.toString());//example5_8910.Employee[name=mike,salary=200.0]
        System.out.println("-------------------------------------------");
        Manager pony =new Manager("pony",3000);
        Manager boss =new Manager("pony",3000);
        boss.setbonus(2000);
        System.out.println("boss.toString():"+boss.toString());//boss.toString():example5_8910.Manager[name=pony,salary=3000.0][bonus=2000.0]
        System.out.println("pony.equals(boss):"+pony.equals(boss));//pony.equals(boss):false
        System.out.println("jack1.hashCode():"+jack1.hashCode());//jack1.hashCode():1180456898
        System.out.println("jack2.hashCode():"+jack2.hashCode());//jack2.hashCode():1180456898
        System.out.println("jack3.hashCode():"+jack3.hashCode());//jack3.hashCode():1180456898
        System.out.println("mike.hashCode():"+mike.hashCode());//mike.hashCode():1184521867
        System.out.println("pony.hashCode():"+pony.hashCode());//pony.hashCode():31
    }
}

class Employee {
    private String name;
    private double salary;

    public Employee() {

    }

    public Employee(String name, double salary) {
        this.name = name;
        this.salary = salary;
    }

    public String getName() {
        return name;
    }

    public void setName(String name) {
        this.name = name;
    }

    public double getSalary() {
        return salary;
    }

    public void setSalary(double salary) {
        this.salary = salary;
    }

    public void raiseSalary(double x) {
        double raise = salary * x / 100;
        salary += raise;
    }

    @Override
    public boolean equals(Object OtherObject)  {
        if (this == OtherObject) return true;//第一步直接检测是否相等
        if (OtherObject == null) return false;//检测是否为null
        if (this.getClass() != OtherObject.getClass()) return false;//检测类是否一致
        /*前三个If相当于事前检测*/
        Employee other = (Employee) OtherObject;/*类型转换，都转成Employee,便于下一步对比两个对象的每个域*/
        return Objects.equals(name,other.name)&&salary==other.salary;
    }//覆盖了比较两个对象的equals方法

    @Override
    public String toString() {
       return getClass().getName()+"[name="+name+",salary="+salary+"]";//覆盖了Object类的toString方法，直接返回对象名+各个域的值
    }

    @Override
    public int hashCode() {
       return Objects.hash(name,salary);
    }
}
//超类

class Manager extends Employee {
    private double bonus;


    public Manager(String name, double salary) {
        super(name, salary);
        bonus = 0;//在构造器里面把bonus初始化
    }

    @Override
    public double getSalary() {
        return bonus + super.getSalary();
    }//覆盖超类的getSalary方法

    public void setbonus(double x) {
        bonus = x;
    }//新定义一个方法给bonus赋值，可控性强

    @Override
    public boolean equals(Object OtherObject) {
       if (!super.equals(OtherObject)) return false;//先让超类编辑好的equals测试一下
        Manager other = (Manager) OtherObject;//比较域之前一定要进行类的类型转换
        return bonus==other.bonus;
    }

    @Override
    public String toString() {
        return super.toString()+"[bonus="+bonus+"]";
    }

    @Override
    public int hashCode() {
        return Objects.hash(bonus);
    }
}//子类

//这个例子主要在于：覆盖Object类的equals,toString，hashcode方法。深入理解覆盖前后的原理和内容
```

### 3.5 泛型数组列表

* **Arraylist类**：是采用**类型参数**的**泛型类**，类似数组但是在添加元素和删除元素的时候，允许自动调节自身容量（数组无法调节）

  ```java
  Arraylist<Employee> staff = new Arraylist<>();//Employee就为类型参数
  ```

* 数组列表本质是管理着**对象引用的一个内部数组**，数组的空间会被用尽。如果调用add且内部数组已经满了，**数组列表会自动创建一个更大的数组，并将所有对象从小数组拷贝到大数组**。

* new Arraylist<>(100)；//这里将100放进构造器里面，不是代表数组容量为100，而是它有**保存100个元素的潜力**。

* Arraylist类不是java自带的，是后期编写的实用类，所有用**set/get方法**来访问其中的元素。==(打印Arraylist也是直接的**值**,而不是内存地址,和String/StringBuilder一样)==

* 常用的Arraylist<>类的方法：

  ```java
  staff.get(i)//获取i位置的元素
  staff.set(i,xxx)//更改i位置的元素
  staff.add(i,xxx)//i位置插入元素，i后面的元素后移一位
  staff.remove(i)//返回移除的位置元素，i后面的元素前移一位,容量减1;  返回值是true/false;根据元素名称删除只能删除第一了;  删除之后确保加上" i-- ",确保不会因为自动缩进而没有删除干净
  staff.size()//返回数组列表中的元素数量
  staff.contains()//判断集合是否有这个元素,可以用于判断对于集合的增删查改是否要继续进行
  ```

* 先创建Arraylist<>,在用toArray方法将其转换成数组。这样可以灵活扩展数组，又可以方便访问数组元素，如：

  ```java
  import java.util.ArrayList;
  import java.util.Arrays;
  
  public class ARRAYLISTTOARRAY {
      public static void main(String[] args) {
          ArrayList<Integer> list = new ArrayList<Integer>(100);//创建Arraylist数组列表，潜力容量是100
          for (int i = 0; i < 120; i++) {//将119个数字塞进这个数组列表，超出了100，自动扩容了
              list.add(i);
          }
  
          Integer[] arr = new Integer[list.size()];//创建容量为list.size的数组
          Integer[] integers = list.toArray(arr);//用list的toArray方法（参数是数组arr）将元素拷贝到arr数组里面,返回了新的数组iNtergers
          String s = Arrays.toString(integers);//用Arrays的静态方法toString（参数是被转换的integers）将数组转换成字符串s
          System.out.println(s);
      }
  }
  ```

### 3.6 对象包装器、参数数量可变方法

#### 3.61自动装箱、拆箱

* 有时候需要将int,double等基本类型转换成对象，每个基本类型都有一个与之对应的类，称为**包装器**，如**Integer/Long/Folat/Double/Short/Byte/Character/Void/Boolean **（注意到首字母都是大写）。

  * 一旦构造了包装器，不允许改变其中的值。对象包装器类**不可变**
  * 包装器类是**final类**，不允许定义它们的子类
  * 鉴于包装器类产生的是对象，**==运算符**比较的是对象的储存区域

* ==**Integer**==注意事项:

  * 用**静态方法ValueOf( )**输入**Int类型/String类型**值作为参数,获取**对象**
  * 在进行操作的时候,最好进行**非null判断**，比如出现了Integer i =null；就会空指针异常
  * **Integer.parseInt( )方法** ,是把**String**类型的数据**转换成int类型（注意是基本类型不是引用类型）**的数据.
    * ( 如果想反过来转,直接==**1.** +""; **2.** String.valueOf(int x)==) 

* **自动装箱**：将基本类型的值自动变成包装器类的方法中的参数的过程==(自动调用Valueof)==，反过来的过程是**拆箱**。**(比如塞入集合的时候,集合只能存储引用数据类型)**

* **自动拆箱**：调用**intValue( )**方法

  ```java
  list.add(3);/*自动转换成*/ list.add(Integer.valueof(3)); 
  ```

#### 3.62 参数可变方法

* **参数数量可变方法**：可以定义可变参数的方法（任意类型），如：

  ```java
  package com.heima.xiangmu;
  
  public class Testprintf {
      public static void main(String...args) {
          double max = max(12, 34, 56, 35, 22, 356);//这里自动将数组new double[]{12,34,56,35,22,356}传递给了max方法。这里是数组，所以在max方法里面可以用foreach遍历
          System.out.println(max);
      }
  
      public static double max(double... values) {//...是java代码的一部分，表示可以接收任意数量的对象。
          double largest = Double.NEGATIVE_INFINITY;//负无穷大
          System.out.println(largest);//-Infinity
          for (double v : values) {//foreach遍历
              if (v > largest) {
                  largest = v;//这里的目的和定义max=arr[o]效果一样，首先让values里面第一个数字是largest(因为之前的largest是负无穷大，任何数字和它比较大小都会取而代之)
              }
          }
          return largest;
      }
  }
  
  ```


### 3.7 枚举类

* **枚举**：枚举的对象是**有限个**，**确定的**，一年四季，一年12个月。
  * 枚举类尽量**不要构造对象**，否则破坏了确定性
  * 比较枚举类的值直接用**==**而非equals
  * 可以在枚举类里面添加**构造器，方法，域**。构造器是构造枚举常量的时候调用

```java
package com.heima.xiangmu;

import java.util.Scanner;

public class ENUM {
    public static void main(String[] args) {
        Scanner sc=new Scanner(System.in);
        System.out.println("Enter a Size:():SMALL,MEDIUM,LARGE,EXTRA_LARGE");
        String input =sc.next().toUpperCase();//把输入的字符全部转换成大写
        Size s = Enum.valueOf(Size.class, input);//关键步骤，Enum类的静态方法valueof，可以根据枚举对象的名字返回这个对象，供后面步骤调用方法，枚举类型Size的变量s只能存储枚举类中的某个值
        System.out.println("Size="+s);//这里的s就是个常量了
       System.out.println("缩写="+s.getAbb());
        if(s==Size.EXTRA_LARGE){//比较两个枚举类型的值，切记是==，而不是equals
            System.out.println("goodjob");
        }
    }

}
enum Size{//首先编写枚举类，不同于普通类，它是enum,而不是class
    SMALL("S"),MEDIUM("M"),LARGE("L"),EXTRA_LARGE("XL"),BIG("XLL");//要放在第一行，（）里面是参数，与有参构造方法对应
    private String abb;//也可以添加域

    private Size(String abb) {//也可以添加构造器
        this.abb=abb;
    }
    public String getAbb(){//也可以添加方法
        return abb;
    }
}

```

```java
package com.heima.xiangmu;

public class ENUM1 {
    public static void main(String[] args) {
        season s = season.spring;
        System.out.println(s);
    }
}
enum season {spring,summer,auntum,winter;}//这几个都相当于是枚举类的对象，自动调用空参构造
//编写了一个最简单的枚举类
```

* 测试枚举类中的方法

```java
package Day19Test;

public class test {
    public static void main(String[] args) {
        t w = t.West;
        System.out.println(w.name());//name()方法
        System.out.println(w.ordinal());//ordinal()；返回索引值
        System.out.println(w.compareTo(t.North));//compareTo()两个索引值的差值
        System.out.println(w.toString());//toString()
        System.out.println(t.valueOf(t.class, "North"));//指定枚举类中指定名称的枚举值,静态方法
        t[] values = t.values();//获取枚举类里面所有的枚举项，返回一个数组
        for (t value : values) {
            System.out.println(value);
        }
    }
}

enum t {
    East("东方"), South("南方"), West("西方"), North("北方");

    private String name;

    private t() {

    }

    private t(String name) {
        this.name = name;
    }
}
```



### 3.8 反射

* 反射库提供了强大的API，能够编写**动态操纵**Java代码的程序。能够分析**类能力**（域，构造器，方法）的程序具有反射性。
  * 运行时分析类的能力，查看对象
  * 实现通用的数组操作代码、利用Method对象

#### 3.81 Class类

* **Class类**：Class类保存着对象所属类的信息，每个类都有个Class对象。可以用==运算符比较两个Class类对象的。创建Class类的对象的三种方法：
  * 对象名.getClass();
  * Class.forName( " name"):
  * 类名.class; 

```java
Employee e =new Employee();
Class cl = e.getClass();//第一种方法
----------------------------------------
Class cl = Class.forName("java.lang.String")//第二种方法,注意参数是全类名字符串，包也是类名的一部分。无论何时使用这个方法，都必须提供异常处理器（防止输入的类名不正确）。
----------------------------------------       
Class cl = Employee.class//第三种方法。int.class也可以。因为Class对象表示一个类型，基本类型也可以
```

* **通过书写properties文件使得不用修改源代码的情况下，直接修改配置文件的信息，使用Class.forName()获取Class对象**

```java
package Day18Test;

import java.io.IOException;
import java.io.InputStream;
import java.util.Properties;

public class MyreflectTest {
    public static void main(String[] args) throws ClassNotFoundException, IOException, NoSuchFieldException {
        ClassLoader loader = ClassLoader.getSystemClassLoader();
        InputStream is = loader.getResourceAsStream("ppp.properties");

        Properties p = new Properties();
        p.load(is);//加载配置文件，变成properties集合
        String className = p.getProperty("className");//从事先写好的配置文件里面获取全类名
        
        Class<?> clazz = Class.forName(className);
    }
}
```

* **newInstance()方法** :**动态**地创造一个类的实例，如：

  * getClass().getDeclaredConstructor().newInstance()方法，创建类的实例
  
  * 可以通过类的字符串称，通过Class.forName.getDeclaredConstructor().newInstance()方法，创建类的实例，如：
  
  ```java
    package example5_123;
    
    import java.lang.reflect.InvocationTargetException;
    
    public class Test {
        public static void main(String[] args) throws ClassNotFoundException, IllegalAccessException, InstantiationException, NoSuchMethodException, InvocationTargetException {
             Student stu =new Student();
           // Student stu1 = stu.getClass().newInstance();（Java9之后不推荐此方法，显示已经过时）
            Student stu2 = stu.getClass().getDeclaredConstructor().newInstance();
          //---------------------------------------------------------------  
            Class<?> cl = Class.forName("example5_123.Student");
         //   Object o = cl.newInstance();（Java9之后不推荐此方法，显示已经过时）
            Object o = cl.getDeclaredConstructor().newInstance();//
            System.out.println(o.toString());
    //----------------------------------------------------------------------------
        }
    }
    
    class Student {
        private String name;
        private int age;
    
        public void nation() {
            System.out.println("China");
    
        }
    
        public String toString() {
            return getClass().getName() + "[name=" + name + ",age=" + age + "]";
        }
    }
    
  ```

#### 3.82 捕获异常

对于可能出现异常的代码，可以**抛出异常（throw exception）/提供异常处理器（try { ...} catch(... ){... }）**。抛出异常比直接终止程序更加灵活，提供了可能发生意外的处理机制。 例如：

```java
 try {//检查异常
          Class<?> cl = Class.forName(name);//用forname创建Class类的实例cl(第2种方式),可能会出现输入名称异常情况
        } catch (ClassNotFoundException e) {
        e.printStackTrace();//idea自动添加了catch,如果try里面的代码出现异常，直接执行catch里面的代码
        }
//这里创建了ClassNotFoundException类的对象e,其父类是Exception类，祖父类是Throwabe类。（printStackTrace()方法是从Throwabe类继承，此方法将此 Throwable 对象的堆栈跟踪输出至错误输出流（打印出栈的轨迹））
```

#### 3.83 利用反射分许类的能力

* java.lang.reflect包的三大类：共有 **getName()方法**：返回项目的名称；**Modifier.toString(x.getModifiers)**:打印访问修饰符；
* **Class类**的**getDeclareFields()/getDeclareMethods()/getDeclaredConstructors()**方法，返回所有的**（私有+共有）域/方法/构造器数组**
  * **Field类**：描述类的域
    * **getType()**方法，返回*Class对象*，用以描述域所属类型，需要**+.getName**才能打印类型名称
  * **Constructor类**：描述类的构造器
    * **getParameterTypes()**方法，返回参数类型数组
  * **Method类**：描述类的方法
    * **getParameterTypes()**方法，返回参数类型数组
    * **getReturnType()**方法，获取返回类型
* 程序5-13例子

```java
package example5_13;
//打印出  public class 类名 extends 超类名 \n{\n public 类名 （参数，参数，参数）；


import java.lang.reflect.*;
import java.util.Scanner;

public class Reflectiontest {
    public static void main(String[] args) {
        String name;
        if (args.length > 0) {
            name = args[0];//检测命令行参数的字符串数组个数
        } else {
            Scanner sc = new Scanner(System.in);
            System.out.println("输入类名（java.lang.String）");
            name = sc.next();//输入类的名称
        }
        try {//检查异常
            Class<?> cl = Class.forName(name);//用forname创建Class类的实例cl(第2种方式)
            Class<?> supercl = cl.getSuperclass();//在用已经创造的实例cl直接（第1种方式）对象名.getSuperclass()，创造超类实例
            String s = Modifier.toString(cl.getModifiers());//获取访问修饰符并且转换为String类型，注意这是Modifier类的静态方法toString()
            if (s.length() > 0) {
                System.out.print(s + " ");
            }//这里用if检测s的长度来选择要不要输出s，因为访问修饰符可能那个是 ，那么就不必输出，省略一个步骤
            System.out.print("class " + name);
            if (cl != null && supercl != Object.class/*第3种方式，类名.class*/) {
                //先用if检测类的实例cl非null同时超类实例supercl不是Object类的实例（否则就没必要输出extends）
                System.out.print("extends " + supercl.getName());
            }
            //至此已经把 访问修饰符，class,类名，extends,超类名 都输出完毕.......................................

            System.out.print("\n{\n");//\n是换行符
            System.out.println("打印域");
            printFields(cl);
            System.out.println("打印构造器");
            printConstructor(cl);
            System.out.println("打印方法");
            printMethod(cl);

            System.out.println("}");
        } catch (ClassNotFoundException e) {
            e.printStackTrace();//idea自动添加了catch,如果try里面的代码出现异常，直接执行catch里面的代码
        }
    }


    public static void printConstructor(Class cl) {
        //打印出public 类名 （参数1，参数2，参数3）；
        Constructor[] Cons =cl.getDeclaredConstructors();//getDeclaredConstructors()是返回子类所有类型的构造器

        for (Constructor c : Cons
                ) {
            System.out.println("    ");
            String name = c.getName();//获取构造器的名字name。(前者是输入的name)
            String s = Modifier.toString(c.getModifiers());
            if (s.length() > 0) {
                System.out.print(s + " ");
            }
            System.out.print(name + "(");
            Class[] parameterTypes = c.getParameterTypes();//返回参数数组
            for (int i = 0; i < parameterTypes.length; i++) {//鉴于大括号里面还要嵌套if（），这里用fori
                if (i > 0) {
                    System.out.print(", ");
                }
                System.out.print(parameterTypes[i].getName());
            }
            System.out.println(");");
        }
    }


    public static void printMethod(Class cl) {
        // public  返回值类型 name ( 参数1，参数2，参数3 )
        Method[] m = cl.getDeclaredMethods();//返回这个类的全部方法
        for (Method ms : m
                ) {
            String name = ms.getName();
          78  Class<?> returnType = ms.getReturnType();//获取返回值类型
            String s = Modifier.toString(ms.getModifiers());
            System.out.println("    ");
            if (s.length() > 0) {
                System.out.print(s + " ");
            }
            System.out.print(returnType);//打印返回值类型
            System.out.print(name + "(");
            Class[] parameterTypes = ms.getParameterTypes();//返回参数数组
            for (int i = 0; i < parameterTypes.length; i++) {//鉴于大括号里面还要嵌套if（），这里用fori
                if (i > 0) {
                    System.out.print(", ");
                }
                System.out.print(parameterTypes[i].getName());
            }
            System.out.println(");");
        }
    }

    public static void printFields(Class cl) {
        //打印 privat String name;
        Field[] f = cl.getDeclaredFields();//返回这个类的所有域
        for (Field fs : f
                ) {
            String name = fs.getName();
            Class<?> type = fs.getType();//获取类型，类型.getName()才能打印
            System.out.println("    ");
            String s = Modifier.toString(fs.getModifiers());
            System.out.println("    ");
            if (s.length() > 0) {
                System.out.print(s + " ");
                System.out.println(type.getName() + " " + name + ";");
            }
        }
    }
}

```

* 5-13例子分析：

  **技术总结：**

  * 11行，用if检查是否在命令行输入了参数，如果>0，则将**数组第一个值args[0]赋值给name**，此时的args[0]就相当于程序开始运行时要输入的那个参数;否则就要程序在run之后自己通过手动输入参数。
  * 18行开始，用try...catch检查异常，**防止输入的类名name参数无效。**
  * 19行，用forName创建Class类对象，20行用Class类的**getSuperClass**获取超类的Class类对象
  * 21行，用Class类的**getModifiers()**获取public/protected/  /private的整型数值，在调用Modifier的静态方法toString输出字符串“public”/“protected”/“  ”/"private"
  * 22行，一个小技巧，鉴于" "的字符串长度为0，这里有个if检查s.length()，若是“ ”，则直接跳过｛ ｝中的输入内容
  * 26行,用if检查是否要输入“extends”,因为如果输入的类的超类是Object类的话就不必要输入“extends”了，这里直接将**超类的Class的supercl直接和Object.class比较**作为检测条件，注意这里用的是**==**比较运算符，直接比较对象地址（因为每个类只有一个Class类的对象，唯一性）。
  * 32行. **\n**是换行符，就和\t是等距空格符一样。
  * 49行，获取所有的构造器数组。54.**getName()**方法获取构造器名字（三大类共有的getName方法）。
  * 60行，构造器和方法类共有的getParameterTypes( )方法，返回参数类型的Class对象。需要getName()打印（**Class类对象的都需要getName打印**）。
  * 62行，小技巧，若怕打印输出是出现（,XXX,YYY,ZZZ）这样的情况，可以添加一个**if（i>0）｛sout“，”｝**,这样i=0的时候不会输出“，”。
  * 78行，**getReturnType()**，Method类特有的方法，返回返回值类型。
  * 103行，**getType()**,Field类特有，返回域的类型。

  **编程思想总结**

  * 此程序是分析类的能力，基本就是按照一定的格式把类名等信息以及的域、构造器、方法信息全部输出。涉及Class类的构造、使用；编写以及调用print方法；Field、Constructor、Method类的各个方法的调用；捕获异常的方法使用。

#### 3.84 运行时利用反射分析对象

* 利用反射可以查看在编译时还不清楚的对象（这就是动态），而指定的对象。查看对象的信息就是查看它的域（Field）以及域的类型

  ```java
  Employee e1 = new Employee("jack",1000);
  Employee e2 = new Employee("mary",1000);
  Class cl = e.getClass();
  Field f = cl.getDeclared("name")//返回指定域
  Object v1 = f.get(e1);//Filed类的get方法是获取域值，参数是要被获取的对象
  Object v2 = f.get(e2);//v2就是mary
  ```

* 这段演示代码有两个问题：

  * 1.**name是Employee的私有域**，正常只有用对象.getName方法才能获取它。这里会因为访问权限问题抛出IllegalAccessException。调用用三大类的setAccessibe()方法解决这个问题。如**f.setAccessibe(true)**; ( setAccessibe()属于AccessibleObject类，此是三大类的超类)

  * 2.数值类型（int,double...）**不是对象**，要用对象包装器转换成对象，如要f.getInt("jack");

    举例解决此两个问题

    ```java
    package example5_13;
    
    import java.lang.reflect.Field;
    import java.lang.reflect.Method;
    import java.lang.reflect.Modifier;
    
    public class test {
        public static void main(String[] args) throws NoSuchFieldException, IllegalAccessException {
            Student st1=new Student("xiaoming",12);
            Class cl = st1.getClass();
            Field f = cl.getDeclaredField("age");
            f.setAccessible(true);//设置打开访问权限
            Object o = f.getInt(st1);//f.getInt()应对基本类型，而非f.get
            System.out.println(o);
        }
    }
    ```

    程序5-14，5-15

    ```java
    package example5_14;
    
    import com.sun.jdi.Accessible;
    
    import java.lang.reflect.AccessibleObject;
    import java.lang.reflect.Array;
    import java.lang.reflect.Field;
    import java.lang.reflect.Modifier;
    import java.util.ArrayList;
    
    public class ObjectAnalyzerTest {
        public static void main(String[] args) {
            ArrayList<Integer> x = new ArrayList<>();
            for (int i = 1; i <= 5; i++) {
                x.add(i * i);
            }//测试集合对象
            String[] y = {"32", "3q", "er"};//测试数组对象
            int[] yy = {1, 23, 4, 5, 2, 0};
            String z = "sagfhwg";//测试字符串对象
            ObjectAnalyzer o = new ObjectAnalyzer();
            System.out.println(o.toString(x));
        }
    }
    
    class ObjectAnalyzer {
        private ArrayList<Object> visited = new ArrayList<>(); //类的声明里面已经将这个类型参数是Object的ArrayList类的名为visited的私有域赋值为一个空的数组列表。（域的赋值三种方法：1.类里面声明，如 private int x = 1; 2.构造器里面赋值 ；3.初始化块里面的赋值）
    
        public String toString(Object obj) {
            if (obj == null) {
                return null;
            }//第一步检测是否为null
            if (visited.contains(obj)) {
                return "此对象已经被包含在ObjectAnalyzer的数组列表中";
            }//第二步检测是否已经包含在数组列表中
            visited.add(obj);//前两个检测过后，将对象添加到visited中
            Class<?> cl = obj.getClass();
            if (cl == String.class) {
                return (String) obj;//(string)obj：前提条件——obj中必须是string变量的内容（如String x = "123",这里的x），如果是其它的出错。而toString所有的类都可以用
            }
            //下面就是检测是否是数组对象，是数组的话直接打印其包含的数据们
            if (cl.isArray()) {//调用Class类的isArray方法
                Class<?> type = cl.getComponentType();//返回类型（int/String/Employee...）
                String r = type + "[]" + "{";//拼接字符串
                for (int i = 0; i < Array.getLength(obj); i++) {
                    if (i > 0) {
                        r += ",";
                    }
                    Object o = Array.get(obj, i);
                    if (cl.getComponentType().isPrimitive()) {//判断是否为基本类型，true的话可以直接拼接
                        r += o;
                    } else {
                        r += toString(o);//这个toString方法是继承的Object的那个
                    }
    
                }
                System.out.println(r + "}");
    
            }
            //以下代码是针对非Array类的对象，要输出此类和它的超类们的所有信息，例子用的是do...while循环，好处先运行一次在进行检测，循环条件是如果此类没有超类，那么就终止循环
            String r = cl.getName();//存疑
            //System.out.println(name);
            do {
                r += "[";
                Field[] fs = cl.getDeclaredFields();
                AccessibleObject.setAccessible(fs, true);//关键步骤，用reflection包里的AccessibleObject类的静态方法SetAccessible()来让fs域组里面所有域开放访问权限。
                for (Field f : fs) {
                    if (!Modifier.isStatic(f.getModifiers())) {//这一步筛掉所有的静态域，静态域存在于类中但是不直接属于对象
                        String s = f.getName()+"=";//这里f.getName返回的域名就是value
                        r += s;
                        try {
                            Class<?> t = f.getType();//返回类型,检测用
                            Object o = f.get(obj);//返回对象obj的域值，这里必须要用try..catch防止异常
                            if (t.isPrimitive()) {//检测是否为基本类型
                                r += o;
                            } else {
                                r += toString(o);
                            }
                        } catch (IllegalAccessException e) {
                            e.printStackTrace();
                        }
                    }
                }
                r += "]";
                cl = cl.getSuperclass();//子类已经循环过一次了，把子类变成自己的超类，作为检测循环的条件
            } while (cl != null);
    
    
            return r;//这个方法很精简，从头到尾都是r+=...,这样return r就行了
        }
    }
    ```

    **技术总结:** 

    * 26行,此处定义新建ObjectAnalyzer类的私有域visited是一个类型参数为Object类的数组列表对象变量,并且引用了一个对象;
    * 29-35行,上来先用If分别检查Object参数obj**是否为null&&是否已经包含在visited**里面了;然后再将obj添加到visited里面;
    * 37行,要点:如果obj的是String类的话,直接可以将obj输出, 这里是return **(String) obj** ;
    *  41行,调用Class类的**isArray()**方法,判断是否为数组;
    * 42行,Class类方法**getComponentType()**返回数组类型;
    * 44行,因为代码的动态性,如果输入的对象参数是数组对象的话,调用Array.getLength()获取长度;

    * 46行.一个技巧,直接**r+=...**就行拼接字符串,到时候直接返回r就行,让代码更加简洁;
    * 49行,用if检查是否是基本类型,**Class类的isPrimitive()方法**
    * 62行,此处用的是do...while循环,好处是先让代码运行一次,后面在用while检测是否继续循环
    * 65行,鉴于后面代码要获取输入对象的域值,此处先用AccessibleObject.setAccessible(fs, true);打开访问权限,让public/private域都可以获取
    * 72行,**三大类的.get()**直接获取域值,(前提是已经开放权限),并且此处必须要进行异常处理
    * 84,85行关键步骤,将cl转变成超类的Class对象,在进行while检测是否为null,true则继续循环,输出超类的信息,false则终止循环;

    **思想总结**

  * 在ObjectAnalyzerTest中,是将赋值好的数组列表对象作为参数输入toString方法里面,就像上个例子是把cl当作参数,想获取谁的信息就把谁当作参数;

#### 3.84用java.lang.reflect包中Array类动态创建数组

```java
package example5_16;

import java.lang.reflect.Array;
import java.util.Arrays;

public class TestNewArray {
    public static void main(String[] args) {
        int[] a = {0, 12, 3, 4, 455, 67, 78};
        a = (int[]) copyArray(a, 3);//强制类型转换,将Object类的元素(实际是个数组)再转换成数组
        System.out.println(Arrays.toString(a));
    }

    public static Object copyArray(Object a, int newLength) {/*注意这里都是Object而非Object[],比如int[]不是Object[]但是一定是Object*/
        Class<? extends Object> cl = a.getClass();
        if (!cl.isArray()) {
            return null;//返回null,
        }
        Class<?> type = cl.getComponentType();//1.获取类型
        int length = Array.getLength(a);//2.获取长度
        Object newArray = Array.newInstance(type, length);//根据获取的1.类型/2.长度信息调用Array.newInstance创建新的数组对象(对象变量的类型是Object,多态特性)
        System.arraycopy(a, 0, newArray, 0, Math.min(length, newLength));//Math的min方法,取两个参数较小的那个
        return newArray;
    }
}
```

技术总结:

* 20行,最关键的是Array的静态方法**newInstance**构建新数组,参数分别为:(数组类型,新数组长度);
* 9行,关键步骤,定义新方法的时候,返回对象必须是Object,而不能是Object[],因为前者是数组的超类,可以利用多态的特性,在第9行可以将其强制转换成int [];

#### 3.85 用反射调用方法

```Java
package example5_17;

import example4_5.Employee;

import java.lang.reflect.InvocationTargetException;
import java.lang.reflect.Method;

public class MethodInvoke {
    public static void main(String[] args) throws NoSuchMethodException, InvocationTargetException, IllegalAccessException {
        Employee jack = new Employee("jack", 1000);
        int x =10;
        String g ="cesjhi00";
        Class<Employee> cl = Employee.class;
        Method m = cl.getMethod("testfor5_17", int.class, String.class);//用Method类的m引用获取Employee类的方法
        Integer iii = (Integer) m.invoke(jack,x,g);//对象,参数1,参数2...
        System.out.println(iii);

    }
}
-------------------------------------------------------------------------------------
public int testfor5_17(int x, String y) {
        x += 3;
        System.out.println(y);
        return x;
    }//Employee类的方法
```



## 4.接口,lambda表达式

### 4.1 接口

#### 4.1.1 概念与定义方式

* 概念:接口是区别于继承的第二种多态类型,**类只能有一个父类(extends)**,但是**可以有多个接口(interface)**,接口让单链的继承树长出分叉.接口类似100%纯天然抽象类(制定了一种或者多种规则,需要子类去实现这些规则)
  * 接口是对类的一组需求描述.这些类要遵循接口描述的**统一格式进行定义**.
  * 接口与接口之间是继承关系
* 定义的注意事项:
  * 将class改成interface,要实现接口的类添加implements
  * 接口中所以的**方法都是必然是public**,所以可以不写public. 用类实现接口的时候,方法必须是public
  * 接口可以有多个方法,但是**绝对不能有实例域**(只能是常量,默认public static final)

```java
package com.ycx.example6_1;

import java.util.Arrays;

public class InterfaceTest {
    public static void main(String[] args) {

        Employee[] staff =new Employee[5];
        staff[0]=new Employee("jack",3427);
        staff[1]=new Employee("mike",1224);
        staff[2]=new Employee("bob",2313);
        staff[3]=new Employee("max",2223);
        staff[4]=new Employee("mary",1613);


        Arrays.sort(staff);

        for (Employee e:staff
             ) {
            System.out.println(e.getName()+e.getSalary());
        }
    }

}

class Employee implements Comparable<Employee>{//实现接口的对象的类
    private String name;
    private double salary;

    public Employee(String name, double salary) {
        this.name = name;
        this.salary = salary;

    }

    public Employee(){

    }

    public String getName() {
        return name;
    }

    public void setName(String name) {
        this.name = name;
    }

    public double getSalary() {
        return salary;
    }

    public void setSalary(double salary) {
        this.salary = salary;
    }

    public void rasise(double byPercent){
        salary*=(byPercent/100+1);
    }

public int  compareTo(Employee x  ){
        return Double.compare(salary,x.salary);//实现了Comparable接口的compareTo方法
    }
}

```

#### 4.1.2接口的特性

* 接口**无法被实例化**(和抽象类一样);
* **可以声明接口的变量接收实现了接口类的对象**, 比如 Chinese c = new Employee(); (这里Chinese是接口,Employee是实现了接口的类),此处也是类似多态的特性
* 可以用**Instanof**检查**==对象==是否实现了某个接口**
* 接口可以**扩展**.如 public interface x extends y;
* 接口中不能有静态方法(Javase8之后有),实例域.但是可以有**常量**,(自动被设置为public static final)

####  4.1.3 接口的默认方法

* 引入接口的概念的原因:一个类不能扩展两个超类(儿子不能有两个父亲),接口可以有多个
* default方法:
  * 在接口内,**有方法体**. 无需在实现类中去定义.(格式是直接在返回值类型前面+default,如default void...)
  * 默认方法可以调用任何其他的方法(如本接口里面的抽象方法)
  * 默认方法的"**接口演化功能**":如果接口中新增加的是非默认方法,那么接口的实现类都要再一次实现这个方法(无法保证源代码兼容). 但是如果新增加的是默认方法,实现类,们就不必全部修改,想覆盖时就覆盖即可
* **default方法冲突**的两规则:
  * 造成冲突的原因:在接口中定义了默认方法,但是在超类/另一个接口中定义了同样的默认方法.(因为两个一样的默认方法都被实现类继承下来了)
  * 1.两个接口中的其中一个提供了默认方法,另一个提供了一样的方法(无论是不是默认),**子类都必须覆盖掉这个方法**
  * 2.超类如果提供了一个具体方法,接口的默认方法就会被忽略(**超类优先**)

##### 4.1.3.1接口中的静态方法(JDK8),私有方法(JDK9)

* **接口中的静态方法**只能通过接口名.静态方法名使用(调用更加简洁)

* **接口中的private方法**,只供接口自己使用(在默认/静态方法中调用,减少相同代码的重复)

#### 4.14 抽象类与接口的共同点以及区别?

* 共同点:
  * 本质上都是抽象的,都是无法被实例化
  * 都需要其他类去继承/实现抽象方法
  * 都可以创建对象变量引用子类
  * 目的相同:都是为了标记多态
  * 接口和抽象类都是可以继续用extends扩展
* 不同点:
  * 接口是纯抽象类,不可以有非抽象方法(JavaSE8之后有静态方法),而抽象类可以有非抽象方法
  * 一个类可以实现多个接口(多继承),但是只能继承一个抽象类(单继承)
  * 抽象类里面可以有default方法,以应对接口演化
  * 接口中不能有实例域,但是可以有常量
  * 抽象类有构造器,接口不能声明构造器

### 4.2 对象克隆

* 概念:克隆一个新的对象(新的内存地址),初始状态和原克隆对象相同,但是之后有自己状态

* 注意事项:clone是Object类的**protected**方法(protected表示被其修饰的成员可以被==本类==, ==同包下的所有类==, 以及==本类的所有子类==所访问)

  * 如果对象的域都是**基本类型**,直接拷贝没有问题
  * **如果对象包含对子对象的引用,**克隆后的对象就和原对象共享引用

* **浅拷贝**:

  * **默认克隆操作是浅拷贝**,并没有克隆对象中引用的其他对象
  * 浅拷贝注意:如果是共享的对象是不可变的,如String,那么就是安全的

* **深拷贝**:

  * 通常子对象都是可变的,必须覆盖clone方法来建立深拷贝,同时克隆所有的域中的对象(被共享的)

  * 1.实现**Cloneabl接口**

    2.重新定义clone方法,并且是public

### 4.3 lambda表达式

#### 4.31 函数式接口

* **只有一个抽象方法的接口(这句话就是lambda表达式得前提：有一个接口；接口里面有且仅有一个抽象方法)**,就是函数式接口.需要这种接口的对象时,就可以提供lambda表达式.lambda表达式更像一个函数,而非一个对象
* lambda表达式是**一段可传递的代码块**, 格式:  ==（参数）-> {方法体}==
  * 编译器可以推导出参数类型/返回值类型
  * lambda表达式如果有if检查,那么If每个分支都要有返回值
  * lambda表达式可以转换成接口

```java
package com.AdvancedCode.Day04;

public class LambdaTest {
    public static void main(String[] args) {
        useShowHandler((iii) ->
                {
                    System.out.println("我是lambda表达式");
                    return iii;
                }
        );//这个;是方法的终结
    }

    public static void useShowHandler(ShowHandler x) {
        int shownum = x.show(9999);
        System.out.println(shownum+"from测试类中的静态方法");
    }


    interface ShowHandler {
        int show(int i);
    }
}
```

* lambda表达式**省略写法**:
  * { } 里面只有一条语句的话,可以省略{ };
  * 参数类型可以省略. 如果只有一个参数,( )都可以省略
  * 如果只有return这一条语句的话,return也可以省略

#### 4.32 构造器的引用

#### 4.33 构造器的引用

#### 4.34 变量的作用域

#### 4.44 处理Lambda表达式

### 4.4 内部类

#### 4.41概念和定义方式

* 内部类(Nested Class),定义在类内部的类，正常一个包里面的类是平级关系。

* 内部类的三种形式：

  * ==1.Innner Class==(成员内部类):直接定义在类的内部，它的**实例必须依附于外部类的实例存在**，不可单独存在.内部类的特权在于:**可以修改外部类的私有域**,如下例所示:

  * 成员内部类不能有静态成员
  
    ```java
    package com.Ycx2;
    
    public class InnerClassTest {
        public static void main(String[] args) {
            OuterClass x1 =new OuterClass();//先实例化一个外部类对象
    
            OuterClass.InnerClass x2 =x1.new InnerClass();//通过外部类对象创建内部类对象,注意格式
            x2.show();
        }
    }
    
    class  OuterClass{
        private int id1;
    
        public void show (){
            System.out.println("外部类");
        }
        class InnerClass{
            private int id2;
    
            public void show(){
                System.out.println("内部类");
                id1=2333;
                System.out.println(id1);//内部类可以方位词外部类的私有域
            }
        }
    }
    ```

    * **==私有内部类==:private class InnerClass调用方法的步骤:**
  
      * 1.先在**外部类的方法m**中**创建私有内部类对象x**(private可以在本类中被调用)，用**内部类对象调用内部类方法n**.
      * 2.在测试类中**创建外部类对象y**，调用**m方法,*，达到间接访问私有内部类方法n的目的
  
      ```java
      package com.AdvancedCode.Day04;
      
      public class InnerClassTest {
          public static void main(String[] args) {
          outerclass o =new outerclass();//创建外边类对象,再调用方法,间接调用私有内部类的方法m
           o.m2();
          }
      }
      
      class outerclass {
          private class innerclass {
              public void m() {
                  System.out.println("私有内部类的调用举例");
              }
          }
      
          public void m2() {//在外边类里面创建内部类对象
              innerclass x = new innerclass();
              x.m();
          }
      }
      ```
  
* ==**2.匿名类(Anonymous Class)***==:

  * 匿名类的概念：接口不可以被实例化，只能通过定义其方法被实现。此处可以**通过定义匿名类，直接实现接口**(简单格式,无需通过传统方式定义类,无需取名)
  * 格式：new 类名/接口名( ){  重写方法   }；如下列所示：

  ```java
  package com.AdvancedCode.Day04;
  
  public class AnonymousTest {
      public static void main(String[] args) {
          m(new Robot() {
                @Override
                public void bark() {
                    System.out.println("补充方法体");
                }
            }
          );
      }
  
      public static void m(Robot x) {
          x.bark();
      }
  }
  
  interface Robot {
      void bark();
  }
  
  ```

  * 接口中存在多个方法时：让**接口变量引用匿名类**（让它有名字），再用变量调用方法

  ```java
    package com.Ycx2;
    
    public class AnonymousClassTest {
        public static void main(String[] args) {
            outerclass x1= new outerclass("外部类");
            x1.testAnonymousTest();//相当于直接调用方法(匿名类在方法里面)
        }
    }
    
    class outerclass {
        private String name;
    
        public outerclass(String name) {
            this.name = name;
        }
    
        void testAnonymousTest() {
            Runnable r = new Runnable() {//表面上看上去没有class，其实是有匿名内部类，被大幅简化了而已
                @Override
                public void run() {
                  System.out.println("匿名类覆盖run方法");
                }
            };//此处直接创建了匿名了实现了Runnable接口,再将此匿名类实例化,少些很多代码
        }
    }
  ```

    * **局部内部类**:在外部类的方法里面的类

      * 1.要在外**部类方法的里面创建内部类对象(因为在外部类方法的里面)，**并且调用内部类的方法
      * 2.在测试类中的部分和私有内部类一致的，都是创建外部类对象，调用方法
    * 
  
      ```java
      package com.AdvancedCode.Day04;
      
      public class InnerClassTest {
          public static void main(String[] args) {
              outerclass o = new outerclass();//这部分和私有内部类方法一致
              o.m2();
          }
      }
      
      class outerclass {
          public void m2() {
              class inner {
                  public void m1() {
                      System.out.println("调用局部内部类");
                  }
              }
              inner x = new inner();//创建内部类对象,也是在外部类方法的里面（方法里面！）
              x.m1();
          }
      }
      ```
    ```
  
    ```
  
* ==3.静态内部类(Static Nested Class)==:与Inner Class不同,静态内部类是完全独立的，**不需要依赖外部类的实例**，同时能访问外部类的静态域和静态方法(==只有内部类可以声明static==)
  
    * ***外部类名.内部类名 x = new 外部类名.内部类名( );***
    
      **x.m1( ); // 静态内部类调用普通方法**
    
      **外部类名.内部类名.m2();// 静态内部类调用静态方法**(idea里面一路 类名. )
    
    ```java
    package com.Ycx2;
    
    public class StaticNestedClass {
        public static void main(String[] args) {
            OuterClass2.StaticNested s = new OuterClass2.StaticNested();
            s.show();//调用的时候不需要外部类的实例
        }
    }
    
    class OuterClass2 {
        private static String name = "-静态域-";
    
        static class StaticNested {
          public void show() {
                System.out.println("静态内部类可以访问" + name);
            }//可以访问外部类的静态域,私有域
        }
    }
    ```
    
    ```java
    package com.ycx.example6_9;
    
    import java.util.Arrays;
    import java.util.Random;
    
    public class TestStaticInnerClass {
        public static void main(String[] args) {
            int[] arr = new int[20];
            Random r = new Random();
            for (int i = 0; i < arr.length; i++) {
                arr[i] = r.nextInt(1000);
            }
            System.out.println(Arrays.toString(arr));
            
            OutClass.pair p = OutClass.MinMax(arr);//通过外部类的类名直接调用静态方法
            System.out.println("最小值="+p.getX());
            System.out.println("最大值="+p.getY());
        }
    }
    
    class OutClass {
        public static class pair {
            private int x;
            private int y;
    
            public pair(int x, int y) {
                this.x = x;
                this.y = y;
            }
    
            public int getX() {
                return x;
            }
    
            public int getY() {
                return y;
            }
        }
    
        public static pair MinMax(int[] x) {
            int min =Integer.MAX_VALUE;
            int max =Integer.MIN_VALUE;
            for (int v:x
                 ) {
                if(v>max){max=v;}
                if(v<min){min=v;}
            }
            return new pair(min,max);//把min/max变成匿名对象的域值
        }
    
    }
    ```

#### 4.42内部类的好处:

* 可以直接访问外部类的私有数据(外部类想访问内部类的域就需要先创建内部类的对象了)
* 隐藏同一个包里面的类
* 匿名的内部类可以减少很多代码

### 4.4 代理

//后面学习

## 5. 异常,断言,日志

###  5.1异常概述和分类

* Java的异常对象都是派生于Throwable类的实例,分为下列子类:
  * Error是虚拟机无法解决的问题:JVM内部错误,资源耗尽等问题,不用代码去解决
  * Exception是运行时候的错误,可以被捕获并处理,分为两大类:
    * **RuntimeException**以及它的子类**(非受查异常(unchecked)),无需强制捕获**
    * ==**非RuntimeException**,(IOException,ReflectiveOperationException)(**受查异常(checked)**)==

### 5.2处理异常的方式

* ==**抛-抓**==模型: 程序正常运行时,一旦出现异常,会在异常代码处**生成对应异常类的对象**,并将此对象抛出;**两个抓:**
  * 1.try-catch-fianlly  ;
  * 2.throws+异常类型

#### 5.21 .try-catch-fianlly 捕获异常的方法细节

* (易解决的异常),**try{可能出现的异常代码...} catch(异常类型,变量名...){处理方式...}finally{ 一定会执行的代码...}**捕获异常,注意事项:

  * ==catch(){}可叠加== ,跳出trycatch结构之后的代码可以继续进行.在catch叠加的时候,如果出现异常有继承关系的时候,要注意顺序,**超类的异常对象要在子类异常的下面。**

  * finally的问题:

    * finally可以选择添加或者不添加,有点类似if判断里面的else{}

    * **finally里面的代码一定会被执行**,正常是catch里面语句执行完就执行finally,==哪怕是try里面是有return语句,finally里面的内容依旧会执行==
    * finally可以用于恰当地**结束数据库的连接**

  ```java
  package com.Ycx2;
  
  import java.util.Scanner;
  
  public class TE {
      public static void main(String[] args) {
          int [] arr ={1,2,3,4,5,6,7};
          Scanner sc = new Scanner(System.in);
          int i = sc.nextInt();
          try {
          System.out.println(arr[i]);
          }catch (IndexOutOfBoundsException e){
              System.out.println("索引越界");
              System.out.println(e.getMessage());//也可以添加getMessage()方法对错误信息进行String类返回  
          }finally {
              System.out.println("finally一定会被执行,无论是catch里面再次出现异常,还是try中的代码有return等语句");
      }
  }
  ```

#### 5.22 throws+异常类型的注意事项

* (难以解决的异常),在方法处throw+异常类型(写在方法声明处),受查异常,如果不是在**==调用层==捕获**,也要在**更高的调用层捕获**,相当于不断往上汇报,异常后续的代码不会执行了.
* 往上抛出异常之后,要在更高的调用层将其处理. **throws本身不会将异常处理掉(区别于try catch真正的处理异常)**
* **子类覆盖超类方法**的时候,这个方法抛出的异常类继承层级要低于低于超类方法的异常类

```java
package com.Ycx2;

import java.util.Scanner;

public class TE {
    public static void main(String[] args) {
        try {
            m1();//在上层捕获下层抛出的异常,并用try catch解决
        } catch (IndexOutOfBoundsException e) {
            System.out.println("在上层捕获");
        }
    }
    private static void m1() {
        m2();
    }

    private static void m2() throws IndexOutOfBoundsException {//将异常抛出
        int[] arr = {1, 2, 3, 4, 5, 6, 7};
        Scanner sc = new Scanner(System.in);
        int i = sc.nextInt();
        System.out.println(arr[i]);
    }
}
```

#### 5.23 处理异常方式的选择

* (**覆盖方法**的情况):超类被覆盖的方法没有throws异常,子类也不能throws,必须用try-catch-finally
* 几个方法**递进**(其他方法里面调用了这个方法)的情况:其他方法throws异常,递进的源头方法用try-catch-finally 

#### 5.24 手动抛出异常(throw),自定义异常类

* 手动抛出异常就是自己设置异常类: 格式是 throw new 异常类型;

```java
package com.Ycx2;

public class TE {
    public static void main(String[] args) {
        s s1 = new s();
        try {
            s1.m(11);
        } catch (java.lang.Exception e) {
            System.out.println(e.getMessage());
            System.out.println("过程就是手动抛出-throws捕获-trycatch处理");
        }
    }
}

class s {
    private int age;

    public void m(int id) throws java.lang.Exception {//在方法的声明上捕获异常
        if (id > 100) {
            throw new java.lang.Exception("这里就是message,可以直接在此处输入");//手动抛出异常
        } else {
            System.out.println(id);
        }
    }
}
```

* 自定义异常类
  * 继承Java已有的异常类
  * 提供全局常量(唯一序列码):static fianl long serialVersionUID =.............
  * 创建构造器:也是调用超类的构造器

```java
package com.Ycx2.YiChang;

public class EcmDef {
    public static void main(String[] args) {
        try {
            int x = Integer.parseInt(args[0]);
            int y = Integer.parseInt(args[1]);//将String类型的命令行参数转成int
            m(x, y);
        } catch (NumberFormatException e) {
            System.out.println("数据类型不一致");
        } catch (ArrayIndexOutOfBoundsException e) {
            System.out.println("缺少命令行参数");
        } catch (VException e) {//捕获异常并且反馈
            System.out.println(e.getMessage());//因继承了超类的getMessage方法
        } catch (ArithmeticException e) {
            System.out.println("除以0异常");
        }
    }

    public static void m(int x, int y) throws VException {//此处将自己创建的异常抛出
        double v = x / y;
        if (x < 0 || y < 0) {
            throw new VException("负数异常");//因调用了超类的构造器
        } else {
            System.out.println(v);
        }

    }
}

//创建自己的异常类
class VException extends java.lang.Exception {//1.继承已有的Exception
    static final long serialVersionUID = -3387516993124223219L;//2.确定序列码

    public VException(String message) {
        super(message);//3.创建构造器,这里是调用超类构造器,注意格式
    }

}
```

###  5.3 常见的异常

* NulllPointerException: 调用一个是null的对象的方法/域,就会出现此异常. 变量定义时为其初始化赋值,如 String s =" "; 能比较好处理该问题

### 5.4 断言

### 5.5 日志

#### 5.5.1 Log4j

* **优点**
  * 控制输出日志信息的目的地：==ConsloeAppender / FileAppender==
  * 控制日志信息输出格式：==Layouts：PatternLayout（灵活设置格式，最为常用）==
  * 控制输出级别：==Loggers :DEBUG<INFO<WARN<ERROR<FATA== （输出日志信息不能低于设定的级别）
  * 通过配置文件灵活配置

```java
package Day20Test;

import org.slf4j.Logger;
import org.slf4j.LoggerFactory;

public class Log4jTest1 {
    private static final Logger LOGGER = LoggerFactory.getLogger(Log4jTest1.class);

    public static void main(String[] args) {
        LOGGER.debug("这是debug");
        LOGGER.warn("这是warn");
        LOGGER.info("这是info");
        LOGGER.error("这是error");
    }
}
```

* **使用步骤：**
  * 导入jar文件
  * 在src文件中导入porperties文件
  * 在代码中创建日志对象
  * 记录日志信息，注意按照级别

```java
package Day20Test;

import org.slf4j.Logger;
import org.slf4j.LoggerFactory;
import java.util.Scanner;

public class Log4jTest1 {
    private static final Logger LOGGER = LoggerFactory.getLogger(Log4jTest1.class);

    public static void main(String[] args) {
        Scanner sc = new Scanner(System.in);
        String s = sc.nextLine();
        try {
            int i = Integer.parseInt(s);
            LOGGER.info("正确" + i);
        } catch (NumberFormatException e) {
            LOGGER.info("输入的类型不正确");
        }
    }
}
```

### 5.6日志技术汇总学习

* 

## 6.常用API总结

### 6.1 String/StringBuilder

* **String类**: **==打印String对象,直接出现内容==,而非内存地址**

  * 注意next()和nextline()的区别:next()遇到空格(结束标记)就不再录入了,nextline()可以遇空格,结束标记是回车键()注意println冲突.

  * 字符串的值不可以被改变

  * 字符串常量池,两个相同字符串地址值一样. ( 常量池(JDK7之后转移到了堆内存),静态域都在内存里面的方法区中)

  * String类的常见构造方法(区别于直接"xxx"创建):

    ```java
    package com.YuChenXi.day09;
    
    public class Practice {
        public static void main(String[] args) {
            String s1 =new String("123");//通过构造方法创建
            System.out.println(s1);
    
            char [] arr ={'1','2','4'};//通过字符数组创建
            String s2 =new String(arr);
            System.out.println(s2);
        }
    }
    
    //构造方法创建区别于直接双引号""创建的区别:直接""回把字符串放进常量池,内容相同的字符串,地址值相同; 构造方法创建的字符串就和普通对象一样,每个new地址都不同
         
    		String s1 =new String("123");//通过构造方法创建,存储在堆内存
            String s2 =new String("123");
            System.out.println(s1==s2);//输出false
    
            String s5 ="good";//""直接创建.存储在字符串常量池
            String s6="good";
            System.out.println(s5==s6);//输出true
    ------------------------------------------------------------------
    String x =new String("aaa");//其实创建了两个对象,常量池一个,new一个
    
    String y ="sss";
    String z =new String("sss")//这句话只创建了一个对象,因为"sss"已经存在于常量池了
    ```

  * 两个以上字符串相加时候,也存在优化机制(预编译时+会被优化),相当于==几个字符串**常量**("abc"+"def")自动合成一个字符串常量==,==是true

  * **equals方法**:比的是字符串的内容(String类把Object类的equals方法覆盖了)

  * substring/replace/endswith/toCharArray/ **x.split**(",");//以输入的内容分割字符串(正则表达式冲突的字符需要"\\\\"转译)    **split( )切割方法从切割得到的数据,从最后一个空字符串" "开始就舍弃,之前的会保留**

* **StringBuilder类**:==字符串**变量**拼接的时候(如: s1+"abc" )==,自动会创建StringBuilder对象,用append方法,再调用toString方法转换,==是false

  *  StringBuilder的append()方法可以提高字符串拼接效率,只在一个对象完成,**可以将任意数据类型拼接为字符串**
  *  StringBuilder本质是容器,返回的是它自己(**链式编程**:一个方法返回的是对象类型,对象可以继续向下调用方法)
  *  直接打印StringBuilder也是字符串(覆盖了toString()), **new StringBuilder(s)**,直接把String对象转换成StringBuilder对象 
  *  reverse()/length()/toString()

* **StringBuffer类**:安全效率更高(加锁,线程)

### 6.2 Math类

* 注意事项:Math类没有构造器,里面的全都是静态方法( **其实是编写类的时候直接把构造方法私有化了**),通过==Math.==调用

* Math.abs: 取绝对值

* Math.ceil:向上取整; Math.floor:向下取整

* Math.round:四舍五入

* Math.max( int a ,int b ): 返回两个数里面较大的

* Math.min( int a ,int b ): 返回两个数里面较小的

* Math.pow( double a, double b): 返回a的b次方 (double)

* Math.random( ) : 在JavaCore1中遇到过,返回[ 0.0 -  1.0 ) 中随机的double正值,如 0.3456763245667

  ```java
  public class Test {
      public static void main(String[] args) {  //[a,b]范围的取值方式
          int a =1;
          int b =10;
          int random = (int) (Math.random()*(b-a+1)+(a));
          System.out.println(random);
      }
  }
  ```

### 6.3 System类

* 没有构造器,里面的全都是静态方法
* System.exit( ) : 填写0的话就是直接终止虚拟机运行
* System.currentTimeMillis( ) :返回**当前**时间,但是是以毫秒形式存在的

* Sysytem.arraycopy( ) ：将一个数组的元素拷贝到另一个数组里面

### 6.4 Objects类

* 没有构造器,里面的全都是静态方法
* Objects.toString( 对象名, nullDefault ):==这个toString方法哪怕对象引用是null也会打印出内容. 内容就是 nullDefault处输入的内容==.
* Objects.isNull( ):判断一个对象是否为null   (Objects.nonNull( ):  反过来判断)

### 6.5 BigDecimal类

* 用以大数据精准运算(==若想要进行精确计算,要使用字符串构造==),可创建对象,用对象调用方法
* X.add(Y) :两个BigDecimal类对象的加法运算 ,如果直接使用数字构造的话,就会出现小数点后面很多位不精确的情况，**最好用字符串构造**
* X.subtracr/multiply/divide(Y) ;//减 乘 除
* **divide( Y , 精确位数 ,舍入模式 ) :其中舍入模式输入的内容是BigDecimal类的常量**,除不尽就用这个方法
  * 舍入模式（常量）：==BigDecimal.ROUND_UP  /FLOOR  /HALF_UP...==(进一/去尾/四舍五入)

### 6.6 Arrays类

* 没有构造器,里面的全都是静态方法
* Arrays.toString( )
* Arrays.sort( )
* Arrays.binarySearch( arr , x ):二分法查找数组元素 ( 如果x不存在,那么返回的值就是**x应该存在的位置的负数-1**)

### 6.7Date时间日期类

* （java.util.Date）Date( )的两个方法：

  * **toString**:显示当前的时间
  * **getTime**:距离1970.1.1.0.0.0到现在的毫秒数
  * Date(655646864)构造器：输入的参数是毫秒数，会转换成日期

* (java.sql.Date)  Date类，是对应**数据库里面的Date**

  * 实例化方法：

    ```java
    java.sql.Date x =new java.sql.Date(3406441635545L);
    System.out.println(x);//实例化方法，输入数字，直接输出的就是距离1970的日期（2077-12-11）
    ```

  * 将java.sql.Date（子类）对象转成java.util.Date（父类）的方法：利用多态强行转换

  * 将java.util.Date（父类）对象转成java.sql.Date（子类）的方法：

    ```java
    Date a =new Date();
    java.sql.Date x =new java.sql.Date(a.getTime());
    System.out.println(x);//就是此时此刻的日期
    ```

* SimpleDateFormat类

  * 将日期Date()转换成字符串
  * 将字符串转换成日期Date()

  ```java
  package com.AdvancedCode.Day05;
  
  import java.text.ParseException;
  import java.text.SimpleDateFormat;
  import java.util.Date;
  
  public class Test {
      public static void main(String[] args) throws ParseException {//这里会抛出异常
          SimpleDateFormat x =new SimpleDateFormat();
          Date date = new Date();
          System.out.println(date);//Thu Jun 10 19:55:27 CST 2021
  
          String s = x.format(date);
          System.out.println(s);//2021/6/10 下午7:55  (格式化之后的格式)
  
          Date parse = x.parse("2077/9/10 下午8:21");
          System.out.println(parse);//Fri Sep 10 20:21:00 CST 2077  (将字符串解析成Date类对象)
  
      }
  }
  ```

* Calendar日历类

  * 实例化方法:Calendar.getInstance();
  * 常用方法:get/set/add(更改后自己也变了,有可变性)

* **JDK8中的日期API(常用)**

  * LocalDate

  * LocalTime

  * **LocalDateTime(不可变性,改变的是返回值)**

    ```java
    package com.AdvancedCode.Day05;
    
    import java.text.ParseException;
    import java.time.LocalDate;
    import java.time.LocalDateTime;
    import java.time.LocalTime;
    
    public class Test {
        public static void main(String[] args) throws ParseException {
            LocalDate localDate = LocalDate.now();
            LocalTime localTime = LocalTime.now();
            LocalDateTime localDateTime = LocalDateTime.now();
            System.out.println(localDate);
            System.out.println(localTime);
            System.out.println(localDateTime);
    
            LocalDateTime time = localDateTime.of(2020, 9, 9, 12, 11, 12);//设置指定时间
            System.out.println(time);
            System.out.println("---------------------------------");
            System.out.println(localDateTime.getDayOfMonth());
            System.out.println(localDateTime.getDayOfWeek());
            System.out.println(localDateTime.getDayOfYear());
            System.out.println(localDateTime.getMonth());
            System.out.println(localDateTime.getMonthValue());
            System.out.println(localDateTime.getMinute());
            System.out.println("---------------------------------");
            System.out.println(localDateTime.withHour(5));
            System.out.println(localDateTime.plusMonths(3));//增加
            System.out.println("---------------------------------");
            System.out.println(localDateTime.minusMonths(4));//减少
        }
    }
    ```

* Instant类:时间线上的瞬时点(类似于Date类)

  ```java
  package com.AdvancedCode.Day05;
  
  import java.time.Instant;
  import java.time.OffsetDateTime;
  import java.time.ZoneOffset;
  
  public class Test {
      public static void main(String[] args)  {
          Instant i = Instant.now();
          System.out.println(i);//获取本初子午线标准时间
  //------------------------------------------------------
          ZoneOffset z = ZoneOffset.ofHours(8);//时区+8小时
          OffsetDateTime izc = i.atOffset(z);
          System.out.println(izc);
  //------------------------------------------------------
          Instant X = Instant.ofEpochMilli(2134543667456L);//通过给定毫秒数获取Instant实例
          System.out.println(X);
      }
  }
  ```

  

## 7. 集合

### 7.1 Collection接口（单列）

* 单列集合，储存一个个的对象。放入自定义类对象之前要==重写自定义类的equals方法==（方便remove（）等方法进行操作、Set类进行比较）
* Collection常用方法如下所示
* 集合转换成数组: **toArray**( )方法:例如：list.toArray(new String[0])；//长度为0的数组，不能存储也不能取出
* 数组转换为集合: **Arrays.asList**( 数组名 )方法

```java
package com.AdvancedCode.Day07JiHe;
import java.util.ArrayList;
import java.util.Collection;
public class CollectionTest {
    public static void main(String[] args) {
        Collection co = new ArrayList();
        co.add("123");//add()方法
        co.add("iii");
        co.add(123);
        co.add(true);
        System.out.println(co.size());
        Collection co1 = new ArrayList();
        co1.add("23");
        co1.add("231");
        co1.addAll(co);//addAll()方法
        System.out.println(co1.size());//size()方法
        System.out.println(co1.isEmpty());//isEmpty()方法
        co1.clear();//clear()方法
        
        Dog d =new Dog("jack",2);
        Dog d2 =new Dog("jack",2);//Dog类重写了equals类,d1,d2内容相同
        co1.add(d);
        System.out.println(co1.contains(d2));//contains方法检查集合是否包含某个元素,如果是对象的话,则调用equals方法进行判断,结果返回ture/false
        System.out.println(co1.remove(new Dog("jack", 2)));//remove()方法也是根据equals方法进行移除操作
      //remove()想删除干净：
      //1.遍历的时候加上i--;
      //2.倒着遍历
    }
}

// removeif():
 package Day08Test;
import java.util.ArrayList;
import java.util.Collection;
import java.util.function.Predicate;

public class removeIfTest {
    public static void main(String[] args) {
        Collection<String> co = new ArrayList<>();
        co.add("1213");
        co.add("123");
        co.add("1213");
        co.add("1");
        co.add("1213");

        co.removeIf(new Predicate<String>() {
            @Override
            public boolean test(String s) {
                return s.length()==4;
            }//接口实现类的匿名对象,也可以转成lambda表达式
        });

        System.out.println(co);//[123, 1]
    }
}  
```

* ==**Iterator( ) :**返回Iterator接口(迭代器接口)的实例,用于遍历集合元素==

  * next( ): 单个取出集合里面的元素，**每次调用此方法，指针下移一个位置**。

  * hasNext( ):判断集合中是否有元素,返回布尔值,用作while遍历循环的条件,如下:

  * remove( ):删除元素：注意两点：1.next前不能remove；2.不能连续两次remove。==可以直接用remove If( )代替==。（**若在迭代器里面调用list自己的remove要注意并发修改异常**）

    ```java
     Iterator i = co.iterator();
            while(i.hasNext()){
                System.out.println(i.next());
            }//用Iterator遍集合(先调用iterator方法,创建Iterator接口实例i,再用i调用方法)
    //注意,集合对象每次调用iterator方法都会创建一个新的Iterator对象,指针都是在集合第一个元素处
    ```

    ```java
    package Day08Test;
    
    import java.util.ArrayList;
    import java.util.Collection;
    import java.util.Iterator;
    
    public class collectionTest {
        public static void main(String[] args) {
            Collection co = new ArrayList();
            co.add("123");//add()方法
            co.add("iii");
            co.add("123");
            co.add(123);
            co.add(true);
            Iterator i = co.iterator();
            while (i.hasNext()) {
                Object o = i.next();
                if (o.equals("123")) {
                    i.remove();
                    //1.不同之处在于用迭代器对象进行remove，而不是之前学的用集合对象remove。在调用next之前不要remove,不然指针还没下来，删除不了
                    //2.不能连续两次remove，第一次remove的时候，指针还在那个位置。必须再次next才能remove
                    System.out.println("---");
                }
            }
            i = co.iterator();//关键步骤，让集合co的迭代器再次赋值给i,不然愿迭代器i指针已经到尾部，无法继续遍历
            while (i.hasNext()) {
                System.out.println(i.next());
            }
        }
    ```

  * **增强for循环**：循环底层就是iterator：单列集合可以使用，双列集合不可以使用（要实现iteratorable接口）。

    * 数据类型一定是集合或者数组中元素的类型
    * 用增强for循环遍历集合的时候中不可用集合自己的方法，因为会出现并发修改异常。
    * 第三方e修改没有意义，修改之后不会影响集合的值。
    * **增强for循环适合仅仅遍历元素（fori适合需要索引的/iterator迭代器适合遍历中途需要删除元素的（removeif方法））**

* ==其他几个方法：==

  * **Collections.shuffle(list):**打乱list集合顺序
  * **Collections.sort(list):**对list集合进行排序（如果是自定义对象，则要确定排序顺序）

#### 7.1.1 List接口 (有序，可重复集合)

* 效果和数组类似,但是可以灵活增添元素,可以当做动态数组

* **1.ArrayList类**：自动扩容、复制原数组机制。==创建对象的时候最好使用带参构造器，确定集合容量的潜力，避免经常自动扩容==

  * Jdk7 中创建对象的时候，就创建了容量为10的Object[ ]数组，容量不够则扩容成之前的1.5倍。
  * **Jdk8创建对象的时候容量为0，调用add方法之后才会创建长度为10的数组，之后每次添满都自动扩容为1.5倍。更加节省内存（用list.of创建集合时，集合刚开始长度就是list.of里面的元素个数，后面也是1.5倍扩容）**

  ```java
  package Day08Test;
  
  import java.util.ArrayList;
  import java.util.Arrays;
  import java.util.List;
  
  public class ArraylistTest {
      public static void main(String[] args) {
          ArrayList list = new ArrayList(10);
          list.add("5656");
          list.add("116");
          list.add("999");
          list.add("999");
          list.add("999");
          list.add(2, "234");//add():在索引1处插入"234"
  
          List<String> i = Arrays.asList("q3", "q5", "q7");//用Arrays的静态方法asList()创建新集合，泛型是String
  
          list.addAll(i);//调用addAll()将新集合全部元素都装入旧集合
          System.out.println(list);//[5656, 116, 234, 999, q3, q5, q7]
  
          int of = list.indexOf("000");//indexOf()找指定元素的索引，找不到就返回-1
          System.out.println(of);//-1
  
          int of1 = list.lastIndexOf("999");//lastIndexOf()找到该元素最后一次出现的索引位置
          System.out.println(of1);//5
  
          boolean b = list.remove("5656");//remove()注意这里remove既可以通过对象equals方法删除元素，也可以通过索引删除元素
          Object o = list.remove(1);//并且注意二者返回值不同
          list.remove(Integer.valueOf(3));//想直接删除数字的话，要包装成对象，否则会直接删除数字对应的索引
  
          list.set(1,"00000");//set()。。。可以返回被替换的元素
  
          List subList = list.subList(2, 4);//subList()获取一个新的list，是截取之前的list索引而得到的
      }
  }
  //add(index element):按照索引添加元素的范围：[0-size],不能超范围用索引添加
  //new arraylist<>(list.of("1","2","3")):集团批量添加元素的方法
  ```

  * **遍历方式：1.iterator.   2增强for循环.**

  ```java
   Iterator it = list.iterator();
          while (it.hasNext()) {
              System.out.println(it.next());
          }// Iterator
  
   for (Object l :list) {
              System.out.println(l);
          }//
  ```

#### 7.1.1.2 数据结构

* 栈：先进后出

* 队列：先进先出

* **链表增删快，查询慢。（区别于数组查询快，增删慢）**

* 单向链表：前一个节点记录本节点的地址值；

* **双向链表**：

  * **记录前一个节点以及后一个节点的地址值；**
  * ==Node是其数据储存的基本单位。双向链表有first node和last node，每一个node由三部分组成：**f , e , l**。==
  * **有头/尾节点，头只能记录下一个，尾只能记录上一个。**
  * （**双向链表**可以选择时**从头开始**找还是**从尾开始找**）

* **==树==**

  * **二叉树：**
    * 节点：二叉树的每个基本单元：==父节点地址==+==值==+==左字节点地址==+==右子节点地址==
    * 度：每个节点的子节点数量（<=2）
    * 根节点，书高，左子树，右子树...
    * **二叉查找树：1.每个节点最多有两个子节点；2.每个左子节点都是小于自己的；3.每个右子节点都是大于自己的**
      * ==**平衡二叉树**==：**1.左右子树高度差不超过1；2.任意节点的两个子树都是平衡二叉树**
        * 左旋：1.以根节点为受力点左拉，原根节点退位，新根节点上位；2.新根节点原先的左子节给旧根节点作右节点
        * 右旋：左旋的机制整体向右操作
        * 左左（根节点的左子树的左子树有节点插入）/左右（根节点的左子树的右子树有节点插入）：整体右旋/先左子树左旋（转变成左左情况），再整体右旋
        * 右右/右左：整体左旋/先右子树右旋（转变成右右情况），再整体左旋
  * **红黑树：**
    * 是根据自己规定的规则实现平衡的
    * 红黑规则：
      * 1.每个节点都是红色/黑色；
      * 2.根节点是黑色；
      * 3.没有子/父的节点是Nil节点（叶节点），必须是是黑色；
      * 4.红节点的子节点必须是黑色；
      * 5.每一个节点到它所有的后代Nil节点的路径上的黑色节点数量都是相同的
    * **添加元素的规则**：
      * 1.**先默认要添加的节点都是==红色==**（是根节点的话就直接改成黑色）；
      * 2.先看父节点，黑色没事，**红色继续看叔叔节点**
      * 3.1==叔叔节点是红色的话==：就要把红父，红叔都改成黑色，祖父却设置成红色（当然如果祖父是根节点那就设置为黑色）
      * 3.2==叔叔节点是黑色的话==：先把红父改成黑父，黑祖父改成红色（和3.1一样）。但是得以祖父为支点旋转（祖父变成叔叔了）

* #### **2.LinkedList类**：双向链表（不是数组）

  * 特有功能：(因为是双向链表结构，增删快)

    ```java
    package Day10Test;
    
    import java.util.LinkedList;
    
    public class animalTest {
        public static void main(String[] args) {
            LinkedList<String> x =new LinkedList<>();
            x.add("qqq");
            x.add("www");
            x.add("eee");
    
            x.addFirst("111");//添加到开头
            x.addLast("ppp");//添加到末尾
    
            String xFirst = x.getFirst();//获取开头元素
            String xLast = x.getLast();//获取末尾元素
    
            System.out.println(xFirst+" "+xLast);
    
            String removeFirst = x.removeFirst();//移除开头元素
            String removeLast = x.removeLast();//移除末尾元素
    
    
            for (String s : x) {
                System.out.println(s);
            }
        }
    }
    ```

* **3.Vector类**

* **三者异同；**

  * 同：都是实现了list接口，都是有序，可重复的

  * 异：

    * 1.ArrayList类是主要实现类，线程不安全，效率较高；

    * 2.LinkedList底层使用的是双向链表结构，==若有频繁的删除/插入，此类效率更高==；
    * 3.vector是古老实现类，线程安全，效率不高。

#### 7.1.2 Set接口（无序，不可重复集合）

* set接口没有新声明的方法，都是collection接口的方法（区别于list新增加了一堆方法）。

* **1.HashSet类**：==快速去重（构造器里面可以直接塞list）。数组+链表结构+红黑树；==

  * 无序、不可重复：

    * 1：==**无序性不是随机性**。每次遍历顺序都是一致，但是和添加顺序不同。==（是根据**元素的HashCode**来决定顺序的）；

    * 2：不可重复是指**HashCode不一样、equals方法不能为true**（**原理是通过算法计算hashcode,确定元素在数组要存放的位置，如果该位置为空，则直接存放**；如果已经被占据，先通过hashcode比较，如果不同，则直接使用链表在此位置存放；如果相同，则通过equals比较，false的话则使用链表在此位置存放。true则代表元素确确实实重复，不能存放）（**加载因子**：哈希表默认数组长度16，加载因子是0.75，则当数组有16*0.75个元素的时候，数组扩容为原来的两倍）
    * 3:jdk7上（新元素指向原来的元素），**jdk8下（原来的元素（老元素在上面）指向新元素（新元素在下面））。**

  * 注意事项：往Set集合里面装入元素之前要将**==原来的hashcode、equals方法覆盖==**

  * 经典面试题，判断对set集合重复概念的理解：

  ```java
  package Day08Test;
  
  import java.util.HashSet;
  import java.util.Objects;
  
  public class Setmianshiti {
      public static void main(String[] args) {
          HashSet s =new HashSet();
          Person p1=new Person(12,"AA");
          Person p2=new Person(13,"BB");
          s.add(p1);
          s.add(p2);
          System.out.println(s);//直接输出
  
          p1.name="CC";//p1的域值改变
          s.remove(p1);//此时输入p1，Java会将修改过的p1的散列码求出（根据覆盖的方法计算，和域值有关），此处的散列码已经和第一次不一样了。set根据新的散列码无法找到要删除的元素位置，无法删除元素。
          System.out.println(s);//因为元素无法被删除，所以此处还是打印出了两个元素
  
          s.add(new Person(12,"CC"));//表面上看去，这里元素重复了，无法添加，其实因为是根据散列码得出数组位置，此新对象和p1散列码（p1散列码第一次存放的时候就已经被确定下来了，哪怕域值更改，散列码不变）不同，位置不同，所以可以直接添加
          System.out.println(s);//打印三个元素
  
          s.add(new Person(12,"AA"));//会和p1散列码一致，所以启动第二步骤：调用equals方法判断是否重复，由于p1域值已经更改，所以equals为false，可以添加
          System.out.println(s);//打印四个元素
  
      }
  }
  
  class Person {
      int id;
      String name;
  
      public Person(int id, String name) {
          this.id = id;
          this.name = name;
      }
  
      @Override
      public boolean equals(Object o) {
          if (this == o) return true;
          if (o == null || getClass() != o.getClass()) return false;
          Person person = (Person) o;
          return id == person.id && Objects.equals(name, person.name);
      }
  
      @Override
      public int hashCode() {
          return Objects.hash(id, name);
      }
  
      @Override
      public String toString() {
          return "Person{" +
                  "id=" + id +
                  ", name='" + name + '\'' +
                  '}';
      }
  }
  ```

  

* **2.LinkedHashSet类**：hashset类的子类，伪有序集合。内部数组其实是无序的，遍历出来是有序的（==原因是在添加数据的同时，每个数据还维护了两个引用，记录此数据前一个数据和后一个数据==）。

* **3.TreeSet类**：==排序，去重（构造器里面可以直接塞list），红黑树结构==

  * 可以按照对象的**指定属性**（所以添加的元素必须都¥是一个类的，才能确保有一致的属性，如na me,age...），进行**排序**。

  * 注意：TreeSet涉及到比较，==它判断元素是否重复是**要看进行比较的属性**是否重复,compareTo( )方法返回值若是0，则代表相等==

  * **两种排序方式**

    * ==自然排序：==

    * 1.**空参构造**创建TreeSet集合
    * 2.自定义类（student/person）实现**Comparable接口**
    * 3.重写**compareTo方法（）** *（return负数，存的元素小，放左边；0就是相等，重复了，不存入；return 正数，大，右边）*

    ```java
    package Day08Test;
    
    import java.util.TreeSet;
    
    public class TreeSetTest {
        public static void main(String[] args) {
            TreeSet set = new TreeSet();
            set.add(new User("jack", 23));
            set.add(new User("jak", 23));
            set.add(new User("ack", 23));
            set.add(new User("jack9", 23));
            set.add(new User("jack00", 23));
    
            for (Object s :
                    set) {
                System.out.println(s);
            }
        }
    }
    
    class User implements Comparable {
        private String name;
        private int age;
    
        public User(String name, int age) {
            this.name = name;
            this.age = age;
        }
    
        @Override
        public int compareTo(Object o) {
            if (o instanceof User) {
                User user = (User) o;
                int i = this.name.compareTo(user.name);
                if (i != 0) {
                    return i;
                } else {//如果name属性比较不出来大小，则继续比较age属性
                    return Integer.compare(this.age, user.age);//基本类型要包装成引用类型，调用静态方法进行比较
                }
            } else {
                throw new RuntimeException("类型不正确");
            }
        }
    
        @Override
        public String toString() {
            return "User{" +
                    "name='" + name + '\'' +
                    ", age=" + age +
                    '}';
        }
    }
    ```

    * ==比较器排序：==

    * **比较器(comparator)排序**：带参构造参数是new comparator ( )；
    * 比较器排序可以**扩充更改自然排序的排序规则**（比如String这种不可以更改的类）
    * 所以比较器排序优先级高于自然排序

    ```java
    package Day10Test;
    
    import java.util.Comparator;
    import java.util.Set;
    import java.util.TreeSet;
    
    public class studentSetTest {
        public static void main(String[] args) {
            student a =new student(12,"ab");
            student b =new student(11,"b");
            student c =new student(15,"cba");
            student d =new student(13,"dbs");
            student e =new student(12,"eeeb");
    
            Set<student> list = new TreeSet<>(new Comparator<student>() {//带参构造
                @Override
                public int compare(student o1, student o2) {
                    student o3=(student) o2;
                    int i = o1.age - o2.age;
                    if(i!=0){
                        return  i;
                    }else {
                        return o1.name.compareTo(o2.name);
                    }//类似匿名内部类，直接重写compare方法
                }
            });
            list.add(a);
            list.add(b);
            list.add(c);
            list.add(d);
            list.add(e);
    
            for (student s : list) {
                System.out.println(s);
            }
        }
    ```

### 7.2 Map接口（双列）

* 双列集合，储存一对对（key-value）数据，映射效果

#### 7.2.1 HashMap

* **==1.HashMap：==**线程不安全，效率高；可以存储null的key/value；是put( )

  * ==注意事项：==
    * key是不可重复的，无序的（用Set存储的）；key所在的类要重写hashcode( )、equals( )方法；**用equals( )方法&&hashcode( ) 判断两个key值是否相等**
    * value是可重复、无序的（用Collection存储）；value所在的类要重写equals( )方法，**用equals( )方法判断两个value值是否相等**
    * **一个key/value组成一个Entry（不可重复的，无序的，用Set存储的）**

  * ==底层实现原理：==
    * JDk7: 1.获取key的hashcode，计算得到数组中的存放位置 --->2.该位置为空直接存放/不为空比较hashcode:不一样就直接存放--->3.hashcode一样的话就看equals( )--->4.false直接放/**true就把value值替换成新的value值**。（这也是和HashSet的区别，HashSet是直接报重复）（HashSet存入的就是HashMap的Key值）
    * JDK8:  相较于JDK7,变化了以下几点：
      * 1.初始没有创建16长度的数组，第一次put的时候才创建；
      * 2.底层数组是Node结构而非Entry结构；3.底层结构变成数组+链表+红黑树：
      * 链表长度>8&&数组长度>64的时候，此索引上的所有数据从链表变成红黑树结构
  * ==Map接口的方法：==

  ```java
  package Day12Test;
  
  import java.util.*;
  
  public class mapp {
      public static void main(String[] args) {
          Map map = new HashMap();
          map.put("ycx", 1);
          map.put("y", 1);
          map.put("ycx", 8);//将上一个ycx替换掉了
          map.put("x", 3);
          System.out.println(map);//{x=3, y=1, ycx=8}
  
          Map map1 = new HashMap();
          map1.put("dd", 666);
          map.putAll(map1);
          System.out.println(map);//{dd=666, x=3, y=1, ycx=8}
  
  
          Object o = map.remove("dd");
          System.out.println(o);//666
  
          boolean empty = map.isEmpty();
          System.out.println(empty);//false
  
          map.clear();
          System.out.println(map);//{}
  
          boolean b = map.containsKey("ycx");
          boolean b1 = map.containsValue(1);
  
  //----------------Map的遍历------------------------------------------------------
          Map map2 = new HashMap();
          map2.put("ycx", 1);
          map2.put("y", 9);
          map2.put("cx", 8);
          map2.put("x", 3);
  
          Set set = map2.keySet();//获取key的set集合
          Collection v = map2.values();//获取values的collections集合
  
          Set es= map2.entrySet();//获取key-value的set集合
          Iterator i = es.iterator();
          while(i.hasNext()){
              Object obj = i.next();
              Map.Entry obj1 = (Map.Entry) obj;//Entry是Map类的内部接口
              Object key = obj1.getKey();
              Object value = obj1.getValue(); 
            System.out.println(key+"-----"+value);//也可以用get(key)取出value
   
  //--------------用foreach遍历（实现接口）---------------------------------------  
            map.forEach(new BiConsumer<String, String>() {
              @Override
              public void accept(String s, String s2) {
                  System.out.println(s+s2);
              }
          }); 
          }
      }
  }
  ```

  * 2.LinkedHashMap：添加了指针，可以实现按照添加元素的顺序遍历（频繁遍历可以用LinkedHashMap）

#### 7.2.2 TreeMap

* ==**3.TreeMap:**==按照Key（所以key必须是同一个类的）排序的（和value无关 ）

  * 和TreeSet一样，也是两种排序方式

  ```java
  package Day12Test;
  
  import java.util.Iterator;
  import java.util.Map;
  import java.util.Set;
  import java.util.TreeMap;
  
  public class treeMap {
      public static void main(String[] args) {
          user u1 =new user(23);
          user u2 =new user(16);
          user u3 =new user(25);
          user u4 =new user(47);
          user u5 =new user(8);
  
          TreeMap t =new TreeMap();
          t.put(u1,"A");
          t.put(u2,"B");
          t.put(u3,"C");
          t.put(u4,"D");
          t.put(u5,"E");
  
          Set set = t.entrySet();//一定要先转成set先
  
          Iterator i = set.iterator();
          while(i.hasNext()){
              Object obj = i.next();
              Map.Entry obj1 = (Map.Entry) obj;
              Object key = obj1.getKey();
              Object value = obj1.getValue();
              System.out.println(key+"-----"+value);
            /*  user{age=8}-----E
              user{age=16}-----B
              user{age=23}-----A
              user{age=25}-----C
              user{age=47}-----D*/
          }
      }
  }
  class user implements Comparable<user>{
      int age;
  
      public user(int age) {
          this.age = age;
      }
  
      @Override
      public int compareTo(user o) {
          return this.age-o.age;//自定义排序
      }
  
      @Override
      public String toString() {
          return "user{" +
                  "age=" + age +
                  '}';
      }
  }
  
  ```

  

* Hashtable古早实现类：线程安全，效率低；不可以存储null的key/value

  * ==**Properties**==：Hashtable的子类，主要来处理配置文件，**key、value都是String。**

  * 提前创建属性文件xxxx.properties
  * load( )、store( )

  ```java
  package Day14Test;
  
  import java.io.FileInputStream;
  import java.io.IOException;
  import java.util.Properties;
  
  public class properties {
      public static void main(String[] args) throws IOException {
          Properties p =new Properties();//创建Properties类对象
          FileInputStream fis =new FileInputStream("/Users/yuchenxi/IdeaProjects/TEST/practice/jbdc.properties");//字节输出流
          p.load(fis);//加载流
          fis.close();
  
          String name = p.getProperty("name");//获取已经写好的配置文件的内容，注意都是字符串
          String password = p.getProperty("password");
  
          System.out.println(name+password);
      }
  }
  --------------------------------------
     Properties p =new Properties();//创建Properties类对象
          p.put("123","566");
          p.put("1234","5669");
  
          FileWriter f =new FileWriter("/Users/yuchenxi/IdeaProjects/TEST/practice/jbdc.properties");
          p.store(f,null);//描述信息，这里是null
          f.close();
  ```

  

* **可变参数：public static void m（int...x）{ };** / / 可变参数其实就是数组

  * 方法里面如果有多个参数。可变参数必须要放在最后一个
  * 能减少重载方法的的定义（比如一会求2个数的和的方法，一会求3个数的和的方法）

  ```java
  package Day12Test;
  
  public class kebiancanshu {
      public static void main(String[] args) {
          System.out.println(getsum(1, 2, 3, 4, 5));
      }
      public static int getsum(int...arr){//可变参数
          int sum =0;
          for (int i = 0; i < arr.length; i++) {
              sum+=arr[i];
          }
          return sum;
      }
  }
  ```

* **不可变集合：List.of ( )** 创建的集合是不可变集合,不可以修改删除添加；但是可以实现批量添加元素构造集合，较为方便。

  * new ArrayList<>(List.of(1,2,3,4,5,6 ))//批量添加元素构造集合

  ```java
  package Day12Test;
  
  import java.util.ArrayList;
  import java.util.List;
  import java.util.Map;
  import java.util.Set;
  
  public class listof {
      public static void main(String[] args) {
          List<Integer> i = List.of(1, 2, 3, 4, 5, 6, 7, 8, 9, 0);
          ArrayList<Integer> list = new ArrayList<>(i);
          System.out.println(list);
  
          Set.of(1, 2, 4, 7);
  
          Map.of(1, 9, 2, 8);//1 9是一对；2 8是一对
  
          Map.ofEntries(Map.entry(1, 9), Map.entry(2, 8));
        
      }
  }
  ```

### 7.3 Stream流

* 过程：**将容器中的数据复制一份，原数据是无法修改的（如果使用容器的方法操作，则可以改变原数据，应该要避免)，** 获取stream流-操作-操作-操作-终结（关闭流水线）；

* 三类方法：

  * ==获取方法：==

    * 单列：Collections接口中的默认方法stream()   	// list.stream()
    * 双列: 先获取key/value的set集合，再获取	//map.keyset().stream()   / /map.entry().stream()
    * 数组: Arrays.stram()
    * 同种数据类型多个数据：stream.of ( .. , .. , ..)

  * ==中间方法:==

    * Filter  // list.stream().filter(s->s.length()==3).forEach(s-> System.out.println(s));
    * limit：截取
    * skip：跳过
    * contact：合并
    * distinct：去重
    * sort：排序

    ```java
    package Day12Test.stream;
    
    import java.util.ArrayList;
    import java.util.Comparator;
    import java.util.List;
    import java.util.stream.Stream;
    
    public class s {
        public static void main(String[] args) {
            ArrayList<String> list = new ArrayList<>(List.of("aaa","bb","ccc","dddd","eeee","qqq"));
    
            list.stream().filter(s->s.length()==3).forEach(s-> System.out.println(s));
    
            Stream<String> stream = list.stream().limit(2);
    
    
            Stream<String> skip = list.stream().skip(3);
    
            Stream.concat(stream,skip);//合并
    
            list.stream().distinct();//去重
    
            list.sort(new Comparator<String>() {
                @Override
                public int compare(String o1, String o2) {
                    return 0;
                }
            });//排序
    
        }
    }
    ```

  * ==终结方法==

    * foreach( )
    * count( ):返回值是long
    * ==收集方法：==**Collectors 的静态方法：toList( )/toSet( )**（collect只是单纯的收集，并没有创建容器,==collectors才是真正创建容器==）

    ```java
    rrayList<Integer> list1 = new ArrayList<>();
            list1.add(1);
            list1.add(2);
            list1.add(3);
            list1.add(4);
            list1.add(5);
            list1.add(6);
    
            List<Integer> list2 = list1.stream().filter(s -> s % 2 == 0).collect(Collectors.toList());
    
            System.out.println(list2);
    ```

    * ==收集方法：==**toMap( )**: toMap( lambda, lambda ). 两个lambda表达式分别获取key/value

  ```java
  package Day12Test.stream;
  
  import java.util.ArrayList;
  import java.util.Map;
  import java.util.stream.Collectors;
  
  public class s {
      public static void main(String[] args) {
          
          ArrayList<String> list1 = new ArrayList<>();
          list1.add("az,11");
          list1.add("tt,13");
          list1.add("ew,14");
          list1.add("yy,15");
  
          Map<String, String> map = list1.stream().filter(s -> {
              String[] strings = s.split(",");
              int i = Integer.parseInt(strings[1]);
              return i > 12;//过滤条件
          }).collect(Collectors.toMap(
                  s -> {
                      String[] strings = s.split(",");
                      return strings[0];//获取key
                  }, s -> {
                      String[] strings = s.split(",");
                      return strings[1];//获取value
                  }
          ));
  
          System.out.println(map);//{tt=13, yy=15, ew=14}
      }
  }
  ```

  

## 8. 泛型程序设计

### 8.1 集合中的泛型

* 在实例化集合类的时候，可以指明具体的泛型类型。如果不指明，则默认为Object类
* 泛型类型必须是引用类型，不可以是基本数据类型，基本数据类型需要用包装器
* 泛型的好处是使得结构更简单，不需要将元素从Object类强制转换成其他类型
* 提供编译时期类型检测
* 可以定义在==类后面/方法申明/接口后面==

### 8.2 自定义泛型类

* 可以有一个泛型参数，也可以有多个
* 声明构造器的时候无需添加泛型，实例化的时候再考虑泛型

```Java
package Day10Test;

public class animalTest {
    public static void main(String[] args) {
        Animal<String,Integer> x = new Animal<>("dog", "111","公",22);
        System.out.println(x);
    }
}

class Animal<T,E>  {
    String name;
    T order;
    T sex;
    E height;
  
    public Animal() {
    }

    public Animal(String name, T order,T sex,E height) {
        this.name = name;
        this.order = order;
        this.sex=sex;
        this.height=height;
    }

    @Override
    public String toString() {
        return "Animal{" +
                "name='" + name + '\'' +
                ", order=" + order +
                ", sex=" + sex +
                ", height=" + height +
                '}';
    }
}
```

### 8.3 泛型方法

* **public < T > void show ( T t ) {  }**：< T >相当于是给方法一个定义，参数列表里面的T要和这个一致

```java
package Day10Test;

import java.util.ArrayList;

public class fanxingmethod {
    public static void main(String[] args) {
        ArrayList<String> list =new ArrayList<>();
        ArrayList<String> list1 = m(list, "abc", "wer", "uii");
        System.out.println(list1);//[abc, wer, uii]

    }
    public static <T> ArrayList<T>  m (ArrayList<T> list,T t1,T t2,T t3){
        list.add(t1);
        list.add(t2);
        list.add(t3);
        return list;
    }
}
```

* 继承关系下的泛型方法
  * 泛型方法被重写，泛型也得保留
  * 输入实参的时候，泛型就被确定了

### 8.4 泛型接口

* 类实现接口：
  * 1.实现类确定泛型类型，是普通类。
  * 2.实现类没有确定泛型类型，也是泛型类。
* 接口的扩展（接口==继承==接口）
  * 1.接口继承接口，确定父接口的泛型类型
  * 2.接口继承接口，没有确定父接口的泛型类型，此时子接口需要定义父接口泛型类型

### 8.5 泛型的通配符

* < ? >:无限制泛型，并且能表示范围。**区别于< T >，不需要方法里面定义< T >**
* 表示范围：
  * ==<? extends x>:x类以及x所有的子类==
  * ==<? super x>:x类以及x所有的超类==
  * 

## 9. IO流

### 9.1 File类的使用

* 创建File对象：
  * File类的对象是一个文件/文件夹
  * 在IO包下面
  * File只是涉及简单的文件/文件目录创建、重命名、删除、获取文件信息等功能，具体的写入/读取文件的内容比如使用IO流
  * File类的对象往往是作为参数传递到流的构造器里面，作为读取/写入的终点

```java
File f1 =new File("h.txt");//相对路径
        
File f2 =new File("/Users/yuchenxi/Documents/testf.txt");//绝对路径

File f3 =new File("/Users/yuchenxi/Documents","testf.txt");//绝对路径文件夹+文件名

File f4 =new File(f3,"testf1.txt"); //另一个file对象+文件名
```

* File类的方法：

```java
package Day13Test;
import java.io.File;
import java.util.Date;

public class FileTest {
    public static void main(String[] args) {
        File f2 =new File("/Users/yuchenxi/IdeaProjects/TEST/out/production/practice/Day13Test/xxx");
        System.out.println(f2.getAbsolutePath());///Users/yuchenxi/IdeaProjects/TEST/out/production/practice/Day13Test/xxx
        System.out.println(f2.getPath());///Users/yuchenxi/IdeaProjects/TEST/out/production/practice/Day13Test/xxx
        System.out.println(f2.getName());//xxx。。。调用者是文件的话则获取文件名+扩展名；调用者是文件夹的话，获取的是文件夹的名字
        System.out.println(f2.getParent());///Users/yuchenxi/IdeaProjects/TEST/out/production/practice/Day13Test
        System.out.println(f2.length());//4
        System.out.println(f2.lastModified());//最后修改时间 1623979593579
        System.out.println(new Date(f2.lastModified()));//转换成日期  Fri Jun 18 09:26:33 CST 2021

        File f3 =new File("/Users/yuchenxi/IdeaProjects/TEST/out/production/practice");
        String[] l = f3.list();//获取该目录下的文件名的字符串数组（也可以用f3.listFiles()，获取文件夹数组）（调用者必须是文件夹，如果是文件的话会返回null）
        for (String s : l) {
            System.out.println(s);
        }
        
        File f4 =new File("/Users/yuchenxi/1.txt");
        File f5 =new File("/Users/yuchenxi/qqq.txt");
        boolean b = f5.renameTo(f4);//让f5的文件名字改成f4,（注意f5要存在，f4不能存在否则会因文件名重复报错）
        System.out.println(b);
    }
}

//public boolean isDirectory():判断是否是文件目录
//public boolean isFile():判断是否是文件
//public boolean exists():
//public boolean canwrite():
//public boolean canread():
//public boolean isHidden():
```



```java
package Day13Test;

import java.io.File;
import java.io.IOException;

public class File2Test {
    public static void main(String[] args) throws IOException {
        File f = new File("/Users/yuchenxi/IdeaProjects/TEST/practice/src/Day13Test/ttt.txt");
        if(!f.exists()){
            f.createNewFile();//。。。这里创建文件的时候路径不存在得先创建父级路径，用.mkdirs()       
            System.out.println("创建成功");
        }else{
            f.delete();//。。。文件可以直接删除/文件夹只能删除空文件夹
            System.out.println("删除成功");
        }

        if(f.mkdir()){//创建单级文件夹
            System.out.println("创建文件目录，如果此文件目录存在、上层文件不存在，不会创建");
        }

        if(f.mkdirs()){//创建多级文件夹
            System.out.println("创建文件目录，如果上层文件不存在，将上层文件一起创建");
        }
    }
}
```

* **练习：用递归删干净文件夹**

```java
package Day13Test.pratice;

import java.io.File;

public class Test2 {
    public static void main(String[] args) {
        File f = new File("/Users/yuchenxi/Desktop/testt");
        if (!f.exists()) {
            System.out.println("文件不存在");
            return;
        }
        extracted(f);
    }

    private static void extracted(File f) {//递归方法
        File[] files = f.listFiles();

        for (File file : files) {
            if (file.isFile()) {//判断是否为文件，是的话直接删除文件
                file.delete();
            } else {
                extracted(file);//是文件夹的话用递归把文件夹里面的文件都删干净
                file.delete();//再把空文件夹本身删除
            }
        }
    }
}
```

### 9.2 IO流的原理以及流的分类

* 按照数据类型：**字节流(非文本文件)；字符流(文本文件)**
* 按照方向：**输入流（InputStream;Reader）；输出流（OutputStream;Writer）**
* 按照角色：**节点(文件)流；处理流**

（其实就是**字节输入/输出流、字符输入/输出流四大类**各自对应的==节点流，处理流（处理流可以看作叠buff）==）

#### 9.2.1 节点流（FileReader、FileWriter、FileInputStream、FileOutputStream）

* idea默认是UTF-8解码，一个字符占用3个字节。Windows默认是GBK，一个字符占用2个字节。
* 不管在哪张码表中，中文的第一个字节一定是一个负数j/ 

* **==1.FileReader==**

  * 步骤：1.找路径创建File对象；2.用File对象创建Filereader类对象；3.获取字符（循环）；4.关闭流
  * 要用try-catch-finally-处理防止异常

  ```java
  package Day13Test;
  import java.io.File;
  import java.io.FileReader;
  import java.io.IOException;
  
  public class filereaderTest {
      public static void main(String[] args) {
          FileReader f = null;
          try {
              File file = new File("/Users/yuchenxi/IdeaProjects/TEST/practice/src/Day13Test/ttt.txt");
              f = new FileReader(file);
              int date = f.read();
              while (date != -1) {
                  System.out.print((char) date);//输出结果："这是测试字符输入流的文件"
                  date = f.read();
              }
          } catch (IOException e) {
              e.printStackTrace();
          } finally {//在一定会执行的finally里面进行关闭流操作
              try {
                  if (f != null)//防止f为null报错
                      f.close();
              } catch (IOException e) {
                  e.printStackTrace();
              }
          }
      }
  }
  ```

  * **将字符打包成一定长度的字符数组读取，核心要点搞清楚遍历的长度和读取的长度**

  ```java
  package Day13Test;
  
  import java.io.File;
  import java.io.FileReader;
  import java.io.IOException;
  
  public class filereaderTest {
      public static void main(String[] args) {
          FileReader f = null;
          try {
              File file = new File("/Users/yuchenxi/IdeaProjects/TEST/practice/src/Day13Test/ttt.txt");
              f = new FileReader(file);
              char[] cbuf = new char[5];//字符数组,将字符装进长度为5的数组打包读取，每次打包5个
              int len;
              while ((len = f.read(cbuf)) != -1) {//read()返回的数据len每次读取字符的个数，前几次都是5，倒数第二次装不满，读的是2，最后一次没有字符了，读的是-1
                  for (int i = 0; i < len; i++) {//遍历数组，此处要注意长度是读取的个数len,不能是单个数组的cbuf.length,因为要考虑到可能最后一次数组没有填满，造成上一次元素残留现象
                      System.out.print(cbuf[i]);
                  }
                  //System.out.print(new String(cbuf, 0, len));//也可以直接将字符数组转换成字符串统一打印，同样要注意范围是[0,len]
              }
          } catch (IOException e) {
              e.printStackTrace();
          } finally {
              try {
                  if (f != null)
                      f.close();
              } catch (IOException e) {
                  e.printStackTrace();
              }
          }
      }
  }
  ```

* **==2.FileWriter:==**

  * 输出文件，可以先不存在相同的文件名的文件
  * **FileWriter("xxxx",true/false )**：同名文件是追加内容/直接替换同名文件

  ```java
  package Day13Test;
  
  import java.io.File;
  import java.io.FileWriter;
  import java.io.IOException;
  
  public class fileWriter  {
      public static void main(String[] args) throws IOException {
          File file =new File("/Users/yuchenxi/IdeaProjects/TEST/practice/src/Day13Test/www.txt");
          FileWriter f =new FileWriter(file,false);//true是在相同文件名的文件进行添加内容；false是直接替换文件。如果追加，注意不要造成追加内容与原始内容编码格式不一致造成的乱码
  
          f.write("试一试写入功能\n");
          f.write("hhhhh");
  
          f.close();
      }
  }
  ```

* **==3.用FileReader、FileWriter 先读后写，实现对文件的复制==**

```java
package Day13Test;

import java.io.File;
import java.io.FileReader;
import java.io.FileWriter;
import java.io.IOException;

public class copyTest {
    public static void main(String[] args) {
        try {
            File file1 = new File("/Users/yuchenxi/IdeaProjects/TEST/practice/src/Day13Test/copytest");
            File file2 = new File("/Users/yuchenxi/IdeaProjects/TEST/practice/src/Day13Test/copytest2");

            FileReader fr = new FileReader(file1);
            FileWriter fw = new FileWriter(file2);

            int len;
            char[] cbuf = new char[5];
            while ((len = fr.read(cbuf)) != -1) {
                fw.write(cbuf, 0, len);//关键步骤，可以直接把字符数组让新的文件写入，同时还是要注意len
            }

            try {
                if (fw != null) {
                    fw.close();
                }
            } catch (Exception e) {
                e.printStackTrace();
            }

            try {
                if (fr != null) {
                    fr.close();
                }
            } catch (Exception e) {
                e.printStackTrace();
            }

        } catch (IOException e) {
            e.printStackTrace();
        }
    }
}
```

* **FileInputStream/FileOutputStream实现对非文本文件的复制**

```java
package Day13Test;

import java.io.*;

public class inputcopytest {
    public static void main(String[] args) throws IOException {
        FileInputStream fi = null;
        FileOutputStream fo = null;
        try {
            File f1 = new File("/Users/yuchenxi/IdeaProjects/TEST/practice/src/Day13Test/IMG_20210418_103057.jpg");
            File f2 = new File("/Users/yuchenxi/IdeaProjects/TEST/practice/src/Day13Test/copyed.jpg");

            fi = new FileInputStream(f1);
            fo = new FileOutputStream(f2);

            int len;

            byte[] buffer = new byte[1000];

            while ((len = fi.read(buffer)) != -1) {
                fo.write(buffer);
            }
        } catch (IOException e) {
            e.printStackTrace();
        } finally {
            try {
                fi.close();
            } catch (IOException e) {
                e.printStackTrace();
            }
            try {
                fo.close();
            } catch (IOException e) {
                e.printStackTrace();
            }
        }
        
    }
}
```

#### 9.2.2 缓冲流（BufferedInputStream、BufferedOutputStream、BufferedReader、BufferedWriter）

* 种类：**缓冲流是一种处理流（给节点流加buff的），所以比字节流多了一个创建缓冲流对象的步骤。**BufferedInputStream、BufferedOutputStream，BufferedReader，BufferedWriter）
* 作用：让读写速度更快（因为内部提供了一个缓冲区）

```java
package Day13Test;

import java.io.*;

public class buffStream {
    public static void main(String[] args) {
        BufferedInputStream bis = null;
        BufferedOutputStream bos = null;
        try {
            File f2 = new File("/Users/yuchenxi/IdeaProjects/TEST/practice/src/Day13Test/IMG_20210418_103057.jpg");
            File f3 = new File("/Users/yuchenxi/IdeaProjects/TEST/practice/src/Day13Test/用缓冲流复制的非文本文件.jpg");

            FileInputStream fi = new FileInputStream(f2);
            FileOutputStream fo = new FileOutputStream(f3);

            bis = new BufferedInputStream(fi);
            bos = new BufferedOutputStream(fo);//多了这两个创建Buffer...对象的步骤

            int len;
            byte[] buffer = new byte[5];
            while ((len = bis.read(buffer)) != -1) {
                bos.write(buffer);
            }
        } catch (IOException e) {
            e.printStackTrace();
        } finally {
            try {
                bis.close();
            } catch (IOException e) {
                e.printStackTrace();
            }
            try {
                bos.close();
            } catch (IOException e) {
                e.printStackTrace();
            }
        }
    }
}
```

* **用缓冲流（字符）复制文本文件**（同时用readline方法读取数据的方式）(传递了一个长度为8192的数组，提高了打包效率)

```java
package Day13Test;

import java.io.*;

public class bufferdReaderCopy {
    public static void main(String[] args) {
        BufferedReader br =null;
        BufferedWriter bw =null;
        try {
             br = new BufferedReader(new FileReader(new File("/Users/yuchenxi/IdeaProjects/TEST/practice/src/Day13Test/buffercopy.txt")));
             bw = new BufferedWriter(new FileWriter(new File("/Users/yuchenxi/IdeaProjects/TEST/practice/src/Day13Test/buffer拷贝.txt")));

            String date;
            while ((date = br.readLine()) != null) {//注意这里是readline(),返回一行字符串
                bw.write(date + "\n");//直接输出字符串并且换行
            }//new line():调用此方法直接换行
          
        } catch (IOException e) {

        } finally {
            try {
                br.close();
            } catch (IOException e) {
                e.printStackTrace();
            }
            try {
                bw.close();
            } catch (IOException e) {
                e.printStackTrace();
            }
        }
    }
}
```

#### 9.2.3 转换流(InputStreamReader、OutputStreamWriter)

* **==属于字符流（注意因为它后缀是reader/writer）==**
* 字节---->字符，字符---->字节

```java
package Day13Test.ZhuanHuanLiu;

import java.io.*;

public class zhuanHuanCopy {//用转换流复制文件并且转码
    public static void main(String[] args) throws IOException {
        File f1 = new File("/Users/yuchenxi/IdeaProjects/TEST/practice/src/Day13Test/ZhuanHuanLiu/被转换的文件.txt");
        File f2 = new File("/Users/yuchenxi/IdeaProjects/TEST/practice/src/Day13Test/ZhuanHuanLiu/新生成的的文件gbk.txt");

        FileInputStream fi = new FileInputStream(f1);
        FileOutputStream fo = new FileOutputStream(f2);//用字节流处理

        InputStreamReader is = new InputStreamReader(fi, "UTF-8");
        OutputStreamWriter os = new OutputStreamWriter(fo, "gbk");//关键步骤，多了转换流，参数是字节流对象（底层还是字节流在操作）、编码规则

        char[] cbuf = new char[20];
        int len;
        while ((len = is.read(cbuf)) != -1) {
            os.write(cbuf, 0, len);
        }
       
        os.close();
        is.close();
    }
}
//用idea创建写出的文件的话，Windows自动识别也是UTF-8
//JKD11之后只用字符流也行。参数列表添加：charset.forname("gbk")
```

#### 9.2.4 标准输入、输出流

#### 9.2.5 数据流

* DataInputStream；DataOutputStream
* 作用：读取/写出基本数据类型的字符串

```java
package Day14Test;

import java.io.*;

public class DataStream {
    public static void main(String[] args) throws IOException {
        DataOutputStream dos =new DataOutputStream(new FileOutputStream("day14.txt"));
        dos.writeBoolean(true);
        dos.flush();//写入之后刷新
        dos.writeInt(999);
        dos.flush();
        dos.writeUTF("字符串");
        dos.close();

        DataInputStream dis =new DataInputStream(new FileInputStream("day14.txt"));
        System.out.println("dis.readBoolean() = " + dis.readBoolean());//注意要和写入顺序一致
        System.out.println("dis.readInt() = " + dis.readInt());
        System.out.println("dis.readUTF() = " + dis.readUTF());
    }
}
```

### 9.3 对象流（ObjectInputStream、ObjectOutputStream）

* 用途：==用于存储/读取基本数据类型/对象的处理流==，可以把对象写入数据源中，并且能从数据源中还原对象。保存的机制叫做**序列化**，读取机制的叫做**反序列化**
* *Java的序列化机制：Java运行将内存中的对象转换成与平无关的二进制流，从而保存在磁盘或者通过网络传递给其他网络节点，其他程序获取了此二进制流可以将其恢复成java对象。*
* 要求对象
  * **==类==以及==属性（基本类型都是可序列化的，就怕属性又是个新定义类）==必须是可以被序列化的**
  * **必须实现==Serializable/Externalizable==接口**
  * 提供全局常量**serialVersionUID**（序列号）。如果没有手动添加序列号，系统会默认添加序列号，只要类的内容更改，默认序列号又会改变。所以必须手动添加序列号才安全。
  * **static/transisent（不想序列化的属性就在前面加transient）**修饰的属性不可被序列化，

```java
package Day14Test;

import java.io.*;

public class objectStream {//序列化就是写出，反序列化就是读入。
    public static void main(String[] args) {
        ObjectOutputStream oop = null;
        try {
            oop = new ObjectOutputStream(new FileOutputStream("day14objextstream"));
            oop.writeObject(new person("张三", 12));//序列化
            oop.flush();//刷新
        } catch (IOException e) {
            e.printStackTrace();
        } finally {
            try {
                oop.close();//记得关闭
            } catch (IOException e) {
                e.printStackTrace();
            }
        }

        ObjectInputStream ois = null;
        try {
            ois = new ObjectInputStream(new FileInputStream("day14objextstream"));
            Object o = ois.readObject();//反序列化...读到文件结束会出现EOFException(而不是-1/null),可以放进死循环，然后catch异常再break;/也可以将多个对象放进集合中，直接将集合这个对象序列化/反序列化
            person p = (person) o;转型
            System.out.println(p);
        } catch (IOException e) {
            e.printStackTrace();
        } catch (ClassNotFoundException e) {
            e.printStackTrace();
        } finally {
            try {
                ois.close();
            } catch (IOException e) {
                e.printStackTrace();
            }
        }
    }
}

class person implements Serializable {//一定要实现接口
    private static final long serialVersionUId = 324564756856L;//序列号
    private String name;
    private int age;

    public person(String name, int age) {
        this.name = name;
        this.age = age;
    }

    public person() {
    }

    @Override
    public String toString() {
        return "person{" +
                "name='" + name + '\'' +
                ", age=" + age +
                '}';
    }
}
```



## 10. 多线程与并发

### 10.1 概念

* **线程（thread）：**每个程序进程可以细化成线程，是程序内部的执行路径
  * 同一个进程的多个线程可以共享相同的内存单元/内存地址空间，**可以访问相同的对象和变量**，高效便捷但是**可能有安全隐患。**
  * **==内存区域==**：**方法区、堆空间**：所有线程共享。**虚拟机栈、程序计数器**：每个线程各自都有一份。

### 10.2 线程的创建与使用

#### 10.2.1 1.创建继承thread类的类对象，调用start()方法

* 必须**使用start( )方法启动线程**，而不是调用重写的run( )方法
* start( )方法两个功能：**1.启动线程；2.调用run方法**
* 已经启动start的线程不能重复start，只能重新创建对象调用start**(多个线程造多个对象 )**

```java
package Day15Test;

public class ThreadTest {
    public static void main(String[] args) {
        mythread m =new mythread();
        m.start();
        for (int i = 0; i < 122; i++) {
            System.out.println("主线程运行");
        }
    }
}
class mythread extends Thread {
    @Override
    public void run() {
        for (int i = 0; i < 100; i++) {
            System.out.println("多线程运行");
        }
    }
}
```

* 创建两个匿名继承Thread类的类的对象，分别重新run方法并且start两个不同的线程

```java
package Day15Test;

public class ThreadTest {
    public static void main(String[] args) {
        new Thread() {
            @Override
            public void run() {
                for (int i = 0; i < 1000; i++) {
                    System.out.println("多线程运行");
                }
            }
        }.start();

        new Thread(){
            @Override
            public void run() {
                for (int i = 0; i < 1000; i++) {
                    System.out.println("第二个多线程运行");
                }
            }
        }.start();
    }
}
```

* ==thread类的几个常用方法==
  * **start()：**创建线程，调用run方法
  * **run()：**需要重写的方法，方法体是要进行的操作
  * **currentThread()：**静态方法，返回当前代码执行的线程。可以追加getName()/setName()
  * **yield()：**释放当前线程的CPU使用权
  * **join()：**在线程a中调用b的join方法，a进入阻塞状态，知道线程b完全进行完之后，a才会解除阻塞状态。
  * **sleep( long millitime)：**静态方法，让线程进入睡眠时间（毫秒），此时间内线程是阻塞状态
  * **isAlive()：**返回线程是否还活着的布尔值
* ==线程的优先级==：线程的优先级并不意味着优先级高的一定先执行完（只是大概率会被优先执行）
  * 表示线程优先级的常量：
    * MAX_PRIORITY=10;
    * MIN_PRIORITY=1;
    * NORM_PRIORITY=5;
  * getPriority (): 获取线程优先级
  * setPriority ()：设置线程优先级
* ==设置守护（后台）线程==：
  * **setDaemon(boolean )**
  * 目的是陪伴主线程，主线程结束之后，守护线程一会也就结束了（并不会执行完）

#### 10.2.2 2.用实现Runnable接口创建多线程

* 实现步骤：
  * 创建类实现Runnable接口
  * 创建实现类的对象
  * 用该对象作为参数创建Thread对象
  * 用Thread对象调用start()方法
* 优点：
  * 更适合多处理个线程有共享数据的情况（每个线程都是一个对象作为参数）
  * 接口没有单继承的限制

```java
package Day15Test;

public class ThreadTest {
    public static void main(String[] args) {
        Thread thread = new Thread(new m());
        thread.start();

    }
}
class m implements Runnable {
    @Override
    public void run() {
        for (int i = 0; i < 10; i++) {
            System.out.println(Thread.currentThread().getName()+"用实现Runnable接口创建多线程");
        }
    }
}
```

#### 10.2.3 3.用callable接口创建多线程

* 实现callable()接口
*  实现call方法，有返回值，return线程结束之后的返回结果
* 不可直接当作参数传递，用参数创建FutureTask对象
* 用FutureTask当参数创建Thread对象，此对象也可以用get()（阻塞方法，一定要在线程结束之后调用）获取返回值

```java
package Day15Test.practice;

import java.util.concurrent.Callable;
import java.util.concurrent.ExecutionException;
import java.util.concurrent.FutureTask;

public class test3 {
    public static void main(String[] args) throws ExecutionException, InterruptedException {
        m1 m2 =new m1();
        FutureTask<String> f =new FutureTask<String>(m2);
        Thread t =new Thread(f);
        t.start();
        System.out.println(f.get());//注意这里是f
    }
}

class m1 implements Callable{
    @Override
    public Object call() throws Exception {
        for (int i = 0; i < 10; i++) {
            System.out.println(i);
        }
        String s ="111111";
        return s ;
    }
}
```

### 10.3 线程的生命周期

* 线程的五种状态：新建、就绪、运行、阻塞、死亡

![](/Users/yuchenxi/Documents/线程的生命周期.png)

### 10.4 线程的同步（代码块/方法/lock）

* 解决线程安全问题
  * 共享数据，破坏了数据
  * 多个线程的不确定性引起执行结果的不稳定
  * 进入线程进入**sleep等阻塞状态的时候更容易出现安全问题**（这个线程在睡眠等待，另一个已经跑进去操作了）

#### 10.4.1同步代码块

* 锁住多个线程要共享的资源，只允许其中一个线程进行操作

* **==方法synchronized(对象(锁)){ 多条语句操作*共享数据*的代码 }==**//**多个线程必须要用同一把锁**
  * ==继承Thead类时候==：注意有多个Thread类的子类对象时，需要将锁对象用**private static**修饰（因为要保证锁唯一，没有static的话那就每个对象创建的时候都有一个锁了）
  * ==实现接口时候==：锁对象定义成**private**即可（接口实现类一般只创建一个对象作为参数，锁天然就是唯一）（所以也可以**直接让this充当锁**）

*   优点：解决了安全问题
* 缺点：耗费资源，降低程序效率

```java
package Day15Test.practice;

public class test4 {
    public static void main(String[] args) {
        x x1 = new x();
        x x2 = new x();
        x x3 = new x();
        x1.start();
        x2.start();
        x3.start();
    }
}

class x extends Thread {
    private static int t = 200;//用static修饰域，让其属于类，被所有对象共享
    private static Object o = new Object();//注意是private static

    @Override
    public void run() {
        while (true) {
           synchronized (o) {//锁（这里面可以用t.class字节码文件作为参数，保证唯一性）
                if (t <= 0) {
                    break;
                } else {
                    try {
                        Thread.sleep(50);
                    } catch (InterruptedException e) {
                        e.printStackTrace();
                    }
                    t--;
                    System.out.println(Thread.currentThread().getName() + "还剩" + t);
                }
            }
        }
    }
}
```

#### 10.4.2同步方法

* 格式 : **synchronized  返回值类型 方法名（方法参数）{ }**
* 区别：==不能指定锁对象（**有默认的锁，不需要显示地声明。非静态的锁是this；静态的锁是类.class**），并且只能锁住方法中所有的代码==

#### 10.4.3 Lock锁接口（JDK5之后）

* lock()    /   unlock()：经常放在finally中
* **和 synchronized不同之处**：synchronized在执行完相应代码的时候，自动释放同步监视器；lock可以手动调用和结束，较为灵活。

```java
package Day15Test.practice;

import java.util.concurrent.locks.ReentrantLock;

public class test4 {
    public static void main(String[] args) {
        x x1 = new x();
        Thread thread = new Thread(x1);
        Thread thread1 = new Thread(x1);
        Thread thread2 = new Thread(x1);
        thread.start();
        thread1.start();
        thread2.start();
    }
}

class x implements Runnable {
    private static int t = 100;//用static修饰域，让其属于类，被所有对象共享
    private ReentrantLock l = new ReentrantLock();//创建锁对象//构造器可以fair:true

    @Override
    public void run() {
        while (true) {
            l.lock();//调用锁对象的lock()方法
            try {
                if (t <= 0) {
                    break;
                } else {
                    try {
                        Thread.sleep(50);
                    } catch (InterruptedException e) {
                        e.printStackTrace();
                    }
                    t--;
                    System.out.println(Thread.currentThread().getName() + "还剩" + t);
                }
            } catch (Exception e) {

            } finally {
                l.unlock();//unclock解锁，放在finally{}里面
            }
        }
    }
}
```

#### 10.4.4 死锁

* 产生原因：**锁产生了嵌套**，多个线程互相持有对方需要的资源，造成线程处于等待状态，无法继续进行
* 解决方法：避免嵌套使用锁

#### 10.4.5 生产者消费者例子

```java
package Day15Test.practice;

public class test5 {
    public static void main(String[] args) {
        food f =new food();
        cook c =new cook();
        f.start();
        c.start();

    }
}
//while(true ) sy  if if 套路
class food extends Thread {
    @Override
    public void run() {
        while (true) {
            synchronized (desk.lock) {//确保锁对象唯一
                if (desk.count == 0) {
                    break;//汉堡吃完了
                } else {
                    if (desk.flag) {
                        System.out.println("我吃汉堡");
                        desk.flag = false;//吃完汉堡改变flag状态让cook线程进行
                        desk.lock.notifyAll();//唤醒机制，去除阻塞
                        desk.count--;//汉堡数量减去1

                    } else {
                        try {
                            desk.lock.wait();//进入wait()阻塞状态
                        } catch (InterruptedException e) {
                            e.printStackTrace();
                        }
                    }
                }
            }
        }
    }
}

class cook extends Thread {
    @Override
    public void run() {
        while (true) {
            synchronized (desk.lock) {
                if (desk.count == 0) {
                    break;
                } else {
                    if (!desk.flag) {
                        System.out.println("厨师做汉堡");
                        desk.flag = true;
                        desk.lock.notifyAll();
                    } else {
                        try {
                            desk.lock.wait();
                        } catch (InterruptedException e) {
                            e.printStackTrace();
                        }
                    }
                }
            }
        }
    }
}

class desk {//desk是容器，也是让food/cook保持平衡的共同物品
    public static boolean flag = false;//true有，false没有
    public static int count = 10;//汉堡数量
    public static final Object lock = new Object();//此对象就是为了food/cook的lock参数
}
```

* **阻塞队列**
  * ArrayBlockingQueue( 容量)：底层是数组，有界
  * LinekedBlockingQueue( )：底层是链表，无界
  * put( )\take( )

### 10.5 线程的通信

* **wait()：**一旦此方法被执行，当前线程会进入阻塞状态，并且释放锁
* **notify()：**一旦执行此方法，就会唤醒wait进程，如果有多个就唤醒优先级高的那个
* **notifyAll()：**一旦执行此方法，就会唤醒所有wait进程
* **以上三个方法必须在同步代码块/同步方法中**
* **以上三个方法的调用者必须是同步代码块/同步方法中的锁**（比如生产者/消费者中的desk.lock）

### 10.6 线程高级

#### 10.6.1 用线程池创建多线程

* 概念：提前创建好线程，放入线程池，使用时直接提取使用，使用完之后归还给线程池。
* 优点：提高响应速度；降低资源消耗；便于线程管理

```java
package Day15Test;

import java.util.concurrent.ExecutorService;
import java.util.concurrent.Executors;

public class xianchengchiTest {
    public static void main(String[] args) {
        ExecutorService e = Executors.newFixedThreadPool(10);
        e.execute(new q());

        Class<? extends ExecutorService> aClass = e.getClass();
        System.out.println(aClass);//用反射获取类名（ThreadPoolExecutor）
    }
}
class q extends Thread{
    @Override
    public void run() {
        for (int i = 0; i < 100; i++) {
            System.out.println(i+"xxx");
        }
    }
}
```

* 线程池方法：

```java
package Day16Test;

import java.util.concurrent.ExecutorService;
import java.util.concurrent.Executors;

public class es {
    public static void main(String[] args) throws InterruptedException {
        ExecutorService executorService = Executors.newCachedThreadPool();//创建int范围容量的线程池
        ExecutorService executorService1 = Executors.newFixedThreadPool(10);//创建最大容量是10的线程池（初始线程数量是0）
      
        executorService.submit(()-> System.out.println(Thread.currentThread().getName()+"执行"));
        
        Thread.sleep(2000);
        
        executorService.submit(()-> System.out.println(Thread.currentThread().getName()+"执行"));
        
        executorService.shutdown();//关闭线程池
    }
```

* Executors.newCachedThreadPool()创建线程池
  * 如果没有sleep，第一个线程执行还没来得及放回线程池，第二个线程就执行了，所以有两个线程
  * 有sleep之后，第一个线程执行之后，主线程睡眠了两秒，此时第一个线程已经放进线程池，第二个步骤可以直接把第一个线程拿出来用
* ==**ThreadPoolExecutor( )**==:创建自己的线程池对象

```java
package Day16Test;

import java.util.concurrent.*;

public class es {
    public static void main(String[] args) throws InterruptedException {
        ThreadPoolExecutor tpe = new ThreadPoolExecutor(
                5,//核心线程数量
                10,//最大线程数量
                2,//空闲临时线程最大存活时间
                TimeUnit.SECONDS,//时间单位
                new ArrayBlockingQueue<>(10),//阻塞队列（线程池外面排队数量）
                Executors.defaultThreadFactory(),//按照默认方式创建线程对象
                new ThreadPoolExecutor.AbortPolicy());//任务拒绝策略：1.拒绝的原因；2.拒绝的方式。

        tpe.submit(() -> System.out.println(Thread.currentThread().getName() + "线程开始"));

        tpe.shutdown();
    }
}
```

* **任务拒绝策略：**
  * ThreadPoolExecutor.AbortPolicy()是默认拒绝策略，线程数量超出最大线程数量+阻塞队列数量则报异常
  * 其他非默认任务拒绝策略
    * DiscardPolicy ：丢弃任务但是不抛出异常
    * DiscardOldestPolicy：抛弃队列中等待最久的任务，把当前任务加进队列
    * CallerRunsPolicy：调用任务的run方法绕过线程池直接执行

#### 10.6.2 voltile

* 概念：一个线程修改了共享数据，其他线程无法发现的情况
* 原因：堆内存是共享的，栈内存和方法区市每个线程一份，线程从堆里面获取变量，要先拷贝到自己的变量副本。当其他线程修改变量数据的时候，用着变量副本的线程可能还没有发觉变量值已经被修改。
* 解决方法：
  * **给共享变量添加voltile关键字**，强迫线程每次使用的时候，都看一下共享变量的最新值
  * **同步代码块**

#### 10.6.3 原子性

* 概念：不可分割，完整性，某线程做某业务的时候，不可被加塞或者分割，需要整体完整，要么同时成功要么同时失败。

* ==**voltile不保证原子性**==

  * 原因：只能保证共享数据是最新值，但是最新值不能保证是原子性操作的结果

  * 解决方法：**1.synchronized**

  * 解决方法：**2.原子类AtomicInteger( )**//参数可以是指定值（只能保证单一操作时候的原子性）

    * get ()：获取值
    * getAndIncrement()：以原子方式当前值+1，返回自增前的值
    * incrementAndGet()：---，返回自增后的值
    * addAndGet()：以原子方式将参数与对象中的值相加，返回结果
    * getAnfSet()：以原子方式设置为newValue值，返回旧值

    * ==原子类的原理：==内存值V、旧预期值A、要修改的值B。A==V的时候，此时没有其他线程动过数据，可以放心替换（我的就是最新值）；A!=V时候，证明其他线程已经修改过了，此时自己就修改失败了，需要获取最新的值，再进行操作。这个过程就是**自旋**。

    ```java
    package Day16Test.practice;
    
    import java.util.concurrent.atomic.AtomicInteger;
    
    public class yuanzixingTest {
        public static void main(String[] args) {
            date d = new date();
            for (int i = 0; i < 20; i++) {//造出20条线程
                new Thread(() -> {
                    for (int i1 = 0; i1 < 1000; i1++) {
                        d.addAtomic();//保证原子性
                        d.addpp();//不保证原子性
                    }
                }).start();
            }
    
            System.out.println(d.ai + "AtomicInteger");//结果是20000
            System.out.println(d.number + "Normal");
        }
    }
    
    class date {
        int number = 0;
    
        public void addpp() {//普通方法自增
            number++;
        }
    
        AtomicInteger ai = new AtomicInteger();//创建原子类对象
    
        public void addAtomic() {
            ai.getAndIncrement();//以原子方式自增，
        }
    }
    ```

#### 10.6.4 悲观锁/乐观锁

* **syn**每次获取数据的时候**默认别人都可能修改过**，所以每次操作共享数据之前，都会上锁；
* **cas**是**假设每次获取数据时候别人都不会修改**，所以不会上锁，只是在修改共享数据的时候会检查下别人有没有修改过这个数据。修改过就直接获取最新值 /没修改过就直接修改；

#### 10.6.5 并发工具类

* **Hashtable：**线程安全（悲观锁），效率低（每次只能让一条线程访问）
* **ConcurrentHashMap：**线程安全，效率高（**原理（JDK7版本）：**数组（长度16，加载因子0.75，创建之后就无法扩容）每个格子上面也都是有一个HashEntey（如果此位置是null的话）,计算位置，确认位置是空的，放进去。二次hash找到HashEntey中的位置（没有元素直接存，有元素就调用equals方法确认是否重复再存入）。线程安全原因是只锁住HashEntry表。（最多可以有16个线程访问）；（**JDK8版本**会将红黑树（链表长度超过8自动转成红黑树）根节点/链表的头节点锁起来保证数据安全性）
* **CountDownLatch**：在某一条线程在其他线程执行完毕之后再执行。构造方法参数是等待线程的数量
* **Semaphore**：参数是可以同时执行的线程的数量； acquire():获得通行证、行驶（操作）、release():归还通行证



## 11. 网络编程

### 11.1 概述

* 网络编程的两个要素：
  * 1.<u>提供**IP**/**端口号**</u>
  * <u>2.提供网络通信协议：</u>TCP/IP参考模型（应用层、传输层、网络层、物理+数据链路层）

### 11.2 通信二要素

* **1.IP/端口号：**

  * ==IP地址==：IPV4/IPv6 ；公网地址/局域网地址（192.168开头）；**（JAVA中的是InetAddress类代表IP）**
  * 域名；本地回路地址：127.0.0.1（对应：localhost）（一般在测试中指代本机）

  ```java
     package Day17Test;
  
  import java.net.InetAddress;
  import java.net.UnknownHostException;
  
  public class inetaddress {
      public static void main(String[] args) throws UnknownHostException {
          InetAddress localhost = InetAddress.getLocalHost();//获取本机地址
          System.out.println(localhost);
  
         // InetAddress iname = InetAddress.getByName("www.vip.com");//报错了？
          //System.out.println(iname);
  
          InetAddress iname2 = InetAddress.getByName("192.168.10.14");
          System.out.println(iname2);
  
          System.out.println(iname2.getHostName());//域名
          System.out.println(iname2.getHostAddress());//ip地址
      }
  }
  ```

  * ==端口号==：**标识正在计算机上运行的进程（程序）**。（一个16位的整数：0-65535）
    * 公认端口：0-1023；知名的网络服务/应用
    * 注册端口：1024-49151：分配给用户进程/应用程序
    * 动态/私有端口：49152-65535
  * **端口号+IP地址=Socket**

* **2.网络通信协议：**

  * TCP协议：

    * 在使用TCP协议前需要**建立TCP连接**形成数据通道

    * ==三次握手==：1.**客户端**向**服务器**发出连接请求，等待服务器确认。2.服务器向客户端返回一个响应，告知已收到请求。3.客户端向服务器再次发出确认信息，连接建立。
    * ==四次挥手==：停止连接的时候；1.客户端发送取消连接请求；2.服务端回应；3.服务器处理最后数据并发送确认消息；   ；4.客户端确定解除连接
    * 传输完毕要释放已经建立的连接，效率低。

  * UDP协议：

    * 无需建立连接（不可靠），**每个数据报**64k以内
    * 可以广播发送，数据发送结束无需释放资源，速度快，开销小

### 11.3 TCP网络编程

* **发送及接收数据：**

```java
package Day17Test;

//创建socket对象，指明要发信息给的服务端的ip+端口号
//创建一个输出流ops对象，写数据
//关闭资源

//创建serversocket,指明自己端口号
//调用accept方法
//创建输入流ips，读取输入流的资源。创建输出流对象baos，调用tostring方法打印
//关闭资源

import java.io.IOException;
import java.io.OutputStream;
import java.net.InetAddress;
import java.net.Socket;
import java.nio.charset.StandardCharsets;

public class testKeHuDuan {
    public static void main(String[] args) throws IOException {

        InetAddress inet = InetAddress.getByName("192.168.12.74");
        Socket socket = new Socket(inet, 6399);//TCP需要直接new Socket(没有前缀)

        OutputStream ops = socket.getOutputStream();//用Scoket对象调用方法获取输出流

        ops.write("俞晨曦".getBytes(StandardCharsets.UTF_8));//getBytes()方法直接将字符串按照输入的格数转变成字节数组,让ops直接write

        ops.close();
        socket.close();

    }
}
//------------------------------------------------------------------

package Day17Test;

import java.io.ByteArrayOutputStream;
import java.io.IOException;
import java.io.InputStream;
import java.net.ServerSocket;
import java.net.Socket;

public class testFuWuDuan {
    public static void main(String[] args) throws IOException {

        while (true) {//套无限循环让服务端不停接收客户端的信息
            ServerSocket ss = new ServerSocket(9399);
            Socket socket = ss.accept();//接受来自客户端的socket
            InputStream is = socket.getInputStream();

            ByteArrayOutputStream baos = new ByteArrayOutputStream();//创建此类的输出流，防止汉字字节被切割
            byte[] b = new byte[5];
            int len;
            while ((len = is.read(b)) != -1) {//read方法也是阻塞的（客户端close()的时候会让read解除阻塞）
                baos.write(b, 0, len);
            }
            System.out.println(baos.toString());//注意此处是调用baos的toString方法

            System.out.println("发送者的ip是"+socket.getInetAddress());//打印发送者的ip

            baos.close();
            is.close();
            socket.close();
            ss.close();
        }
    }
}
//如果是想给别人发东西的话，可以先让对方写服务端，告诉我端口号、IP地址；我更改输入他的IP地址和端口号，启动程序发送即可
```

* **传输信息并且要求服务端返回数据**

```java
package Day17Test.TCPfuxi.TPC1WenZiChuanShu.Client;

import java.io.BufferedReader;
import java.io.IOException;
import java.io.InputStreamReader;
import java.io.OutputStream;
import java.net.Socket;

public class client {
    public static void main(String[] args) throws IOException {
        Socket socket = new Socket("127.0.0.1", 5413);//首先创建socket对象
        OutputStream ops = socket.getOutputStream();//用socket对象创建ops

        ops.write("复习TPC-test-1".getBytes());//将字符串直接转成字节数组
        ops.flush();
        socket.shutdownOutput();//对于要求服务端返回代码的操作来说，这一步是关键，能解除服务端的read阻塞。不然程序会一直卡死在这里

        BufferedReader br = new BufferedReader(new InputStreamReader(socket.getInputStream()));
        String s;
        while ((s = br.readLine()) != null) {
            System.out.println(s);
        }

        br.close();
        ops.close();
        socket.close();
    }
}

//--------------------------------
package Day17Test.TCPfuxi.TPC1WenZiChuanShu.Client;

import java.io.*;
import java.net.ServerSocket;
import java.net.Socket;

public class server {
    public static void main(String[] args) throws IOException {
        ServerSocket ss = new ServerSocket(5413);
        Socket socket = ss.accept();
        InputStream ips = socket.getInputStream();

        ByteArrayOutputStream baos = new ByteArrayOutputStream();//要用baos防止中文字符被切割
        byte [] b =new byte[1024];
        int len;
        while ((len=ips.read(b))!=-1){
            baos.write(b,0,len);
        }
        System.out.println(baos.toString());
        baos.flush();

        BufferedWriter bw = new BufferedWriter(new OutputStreamWriter(socket.getOutputStream()));
        bw.write("已经收到");//因为已经使用了转换流-缓冲流，字符串直接输入就行
        bw.newLine();
        bw.flush();

        bw.close();
        baos.close();
        ss.close();
        socket.close();
    }
}
```

* **用客户端、服务端传输文件并且让服务端返回“传输成功”**
* **UUID类**：静态randomUUID:生成随机且唯一的UUID对象

* **==多线程网络编程==**（使用线程池）

```java
package Day17Test.TCPfuxi.TPC2DuoXianCheng;

import java.io.*;
import java.net.ServerSocket;
import java.net.Socket;
import java.util.concurrent.ArrayBlockingQueue;
import java.util.concurrent.Executors;
import java.util.concurrent.ThreadPoolExecutor;
import java.util.concurrent.TimeUnit;

public class test {//这个是服务端使用线程池，客户端不变
    public static void main(String[] args) throws IOException {
        ServerSocket ss = new ServerSocket(5413);
        ThreadPoolExecutor pool = new ThreadPoolExecutor(5,
                10,
                10, TimeUnit.SECONDS,
                new ArrayBlockingQueue<>(5),
                Executors.defaultThreadFactory(),
                new ThreadPoolExecutor.AbortPolicy()
        );//创建线程池对象

        while (true) {
            Socket socket = ss.accept();
            t t = new t(socket);//创建类的对象
            Thread ts = new Thread(t);
            //  ts.start();
            pool.submit(ts);//使用submit
        }
    }
}

class t implements Runnable {
    private Socket socket;//创建域和构造方法，将创建对象时输入的域值作为变量使用

    public t(Socket socket) {
        this.socket = socket;
    }

    @Override
    public void run() {
        ByteArrayOutputStream baos = null;
        BufferedWriter bw = null;

        try {
            InputStream ips = socket.getInputStream();

            baos = new ByteArrayOutputStream();//要用baos防止中文字符被切割
            byte[] b = new byte[1024];
            int len;
            while ((len = ips.read(b)) != -1) {
                baos.write(b, 0, len);
            }
            System.out.println(baos.toString());
            baos.flush();
            bw = new BufferedWriter(new OutputStreamWriter(socket.getOutputStream()));
            bw.write("已经收到");//因为已经使用流转换了-缓冲流，字符串直接输入就行
            bw.newLine();
            bw.flush();
        } catch (IOException e) {
            e.printStackTrace();
        } finally {
            if (bw != null) {
                try {
                    bw.close();
                } catch (IOException e) {
                    e.printStackTrace();
                }
            }
            if (baos != null) {
                try {
                    baos.close();
                } catch (IOException e) {
                    e.printStackTrace();
                }
            }
            if (socket != null) {
                try {
                    socket.close();
                } catch (IOException e) {
                    e.printStackTrace();
                }
            }
        }
    }
}
```

### 11.4 UDP网络编程

* **单播（一对一）：**

* ==发送端：==
  * 创建发送端**DatagramSocket**对象dgs
  * 创建数据**DatagramPacket（数组，长度，地址，端口）**对象dgp
  * 调用发送端对象传输**dgs.send(dgp)**数据对象
  * 释放资源
* ==接收端：==
  * 创建接收端**DategramSocket(端口号(和发送端对应))**对象ds
  * 创建**DatagramPacket（数组，长度）**对象dp
  * 接收端对象**ds.receive(dp)（阻塞方法）**，调用**dp.getData()**(相当于拿出数据)获取字节数组，释放资源
  * **(必须先运行接收端，再运行发送端)（调用getLength()方法，获取len，避免空格）**

```java
package Day17Test.practice;

import java.io.IOException;
import java.io.UnsupportedEncodingException;
import java.net.*;

public class udpTest{
    public static void main(String[] args) throws IOException {
        DatagramSocket dgs = new DatagramSocket();

        String s ="哈哈哈哈";
        byte[] sBytes = s.getBytes();

        DatagramPacket dgp = new DatagramPacket(sBytes,sBytes.length, InetAddress.getByName("127.0.0.1"),8787);

        dgs.send(dgp);

        dgs.close();

    }
}
//----------------------------------------------------------------------
package Day17Test.practice;

import java.io.IOException;
import java.net.DatagramPacket;
import java.net.DatagramSocket;
import java.net.SocketException;

public class udpTest2 {
    public static void main(String[] args) throws IOException {
        DatagramSocket ds = new DatagramSocket(8787);//指定端口号
        byte [] b =new byte[1024];
        DatagramPacket dp = new DatagramPacket(b, b.length);
        ds.receive(dp);

        byte[] data = dp.getData();
        int len = dp.getLength();
        String s = new String(data,0,len);

        System.out.println(s);//9

        ds.close();
    }
}
```

* **组播（一对多）**
  * 组播地址（和单播地址的区别）（如：224.0.1.0）
  * ms.joinGroup(InetAddress.getByName("224.0.1.0"))：绑定组播地址

* **广播（一对所有）**
  * （255.255.255.255）

### 11.5 注解

* 代码中的特殊标记，类似于修饰符，程序运行的时候会被加载。写给虚拟机看的

* ==框架=注解+反射+设计模式==

#### 11.5.1 注解的三个阶段

* **注解存在的三种个阶段：**
  * Java 源文件阶段：如@override ，编译完成即被丢弃
  * class文件阶段：JVM运行.class时被丢弃
  * 运行时阶段：存活到JVM运行程序的时候

#### 11.5.2 自定义注解

* **自定义注解：**

```java
package Day19Test;

public @interface ttttt {
     int b() default 100;//默认值可写可不写

     String name();//没有默认值的

     Class clazz() default test.class;//Class类型的

     t west() default t.West;//枚举类型的

     int[] arr() default {1,2,3};//数组类型的

}
```

* **value：** 当自定义注解里面讲一个属性定义命名为value，且只有它一个的时候。添加注解的时候（）里面只需要写值就行。如 : @test（2233） 

* **注解+反射：（如何获取带有注解的自定义方法）**(isAnnotationPrensent( 注解.class )方法，返回布尔值)

#### 11.5.3 元注解

* **元注解：注解的注解**

  * @Target：指定注解在哪里使用
  * @Retention：注解的生命周期
  * @Inherited：表示此注解可以被子类继承

  ```java
  @Target({ElementType.FIELD,ElementType.METHOD})//指定此注解在域、方法中使用
  @Retention(value = RetentionPolicy.RUNTIME)//控制注解的存活阶段
  @Inherited//该注解可以被继承
  ```

