# test
2022.11.6 仅用于测试
2022.11.7 C文件新增 计算机提供随机1-100数，用户猜数输出猜的次数   使用stdlib.h  tine.h  两个库，并使用srand(time(0))   rand()生成随机数
2022.11.8 C文件新增 1、计算机读取用户提供的数字，数量不固定，以-1结尾，计算算术平均数，两种方法 if else 加 do while   另一种while。
                   2、用户输入数字，计算机倒序输出，分为输出数字例如 用户输入700 计算机输出007；和输出数例如 用户输入700 计算机输出7；
2022.11.9 C文件新增 1、阶乘的计算
                   2、循环共有三种while/do while/for;
                   3、i++和++i的区别 
                   在独立语句中等价  
                   在赋值时 i++ 例如 int m; int i=1;  m=i++; printf("%d %d",m,i); m=1 i=2  先赋值，然后在运算 先将i的值赋给m，在进行i++；
                           ++i 例如 int m; int i=1;  m=i++; printf("%d %d",m,i); m=2 i=2   先运算，在赋值  先计算++i，在将++i赋给m；
                    在条件语句中，i++  int i=0; while（i++）会判定先赋值 即while（0），然后在运算i++；
                                 ++i  int i=0; while（++i）会判定先运算++i，然后在赋值 即while（1）；
2022.11.10 C文件新增 1、对于三种循环的选择，有固定次数的一般选择for循环；必须要做一次的选择do while 循环； 其他情况用while；
2022.11.11
2022.11.12 C文件新增  break和continue在循环语句中的用法，以及两个的区别
                     break： 在循环的执行中中遇到break则直接结束整个循环，跳出循环，执行下面的东西；
                     continue：在循环的执行中遇到continue则不执行continue后面的循环语句的内容，转而继续执行循环下一轮；而且continue只会跳过其所在循环外面对最近的一个循环任务；
2022.11.13 C文件新增  1、输出100以内的所有素数，用到了嵌套的循环
                     2、输出从0开始的前50个素数，用到了循环嵌套，以及break 跳出嵌套的循环，与2022.11.12 break的用法相似；
                     3、输出50个数（使用的是stdlib.h和time.h srand(time(0)) rand() 来创建50个随机数，尽管是一样的50个数），让他们每5个一行；
                     4、接力break跳出嵌套循环，注意：在使用break跳出每一层循环时一定要判断是需要跳出循环的时候，还是恰好程序运行到这里偶遇break；
		     5、goto out; 
		        out:  跳出循环到指定位置  要在很特定的场合下使用；

周总结 ：     1、m = abs(n)
                计算n的绝对值；
             2、#include<stdlib.h>
                #include<time.h>
                srand(time(0));
                int number = rand()%100+1;
                创建随机数；
             3、break  是直接跳出循环，并不在做这个跳出的循环；接力break跳出嵌套循环，在使用break跳出每一层循环时一定要判断是需要跳出循环的时候，还是恰好程序运行到这里偶遇break；
                continue 是不做这个循环里面在continue下面的语句，转而继续做这个循环剩下的步骤；
             4、i++和++i的区别
                i++ 是先把i的值拿去做要做的事，例如赋值，例如判断，然后在对i进行+1；
                ++i 是先把i=i+1做了，然后在用i去做要做的事，例如赋值，例如判断；
	     5、goto out;
		out: 
   		用这个来直接从一个地方跳到任意地方 特定情况下使用；
                
2022.11.14 C文件新增 C语言的数据类型：1、整形（char\short\int\long\longlong）、浮点型(float\double\long double)、指针、逻辑(bool);
                                    2、怎么判断数据类型的大小：size of(int/short...)这样就能输出不同的数据类型的空间大小;64位
                                       char 1byte\short 2byte\int 取决于计算机CPU\long 取决于计算机CPU\long long 8byte\float 4byte\double 8byte;
				       对于int的大小取决于计算机硬件的构造，它的大小是用来表示CPU和RAM之间通过CAN总线一次所能传递的最大字节数，32位计算机一次
				       最多能在CPU和RAM中传递4字节，所以这里的int的大小就是4byte；而64位计算机CPU和RAM中就能传递8字节，所以此时的int大小是8byte；
                                    3、在printf中输出不同的数据类型需要用到不同的结构
                                       int        printf("%d") scanf_s("%d")
                                       long       printf("%ld") scanf_s("%ld")
                                       long long  printf("%lld") scanf_s("%lld")
                                       float      printf("%f") scanf_s("%f")
                                       double     printf("%f") scanf_s("%lf")
2022.11.15 C语言知识点：原码、反码、补码这三种表示方式都是为了解决计算机减法计算的问题；
                       正数原码、反码、补码都一样；
		       下面是负数的
		       原码：以4位2进制数来说最高位是符号位，0是正号、1是负号另外三个位置表示的是数，例如0010是+2、1010是-2；
		       反码：以4位2进制数来说 在原码的基础上，保持最高位符号位不变，对后三位全部取反得到的就是反码；例如：-2原码是1010，那它的反码就是1101；
		       补码：以4位2进制数来说，所谓补码就是例如-2的补码假设是x，-2和x在计算机做减法的时候是一样的效果，这就是补码，而补码涉及到 模（4位的模就是16、8位是256）、
		             同余数（-2的同余数就是 模16-2=14），也就是说在计算机计算中 例如4-2=2可以等价与4+14=2，所以14所代表的二进制数1110把它的最高位看作是符号位，那么这个		                 二进制数1110就是-2的补码，，最高位1也就是代表-号，也就明白了为什么1代表-号0代表+号；
			     所以计算一个负数的补码就很简单了，就是这个负数的同余数；
2022.11.16 C文件新增：unsigned的用法，在定义一个变量的时候例如：char i=255；int m=255;在用%d输出这两个变量的时候，i=-1；m=255；原因是char是1位也就是8bit存放255的二进制的时候是
	 	     11111111，而在二进制中最高位的1/0代表的是-和+，所以系统认为这是-1；而m是4位32bit 在存放时是00000000 00000000 00000000 11111111 ，所以m还是255，但是当char                      加上unsigned之后就变成了无符号变量，这样最高位的1就不再表示正负，而是参与存放数字，因此 unsigned char i=255 ；输出时 i=255；
2022.11.17 C文件新增：8进制和16进制，在输出时%o代表输出的是8进制；%x代表输出的是16进制；加入想要输出1A这个16进制数，那么%X中的X就需要大写；
2022.11.18 C文件新增： 1、强制类型转换的函数 （double）(a) 强制将a转换为double类型；
                      2、
2022.11.22 C文件新增： 特殊转义字符 \n 换行；\t 将光标移动至从头向后一个固定的距离；\b 将光标向前移动一位，继续输出；\" 输出" ；\' 输出' ；\\ 输出\ ；
2022.11.26 C文件新增：  bool量：只能输出0或1；
                       条件运算：（a>b）?a++:b++;  意思是如果a>b那么a++，否则b++;
                       逗号表达式： a=(3+4,5+6) 此时a的值是11，也就是说这个赋值运算中a被赋的是逗号后面的式子的值；
2022.11.27 C文件新增： 函数的调用，在调用函数时，需要给函数输入变量，输入的变量需要是赋值的变量

