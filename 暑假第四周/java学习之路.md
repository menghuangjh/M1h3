# 第一天 #


    package demo1;   //声明包
    public class TestJava3_1 {
    	/**
    	 * 主方法
    	 * 一个类如果用public声明 那么它必须与文件名一致 如左边*.java
    	 */
    	public static void main(String[] args) {
		int num; //声明一个整型变量num
		num = 5; //赋值
    		System.out.println("这是数字"+num);  //输出
    		System.out.println("我有"+num+"本书！");  //输出
    		//System.out 标准输出流 与打印机、显示器相关
    		//println=print+line（换行）
    		//也可以使用print 就不会换行
    	}
    }



## java的标识符 ##
规则：只能用字母、数字、下划线、&组成，且数字不能作为开头，避免关键字

规范：标识符阅读性好

## 三种注释 ##
单行注释：//

多行注释：/**/

文档注释：/*代码/ 一般敲/**以后再敲个回车会自动生成

## 数据类型 ##
1.基本数据类型：
整型：字节（byte）、短整型（short）、整型（int）、长整形（long）

浮点：单精度（float）、双精度（double）
字符：存储字符（char）

布尔：存储真假关系(boolean)，里面只有两个值（true与false）

2.引用数据类型：

字符串：（string）

类 ：（class）

## 实例 ##

    public class TestJava3_1 {
    	/**
    	 * 主方法
    	 * 一个类如果用public声明 那么它必须与文件名一致 如左边*.java
    	 */
    	public static void main(String[] args) {
    		int num = 10;
    		byte age = 20;
    		float price =12.5f;
    		double weight = 12.5;
    	}
    }


## 数据类型的转换 ##

1.自动类型转换：低到高；

比如：byte a = 10；int num = b；

double d = 10；用system.out.println(d);会答应出10.0；

2.强制类型转换：

double d = 10.1；

system.out.println((int) d)；

此时输出会省略d的小数部分输出10；


# 第二天 常量与变量#

## 1.常量 ##


    public class TestFinal4_1 {
    	static final int YEAR = 365;	//定义一个常量（在main外或者里面都可以）
    	//main方法是静态的 所以上面定义也要加static
    	public static void main(String[] args) {
    		System.out.println("一年有"+YEAR+"天"); 	
    		System.out.println("两年有"+YEAR*2+"天"); 
    	}
    }
    如果把YEAR的定义放在main里面就可以不加
    public class TestFinal4_1 {
    	public static void main(String[] args) {
    		final int YEAR = 365;	
    		System.out.println("一年有"+YEAR+"天"); 			
    	}
    
    }


## 2.变量 ##

## 2.1声明变量 ##

    public static void main(String[] args) {
    		int num = 10;
    		System.out.println("num="+num);
    		double money = 1000000;
    		System.out.println("money="+money);
    		num = 100;
    		System.out.println("num="+num);
    		char ch = 'z';
    		System.out.println("ch="+ch);
    	}

## 2.2变量的作用范围 ##
按作用范围分类：成员变量和局部变量

1.成员变量:在类体中定义的变量，作用范围为整个类，这个类中都可以访问到定义的这个变量

    public class Test4_2 {
    	static int k = 1;   //即为成员变量---在类体中定义
    	public static void main(String[] args) {
    	
    	}
    
    }

2.局部变量:在一个函数（方法）或代码块中定义的变量

特点：局部变量在方法或代码块被执行的时候创建，在结束时被销毁

    public class Test4_2 {
    
    	public static void main(String[] args) {
    		int a = 1;
    		//以下就是一个块
    		{
    			int b = 2;
    			System.out.println("a="+a);
    			System.out.println("b="+b);
    		}
    		int b = 3; //因为在上面执行结束后 代码块就被销毁了
    		System.out.println("a="+a);
    		System.out.println("b+"+b);
    	}
    
    }
    
> 成员变量可以与局部变量重名
> 
> 其调用服从“就近原则”
> 
> 下面给出一个例子
> 
> 如果不删除int var = 2，结果会显示 2，删除后则为1；

    public class Test4_2 {
    	static int var = 1;
    	public static void main(String[] args) {
    		int var = 2;
    		System.out.println("the value of var = "+var);
    	}
    
    }
    
    
    public class Test4_2 {
    	static int var = 1;
    	public static void main(String[] args) {
    		int var = 2;
    		System.out.println("the value of var = "+var);
    		pt();
    	}
    	public static void pt() {
    		System.out.println("the value of var = "+var);
    	}
    
    }

## 3.拓展 ##

1.Java中作用范围禁止嵌套，而在c/c++中则可以，在下面分别给出在java与c中的例子；

    错误！！！或报错
    public static void main(String[] args) {
    		int a = 1;
    		{
    			int a =2
    			System.out.println("a="+a);
    		}
    	}
    

    在C语言中 正确！！！
    #include<stdio.h>
    
    int main()
    {
    	int a = 1;
    	{
    		int a=2;
    		printf("%d",a);
    	}
     } 
    
2.Java中类与方法中变量的作用域可以嵌套：也就是上面说的就近原则那个，这里不再细讲；

## 4.实战练习 ##
实现一个从1~100累加的和（很简单 因为学过C了 所以感觉这些很多东西都差不多）

    public class welcom {
    	public static void main(String[] args) {
    		int sum = 0;
    		for(int i=0;i<100;i++){
    			sum=sum+i;
    		}
    		System.out.println(num);
    	}
    
    }
    

## 第三天 数据类型##

## 一、各种数据类型所占空间（没必要去记忆，了解即可） ##
①基本

字 节------byte------1字节

短整型------short------2字节

整 型------ int ------4字节

长整型------ long------8字节

布尔型------boolean—1bit

单精度------ float ------4字节

双精度------double------8字节

字 符------ char ------2字节

②包装类

整数类型对应的包装类

为什么引入包装类？万物即对象，而像byte、short等不是对象，所以由包装类引入对象的概念；

通常在后面加一个.可以得到其属性；

详细见下面的代码

byte------Byte

short------Short

int------Integer

long-----Long

float-----Float

double-----Double

char------Character

    public static void main(String[] args) {
    		byte byte_max = Byte.MAX_VALUE;   //最大值
    		byte byte_min = Byte.MIN_VALUE;   //最小值
    		System.out.println("the maximum of byte is "+byte_max);
    		System.out.println("the minimum of byte is "+byte_min);
    		System.out.println("byte对应的比特位"+Byte.SIZE); 
    		System.out.println("byte对应的类型"+Byte.TYPE);
    	}
    
> 小补充
> 
> 在Java中数字默认是int类型；
> 
> 所以在初始化赋值long类型时候应该 long 变量 = 1L;（L小写也可）
> 
> int num = 1; //定义一个int类型
> 
> long num1 = 1; //设计自动转换，因为在java中默认数字为int类型
> 
> long num 2 = 2L; //定义一个long类型
> 
> char ch = 91; 代表ch为’a‘;
> 
> 当要查看 字符对应的ASCII码时
> 
> 可以int ch2 = 'a';
> 
> 同理可以查看中文的GBK码表，此编码表也兼容ASCII码；
> 
> 这里同时拓展一下Unicode：将所有国家的编码表融合到一个表中

## 二、基本数据类型的默认值 ##
> 成员变量有默认值，而局部变量没有

下面即为成员变量的默认值：

byte—(byte)0；

short—(short)0;

int—0;

long—0L;

float—0.0F;

double—0.0D;

char— ’ '或\u0000(也代表空，它为Unicode字符) 打印时像这样使用’\u0000‘

boolean—false;

## 三、拓展 ##

（布尔类型）在c\c++中规定所有非零数即为真，零为假；而在Java中，布尔变量只有true与false两个变量，除此之外没有其他的任何值，因而它和任何数字都无关；

①打印int类型中最小值到最大值是否为偶数

    public static void main(String[] args) {
    		for(int i = Integer.MIN_VALUE;i<=Integer.MAX_VALUE;i++)
    		{
    			boolean isEven = (i%2==0);
    			System.out.println("i = "+i+",isEven = "+isEven);
    也等价于		System.out.println("i=%d,isEven=%b",i,isEven);
    		}
    

②拼接符号的使用

“+”的功能:加法运算与拼接符号

加法运算：只有数字的时候，结果得到数字；

拼接符号：有字符串的时候，与字符串进行相加，得到字符串；

    public static void main(String[] args) {
    		int x1 = 5;
    		int x2 = 2;
    		System.out.println(x1+x2);
    		System.out.println(x1+x2+"1");
    		System.out.println(x1+x2+"K");
    		System.out.println("A"+x1+x2);
    	}
    

“A”+x1为字符串与数字相加得到“A5”这个字符串再与x2相加得到字符串“A52"；


# 第四天 程序控制结构 #

foreach循环：用来循环遍历一个数组或集合框架

	for（类型 迭代类型:数组或集合）{
					代码块
	}

    实现数组的遍历，有一说一还挺方便哈哈哈
    public static void main(String[] args) {
    		int arr[] = {1,2,3,4,5};
    		for(int item:arr) {
    			System.out.println(item);
    		}
    }

contiue:结束本次循环进入下一次循环

return:离开语句所在的方法


# 第五天 数组 #

## 一、一维数组 ##

Java按引用传值的方式也有点不太一样！！！

**Add:两个数组对应同一个内存区域！！！**


    public class Tst_1 {
    	public static void main(String[] args) {
    			int[] nums1 = {1,2};
    			int[] nums2 = nums1;  //这里其实把nums1中记录的数组的地址传给了nums2
    			//现在遍历两个数组
    			System.out.println("第一个数组");
    			for(int x:nums1) {
    				System.out.println(x);
    			}
    			System.out.println("第二个数组");
    			for(int y:nums2) {
    				System.out.println(y);
    			}
    			//现在 修改下第二个数组中元素值
    			nums2[1] = 100;
    			System.out.println("第一个数组");
    			for(int x:nums1) {
    				System.out.println(x);
    			}
    			System.out.println("第二个数组");
    			for(int y:nums2) {
    				System.out.println(y);
    			}
    	}
    }
    输出结果为：
    第一个数组
    1
    2
    第二个数组
    1
    2
    第一个数组
    1
    100
    第二个数组
    1
    100
    

## 二、二维数组 ##

定义：数据类型[ ][ ] 数组名 = new int[行数][列数];

如：int[ ][ ] array = new int [3][2];或者int[ ][ ] array; array = new int[3][2];

实质我感觉就像是数组的数组

下面举一个行数列数都定了的二维数组

**（一定记得用new初始化）**

    
    public class Tst_2 {
    
    	public static void main(String[] args) {
    		int[][] nums;
    		nums = new int[3][2];
    		for(int i=0;i<nums.length;i++) {
    			for(int j=0;j<nums[i].length;j++) {
    				System.out.println("nums["+i+"]["+j+"]="+nums[i][j]);
    			}
    		}
    	}
    
    }
    

再举例列数不定


    public class Tst_2 {
    
    	public static void main(String[] args) {
    		int[][] nums = new int[3][];
    		nums[0] = new int[3];
    		nums[1] = new int[4];
    		nums[2] = new int[] {1,2};
    		for(int i=0;i<nums.length;i++) {
    			for(int j=0;j<nums[i].length;j++) {
    				System.out.println("nums["+i+"]["+j+"]="+nums[i][j]);
    			}
    		}
    	}
    
    }

下面补充一道例题，计算某个员工的工资总额

    public class Tst_2 {
    
    	public static void main(String[] args) {
    		int sum = 0;
    		int[][] nums = {{1,2},{1,2,3},{2}};
    		for(int i=0;i<nums.length;i++) {
    			System.out.printf("第%d个人的销售总额为：",(i+1));
    			for(int j=0;j<nums[i].length;j++) {
    				sum += nums[i][j];
    			}
    			System.out.println(sum);
    			sum = 0;   //清零便于下一次计算
    		}
    	}
    
    }
    


## 三、多维数组 ##
定义：数据类型[ ][ ]…[] 数组名 = new int[ ][ ]…[];




