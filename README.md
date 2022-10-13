//#include <stdio.h>    //包含头文件，声明本段代码已包含标准输入/输出库函数（stand input output），后续可直接调用
//int main()   
//{
//	printf("Hello World\n");
//	return 0;   //返回 整型值0;
//}

// 1.1 C语言的数据类型-基本类型:（除基本类型外，还有 构造类型/指针类型/空类型）
// 字符型：char 字符型（1byte）  // 字符型数据用单引号'A'(字符型只能包括一个字符，不能是字符串如'AA';字符串则用双引号"ABC"表示//字符串"ABC"实际上是"ABC\0",其中\0是字符串的结束标志)
//#include <stdio.h>  
//int main()
//{
//	char arr1[] = "abc";
//	char arr2[] = { 'a','b','c' };
//	printf("%d\n",strlen(arr1));//输出3
//	printf("%d\n", strlen(arr2));//输出随机值，随机在'a''b''c'之后找到一个\0后结束   arr2增加0或'\0'便输出3
//	return 0;  
//}
// 
// 整型：int 基本整型（4bytes）、short int 短整型（2bytes）、long int 长整型（4/8bytes）、long long int双长整型（8bytes）、unsigned 无符号整型、signed 有符号整型
// 浮点型/实型：float 单精度浮点型（4bytes）、double 双精度浮点型（8bytes）
// 枚举类型-关键字：enum
//        
//   定义一个数组（存放多个同类型的数据）
//   int arr1[10]={1,2,3,4,5,6,7,8,9,10};//数组内数据的下标从0开始计数，如printf("%d\n",arr[8])→9
//   float arr2[100];
// 
// 定义变量：
// int age=18;
// float weight=75.1;
// char F='好';
// 
// 1.2 全局变量和局部变量（区别：函数体{}的内外）
//#define _CRT_SECURE_NO_WARNINGS  //不显示编译可能的错误，如scanf\strcpy\strlen\strcat
//#include <stdio.h>
// int year=2022;
// int main()
// {
// int year=1997; //一般而言,全局变量和局部变量最好使用不同的名字，当重合时，局部变量优先级更高
// int month=9;
// int sum = 0;
// scanf("%d%d", &year, &month);
// sum =year + month; //常见的运算符：%取模、/除法
 //printf("sum=%d\n",sum);
 //return 0;
 //}
// 
 //1.3 常量和变量：
 //常量：整型常量8、浮点型常量1.14、字符型常量'A'、符号常量year=2022;  
 // const 修饰的变量--让一个变量始终保持不变/常变量
 // #define 定义的标识符常量
 //变量：整型变量、浮点型变量、字符型变量;
//  
//1.4 常见的转义字符：\n换行、\t水平制表符(类似tab键)、\v垂直制表符、\b退格、\r回车、\f走纸换页、\a鸣笛警告
//                    \\保持反斜杠本身（避免错误解析）、\'保持单引号本身、\"保持双引号本身
//					  \ddd：ddd表示1-3个八进制的数字（如\130）、\xdd：dd表示2个十六进制的数字(如\x61)
//                                （八/十六进制→十进制→ASCII码所对应的字符）
//
//1.5 算术运算符、关系运算符、逻辑运算符
//  ++ 自增运算：变量每次加1   // b=a++ 后置++，先使用a的值再+1；b=++a，前置++,先+1再使用a
//  -- 自减运算：变量每次减1
//  >= 大于等于
//  <= 小于等于
//  != 不等于
//  == 等于    //注意和=的区别
//  = 赋值运算符 （还有+=、-=、%=、&=、^=、/=、>>=、<<=、|=、*=） a=a+3等价于a+=3
//  && 逻辑 与；同真为真； eg： int a = 0（假）；int b = 2（!0为真）；int c = a&&b（==0）。
//  || 逻辑 或
//  !  逻辑 非
//  ～ 按(二进制)位取反
//  *  指针运算符/解引用操作符
//  [] 下标引用运算符
//  -> 指向结构体成员运算符
//  .  结构体成员运算符
//  ， 顺序求值运算符
//  sizeof  长度运算符
//  &  按位 与 / 地址 与
//  ^  按位 异或
//  |  按位 或
//  （变量类型）强制类型转换； int A = （int）3.14；
//
//
//  条件/三目运算符(?:)、逗号/顺序求值运算符(,)
//  exp1？exp2：exp3；    表达式exp1成立则执行exp2，不成立则执行exp3；
//  eg：
//  int a =1；
//  int b =2；
//  int c =0；
//  c = （a＞=b？a：b）  //c = 2
//
// 1.6 常用的关键字
// auto 用于定义一个局部变量为自变量（常被省略） eg： auto int a = 1；
// break 
// case
// const
// continue
// default
//          利用 #define定义标识符常量 和 宏(带参数) //define不是关键字
//          eg：  
//			#define GDP 10000;
//			#define MAX（x，y）（x＞y？x：y）        
// do 
// double
// else 
// enum 枚举
// extern 外部存储变量；在同一个源文件中，不同的 .c文件之间的全局变量/函数可以相互引用。
// float 
// for
// goto
// if
// long
// register 寄存器存储（将常用变量存储在硬件寄存器中，而非内存中，以提高程序的运算速度） eg： register int a = 1；
// return
// short
// signed 符号变量（常被省略）eg： signed int a = 1；       
// sizeof
// static 静态变量；
//			修饰局部变量，延长其生命周期——表示第一次执行时保持本身的值，在随后执行过程中变量保持函数上一次执行时的值；
//			修饰全局变量，缩小其作用域——所修饰的全局变量只能在自身所在的源文件中内部使用；（外部链接属性变为内部链接属性）
//			修饰函数，类似修饰全局变量；
// struct 结构体关键字
// switch
// typedef 类型重新定义  eg： unsigned int a = 1；等价于 typedef unsigned int u_int; u_int a =1 ;
// union 联合体/共用体
// unsigned
// void 空 1、放在返回值位置上，表示此函数执行完不返回任何值；2、放在参数位置上，表示无形式参数
// volatile
// while
// 
// 1.7 指针
//  计算机内存中，每一个内存单元 存储 一个byte，系统按照byte对每个内存单元进行编号。如 int a = 10，整型变量占用4bytes，如存储在编号为512-515的内存编号之中。
//	这时候想要知道 a 的地址，则使用 &a；如下：
 //#include<stdio.h>
 //int main()
 //{
 //int a = 1;
 //printf("%p\n",&a); //0x00000058BAB5F744
 //int* b = &a; //此时b记录的便是a的hex地址，64bit电脑中一个“指针”sizeof b = 8 （byte）
 //printf("%d\n", sizeof b);//8
 //*b = 2; // *b原本为a==1，此处将2赋值给*b，原本存储的1变为2
 //return 0;
 //}
// 
// 1.8 顺序结构、选择结构、循环结构
//  分支语句：if、switch
//  循环语句：while、do……while、for
// 
//                                               if语句的基本形式
// 单分支eg：   
// #include<stdio.h>
// int main()
// {
// int age =25;
// if(age＞18)  //if（表达式）后不加分号
// printf（"你成年了\n"）;
// return=0;
// }
// 双分支eg：
// #include<stdio.h>
// int main()
// {
// int age =25;
// if(age＜18)
// printf（"你未成年\n"）;
// else
// printf（"你成年了\n"）;
// return=0;
// }
// 多分支eg：
//
// #include<stdio.h>
//int main()
// {
// int age = 56;
// if (age < 18)
//	 printf("未成年人\n");
// else if (age >= 18 && age < 35)
//	 printf("青年人\n");
// else if (age >= 35 && age < 50)
//	 printf("中年人\n");
// else if (age >= 50 && age < 65)
//	 printf("壮年人\n");
// else     //else自动和最近未匹配的if进行匹配，而非简单地和对齐的if匹配，如需要隔离则添加{}
//	 printf("老年人\n");
// return 0;
// }
//
//例题：输出1-100之间的奇数
// #include<stdio.h>
//int main()
//{
// int a = 1;
// while(a<=100)
//	{
//	 if(a%2 == 1)
//		 printf("%d\n",a);
//	 a++;
//	}
// return 0;
// }
//
//                                       switch语句的基本形式——常用于多分支、避免多层if嵌套
//#define _CRT_SECURE_NO_WARNINGS
//#include<stdio.h>
//int main()
// {
//	int num;
//	int b;
//	printf("请在此输入任意正整数:\n");
//	scanf("%d", &num);
//	b = num % 3;
//	switch (b)  //必须为整型表达式
//	{
//	case 1:     //case后面必须为整型常量表达式，注意不要忘记冒号：case中可嵌套if、switch等语句
//	case 2:
//		printf("所输入的整数不是3的倍数\n");
//		break;  //若满足case2则从此跳出，break非switch语句所必需；一般而言，最后一个case最好加上break
//	default:    //剩余部分放在此处，可选
//		printf("所输入的整数是3的倍数\n");
//		break;
//	}
// return 0;
// }
//
//                                              while语句的基本形式
//输出1到50的整数
// #define _CRT_SECURE_NO_WARNINGS
//#include<stdio.h>
//int main()
//{
//	int a = 0;
//	while (a <= 100)  //if、while后都没有分号
//	{
//		a++;
//		if (51 == a)
//			break;    //break永久跳出循环；对比continue，跳过本次循环，回到while语句判断部分
//		printf("a等于:%d\n", a);
//	}
//	return 0;
//}
//
//getchar 和 putchar 的使用
//#define _CRT_SECURE_NO_WARNINGS
//#include<stdio.h>
//int main()
//{
//	int ch = 0;
//	while ((ch = getchar()) != EOF)   //接收字符、end of file
//	{
//		putchar(ch); //输出字符
//	}
//	return 0;
// }
// 
//
//一个输入密码的小程序
// #define _CRT_SECURE_NO_WARNINGS
//#include<stdio.h>
//int main()
//{
//	int a = 0;
//	int b = 0;
//	char password[50] = { 0 };
//	printf("请在此输入你的密码：");
//	scanf("%s", password);
//	while ((b = getchar()) != '\n')   //读取缓冲区数据以清空数据，便于a=getchar接收下一步信息
//	{
//		;     //注意分号，空语句
//	}
//	printf("你输入的密码是：%s\n", password);
//	printf("请输入Y/N以确认你的密码:");
//	a = getchar(); //接收Y/N
//	if (a == 'Y')
//		printf("密码确认成功");
//	else
//		printf("密码确认失败");
//	return 0;
//}
// 
// 
//                                             do…while语句的基本形式
//do
// {
//   语句块（循环体）
// }
// while（表达式）;    //分号别忘
// 
// 
// 计算1到n的代数和
//#define _CRT_SECURE_NO_WARNINGS
//#include<stdio.h>
//int main()
//{
//	int n = 0;
//	int i = 0;
//	int sum = 0;
//	printf("请输入一个正整数：");
//	scanf("%d",&n);
//	do
//	{
//		sum = sum + i;
//		i++;
//	} while (i <= n);  //当满足while内的条件时继续执行do循环
//	printf("%d", sum);
//	return 0;
//}
//
//                                                for语句的基本形式
// for(exp1;exp2;exp3)  //for(循环变量赋初始值;循环条件;循环变量的调整)
//	{语句块}
//
//计算1到n的代数和
//#define _CRT_SECURE_NO_WARNINGS
//#include<stdio.h>
//int main()
//{
//	int n = 0;
//	int i = 0;
//	int sum = 0;
//	printf("请输入一个正整数：");
//	scanf("%d",&n);
//	for (i = 0; i <= n; i++)
//	{
//		sum = sum + i;
//	}
//	printf("%d\n", sum);
//	return 0;
//}
//
//     for语句表达式的省略
//#define _CRT_SECURE_NO_WARNINGS
//#include<stdio.h>
//int main()
//{
//	for (;;)    //三个exp都可省略，当exp2循环条件被省略，那么即：恒为真；一般而言，不要省略；	
//	{printf("死循环\n");}
//	return 0;
//}
//
//例题：
//#define _CRT_SECURE_NO_WARNINGS
//#include<stdio.h>
//#include<string.h>
//#include<windows.h>
//#include<stdlib.h>
//int main()
//{
//	char arr1[] = "Guess what you will see on the screen";
//	char arr2[] = "#####################################";
//	int left = 0;
//	int right = strlen(arr1) - 1;//寻找最右端"n"的下标
//	while (left <= right)
//	{
//		arr2[left] = arr1[left];
//		arr2[right] = arr1[right];
//		printf("%s\n", arr2);
//		Sleep(100);   //每打印一次延时100ms——#include<windows.h>
//		system("cls");     //执行系统命令——#include<stdlib.h>；"cls"清屏指令
//		left++;
//		right--;
//	}
//	printf("%s\n", arr2);
//	return 0;
//}
//
//例题：打印乘法口诀表
//#include<stdio.h>
//int main()
//{
//	int i = 1;
//	for (i = 1; i <= 9; i++)
//	{
//		int j = 1;
//		for (j = 1; j <= i; j++)
//		{printf("%d*%d=%-3d", i, j, i * j); }  //3表示打印3位，-表示向左对齐
//	printf("\n");		
//	}
//	return 0;
//}
//
//                        break\continue\goto语句（goto+again常用于从深度嵌套语句中跳出）
// 
// 
//                                                                                                                             
//                           2.1  函数 ：  库函数 和 自定义函数  www.cplusplus.com    www.cppreference.com                           
//  库函数：IO函数、字符串操作、字符操作、内存操作、时间/日期、数学……
#define _CRT_SECURE_NO_WARNINGS
#include<stdio.h>
#include<string.h>
#include<stdlib.h>
#include<math.h>
//int main()
//{
//	system("cls");
//	char arr1[] = "AAAAAAAAAA";
//	char arr2[] = "BBBBBBBBBBBB";
//	strcpy(arr2,arr1);                  //字符串替代函数
//	printf("%s\n", arr2);
//	return 0;
//}
//
//{
//	system("cls");
//	char arr1[] = "AAAAAAAAAAAA";
//	int num = 6;
//	memset(arr1, '1', num);     //内存替代函数
//	printf("%s\n", arr1);
//	return 0;
//}
//
//   自定义函数的语法格式：
//   int AddTwoNum（int Num1,,int Num2）   //函数头
//		{                               
//      int sum;
//		sum=Num1+Num2;
//		return sum;
//       }                                 //函数体
//
// 
//void exchange(int* x,int* y)       //自定义交换x和y函数（从指针入手）、void表示无返回值
//{
//	int z = 0;
//	z = *x;
//	*x = *y;
//	*y = z;
//}
//int main()
//{
//	system("cls");
//	int a = 111;
//	int b = 222;
//	printf("a=%d b=%d\n",a, b);
//	int* pa = &a;    //pa来存储a的地址
//	int* pb = &b;
//	exchange(&a, &b);          //传递过去的不是a和b的值，而是a和b的地址   
//	//如果直接传递实参，那么形参实例化之后其实相当于实参的一份临时拷贝，对形参的改变不会影响实参
//    //调用函数的两种方式：1、传值调用（形参和实参分别占用不同的内存，对形参的改变不会影响实参）；2、传址调用（使得函数内外建立实质性联系，使得函数内可以直接操作函数外的变量）。
//	printf("a=%d b=%d\n",a, b);
//	return 0;
//}
//                                        形式参数 和 实际参数
//形式参数：如Exchange括号中的x和y
//实际参数：实际传递给Exchange的参数，如上面的&a和&b     //可以是常量、变量、数组、指针、表达式等
//
//函数例子：有序数组中（通过二分法）查找某个数
int binary_search(int arr[], int k,int right)
{
	int p = -1;                          
	int left = 0;
	//int right = sizeof(arr) / sizeof(arr[0]) - 1;   //此处right==1,仅仅传送了arr的第一个元素;解决方法：函数增加一个right参数，直接在函数外计算right再传进来
	int mid = (left + right) / 2;               //先找出数组中的中间元素
	while (left<=right)                     
	{
		if(arr[mid]>k)
		{
			right = mid - 1;
			mid = (left + right) / 2;
		}
		else if(arr[mid<k])
		{ 
			left = mid + 1;
			mid = (left + right) / 2;
		}
		else
		{
			return mid;     //找到了，使得 binary_search=mid;
		}
	}
	return -1;              //未找到，使得 binary_search=-1;
}
int main()
{
	int arr[] = {0,1,2,3,4,5,6,7,8,9,10,11,12,13,14,15,16,17,18,19,20};
	int right= sizeof(arr) / sizeof(arr[0]) - 1;
	int k = 0;
	printf("请输入0至20内你要查找的正整数：\n");
	again:
	scanf("%d",&k);
	int p = binary_search(arr, k,right);
	if (-1 == p)
	{
		printf("找不到你所输入的数字,请重新输入：\n");
		goto again;
	}
	else
	{
		printf("找到了你所输入的数字，其下标是：%d\n", p);
	}
		return 0;
}
//
//
//
//
//
//
//
//
//
//
//
//
//
//
//
//
//
//
//
//
//
//
//
//
//
//
//
//
//

