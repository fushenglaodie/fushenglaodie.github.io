---
title: Java基础
date: 2023-07-16 19:29:09
categories:
 - 核心基础
---

- [ ] 01_Java语言概述
- [X] 02_变量与运算符
- [X] 03_流程控制
- [ ] 04_IDEA开发工具
- [x] 04_数组
- [ ] 05_面向对象
- [ ] 06_异常处理
- [ ] 07_多线程
- [ ] 08_常用类和基础API
- [ ] 09_集合框架
- [ ] 10_泛型
- [ ] 11_File类与IO流
- [ ] 12_网络编程
- [ ] 13_反射机制
- [ ] 14_版本新特性


# Java语言概述
略

---

# 变量与运算符

## 关键字(keyword)

> 定义：专门用途的字符串
> 特点：全小写

{% tabs 关键字 %}
<!-- tab 第一部分-->
{% asset_img 02_01.png %}
<!-- endtab -->
<!-- tab 第二部分-->
{% asset_img 02_02.png %}
<!-- endtab -->
{% endtabs %}


## 识别符(identifier)

{% tabs 标识符 %}
<!-- tab 定义-->
> 对变量、方法、类等命名时用的字符序列
<!-- endtab -->
<!-- tab 命名规则-->
1. 组成：英文字母、数字、_或$
2. 开头：不能数字
3. 大小写：严格区分
4. 空格：不能有
5. 关键字：不能用，可包含
<!-- endtab -->
<!-- tab 命名规范-->
1. 包名：全小写
2. 类、接口名：大驼峰命名法
3. 变量、方法名：小驼峰命名法
4. 常量名：大写，下划线连接
<!-- endtab -->
{% endtabs %}


## 变量

{% tabs 变量 %}
<!-- tab 概念-->
> 定义：最基本的存储单元
> 构成：数据类型、变量名、变量值
> 作用：内存种保存数据
> 
<!-- endtab -->
<!-- tab 注意事项-->
>1. 先声明，后使用
>2. 通过变量名访问数据
>3. 作用域在所在的{}内
>4. 统一作用域，不能重名定义
<!-- endtab -->
<!-- tab 基本数据类型-->
- 整数型
    - byte：1字节
    - short：2字节
    - int：4字节
    - long：8字节
- 浮点型
    - float：4字节
    - double：8字节
- 字符型：char
    - 单引号表示
    - Unicode表示
    - 转义字符表示
- 布尔型：boolean
<!-- endtab -->
<!-- tab 引用数据类型-->
- 数组
- 类
- 接口
- 枚举
- 注解
- 记录
<!-- endtab -->
<!-- tab 基本类型运算规则-->
- 自动类型转换
    - 小赋值给大
    - 小与大一起计算
    - byte、short、char一起运算，按int处理
- 强制类型转换
    - 与String一起运算
    - String不能强制类型转换
    - 可以通过加号与String连接
<!-- endtab -->
{% endtabs %}    

## 进制

- 二进制(binary)：补码的方式表示二进制数
- 八进制(octal)：
- 十进制(decimal)：
- 十六进制

**进制转换：通过二进制来转换**

## 运算符(Operator)
**运算符分类**
{% tabs 运算符分类 %}
<!-- tab 按功能分-->
{% asset_img 02_03.png %}
<!-- endtab -->
<!-- tab 按操作数个数分-->
{% asset_img 02_04.png %}
<!-- endtab -->
{% endtabs %}

**运算符用法**
{% tabs 运算符用法 %}
<!-- tab 算术-->
{% asset_img 02_05.png %}<!-- endtab -->
<!-- tab 赋值-->
{% asset_img 02_06.png %}
<!-- endtab -->
<!-- tab 比较-->
{% asset_img 02_07.png %}<!-- endtab -->
<!-- tab 逻辑-->
{% asset_img 02_08.png %}
<!-- endtab -->
<!-- tab 位-->
{% asset_img 02_09.png %}
{% asset_img 02_10.png %}
<!-- endtab -->
<!-- tab 条件-->
{% asset_img 02_11.png %}
<!-- endtab -->
<!-- tab Lambda-->

<!-- endtab -->
<!-- tab 优先级-->
{% asset_img 02_12.png %}
<!-- endtab -->
{% endtabs %}

## 字符集

- **ASCII(American Standard Code for Information Interchange)**
- **ISO-8859-1(Latin-1)**
- **GBxxx**
- **Unicode**
    - UTF-8:编码方案
  
---

# 流程控制

## 顺序结构
{% tabs 顺序结构 %}
<!-- tab 定义 -->
> 顺序结构就是程序`从上到下逐行`地执行。表达式语句都是顺序执行的。并且上一行对某个变量的修改对下一行会产生影响。
<!-- endtab -->
<!-- tab 流程图 -->
{% asset_img 03_01.png %}
<!-- endtab -->
{% endtabs %}



## 分支结构

### if-else

{% tabs if-else %}
<!-- tab 基本语法 -->
**单分支条件判断**
```java
if(条件表达式)｛
  	语句块;
｝
```
**双分支条件判断**
```java
if(条件表达式) { 
  	语句块1;
}else {
  	语句块2;
}
```
**多分支条件判断**
```java
if (条件表达式1) {
  	语句块1;
} else if (条件表达式2) {
  	语句块2;...
} else if (条件表达式n) {
 	语句块n;
} else {
  	语句块n+1;
}

```
<!-- endtab -->
<!-- tab 其他说明 -->
- 语句块只有一条执行语句时，一对`{}可以省略`，但建议保留
- 当if-else结构是“多选一”时，最后的`else是可选的`，根据需要可以省略
<!-- endtab -->
{% endtabs %}


### switch-case

{% tabs switch-case %}
<!-- tab 语法格式 -->
```java
switch(表达式){
    case 常量值1:
        语句块1;
        //break;
    case 常量值2:
        语句块2;
        //break; 
    // ...
   [default:
        语句块n+1;
        break;
   ]
}
```
<!-- endtab -->
<!-- tab 流程图 -->
{% asset_img 03_02.png %}
<!-- endtab -->
<!-- tab case的穿透性 -->
在switch语句中，如果case的后面不写break，将出现穿透现象，也就是一旦匹配成功，不会在判断下一个case的值，直接向后运行，直到遇到break或者整个switch语句结束，执行终止。
<!-- endtab -->
{% endtabs %}

### 两种选择结构的比较
{% tabs 两种选择结构的比较 %}
<!-- tab 结论 -->
凡是使用switch-case的结构都可以转换为if-else结构。反之，不成立。
<!-- endtab -->
<!-- tab 开发经验 -->
如果既可以使用switch-case，又可以使用if-else，建议使用switch-case。因为效率稍高。<!-- endtab -->
<!-- tab 细节对比 -->
- if-else语句优势
    - if语句的条件是一个布尔类型值，if条件表达式为true则进入分支，可以用于范围的判断，也可以用于等值的判断，`使用范围更广`。
    - switch语句的条件是一个常量值（byte,short,int,char,枚举,String），只能判断某个变量或表达式的结果是否等于某个常量值，`使用场景较狭窄`。
- switch语句优势
    - 当条件是判断某个变量或表达式是否等于某个固定的常量值时，使用if和switch都可以，习惯上使用switch更多。因为`效率稍高`。当条件是区间范围的判断时，只能使用if语句。
    - 使用switch可以利用`穿透性`，同时执行多个分支，而if...else没有穿透性。
<!-- endtab -->
{% endtabs %}
  
## 循环结构

### for

> **基本语法**

{% tabs for%}
<!-- tab 语法格式 -->
```java
for (①初始化部分; ②循环条件部分; ④迭代部分)｛
    ③循环体部分;
｝
```
<!-- endtab -->
<!-- tab 流程图 -->
{% asset_img 03_03.png %}
<!-- endtab -->
<!-- tab 说明 -->
- for(;;)中的两个；不能多也不能少
- ①初始化部分可以声明多个变量，但必须是同一个类型，用逗号分隔
- ②循环条件部分为boolean类型表达式，当值为false时，退出循环
- ④可以有多个变量更新，用逗号分隔
<!-- endtab -->
{% endtabs %}

> **应用举例**

{% tabs  举例%}
<!-- tab 重复执行语句 -->
> 题目：输出5行HelloWorld
<!-- tab -->
```java
public class ForTest1 {
    public static void main(String[] args) {
        //需求1：控制台输出5行Hello World!
		//写法1：
		//System.out.println("Hello World!");
		//System.out.println("Hello World!");
		//System.out.println("Hello World!");
		//System.out.println("Hello World!");
		//System.out.println("Hello World!");

		//写法2：
		for(int i = 1;i <= 5;i++){
			System.out.println("Hello World!");
		}
    }
}
```
<!-- tab 格式的多样性 -->

> 题目：写出输出的结果

```java
public class ForTest2 {
	public static void main(String[] args) {
        int num = 1;
        for(System.out.print("a");num < 3;System.out.print("c"),num++){
            System.out.print("b");

        }
    }
}
```
<!-- endtab -->
<!-- tab 累加的思想 -->

> 题目：遍历1-100以内的偶数，并获取偶数的个数，获取所有的偶数的和
```java
public class ForTest3 {
	public static void main(String[] args) {
        int count = 0;//记录偶数的个数
        int sum = 0;//记录偶数的和

        for(int i = 1;i <= 100;i++){

            if(i % 2 == 0){
                System.out.println(i);
                count++;
                sum += i;
            }	

            //System.out.println("偶数的个数为：" + count);
        }

        System.out.println("偶数的个数为：" + count);	
        System.out.println("偶数的总和为：" + sum);
    }
}
```
<!-- endtab -->
<!-- tab 结合分支结构 -->

> 题目：输出所有的水仙花数，所谓水仙花数是指一个3位数，其各个位上数字立方和等于其本身。例如： `153 = 1*1*1 + 3*3*3 + 5*5*5`

```java
public class ForTest4 {
	public static void main(String[] args) {
		//定义统计变量，初始化值是0
		int count = 0;
		
		//获取三位数，用for循环实现
		for(int x = 100; x < 1000; x++) {
			//获取三位数的个位，十位，百位
			int ge = x % 10;
			int shi = x / 10 % 10;
			int bai = x / 100;
			
			//判断这个三位数是否是水仙花数，如果是，统计变量++
			if((ge*ge*ge+shi*shi*shi+bai*bai*bai) == x) {
                System.out.println("水仙花数：" + x);
				count++;
			}
		}
		
		//输出统计结果就可以了
		System.out.println("水仙花数共有"+count+"个");
	}
}
```
<!-- endtab -->
<!-- tab 结合break -->

> 说明：输入两个正整数m和n，求其最大公约数和最小公倍数。比如：12和20的最大公约数是4，最小公倍数是60。
```java
/**
 * @author 尚硅谷-宋红康
 * @create 17:43
 */
public class ForTest5 {
    public static void main(String[] args) {
        //需求1：最大公约数
        int m = 12, n = 20;
        //取出两个数中的较小值
        int min = (m < n) ? m : n;

        for (int i = min; i >= 1; i--) {//for(int i = 1;i <= min;i++){

            if (m % i == 0 && n % i == 0) {
                System.out.println("最大公约数是：" + i); //公约数

                break; //跳出当前循环结构
            }
        }


        //需求2：最小公倍数
        //取出两个数中的较大值
        int max = (m > n) ? m : n;

        for (int i = max; i <= m * n; i++) {

            if (i % m == 0 && i % n == 0) {

                System.out.println("最小公倍数是：" + i);//公倍数

                break;
            }
        }

    }
}
```
<!-- endtab -->
<!-- tab 说明 -->
1、我们可以在循环中使用break。一旦执行break，就跳出当前循环结构。

2、小结：如何结束一个循环结构？

​      结束情况1：循环结构中的循环条件部分返回false

​      结束情况2：循环结构中执行了break。

3、如果一个循环结构不能结束，那就是一个死循环！我们开发中要避免出现死循环。
<!-- endtab -->
{% endtabs %}

### while

{% tabs while %}
<!-- tab 基本语法 -->
**语法格式**
```java
①初始化部分
while(②循环条件部分)｛
    ③循环体部分;
    ④迭代部分;
}
```
**执行过程** :①-②-③-④-②-③-④-②-③-④-...-②
**流程图**:
{% asset_img 03_04.png%}
**说明**
- while(循环条件)中循环条件必须是boolean类型。
- 注意不要忘记声明④迭代部分。否则，循环将不能结束，变成死循环。
- for循环和while循环可以相互转换。二者没有性能上的差别。实际开发中，根据具体结构的情况，选择哪个格式更合适、美观。
- for循环与while循环的区别：初始化条件部分的作用域不同。
<!-- endtab -->
<!-- tab 举例 -->
**案例1：**输出5行HelloWorld!
```java
class WhileTest1 {
	public static void main(String[] args) {
		
		int i = 1;
		while(i <= 5){
			System.out.println("Hello World!");
			i++;
		}
	}
}
```
**案例2：**遍历1-100的偶数，并计算所有偶数的和、偶数的个数（累加的思想）
```java
class WhileTest2 {
	public static void main(String[] args) {
		//遍历1-100的偶数，并计算所有偶数的和、偶数的个数（累加的思想）
		int num = 1;

		int sum = 0;//记录1-100所有的偶数的和
		int count = 0;//记录1-100之间偶数的个数

		while(num <= 100){
			
			if(num % 2 == 0){
				System.out.println(num);
				sum += num;
				count++;
			}
			
			//迭代条件
			num++;
		}
	
		System.out.println("偶数的总和为：" + sum);
		System.out.println("偶数的个数为：" + count);
	}
}
```
**案例3：**猜数字游戏
> 随机生成一个100以内的数，猜这个随机数是多少？
> 从键盘输入数，如果大了，提示大了；如果小了，提示小了；如果对了，就不再猜了，并统计一共猜了多少次。
> 提示：生成一个[a,b] 范围的随机数的方式：(int)(Math.random() * (b - a + 1) + a)
```java
/**
 * @author 尚硅谷-宋红康
 * @create 16:42
 */
public class GuessNumber {
    public static void main(String[] args) {
        //获取一个随机数
        int random = (int) (Math.random() * 100) + 1;

        //记录猜的次数
        int count = 1;

        //实例化Scanner
        Scanner scan = new Scanner(System.in);
        System.out.println("请输入一个整数(1-100):");
        int guess = scan.nextInt();

        while (guess != random) {

            if (guess > random) {
                System.out.println("猜大了");
            } else if (guess < random) {
                System.out.println("猜小了");
            }

            System.out.println("请输入一个整数(1-100):");
            guess = scan.nextInt();
			//累加猜的次数
            count++;

        }

        System.out.println("猜中了！");
        System.out.println("一共猜了" + count + "次");
    }
}
```
**案例4：折纸珠穆朗玛峰**
> 世界最高山峰是珠穆朗玛峰，它的高度是8848.86米，假如我有一张足够大的纸，它的厚度是0.1毫米。
请问，我折叠多少次，可以折成珠穆朗玛峰的高度?
```java
/**
 * @author 尚硅谷-宋红康
 * @create 19:08
 */
public class ZFTest {
    public static void main(String[] args) {
        //定义一个计数器，初始值为0
        int count = 0;

        //定义珠穆朗玛峰的高度
        int zf = 8848860;//单位：毫米

        double paper = 0.1;//单位：毫米

        while(paper < zf){
            //在循环中执行累加，对应折叠了多少次
            count++;
            paper *= 2;//循环的执行过程中每次纸张折叠，纸张的厚度要加倍
        }

        //打印计数器的值
        System.out.println("需要折叠：" + count + "次");
        System.out.println("折纸的高度为" + paper/1000 + "米，超过了珠峰的高度");
    }
}
```
<!-- endtab -->
{% endtabs %}

### do-while

{% tabs do-while %}

<!-- tab 语法 -->
**语法格式:**
```java
①初始化部分;
do{
	③循环体部分
	④迭代部分
}while(②循环条件部分); 
```
**执行过程:**①-③-④-②-③-④-②-③-④-...-②
**流程图:**
{% asset_img 03_05.png %}
**说明:**
- 结尾while(循环条件)中循环条件必须是boolean类型
- do{}while();最后有一个分号
- do-while结构的循环体语句是至少会执行一次，这个和for和while是不一样的
- 循环的三个结构for、while、do-while三者是可以相互转换的。
<!-- endtab -->
<!-- tab 举例 -->
**案例1：**遍历1-100的偶数，并计算所有偶数的和、偶数的个数（累加的思想）
```java
class DoWhileTest1 {
	public static void main(String[] args) {

		//遍历1-100的偶数，并计算所有偶数的和、偶数的个数（累加的思想）
		//初始化部分
		int num = 1;
		
		int sum = 0;//记录1-100所有的偶数的和
		int count = 0;//记录1-100之间偶数的个数

		do{
			//循环体部分
			if(num % 2 == 0){
				System.out.println(num);
				sum += num;
				count++;
			}
			
			num++;//迭代部分


		}while(num <= 100); //循环条件部分


		System.out.println("偶数的总和为：" + sum);
		System.out.println("偶数的个数为：" + count);
	}
}
```
**案例2：**体会do-while至少会执行一次循环体
```java
class DoWhileTest2 {
	public static void main(String[] args) {
        //while循环:
		int num1 = 10;
		while(num1 > 10){
			System.out.println("hello:while");
			num1--;
		}

		//do-while循环:
		int num2 = 10;
		do{
			System.out.println("hello:do-while");
			num2--;
		}while(num2 > 10);

	}
}
```
**案例3：ATM取款:**
>声明变量balance并初始化为0，用以表示银行账户的余额，下面通过ATM机程序> 实现存款，取款等功能。
> 
> =========ATM========
>    1、存款
>    2、取款
>    3、显示余额
>    4、退出
> 请选择(1-4)：

```java
import java.util.Scanner;

/**
 * @author 尚硅谷-宋红康
 * @create 19:12
 */
public class ATM {
	public static void main(String[] args) {

		//初始化条件
		double balance = 0.0;//表示银行账户的余额
		Scanner scan = new Scanner(System.in);
		boolean isFlag = true;//用于控制循环的结束

		do{
			System.out.println("=========ATM========");
			System.out.println("\t1、存款");
			System.out.println("\t2、取款");
			System.out.println("\t3、显示余额");
			System.out.println("\t4、退出");
			System.out.print("请选择(1-4)：");

			int selection = scan.nextInt();
			
			switch(selection){
				case 1:
					System.out.print("要存款的额度为：");
					double addMoney = scan.nextDouble();
					if(addMoney > 0){
						balance += addMoney;
					}
					break;
				case 2:
					System.out.print("要取款的额度为：");
					double minusMoney = scan.nextDouble();
					if(minusMoney > 0 && balance >= minusMoney){
						balance -= minusMoney;
					}else{
						System.out.println("您输入的数据非法或余额不足");
					}
					break;
				case 3:
					System.out.println("当前的余额为：" + balance);
					break;
				case 4:
					System.out.println("欢迎下次进入此系统。^_^");
					isFlag = false;
					break;
				default:
					System.out.println("请重新选择！");
					break;	
			}
		
		}while(isFlag);

		//资源关闭
		scan.close();
		
	}
}
```
<!-- endtab -->
<!-- tab 练习 -->
**练习1：**
> 随机生成一个100以内的数，猜这个随机数是多少？
> 从键盘输入数，如果大了提示，大了；如果小了，提示小了；如果对了，就不再猜了，并统计一共猜了多少次。
```java
import java.util.Scanner;

public class DoWhileExer {
    public static void main(String[] args) {
        //随机生成一个100以内的整数
		/*
		Math.random() ==> [0,1)的小数
		Math.random()* 100 ==> [0,100)的小数
		(int)(Math.random()* 100) ==> [0,100)的整数
		*/
        int num = (int)(Math.random()* 100);
        //System.out.println(num);

        //声明一个变量，用来存储猜的次数
        int count = 0;

        Scanner input = new Scanner(System.in);
        int guess;//提升作用域
        do{
            System.out.print("请输入100以内的整数：");
            guess = input.nextInt();

            //输入一次，就表示猜了一次
            count++;

            if(guess > num){
                System.out.println("大了");
            }else if(guess < num){
                System.out.println("小了");
            }
        }while(num != guess);

        System.out.println("一共猜了：" + count+"次");

        input.close();
    }
}
```
<!-- endtab -->

{% endtabs %}

---


### 对比三种循环结构

{% tabs 对比循环结构 %}
<!-- tab 都具有四个要素 -->
- 循环变量的初始化条件
- 循环条件
- 循环体语句块
- 循环变量的修改的迭代表达式
<!-- endtab -->
<!-- tab 循环次数角度分析 -->
- do-while循环至少执行一次循环体语句。
- for和while循环先判断循环条件语句是否成立，然后决定是否执行循环体。
<!-- endtab -->
<!-- tab 如何选择 -->
- 遍历有明显的循环次数（范围）的需求，选择for循环
- 遍历没有明显的循环次数（范围）的需求，选择while循环
- 如果循环体语句块至少执行一次，可以考虑使用do-while循环
- 本质上：三种循环之间完全可以互相转换，都能实现循环的功能
<!-- endtab -->
{% endtabs %}

### “无限”循环

{% tabs 无限循环 %}
<!-- tab 语法 -->
**语法格式：**

- 最简单"无限"循环格式：`while(true)` , `for(;;)` 

**适用场景：**

- 开发中，有时并不确定需要循环多少次，需要根据循环体内部某些条件，来控制循环的结束（使用break）。
- 如果此循环结构不能终止，则构成了死循环！开发中要避免出现死循环。
<!-- endtab -->
<!-- tab 举例 -->
**案例1：**实现爱你到永远...
```java
public class EndlessFor1 {
    public static void main(String[] args) {
        for (;;){
            System.out.println("我爱你！");
        }
//        System.out.println("end");//永远无法到达的语句，编译报错
    }
}
```
```java
public class EndlessFor2 {
    public static void main(String[] args) {
        for (; true;){ //条件永远成立，死循环
            System.out.println("我爱你！");
        }
    }
}
```
```java
public class EndlessFor3 {
    public static void main(String[] args) {
        for (int i=1; i<=10; ){ //循环变量没有修改，条件永远成立，死循环
            System.out.println("我爱你！");
        }
    }
}
```
思考：如下代码执行效果
```java
public class EndlessFor4 {
    public static void main(String[] args) {
        for (int i=1; i>=10; ){ //一次都不执行
            System.out.println("我爱你！");
        }
    }
}
```
**案例2：**从键盘读入个数不确定的整数，并判断读入的正数和负数的个数，输入为0时结束程序。
```java
import java.util.Scanner;

class PositiveNegative {
	public static void main(String[] args) {
		Scanner scanner = new Scanner(System.in);
        
		int positiveNumber = 0;//统计正数的个数
		int negativeNumber = 0;//统计负数的个数
		for(;;){  //while(true){
			System.out.println("请输入一个整数：(输入为0时结束程序)");
			int num = scanner.nextInt();
			if(num > 0){
				 positiveNumber++;
            }else if(num < 0){
				 negativeNumber++;
        	}else{
                System.out.println("程序结束");
				break; 
            }
         }
		 System.out.println("正数的个数为："+ positiveNumber);
		 System.out.println("负数的个数为："+ negativeNumber);  
        
         scanner.close();
	} 
}

```
<!-- endtab -->
{% endtabs %}

### 嵌套循环

{% tabs 嵌套循环 %}
<!-- tab 说明 -->
- for循环，就是嵌套循环。其中，for ,while ,do-while均可以作为外层循环或内层循环。
  - 外层循环：循环结构A
  - 内层循环：循环结构B
- 实质上，`嵌套循环就是把内层循环当成外层循环的循环体`。只有当内层循环的循环条件为false时，才会完全跳出内层循环，才可结束外层的当次循环，开始下一次的外层循环。
- 设外层循环次数为`m`次，内层为`n`次，则内层循环体实际上需要执行`m*n`次。
- **技巧：**从二维图形的角度看，外层循环控制`行数`，内层循环控制`列数`。
- **开发经验：**实际开发中，我们最多见到的嵌套循环是两层。一般不会出现超过三层的嵌套循环。如果将要出现，一定要停下来重新梳理业务逻辑，重新思考算法的实现，控制在三层以内。否则，可读性会很差。

例如：两个for嵌套循环格式	

```java
for(初始化语句①; 循环条件语句②; 迭代语句⑦) {
    for(初始化语句③; 循环条件语句④; 迭代语句⑥) {
      	循环体语句⑤;
    }
}

//执行过程：① - ② - ③ - ④ - ⑤ - ⑥ - ④ - ⑤ - ⑥ - ... - ④ - ⑦ - ② - ③ - ④ - ⑤ - ⑥ - ④..
```

**执行特点：**外层循环执行一次，内层循环执行一轮。
<!-- endtab -->
<!-- tab 举例 -->
**案例1：**打印5行6个*

```java
class ForForTest1 {
	public static void main(String[] args) {
		/*
		
		******
		******
		******
		******
		******
		
		*/
		
		for(int j = 1;j <= 5;j++){

			for(int i = 1;i <= 6;i++){
				System.out.print("*");
			}
			
			System.out.println();
		}
    }
}
```

**案例2：**打印5行直角三角形

```
*
**
***
****
*****
```

```java
public class ForForTest2 {
    public static void main(String[] args){
        for (int i = 1; i <= 5; i++) {
            for (int j = 1; j <= i; j++) {
                System.out.print("*");
            }
            System.out.println();
        }
    }
}	
```

**案例3：**打印5行倒直角三角形

```
*****
****
***
**
*
```

```java
public class ForForTest3 {
    public static void main(String[] args){
        for(int i = 1;i <= 5;i++){
			for(int j = 1;j <= 6 - i;j++){
				System.out.print("*");
			
			}
			System.out.println();
		
		}
    }
}
```

**案例4：打印"菱形"形状的图案**

```
        * 
      * * * 
    * * * * * 
  * * * * * * * 
* * * * * * * * * 
  * * * * * * * 
    * * * * * 
      * * * 
        * 	
```

```java
public class ForForTest4 {

    public static void main(String[] args) {
    /*
        上半部分		i		m(表示-的个数)    n(表示*的个数)关系式：2*i + m = 10 --> m = 10 - 2*i
    --------*		   1	   8			   1							n = 2 * i - 1
    ------* * *		   2	   6			   3
    ----* * * * *	   3	   4			   5
    --* * * * * * *	   4	   2		       7
    * * * * * * * * *  5	   0			   9

        下半部分         i      m                n              关系式： m = 2 * i
    --* * * * * * *    1       2                7                     n = 9 - 2 * i
    ----* * * * *      2       4                5
    ------* * *        3       6                3
    --------*          4       8                1

            */
        //上半部分
        for (int i = 1; i <= 5; i++) {
            //-
            for (int j = 1; j <= 10 - 2 * i; j++) {
                System.out.print(" ");
            }
            //*
            for (int k = 1; k <= 2 * i - 1; k++) {
                System.out.print("* ");
            }
            System.out.println();
        }
        //下半部分
        for (int i = 1; i <= 4; i++) {
            //-
            for (int j = 1; j <= 2 * i; j++) {
                System.out.print(" ");
            }

            //*
            for (int k = 1; k <= 9 - 2 * i; k++) {
                System.out.print("* ");
            }
            System.out.println();
        }
    }

}
```

**案例5：九九乘法表**

```java
public class ForForTest5 {
    public static void main(String[] args) {
        for (int i = 1; i <= 9; i++) {
            for (int j = 1; j <= i; j++) {
                System.out.print(i + "*" + j + "=" + (i * j) + "\t");
            }
            System.out.println();
        }
    }
}
```

<!-- endtab -->
<!-- tab 练习 -->
**练习1：**将一天中的时间打印到控制台

```java
public class ForForDemo {
	public static void main (String[] args) {
		for (int hour = 0;hour < 24 ;hour++ ) {
			for (int min = 0; min < 60 ; min++) {
				System.out.println(hour + "时" + min +"分");
			}
		}	
	}
}
```

<!-- endtab -->
{% endtabs %}

## 关键字break和continue
{% tabs break&continue %}
<!-- tab 说明 -->
|关键字|适用范围|作用|相同点|
|---  |---     |---|---|
|break|switch-case循环结构|一旦执行，就结束(或跳出)当前循环结构|此关键字的后面，不能声明语句|
|continue|循环结构|一旦执行，就结束(或跳出)当次循环结构|此关键字的后面，不能声明语句|
> 此外，很多语言都有goto语句，goto语句可以随意将控制转移到程序中的任意一条语句上，然后执行它，但使程序容易出错。Java中的break和continue是不同于goto的。
<!-- endtab -->
<!-- tab 举例 -->
```java
class BreakContinueTest1 {
	public static void main(String[] args) {
	
		for(int i = 1;i <= 10;i++){
			
			if(i % 4 == 0){
				//break;//123
				continue;//123567910
				//如下的语句不可能被执行，编译不通过
				//System.out.println("今晚迪丽热巴要约我吃饭");
			}

			System.out.print(i);
		}

		System.out.println("####");

		//嵌套循环中的使用
		for(int i = 1;i <= 4;i++){
		
			for(int j = 1;j <= 10;j++){
				if(j % 4 == 0){
					//break; //结束的是包裹break关键字的最近的一层循环！
					continue;//结束的是包裹break关键字的最近的一层循环的当次！
				}
				System.out.print(j);
			}
			System.out.println();
		}

	}
}
```
<!-- endtab -->
<!-- tab 带标签的使用 -->
```java
break语句用于终止某个语句块的执行
{    ……	 
	break;
	 ……
}

break语句出现在多层嵌套的语句块中时，可以通过标签指明要终止的是哪一层语句块 
	label1: {   ……        
	label2:	     {   ……
	label3:			 {   ……
				           break label2;
				           ……
					 }
			     }
			} 
```
- continue语句出现在多层嵌套的循环语句体中时，也可以通过标签指明要跳过的是哪一层循环。
- 标号语句必须紧接在循环的头部。标号语句不能用在非循环语句的前面。

- 举例：
```java
class BreakContinueTest2 {
	public static void main(String[] args) {
		l:for(int i = 1;i <= 4;i++){
		
			for(int j = 1;j <= 10;j++){
				if(j % 4 == 0){
					//break l;
					continue l;
				}
				System.out.print(j);
			}
			System.out.println();
		}
	}
}
```

<!-- endtab -->

<!-- tab 经典案例 -->
**题目：找出100以内所有的素数（质数）？100000以内的呢？**

目的：不同的代码的实现方式，可以效率差别很大。

分析：素数（质数）：只能被1和它本身整除的自然数。  ---> 从2开始，到这个数-1为止，此范围内没有这个数的约数。则此数是一个质数。
比如：2、3、5、7、11、13、17、19、23、...

**实现方式1：**

```java
class PrimeNumberTest {
	public static void main(String[] args) {
		
		
		//boolean isFlag = true; //用于标识i是否被除尽过

		long start = System.currentTimeMillis(); //记录当前时间距离1970-1-1 00:00:00的毫秒数
			
		int count = 0;//记录质数的个数


		for(int i = 2;i <= 100000;i++){  //i

			boolean isFlag = true; //用于标识i是否被除尽过
		
			for(int j = 2;j <= i - 1;j++){
				
				if(i % j == 0){ //表明i有约数
					isFlag = false;
				}
			
			}

			//判断i是否是质数
			if(isFlag){ //如果isFlag变量没有给修改过值，就意味着i没有被j除尽过。则i是一个质数
				//System.out.println(i);
				count++;
			}

			//重置isFlag
			//isFlag = true;
		
		}

		long end = System.currentTimeMillis();
		System.out.println("质数的个数为：" + count);
		System.out.println("执行此程序花费的毫秒数为：" + (end - start)); //16628

	}
}
```

**实现方式2：**针对实现方式1进行优化

```java
class PrimeNumberTest1 {
	public static void main(String[] args) {
		
		long start = System.currentTimeMillis(); //记录当前时间距离1970-1-1 00:00:00的毫秒数

		int count = 0;//记录质数的个数

		for(int i = 2;i <= 100000;i++){  //i

			boolean isFlag = true; //用于标识i是否被除尽过
		
			for(int j = 2;j <= Math.sqrt(i);j++){ //优化2：将循环条件中的i改为Math.sqrt(i)
				
				if(i % j == 0){ //表明i有约数
					isFlag = false;
					break;//优化1：主要针对非质数起作用
				}
			
			}

			//判断i是否是质数
			if(isFlag){ //如果isFlag变量没有给修改过值，就意味着i没有被j除尽过。则i是一个质数
				//System.out.println(i);
				count++;
			}
		
		}

		long end = System.currentTimeMillis();
		System.out.println("质数的个数为：" + count);
		System.out.println("执行此程序花费的毫秒数为：" + (end - start));//1062

	}
}
```

**实现方式3（选做）：**使用continue + 标签

```java
class PrimeNumberTest2 {
	public static void main(String[] args) {
		
		long start = System.currentTimeMillis(); //记录当前时间距离1970-1-1 00:00:00的毫秒数

		int count = 0;//记录质数的个数

		label:for(int i = 2;i <= 100000;i++){  //i
		
			for(int j = 2;j <= Math.sqrt(i);j++){ //优化2：将循环条件中的i改为Math.sqrt(i)
				
				if(i % j == 0){ //表明i有约数
					continue label;
				}
			
			}
			//一旦程序能执行到此位置，说明i就是一个质数
			System.out.println(i);
			count++;
		}
		

		long end = System.currentTimeMillis();
		System.out.println("质数的个数为：" + count);
		System.out.println("执行此程序花费的毫秒数为：" + (end - start));//1062

	}
}
```

<!-- endtab -->

<!-- tab 练习 -->
**练习1：**

> 生成 1-100 之间的随机数，直到生成了 97 这个数，看看一共用了几次？
> 提示：使用 (int)(Math.random() * 100) + 1

```java
public class NumberGuessTest {
    public static void main(String[] args) {
        int count = 0;//记录循环的次数（或生成随机数进行比较的次数）
        while(true){
            int random = (int)(Math.random() * 100) + 1;
            count++;
            if(random == 97){
                break;
            }
        }

        System.out.println("直到生成随机数97，一共比较了" + count + "次");

    }
}
```

<!-- endtab -->
{% endtabs %}
---

# 数组

## 数组的概念
{% tabs 数组的概念 %}
<!-- tab 数组的定义-->
数组(Array)，是多个相同类型数据按一定顺序排列的集合，并使用一个名字命名并通过编号的方式对这些数据进行统一管理
- 数组中的概念
  - 数组名
  - 下标（或索引）
  - 元素
  - 数组的长度
<!-- endtab -->
<!-- tab 数组的特点-->
- 数组本身是`引用数据类型`，而数组中的元素可以是`任何数据类型`，包括基本数据类型和引用数据类型。
- 创建数组对象会在内存中开辟一整块`连续的空间`。占据的空间的大小，取决于数组的长度和数组中元素的类型。
- 数组中的元素在内存中是依次紧密排列的，有序的。
- 数组，一旦初始化完成，其长度就是确定的。数组的`长度一旦确定，就不能修改`。
- 我们可以直接通过下标(或索引)的方式调用指定位置的元素，速度很快。
- 数组名中引用的是这块连续空间的首地址。
<!-- endtab -->
<!-- tab 数组的分类-->
**按照元素类型分**
- 基本数据类型元素的数组
- 引用数据类型元素的数组

**按照维度分**
- 一维数组
- 多维数组
<!-- endtab -->

{% endtabs %}



## 一维数组的使用

{% tabs 一维数组的使用 %}
<!-- tab 声明-->
**声明格式**
```java
//推荐
元素的数据类型[] 一维数组的名称;
//不推荐
元素的数据类型  一维数组名[];
```
**例子**
```java
int[] arr;
int arr1[];
double[] arr2;
String[] arr3;  //引用类型变量数组
```

**数组的声明，需要明确**
1. 数组的维度：在Java中数组的符号是[]，[]表示一维，\[]\[]表示二维。
2. 数组的元素类型：即创建的数组容器可以存储什么数据类型的数据。元素的类型可以是任意的Java的数据类型。例如：int、String、Student等。
3. 数组名：就是代表某个数组的标识符，数组名其实也是变量名，按照变量的命名规范来命名。数组名是个引用数据类型的变量，因为它代表一组数据。

**例子**
```java
public class ArrayTest1 {
    public static void main(String[] args) {
        //比如，要存储一个小组的成绩
		int[] scores;
		int[] grades;
		//未初始化不能使用
		System.out.println(scores);
        //比如，要存储一组字母
        char[] letters;
        //比如，要存储一组姓名
        String[] names;
        //比如，要存储一组价格
        double[] prices;
    }
}
```

**注意**
> Java语言中声明数组时不能指定其长度(数组中元素的个数)。 例如： int a[5]; //非法
<!-- endtab -->

<!-- tab 静态初始化 -->
> - 如果数组变量的初始化和数组元素的赋值操作同时进行，那就称为静态初始化。
- 静态初始化，本质是用静态数据（编译时已知）为数组初始化。此时数组的长度由静态数据的个数决定。
**模板1：**
```java
数据类型[] 数组名 = new 数据类型[]{元素1,元素2,元素3,...};
或 
数据类型[] 数组名;
数组名 = new 数据类型[]{元素1,元素2,元素3,...};
```
**实例1**
```java
//定义存储1，2，3，4，5整数的数组容器。
int[] arr = new int[]{1,2,3,4,5};//正确
//或
int[] arr;
arr = new int[]{1,2,3,4,5};//正确
```
**模板2**
```java
数据类型[] 数组名 = {元素1,元素2,元素3...};//必须在一个语句中完成，不能分成两个语句写
```
**实例2**
```java
//定义存储1，2，3，4，5整数的数组容器
int[] arr = {1,2,3,4,5};//正确

int[] arr;
arr = {1,2,3,4,5};//错误
```
**综合应用**
```java
public class ArrayTest2 {
    public static void main(String[] args) {
        int[] arr = {1,2,3,4,5};//右边不需要写new int[]

        int[] nums;
        nums = new int[]{10,20,30,40}; //声明和初始化在两个语句完成，就不能使用new int[]

        char[] word = {'h','e','l','l','o'};

        String[] heros = {"袁隆平","邓稼先","钱学森"};

        System.out.println("arr数组：" + arr);//arr数组：[I@1b6d3586
        System.out.println("nums数组：" + nums);//nums数组：[I@4554617c
        System.out.println("word数组：" + word);//word数组：[C@74a14482
        System.out.println("heros数组：" + heros);//heros数组：[Ljava.lang.String;@1540e19d
    }
}
```
<!-- endtab -->

<!-- tab 动态初始化 -->

> 数组变量的初始化和数组元素的赋值操作分开进行，即为动态初始化。
> 动态初始化中，只确定了元素的个数（即数组的长度），而元素值此时只是默认值，还并未真正赋自己期望的值。真正期望的数据需要后续单独一个一个赋值。

**格式**
```java
//[长度]：数组的长度，表示数组容器中可以最多存储多少个元素。
数组存储的元素的数据类型[] 数组名字 = new 数组存储的元素的数据类型[长度];

或

数组存储的数据类型[] 数组名字;
数组名字 = new 数组存储的数据类型[长度];
```
**注意**
> **数组有定长特性，长度一旦指定，不可更改。**和水杯道理相同，买了一个2升的水杯，总容量就是2升是固定的。

**例子1:正确写法**
```java
int[] arr = new int[5];

int[] arr;
arr = new int[5];

```
**例子2：错误写法**
```java
int[] arr = new int[5]{1,2,3,4,5};//错误的，后面有{}指定元素列表，就不需要在[]中指定元素个数了。
```
<!-- endtab -->
<!-- tab 数组长度 -->
> - 数组的元素总个数，即数组的长度
> - 每个数组都有一个属性length指明它的长度，例如：arr.length 指明数组arr的长度(即元素个数)
> - 每个数组都具有长度，而且一旦初始化，其长度就是确定，且是不可变的。
<!-- endtab -->

<!-- tab 数组元素引用 -->
**如何表示数组中的一个元素？**
> 每一个存储到数组的元素，都会自动的拥有一个编号，从0开始，这个自动编号称为`数组索引(index)或下标`，可以通过数组的索引/下标访问到数组中的元素。
> ```java
> 数组名[索引/下标]
> ```

**数组的下标范围**
> Java中数组的下标从[0]开始，下标范围是[0, 数组的长度-1]，即[0, 数组名.length-1]
> 数组元素下标可以是整型常量或整型表达式。如a[3] , b[i] , c[6*i];

**例子**
```java
public class ArrayTest3 {
    public static void main(String[] args) {
        int[] arr = {1,2,3,4,5};

        System.out.println("arr数组的长度：" + arr.length);
        System.out.println("arr数组的第1个元素：" + arr[0]);//下标从0开始
        System.out.println("arr数组的第2个元素：" + arr[1]);
        System.out.println("arr数组的第3个元素：" + arr[2]);
        System.out.println("arr数组的第4个元素：" + arr[3]);
        System.out.println("arr数组的第5个元素：" + arr[4]);

        //修改第1个元素的值
        //此处arr[0]相当于一个int类型的变量
        arr[0] = 100;
        System.out.println("arr数组的第1个元素：" + arr[0]);
    }
}
```
<!-- endtab -->
<!-- tab 一维数组的遍历 -->
> 将数组中的每个元素分别获取出来，就是`遍历`。for循环与数组的遍历是绝配。
**例子1**
```java
public class ArrayTest4 {
    public static void main(String[] args) {
        int[] arr = new int[]{1,2,3,4,5};
        //打印数组的属性，输出结果是5
        System.out.println("数组的长度：" + arr.length);

        //遍历输出数组中的元素
        System.out.println("数组的元素有：");
        for(int i=0; i<arr.length; i++){
            System.out.println(arr[i]);
        }
    }
}
```
**例子2**
```java
public class ArrayTest5 {
    public static void main(String[] args) {
        int[] arr = new int[5];

        System.out.println("arr数组的长度：" + arr.length);
        System.out.print("存储数据到arr数组之前：[");
        for (int i = 0; i < arr.length; i++) {
            if(i==0){
                System.out.print(arr[i]);
            }else{
                System.out.print("," + arr[i]);
            }
        }
        System.out.println("]");

        //初始化
 		/* 
 		arr[0] = 2;
        arr[1] = 4;
        arr[2] = 6;
        arr[3] = 8;
        arr[4] = 10;
        */

        for (int i = 0; i < arr.length; i++) {
            arr[i] = (i+1) * 2;
        }

        System.out.print("存储数据到arr数组之后：[");
        for (int i = 0; i < arr.length; i++) {
            if(i==0){
                System.out.print(arr[i]);
            }else{
                System.out.print("," + arr[i]);
            }
        }
        System.out.println("]");
    }
}
```
<!-- endtab -->
<!-- tab 数组元素的默认值 -->
> 数组是引用类型，当我们使用动态初始化方式创建数组时，元素值只是默认值。例如：
```java
public class ArrayTest6 {
	public static void main(String argv[]){
		int a[]= new int[5]; 
		System.out.println(a[3]); //a[3]的默认值为0
	}
} 
```
> 对于基本数据类型而言，默认初始化值各有不同。
> 对于引用数据类型而言，默认初始化值为null（注意与0不同！）
{% gallery %}
![](05_01.png)
{% endgallery %}

**实例**
```java
public class ArrayTest7 {
    public static void main(String[] args) {
        //存储26个字母
        char[] letters = new char[26];
        System.out.println("letters数组的长度：" + letters.length);
        System.out.print("存储字母到letters数组之前：[");
        for (int i = 0; i < letters.length; i++) {
            if(i==0){
                System.out.print(letters[i]);
            }else{
                System.out.print("," + letters[i]);
            }
        }
        System.out.println("]");

       //存储5个姓名
        String[] names = new String[5];
        System.out.println("names数组的长度：" + names.length);
        System.out.print("存储姓名到names数组之前：[");
        for (int i = 0; i < names.length; i++) {
            if(i==0){
                System.out.print(names[i]);
            }else{
                System.out.print("," + names[i]);
            }
        }
        System.out.println("]");
    }
}
```
<!-- endtab -->
{% endtabs %}

## 一维数组内存分析

{% tabs 一维数组内存分析 %}
<!-- tab Java虚拟机的内存划分 -->
> 为了提高运算效率，就对空间进行了不同区域的划分，因为每一片区域都有特定的处理数据方式和内存管理方式。
> {% gallery %}
> ![](05_02.png)
> {% endgallery %}
> 
> | 区域名称   | 作用                                                      |
> | ----------| ---------------------------------------------------------|
> | `虚拟机栈` | 用于存储正在执行的每个Java方法的局部变量表等。局部变量表存放了编译期可知长度<br/>的各种基本数据类型、对象引用，方法执行完，自动释放。 |
> | `堆内存` | 存储对象（包括数组对象），new来创建的，都存储在堆内存。 |
> | `方法区` | 存储已被虚拟机加载的类信息、常量、（静态变量）、即时编译器编译后的代码等数据。 |
> | 本地方法栈 | 当程序中调用了native的本地方法时，本地方法执行期间的内存区域 |
> | 程序计数器 | 程序计数器是CPU中的寄存器，它包含每一个线程下一条要执行的指令的地址 |

<!-- endtab -->
<!-- tab 一维数组内存分析 -->
**一个一维数组的内存图**
```java
public static void main(String[] args) {
  	int[] arr = new int[3];
  	System.out.println(arr);//[I@5f150435
}

```
{% gallery %}
![](05_03.png)
{% endgallery %}

**数组下标0开始的原因**

> 因为第一个元素距离数组首地址间隔0个单元格。

**两个一维数组内存图**

```java
//两个数组独立
public static void main(String[] args) {
    int[] arr = new int[3];
    int[] arr2 = new int[2];
    System.out.println(arr);
    System.out.println(arr2);
}

```
{% gallery %}
![](05_04.png)
{% endgallery %}

**两个变量指向同一个一维数组**

> 两个数组变量本质上代表同一个数组。

```java
public static void main(String[] args) {
    // 定义数组，存储3个元素
    int[] arr = new int[3];
    //数组索引进行赋值
    arr[0] = 5;
    arr[1] = 6;
    arr[2] = 7;
    //输出3个索引上的元素值
    System.out.println(arr[0]);
    System.out.println(arr[1]);
    System.out.println(arr[2]);
    //定义数组变量arr2，将arr的地址赋值给arr2
    int[] arr2 = arr;
    arr2[1] = 9;
    System.out.println(arr[1]);
}
```
{% gallery %}
![](05_05.png)
{% endgallery %}
<!-- endtab -->

{% endtabs %}

## 一维数组的应用

{% tabs 一维数组的应用 %}

<!-- tab 案例1 -->
> 升景坊单间短期出租4个月，550元/月（水电煤公摊，网费35元/月），空调、卫生间、厨房齐全。屋内均是IT行业人士，喜欢安静。所以要求来租者最好是同行或者刚毕业的年轻人，爱干净、安静。
> 
```java
public class ArrayTest {
      public static void main(String[] args) {
      int[] arr = new int[]{8,2,1,0,3};
      int[] index = new int[]{2,0,3,2,4,0,1,3,2,3,3};
      String tel = "";
      for(int i = 0;i < index.length;i++){
            tel += arr[index[i]];
      }
      System.out.println("联系方式：" + tel);
      }
}
```
<!-- endtab -->

<!-- tab 案例2 -->

> 用一个数组，保存星期一到星期天的7个英语单词，从 键盘输入1-7，显示对应的单词
{"Monday","Tuesday","Wednesday","Thursday","Friday","Saturday","Sunday"}

```java
import java.util.Scanner;

/**
 * @author 尚硅谷-宋红康
 * @create 14:37
 */
public class WeekArrayTest {
    public static void main(String[] args) {

        //1. 声明并初始化星期的数组
        String[] weeks = {"Monday","Tuesday","Wednesday","Thursday","Friday","Saturday","Sunday"};

        //2. 使用Scanner从键盘获取1-7范围的整数
        Scanner scanner = new Scanner(System.in);
        System.out.println("请输入[1-7]范围的整数：");
        int number = scanner.nextInt();

        if(number < 1 || number > 7){
            System.out.println("你输入的输入非法");
        }else{

            //3. 根据输入的整数，到数组中相应的索引位置获取指定的元素（即：星期几）
            System.out.println("对应的星期为：" + weeks[number - 1]);

        }
        
        scanner.close();

    }
}
```

<!-- endtab -->

<!-- tab 案例3 -->
> 从键盘读入学生成绩，找出最高分，并输出学生成绩等级。
> - 成绩>=最高分-10  等级为’A’  
> - 成绩>=最高分-20  等级为’B’
> - 成绩>=最高分-30  等级为’C’  
> - 其余            等级为’D’
> 提示：先读入学生人数，根据人数创建int数组，存放学生成绩。
>
> {% gallery %}
> ![](05_06.png)
> {% endgallery %}

```java
/**
 * @author 尚硅谷-宋红康
 * @create 14:55
 */
public class ScoreTest1 {
    public static void main(String[] args) {

        //1. 根据提示，获取学生人数
        System.out.print("请输入学生人数：");
        Scanner scanner = new Scanner(System.in);
        int count = scanner.nextInt();

        //2. 根据学生人数，创建指定长度的数组 (使用动态初始化)
        int[] scores = new int[count];

        //3. 使用循环，依次给数组的元素赋值
        int maxScore = 0; //记录最高分
        System.out.println("请输入" + count + "个成绩");
        for (int i = 0; i < scores.length; i++) {
            scores[i] = scanner.nextInt();
            //4. 获取数组中元素的最大值，即为最高分
            if(maxScore < scores[i]){
                maxScore = scores[i];
            }
        }

        System.out.println("最高分是：" + maxScore);

        //5. 遍历数组元素，输出各自的分数，并根据其分数与最高分的差值，获取各自的等级
        char grade;
        for (int i = 0; i < scores.length; i++) {

            if(scores[i] >= maxScore - 10){
                grade = 'A';
            }else if(scores[i] >= maxScore - 20){
                grade = 'B';
            }else if(scores[i] >= maxScore - 30){
                grade = 'C';
            }else{
                grade = 'D';
            }
            System.out.println("student " + i + " socre is " + scores[i] + ", grade is " + grade);
        }
        //关闭资源
        scanner.close();

    }
}
```

<!-- endtab -->

{% endtabs %}


## 多维数组的使用

{% tabs %}

<!-- tab 概述 -->
> - Java 语言里提供了支持多维数组的语法。
> - 如果说可以把一维数组当成几何中的`线性图形`，那么二维数组就相当于是`一个表格`，像Excel中的表格、围棋棋盘一样。
> {% gallery %}
> ![](05_07.png)
> {% endgallery %}

**举例1**
> 某公司2022年全年各个月份的销售额进行登记。按月份存储，可以使用一维数组。如下：
```java
int[] monthData = new int[]{23,43,22,34,55,65,44,67,45,78,67,66};
```
> 如果改写为按`季度`为单位存储怎么办呢？
```java
int[][] quarterData = new int[][]{{23,43,22},{34,55,65},{44,67,45},{78,67,66}};
``` 

**举例2**
> 高一年级三个班级均由多个学生姓名构成一个个数组。如下：

```java
String[] class1 = new String[]{"段誉","令狐冲","任我行"};

String[] class2 = new String[]{"张三丰","周芷若"};

String[] class3 = new String[]{"赵敏","张无忌","韦小宝","杨过"};

```

> 那从整个年级看，我们可以声明一个二维数组。如下：

```java
String[][] grade = new String[][]{{"段誉","令狐冲","任我行"},{"张三丰","周芷若"},{"赵敏","张无忌","韦小宝","杨过"}};
```

**举例3**

> {% gallery %}
> ![](05_09.png)
> {% endgallery %}
> 
> 蓝框的几个元素，可以使用一维数组来存储。但现在发现每个元素下还有下拉框，其内部还有元素，那就需要使用二维数组来存储：
> 
> {% gallery %}
> ![](05_10.png)
> {% endgallery %}
> 使用说明
> 
> {% gallery %}
> ![](05_11.png)
> {% endgallery %}
> 
> - 对于二维数组的理解，可以看成是一维数组array1又作为另一个一维数组array2的元素而存在。
> - 其实，从数组底层的运行机制来看，其实没有多维数组。
<!-- endtab -->
<!-- tab 声明 -->
**二维数组声明的语法格式**
```java
//推荐
元素的数据类型[][] 二维数组的名称;

//不推荐
元素的数据类型  二维数组名[][];
//不推荐
元素的数据类型[]  二维数组名[];
```
**例子**
```java
public class Test20TwoDimensionalArrayDefine {
    public static void main(String[] args) {
        //存储多组成绩
        int[][] grades;

        //存储多组姓名
        String[][] names;
    }
}
```
**面试**
```java
int[] x, y[];
//x是一维数组，y是二维数组
```
<!-- endtab -->

<!-- tab 静态初始化 -->
**格式**
```java
int[][] arr = new int[][]{{3,8,2},{2,7},{9,0,1,6}};
```
> 定义一个名称为arr的二维数组，二维数组中有三个一维数组
> 
> - 每一个一维数组中具体元素也都已初始化
>   - 第一个一维数组 arr[0] = {3,8,2};
>   - 第二个一维数组 arr[1] = {2,7};
>   - 第三个一维数组 arr[2] = {9,0,1,6};
> - 第三个一维数组的长度表示方式：arr[2].length;
> 
> > - 注意特殊写法情况：int[] x,y[]; x是一维数组，y是二维数组。

**例子1**
```java
int[][] arr = {{1,2,3},{4,5,6},{7,8,9,10}};//声明与初始化必须在一句完成

int[][] arr = new int[][]{{1,2,3},{4,5,6},{7,8,9,10}};

int[][] arr;
arr = new int[][]{{1,2,3},{4,5,6},{7,8,9,10}};

arr = new int[3][3]{{1,2,3},{4,5,6},{7,8,9,10}};//错误，静态初始化右边new 数据类型[][]中不能写数字
```

**例子2**
```java
public class TwoDimensionalArrayInitialize {
    public static void main(String[] args) {
        //存储多组成绩
        int[][] grades = {
                    {89,75,99,100},
                    {88,96,78,63,100,86},
                    {56,63,58},
                    {99,66,77,88}
                };

        //存储多组姓名
        String[][] names = {
            {"张三","李四", "王五", "赵六"},
            {"刘备","关羽","张飞","诸葛亮","赵云","马超"},
            {"曹丕","曹植","曹冲"},
            {"孙权","周瑜","鲁肃","黄盖"}
        };
    }
}
```
<!-- endtab -->
<!-- tab 动态初始化 -->
> 如果二维数组的每一个数据，甚至是每一行的列数，需要后期单独确定，那么就只能使用动态初始化方式了。动态初始化方式分为两种格式：
**格式1：规则二维表：每一行的列数是相同的**
```java
//（1）确定行数和列数
元素的数据类型[][] 二维数组名 = new 元素的数据类型[m][n];
	//其中，m:表示这个二维数组有多少个一维数组。或者说一共二维表有几行
	//其中，n:表示每一个一维数组的元素有多少个。或者说每一行共有一个单元格

//此时创建完数组，行数、列数确定，而且元素也都有默认值

//（2）再为元素赋新值
二维数组名[行下标][列下标] = 值;
```

**例子**

```java
int[][] arr = new int[3][2];
```
> -  定义了名称为arr的二维数组
> -  二维数组中有3个一维数组
> -  每一个一维数组中有2个元素
> -  一维数组的名称分别为arr[0], arr[1], arr[2]
> -  给第一个一维数组1脚标位赋值为78写法是：`arr[0][1] = 78;`

**格式2：不规则：每一行的列数不一样**

```java
//（1）先确定总行数
元素的数据类型[][] 二维数组名 = new 元素的数据类型[总行数][];

//此时只是确定了总行数，每一行里面现在是null

//（2）再确定每一行的列数，创建每一行的一维数组
二维数组名[行下标] = new 元素的数据类型[该行的总列数];

//此时已经new完的行的元素就有默认值了，没有new的行还是null

//(3)再为元素赋值
二维数组名[行下标][列下标] = 值;
```

**例子**

```java
int[][] arr = new int[3][];
```

> -  二维数组中有3个一维数组。
> -  每个一维数组都是默认初始化值null (注意：区别于格式1）
> -  可以对这个三个一维数组分别进行初始化：arr[0] = new int[3];    arr[1] = new int[1];   arr[2] = new int[2];
> -  注：`int[][]arr = new int[][3]; ` //非法

**练习**
```java
/*
 1
 2 2
 3 3 3
 4 4 4 4
 5 5 5 5 5
 */
public class Test25DifferentElementCount {
    public static void main(String[] args){
        //1、声明一个二维数组，并且确定行数
        //因为每一行的列数不同，这里无法直接确定列数
        int[][]  arr = new int[5][];

        //2、确定每一行的列数
        for(int i=0; i<arr.length; i++){
			/*
			arr[0] 的列数是1
			arr[1] 的列数是2
			arr[2] 的列数是3
			arr[3] 的列数是4
			arr[4] 的列数是5
			*/
            arr[i] = new int[i+1];
        }

        //3、确定元素的值
        for(int i=0; i<arr.length; i++){
            for(int j=0; j<arr[i].length; j++){
                arr[i][j] = i+1;
            }
        }

        //4、遍历显示
        for(int i=0; i<arr.length; i++){
            for(int j=0; j<arr[i].length; j++){
                System.out.print(arr[i][j] + " ");
            }
            System.out.println();
        }

    }
}
```

<!-- endtab -->

<!-- tab 数列长度和角标-->
> - 二维数组的长度/行数：二维数组名.length
> - 二维数组的某一行：二维数组名[行下标]，此时相当于获取其中一组数据。它本质上是一个一维数组。行下标的范围：[0, 二维数组名.length-1]。此时把二维数组看成一维数组的话，元素是行对象。
> - 某一行的列数：二维数组名[行下标].length，因为二维数组的每一行是一个一维数组。
> - 某一个元素：二维数组名\[行下标\]\[列下标\]，即先确定行/组，再确定列。
```java
public class Test22TwoDimensionalArrayUse {
    public static void main(String[] args){
        //存储3个小组的学员的成绩，分开存储，使用二维数组。
		/*
		int[][] scores1;
		int scores2[][];
		int[] scores3[];*/

        int[][] scores = {
                {85,96,85,75},
                {99,96,74,72,75},
                {52,42,56,75}
        };

        System.out.println(scores);//[[I@15db9742
        System.out.println("一共有" + scores.length +"组成绩.");

        //[[：代表二维数组，I代表元素类型是int
        System.out.println(scores[0]);//[I@6d06d69c
        //[：代表一维数组，I代表元素类型是int
        System.out.println(scores[1]);//[I@7852e922
        System.out.println(scores[2]);//[I@4e25154f
        //System.out.println(scores[3]);//ArrayIndexOutOfBoundsException: 3

        System.out.println("第1组有" + scores[0].length +"个学员.");
        System.out.println("第2组有" + scores[1].length +"个学员.");
        System.out.println("第3组有" + scores[2].length +"个学员.");

        System.out.println("第1组的每一个学员成绩如下：");
        //第一行的元素
        System.out.println(scores[0][0]);//85
        System.out.println(scores[0][1]);//96
        System.out.println(scores[0][2]);//85
        System.out.println(scores[0][3]);//75
        //System.out.println(scores[0][4]);//java.lang.ArrayIndexOutOfBoundsException: 4
    }
}
```
<!-- endtab -->

<!-- tab 二维数组遍历 -->
**格式**
```java
for(int i=0; i<二维数组名.length; i++){ //二维数组对象.length
    for(int j=0; j<二维数组名[i].length; j++){//二维数组行对象.length
        System.out.print(二维数组名[i][j]);
    }
    System.out.println();
}
```
**举例**
```java
public class Test23TwoDimensionalArrayIterate {
    public static void main(String[] args) {
        //存储3个小组的学员的成绩，分开存储，使用二维数组。
        int[][] scores = {
                {85,96,85,75},
                {99,96,74,72,75},
                {52,42,56,75}
        };

        System.out.println("一共有" + scores.length +"组成绩.");
        for (int i = 0; i < scores.length; i++) {
            System.out.print("第" + (i+1) +"组有" + scores[i].length + "个学员，成绩如下：");
            for (int j = 0; j < scores[i].length; j++) {
                System.out.print(scores[i][j]+"\t");
            }
            System.out.println();
        }
    }
}
```
<!-- endtab -->

<!-- tab 内存解析 -->
> 二维数组本质上是元素类型是一维数组的一维数组。

```java
int[][] arr = {
    {1},
    {2,2},
    {3,3,3},
    {4,4,4,4},
    {5,5,5,5,5}
};
```

{% asset_img 05_12.png %}

```java
//1、声明二维数组，并确定行数和列数
int[][] arr = new int[4][5];

//2、确定元素的值
for (int i = 0; i < arr.length; i++) {
    for (int j = 0; j < arr.length; j++) {
        arr[i][j] = i + 1;
    }
}
```

{% asset_img 05_13.png %}

```java
//1、声明一个二维数组，并且确定行数
//因为每一行的列数不同，这里无法直接确定列数
int[][]  arr = new int[5][];

//2、确定每一行的列数
for(int i=0; i<arr.length; i++){
    /*
			arr[0] 的列数是1
			arr[1] 的列数是2
			arr[2] 的列数是3
			arr[3] 的列数是4
			arr[4] 的列数是5
			*/
    arr[i] = new int[i+1];
}

//3、确定元素的值
for(int i=0; i<arr.length; i++){
    for(int j=0; j<arr[i].length; j++){
        arr[i][j] = i+1;
    }
}
```

{% asset_img 05_14.png %}

<!-- endtab -->

<!-- tab 应用举例 -->
**案例1**:获取arr数组中所有元素的和。
> 提示：使用for的嵌套循环即可。
{% asset_img 05_15.png %}

**案例2**:声明：int[] x,y[]; 在给x,y变量赋值以后，以下选项允许通过编译的是： 
```java
声明：int[] x,y[]; 在给x,y变量赋值以后，以下选项允许通过编译的是：
a)    x[0] = y;                 //no
b)    y[0] = x;                 //yes
c)    y[0][0] = x;              //no
d)    x[0][0] = y;              //no
e)    y[0][0] = x[0];           //yes
f)    x = y;                    //no

提示：
一维数组：int[] x  或者int x[]   
二维数组：int[][] y 或者  int[] y[]  或者 int  y[][]

```

**案例3**:使用二维数组打印一个 10 行杨辉三角。
> 提示：
> 1. 第一行有 1 个元素, 第 n 行有 n 个元素
> 2. 每一行的第一个元素和最后一个元素都是 1
> 3. 从第三行开始, 对于非第一个元素和最后一个元素的元素。即：
> ```java
> yanghui[i][j] = yanghui[i-1][j-1] + yanghui[i-1][j];
> ```

{% asset_img 05_16.png%}

```java
/**
 * @author 尚硅谷-宋红康
 * @create 10:11
 */
public class YangHuiTest {
    public static void main(String[] args) {

        //1. 动态初始化的方式创建二维数组
        int[][] yangHui = new int[10][];

        for (int i = 0; i < yangHui.length; i++) {
            yangHui[i] = new int[i + 1];

            //2. 给数组元素赋值
            // 2.1 给外层数组元素中的首元素和末元素赋值
            yangHui[i][0] = yangHui[i][i] = 1;

            //2.2 给外层数组元素中的非首元素和非末元素赋值（难）
            //if(i > 1){ //从 i == 2 开始执行
                for(int j = 1;j < yangHui[i].length - 1;j++){ //非首元素和非末元素的角标范围
                    yangHui[i][j] = yangHui[i-1][j-1] + yangHui[i-1][j];

                }
            //}
        }



        //3. 遍历二维数组
        for (int i = 0; i < yangHui.length; i++) {
            for (int j = 0; j < yangHui[i].length; j++) {
                System.out.print(yangHui[i][j] + "\t");
            }

            System.out.println();
        }

    }
}
```
<!-- endtab -->

{% endtabs %}

## 数组的常见算法

{% tabs 数组常见算法 %}

<!-- tab 数值型数组特征值统计 -->
> 这里的特征值涉及到：平均值、最大值、最小值、总和等

**举例1：**数组统计：求总和、均值

```java
public class TestArrayElementSum {
    public static void main(String[] args) {
        int[] arr = {4,5,6,1,9};
        //求总和、均值
        int sum = 0;//因为0加上任何数都不影响结果
        for(int i=0; i<arr.length; i++){
            sum += arr[i];
        }
        double avg = (double)sum/arr.length;

        System.out.println("sum = " + sum);
        System.out.println("avg = " + avg);
    }
}
```

**举例2：**求数组元素的总乘积
```java
public class TestArrayElementMul {
    public static void main(String[] args) {
        int[] arr = {4,5,6,1,9};

        //求总乘积
        long result = 1;//因为1乘以任何数都不影响结果
        for(int i=0; i<arr.length; i++){
            result *= arr[i];
        }

        System.out.println("result = " + result);
    }
}
```

**举例3：**求数组元素中偶数的个数
```java
public class TestArrayElementEvenCount {
    public static void main(String[] args) {
        int[] arr = {4,5,6,1,9};
        //统计偶数个数
        int evenCount = 0;
        for(int i=0; i<arr.length; i++){
            if(arr[i]%2==0){
                evenCount++;
            }
        }

        System.out.println("evenCount = " + evenCount);
    }
}
```

**举例4：**求数组元素的最大值
> 一楼到十楼的每层电梯门口都放着一颗钻石，钻石大小不一，你乘坐电梯从一楼到十楼，每层电梯都会打开一次，手里只能拿一颗钻石，问怎样才能拿到最大的一颗？

```java
public class TestArrayMax {
    public static void main(String[] args) {
        int[] arr = {4,5,6,1,9};
        //找最大值
        int max = arr[0];
        for(int i=1; i<arr.length; i++){//此处i从1开始，是max不需要与arr[0]再比较一次了
            if(arr[i] > max){
                max = arr[i];
            }
        }

        System.out.println("max = " + max);
    }
}
```

**举例5：**找最值及其第一次出现的下标

```java
public class TestMaxIndex {
    public static void main(String[] args) {
        int[] arr = {4,5,6,1,9};
        //找最大值以及第一个最大值下标
        int max = arr[0];
        int index = 0;
        for(int i=1; i<arr.length; i++){
            if(arr[i] > max){
                max = arr[i];
                index = i;
            }
        }

        System.out.println("max = " + max);
        System.out.println("index = " + index);
    }
}
```

**举例6：**找最值及其所有最值的下标

```java
public class Test13AllMaxIndex {
    public static void main(String[] args) {
        int[] arr = {4,5,6,1,9,9,3};
        //找最大值
        int max = arr[0];
        for(int i=1; i<arr.length; i++){
            if(arr[i] > max){
                max = arr[i];
            }
        }
        System.out.println("最大值是：" + max);
        System.out.print("最大值的下标有：");

        //遍历数组，看哪些元素和最大值是一样的
        for(int i=0; i<arr.length; i++){
            if(max == arr[i]){
                System.out.print(i+"\t");
            }
        }
        System.out.println();
    }
}
```

优化

```java
public class Test13AllMaxIndex2 {
    public static void main(String[] args) {
        int[] arr = {4,5,6,1,9,9,3};
        //找最大值
        int max = arr[0];
        String index = "0";
        for(int i=1; i<arr.length; i++){
            if(arr[i] > max){
                max = arr[i];
                index = i + "";
            }else if(arr[i] == max){
                index += "," + i;
            }
        }

        System.out.println("最大值是" + max);
        System.out.println("最大值的下标是[" + index+"]");
    }
}
```

**举例7(难)：**输入一个整形数组，数组里有正数也有负数。数组中连续的一个或多个整数组成一个子数组，每个子数组都有一个和。求所有子数组的和的最大值。要求时间复杂度为O(n)。
例如：输入的数组为1, -2, 3, -10, -4, 7, 2, -5，和最大的子数组为3, 10, -4, 7, 2，因此输出为该子数组的和18。

```java
public class Test5 {
	public static void main(String[] args) {
		int[] arr = new int[]{1, -2, 3, 10, -4, 7, 2, -5};
		int i = getGreatestSum(arr);
		System.out.println(i);
	}
	
	public static int getGreatestSum(int[] arr){
		int greatestSum = 0;
		if(arr == null || arr.length == 0){
			return 0;
		}
		int temp = greatestSum;
		for(int i = 0;i < arr.length;i++){
			temp += arr[i];
			
			if(temp < 0){
				temp = 0;
			}
			
			if(temp > greatestSum){
				greatestSum = temp;
			}
		}
		if(greatestSum == 0){
			greatestSum = arr[0];
			for(int i = 1;i < arr.length;i++){
				if(greatestSum < arr[i]){
					greatestSum = arr[i];
				}
			}
		}
		return greatestSum;
	}
}
```

**举例8：评委打分**

分析以下需求，并用代码实现：

（1）在编程竞赛中，有10位评委为参赛的选手打分，分数分别为：5，4，6，8，9，0，1，2，7，3

（2）求选手的最后得分（去掉一个最高分和一个最低分后其余8位评委打分的平均值）

```java
/**
 * @author 尚硅谷-宋红康
 * @create 10:03
 */
public class ArrayExer {
    public static void main(String[] args) {
        int[] scores = {5,4,6,8,9,0,1,2,7,3};

        int max = scores[0];
        int min = scores[0];
        int sum = 0;
        for(int i = 0;i < scores.length;i++){
            if(max < scores[i]){
                max = scores[i];
            }

            if(min > scores[i]){
                min = scores[i];
            }

            sum += scores[i];
        }

        double avg = (double)(sum - max - min) / (scores.length - 2);

        System.out.println("选手去掉最高分和最低分之后的平均分为：" + avg);
    }
}
```

<!-- endtab -->
<!-- tab 数组元素的赋值与数组复制 -->
**举例1：**杨辉三角（见二维数组课后案例）
**举例2：**使用简单数组

> (1)创建一个名为ArrayTest的类，在main()方法中声明array1和array2两个变量，他们是int[]类型的数组。
> 
> (2)使用大括号{}，把array1初始化为8个素数：2,3,5,7,11,13,17,19。
> 
> (3)显示array1的内容。
> 
> (4)赋值array2变量等于array1，修改array2中的偶索引元素，使其等于索引值(如array[0]=0,array[2]=2)。打印出array1。  array2 = array1;
> 
> > **思考：**array1和array2是什么关系？
> >
> > **拓展：**修改题目，实现array2对array1数组的复制

{% gallery %}
![](05_17.png)
![](05_18.png)
{% endgallery %}

**举例3：**一个数组，让数组的每个元素去除第一个元素，得到的商作为被除数所在位置的新值。

```java
public class Test3 {
	public static void main(String[] args) {
		int[] arr = new int[]{12,43,65,3,-8,64,2};
		
//		for(int i = 0;i < arr.length;i++){
//			arr[i] = arr[i] / arr[0];
//		}
		for(int i = arr.length -1;i >= 0;i--){
			arr[i] = arr[i] / arr[0];
		}
		//遍历arr
		for(int i = 0;i < arr.length;i++){
			System.out.print(arr[i] + " ");
		}
	}
}
```

**举例4：**创建一个长度为6的int型数组，要求数组元素的值都在1-30之间，且是随机赋值。同时，要求元素的值各不相同。 

```java
public class Test4 {
	// 5-67 Math.random() * 63 + 5;
	@Test
	public void test1() {
		int[] arr = new int[6];
		for (int i = 0; i < arr.length; i++) {// [0,1) [0,30) [1,31)
			arr[i] = (int) (Math.random() * 30) + 1;

			boolean flag = false;
			while (true) {
				for (int j = 0; j < i; j++) {
					if (arr[i] == arr[j]) {
						flag = true;
						break;
					}
				}
				if (flag) {
					arr[i] = (int) (Math.random() * 30) + 1;
					flag = false;
					continue;
				}
				break;
			}
		}

		for (int i = 0; i < arr.length; i++) {
			System.out.println(arr[i]);
		}
	}
	//更优的方法
	@Test
	public void test2(){
		int[] arr = new int[6];
		for (int i = 0; i < arr.length; i++) {// [0,1) [0,30) [1,31)
			arr[i] = (int) (Math.random() * 30) + 1;
			
				for (int j = 0; j < i; j++) {
					if (arr[i] == arr[j]) {
						i--;
						break;
					}
				}
			}

		for (int i = 0; i < arr.length; i++) {
			System.out.println(arr[i]);
		}
	}
}
```

**举例5：**扑克牌
> 案例：遍历扑克牌
> 遍历扑克牌，效果如图所示：
> {% asset_img 05_19.png %}
> 提示：使用两个字符串数组，分别保存花色和点数，再用一个字符串数组保存最后的扑克牌。
> ```java
> String[] hua = {"黑桃","红桃","梅花","方片"};
> String[] dian = {"A","2","3","4","5","6","7","8","9","10","J","Q","K"};
> ```
```java 
package com.atguigu3.common_algorithm.exer5;

/**
 * @author 尚硅谷-宋红康
 * @create 17:16
 */
public class ArrayExer05 {
    public static void main(String[] args) {
        String[] hua = {"黑桃","红桃","梅花","方片"};
        String[] dian = {"A","2","3","4","5","6","7","8","9","10","J","Q","K"};


        String[] pai = new String[hua.length * dian.length];
        int k = 0;
        for(int i = 0;i < hua.length;i++){
            for(int j = 0;j < dian.length;j++){
                pai[k++] = hua[i] + dian[j];
            }
        }

        for (int i = 0; i < pai.length; i++) {
            System.out.print(pai[i] + "  ");
            if(i % 13 == 12){
                System.out.println();
            }
        }

    }
}
```
> 拓展：在上述基础上，增加大王、小王。

**举例6：**回形数
> 从键盘输入一个整数（1~20） ，则以该数字为矩阵的大小，把1,2,3…n*n 的数字按照顺时针螺旋的形式填入其中。
> 
> 例如： 输入数字2，则程序输出： 
> 1 2 
> 4 3 
> 
> 输入数字3，则程序输出： 
> 1 2 3 
> 8 9 4 
> 7 6 5 
> 输入数字4， 则程序输出： 
> 1    2    3    4 
> 12  13  14  5 
> 11  16  15  6 
> 10   9   8    7

方式1:
```java
//方式1
public class RectangleTest {
	public static void main(String[] args) {
		Scanner scanner = new Scanner(System.in);
		System.out.println("输入一个数字");
		int len = scanner.nextInt();
		int[][] arr = new int[len][len];
		
		int s = len * len;
		/*
		 * k = 1:向右
		 * k = 2:向下
		 * k = 3:向左
		 * k = 4:向上
		 */
		int k = 1;
		int i = 0,j = 0;
		for(int m = 1;m <= s;m++){
			if(k == 1){
				if(j < len && arr[i][j] == 0){
					arr[i][j++] = m;
				}else{
					k = 2;
					i++;  
					j--;
					m--;
				}
			}else if(k == 2){
				if(i < len && arr[i][j] == 0){
					arr[i++][j] = m;
				}else{
					k = 3;
					i--;
					j--;
					m--;
				}
			}else if(k == 3){
				if(j >= 0 && arr[i][j] == 0){
					arr[i][j--] = m;
				}else{
					k = 4;
					i--;
					j++;
					m--;
				}
			}else if(k == 4){
				if(i >= 0 && arr[i][j] == 0){
					arr[i--][j] = m;
				}else{
					k = 1;
					i++;
					j++;
					m--;
				}
			}
		}
		
		//遍历
		for(int m = 0;m < arr.length;m++){
			for(int n = 0;n < arr[m].length;n++){
				System.out.print(arr[m][n] + "\t");
			}
			System.out.println();
		}
	}
}
```
方式2:
```java
//方式2
/*
	01 02 03 04 05 06 07 
	24 25 26 27 28 29 08 
	23 40 41 42 43 30 09 
	22 39 48 49 44 31 10 
	21 38 47 46 45 32 11 
	20 37 36 35 34 33 12 
	19 18 17 16 15 14 13 
 */
public class RectangleTest1 {

	public static void main(String[] args) {
		int n = 7;
		int[][] arr = new int[n][n];
		
		int count = 0; //要显示的数据
		int maxX = n-1; //x轴的最大下标
		int maxY = n-1; //Y轴的最大下标
		int minX = 0; //x轴的最小下标
		int minY = 0; //Y轴的最小下标
		while(minX<=maxX) {
			for(int x=minX;x<=maxX;x++) {
				arr[minY][x] = ++count;
			}
			minY++;
			for(int y=minY;y<=maxY;y++) {
				arr[y][maxX] = ++count;
			}
			maxX--;
			for(int x=maxX;x>=minX;x--) {
				arr[maxY][x] = ++count;
			}
			maxY--;
			for(int y=maxY;y>=minY;y--) {
				arr[y][minX] = ++count;
			}
			minX++;
		}
		
		
		for(int i=0;i<arr.length;i++) {
			for(int j=0;j<arr.length;j++) {
				String space = (arr[i][j]+"").length()==1 ? "0":"";
				System.out.print(space+arr[i][j]+" ");
			}
			System.out.println();
		}
	}
}


```
<!-- endtab -->
<!-- tab 数组元素的反转 -->
**实现思想：**数组堆成位置的元素互换
{% asset_img 05_20.png %}
```java
public class TestArrayReverse1 {
    public static void main(String[] args) {
        int[] arr = {1,2,3,4,5};
        System.out.println("反转之前：");
        for (int i = 0; i < arr.length; i++) {
            System.out.println(arr[i]);
        }

        //反转
         /*
        思路：首尾对应位置的元素交换
        （1）确定交换几次
           次数 = 数组.length / 2
        （2）谁和谁交换
        for(int i=0; i<次数; i++){
             int temp = arr[i];
             arr[i] = arr[arr.length-1-i];
             arr[arr.length-1-i] = temp;
        }
         */
        for(int i=0; i<arr.length/2; i++){
            int temp = arr[i];
            arr[i] = arr[arr.length-1-i];
            arr[arr.length-1-i] = temp;
        }

        System.out.println("反转之后：");
        for (int i = 0; i < arr.length; i++) {
            System.out.println(arr[i]);
        }
    }

}
```
方法2：
{% asset_img 05_21.png %}
```java
public class TestArrayReverse2 {
    public static void main(String[] args) {
        int[] arr = {1,2,3,4,5};
        System.out.println("反转之前：");
        for (int i = 0; i < arr.length; i++) {
            System.out.println(arr[i]);
        }

        //反转
        //左右对称位置交换
        for(int left=0,right=arr.length-1; left<right; left++,right--){
            //首  与  尾交换
            int temp = arr[left];
            arr[left] = arr[right];
            arr[right] = temp;
        }

        System.out.println("反转之后：");
        for (int i = 0; i < arr.length; i++) {
            System.out.println(arr[i]);
        }
    }
}
```
<!-- endtab -->

<!-- tab 数组扩容与缩容 -->
**数组的扩容**
> 题目：现有数组 `` int[] arr = new int[]{1,2,3,4,5};`` ，现将数组长度扩容1倍，并将10,20,30三个数据添加到arr数组中，如何操作？
> ```java
> public class ArrTest1 {
>     public static void main(String[] args) {
> 
>         int[] arr = new int[]{1,2,3,4,5};
>         int[] newArr = new int[arr.length << 1];
> 
>         for(int i = 0;i < arr.length;i++){
>             newArr[i] = arr[i];
>         }
> 
>         newArr[arr.length] = 10;
>         newArr[arr.length + 1] = 20;
>         newArr[arr.length + 2] = 30;
> 
>         arr = newArr;
> 
>         //遍历arr
>         for (int i = 0; i < arr.length; i++) {
>             System.out.println(arr[i]);
>         }
>     }
> }
> ```

**数组的缩容**
> 题目：现有数组 `int[] arr={1,2,3,4,5,6,7}`。现需删除数组中索引为4的元素。
> ```java
> public class ArrTest2 {
>     public static void main(String[] args) {
> 
>         int[] arr = {1, 2, 3, 4, 5, 6, 7};
>         //删除数组中索引为4的元素
>         int delIndex = 4;
>         //方案1：
>         /*//创建新数组
>         int[] newArr = new int[arr.length - 1];
> 
>         for (int i = 0; i < delIndex; i++) {
>             newArr[i] = arr[i];
>         }
>         for (int i = delIndex + 1; i < arr.length; i++) {
>             newArr[i - 1] = arr[i];
>         }
> 
>         arr = newArr;
>         for (int i = 0; i < arr.length; i++) {
>             System.out.println(arr[i]);
>         }*/
> 
>         //方案2：
>         for (int i = delIndex; i < arr.length - 1; i++) {
>             arr[i] = arr[i + 1];
>         }
>         arr[arr.length - 1] = 0;
> 
>         for (int i = 0; i < arr.length; i++) {
>             System.out.println(arr[i]);
>         }
>     }
> }
> ```

<!-- endtab -->
<!-- tab 数组的元素查找 -->
**顺序查找**
> 顺序查找：挨个查看
> 要求：对数组元素的顺序没要求
> ```java
> public class TestArrayOrderSearch {
>     //查找value第一次在数组中出现的index
>     public static void main(String[] args){
>         int[] arr = {4,5,6,1,9};
>         int value = 1;
>         int index = -1;
> 
>         for(int i=0; i<arr.length; i++){
>             if(arr[i] == value){
>                 index = i;
>                 break;
>             }
>         }
> 
>         if(index==-1){
>             System.out.println(value + "不存在");
>         }else{
>             System.out.println(value + "的下标是" + index);
>         }
>     }
> }
> ```

**二分查找**
> 举例：
> {% asset_img 05_22.png %}
> 实现步骤：
> {% asset_img 05_23.png %}
> ```java
> //二分法查找：要求此数组必须是有序的。
> int[] arr3 = new int[]{-99,-54,-2,0,2,33,43,256,999};
> boolean isFlag = true;
> int value = 256;
> //int value = 25;
> int head = 0;//首索引位置
> int end = arr3.length - 1;//尾索引位置
> while(head <= end){
>     int middle = (head + end) / 2;
>     if(arr3[middle] == value){
>         System.out.println("找到指定的元素，索引为：" + middle);
>         isFlag = false;
>         break;
>     }else if(arr3[middle] > value){
>         end = middle - 1;
>     }else{//arr3[middle] < value
>         head = middle + 1;
>     }
> }
> 
> if(isFlag){
>     System.out.println("未找打指定的元素");
> }
> ```
<!-- endtab -->

<!-- tab 数组元素排序 -->
{% tabs 数组元素排序 %}
<!-- tab 算法概述 -->
**定义**
> - 排序：假设含有n个记录的序列为{R1，R2，...,Rn},其相应的关键字序列为{K1，K2，...,Kn}。将这些记录重新排序为{Ri1,Ri2,...,Rin},使得相应的关键字值满足条Ki1<=Ki2<=...<=Kin,这样的一种操作称为排序。
> - 通常来说，排序的目的是快速查找。

**衡量排序算法的优劣：**
> - `时间复杂度`：分析关键字的比较次数和记录的移动次数
> - 常见的算法时间复杂度由小到大依次为：Ο(1)＜Ο(log2n)＜Ο(n)＜Ο(nlog2n)＜Ο(n<sup>2</sup>)＜Ο(n<sup>3</sup>)＜…＜Ο(2<sup>n</sup>)＜Ο(n!)<O(n<sup>n</sup>)
> - `空间复杂度`：分析排序算法中需要多少辅助内存
>   ```
>   一个算法的空间复杂度S(n)定义为该算法所耗费的存储空间，它也是问题规模n的函数。
>   ```
> - `稳定性`：若两个记录A和B的关键字值相等，但排序后A、B的先后次序保持不变，则称这种排序算法是稳定的。
> {% asset_img 05_24.png%}
<!-- endtab -->
<!-- tab 排序算法概述 -->
**排序算法分类：内部排序和外部排序**
> - `内部排序`：整个排序过程不需要借助于外部存储器（如磁盘等），所有排序操作都在内存中完成。
> - `外部排序`：参与排序的数据非常多，数据量非常大，计算机无法把整个排序过程放在内存中完成，必须借助于外部存储器（如磁盘）。外部排序最常见的是多路归并排序。可以认为外部排序是由多次内部排序组成。

**十大内部排序算法**
> 数组的排序算法很多，实现方式各不相同，时间复杂度、空间复杂度、稳定性也各不相同：
> {% asset_img 05_25.png %}
> 常见时间复杂度所消耗的时间从小到大排序：
> **O(1) < O(logn) < O(n) < O(nlogn) < O(n^2) < O(n^3) < O(2^n) < O(n!) < O(n^n)**
> 注意，经常将以2为底n的对数简写成**logn**。
> {% asset_img 05_26.png %}
<!-- endtab -->
<!-- tab 冒泡排序 -->
**排序思想**
> 1. 比较相邻的元素。如果第一个比第二个大（升序），就交换他们两个。
> 2. 对每一对相邻元素作同样的工作，从开始第一对到结尾的最后一对。这步做完后，最后的元素会是最大的数。
> 3. 针对所有的元素重复以上的步骤，除了最后一个。
> 4. 持续每次对越来越少的元素重复上面的步骤，直到没有任何一对数字需要比较为止。
> {% asset_img 05_27.png%}
> ```java
> /*
> 1、冒泡排序（最经典）
> 思想：每一次比较“相邻（位置相邻）”元素，如果它们不符合目标顺序（例如：从小到大），
>      就交换它们，经过多轮比较，最终实现排序。
> 	 （例如：从小到大）	 每一轮可以把最大的沉底，或最小的冒顶。
> 	 
> 过程：arr{6,9,2,9,1}  目标：从小到大
> 
> 第一轮：
> 	第1次，arr[0]与arr[1]，6>9不成立，满足目标要求，不交换
> 	第2次，arr[1]与arr[2]，9>2成立，不满足目标要求，交换arr[1]与arr[2] {6,2,9,9,1}
> 	第3次，arr[2]与arr[3]，9>9不成立，满足目标要求，不交换
> 	第4次，arr[3]与arr[4]，9>1成立，不满足目标要求，交换arr[3]与arr[4] {6,2,9,1,9}
> 	第一轮所有元素{6,9,2,9,1}已经都参与了比较，结束。
> 	第一轮的结果：第“一”最大值9沉底（本次是后面的9沉底），即到{6,2,9,1,9}元素的最右边
> 
> 第二轮：
> 	第1次，arr[0]与arr[1]，6>2成立，不满足目标要求，交换arr[0]与arr[1] {2,6,9,1,9}
> 	第2次，arr[1]与arr[2]，6>9不成立，满足目标要求，不交换
> 	第3次：arr[2]与arr[3]，9>1成立，不满足目标要求，交换arr[2]与arr[3] {2,6,1,9,9}
> 	第二轮未排序的所有元素 {6,2,9,1}已经都参与了比较，结束。
> 	第二轮的结果：第“二”最大值9沉底（本次是前面的9沉底），即到{2,6,1,9}元素的最右边
> 第三轮：
> 	第1次，arr[0]与arr[1]，2>6不成立，满足目标要求，不交换
> 	第2次，arr[1]与arr[2]，6>1成立，不满足目标要求，交换arr[1]与arr[2] {2,1,6,9,9}
> 	第三轮未排序的所有元素{2,6,1}已经都参与了比较，结束。
> 	第三轮的结果：第三最大值6沉底，即到 {2,1,6}元素的最右边
> 第四轮：
> 	第1次，arr[0]与arr[1]，2>1成立，不满足目标要求，交换arr[0]与arr[1] {1,2,6,9,9}
> 	第四轮未排序的所有元素{2,1}已经都参与了比较，结束。
> 	第四轮的结果：第四最大值2沉底，即到{1,2}元素的最右边
> 
> */
> public class Test19BubbleSort{
>     public static void main(String[] args){
>         int[] arr = {6,9,2,9,1};
> 
>         //目标：从小到大
>         //冒泡排序的轮数 = 元素的总个数 - 1
>         //轮数是多轮，每一轮比较的次数是多次，需要用到双重循环，即循环嵌套
>         //外循环控制 轮数，内循环控制每一轮的比较次数和过程
>         for(int i=1; i<arr.length; i++){ //循环次数是arr.length-1次/轮
> 			/*
> 			假设arr.length=5
> 			i=1,第1轮，比较4次
> 				arr[0]与arr[1]
> 				arr[1]与arr[2]
> 				arr[2]与arr[3]
> 				arr[3]与arr[4]
> 				
> 				arr[j]与arr[j+1]，int j=0;j<4; j++
> 				
> 			i=2,第2轮，比较3次
> 				arr[0]与arr[1]
> 				arr[1]与arr[2]
> 				arr[2]与arr[3]
> 				
> 				arr[j]与arr[j+1]，int j=0;j<3; j++
> 				
> 			i=3,第3轮，比较2次
> 				arr[0]与arr[1]
> 				arr[1]与arr[2]
> 				
> 				arr[j]与arr[j+1]，int j=0;j<2; j++
> 			i=4,第4轮，比较1次
> 				arr[0]与arr[1]
> 			
> 				arr[j]与arr[j+1]，int j=0;j<1; j++
> 				
> 				int j=0; j<arr.length-i; j++
> 			*/
>             for(int j=0; j<arr.length-i; j++){
>                 //希望的是arr[j] < arr[j+1]
>                 if(arr[j] > arr[j+1]){
>                     //交换arr[j]与arr[j+1]
>                     int temp = arr[j];
>                     arr[j] = arr[j+1];
>                     arr[j+1] = temp;
>                 }
>             }
>         }
> 
>         //完成排序，遍历结果
>         for(int i=0; i<arr.length; i++){
>             System.out.print(arr[i]+"  ");
>         }
>     }
> }
> 
> ```

**冒泡排序优化**
```java
/*
思考：冒泡排序是否可以优化
*/
class Test19BubbleSort2{
	public static void main(String[] args) {
        int[] arr = {1, 3, 5, 7, 9};

        //从小到大排序
        for (int i = 0; i < arr.length - 1; i++) {
            boolean flag = true;//假设数组已经是有序的
            for (int j = 0; j < arr.length - 1 - i; j++) {
                //希望的是arr[j] < arr[j+1]
                if (arr[j] > arr[j + 1]) {
                    //交换arr[j]与arr[j+1]
                    int temp = arr[j];
                    arr[j] = arr[j + 1];
                    arr[j + 1] = temp;

                    flag = false;//如果元素发生了交换，那么说明数组还没有排好序
                }
            }
            if (flag) {
                break;
            }
        }

        //完成排序，遍历结果
        for (int i = 0; i < arr.length; i++) {
            System.out.print(arr[i] + "  ");
        }
    }
}
```
<!-- endtab -->
<!-- tab 快速排序 -->
> 快速排序（Quick Sort）由`图灵奖`获得者`Tony Hoare`发明，被列为`20世纪十大算法之一`，是迄今为止所有内排序算法中速度最快的一种，快速排序的时间复杂度为O(nlog(n))。
> 快速排序通常明显比同为O(nlogn)的其他算法更快，因此常被采用，而且快排采用了分治法的思想，所以在很多笔试面试中能经常看到快排的影子。

**排序思想：**
> 1. 从数列中挑出一个元素，称为"基准"（pivot），
> 2. 重新排序数列，所有元素比基准值小的摆放在基准前面，所有元素比基准值大的摆在基准的后面（相同的数可以到任一边）。在这个分区结束之后，该基准就处于数列的中间位置。这个称为分区（partition）操作。
> 3. 递归地（recursive）把小于基准值元素的子数列和大于基准值元素的子数列排序。
> 4. 递归的最底部情形，是数列的大小是零或一，也就是永远都已经被排序好了。虽然一直递归下去，但是这个算法总会结束，因为在每次的迭代（iteration）中，它至少会把一个元素摆到它最后的位置去。
>
图示1：
> {% asset_img 05_28.png%}

图示2：

> 第一轮操作：
> {% asset_img 05_29.png%}
> 第二轮操作：
> {% asset_img 05_30.png%}
<!-- endtab -->

<!-- tab 内部排序性能比较与选择 -->
**性能比较**
> - **从平均时间而言**：快速排序最佳。但在最坏情况下时间性能不如堆排序和归并排序。
> - **从算法简单性看**：由于直接选择排序、直接插入排序和冒泡排序的算法比较简单，将其认为是简单算法。对于Shell排序、堆排序、快速排序和归并排序算法，其算法比较复杂，认为是复杂排序。
> - **从稳定性看**：直接插入排序、冒泡排序和归并排序时稳定的；而直接选择排序、快速排序、 Shell排序和堆排序是不稳定排序
> - **从待排序的记录数n的大小看**，n较小时，宜采用简单排序；而n较大时宜采用改进排序。

**选择**

> - 若n较小(如n≤50)，可采用直接插入或直接选择排序。
>   当记录规模较小时，直接插入排序较好；否则因为直接选择移动的记录数少于直接插入，应选直接选择排序为宜。
> - 若文件初始状态基本有序(指正序)，则应选用直接插入、冒泡或随机的快速排序为宜；
> - 若n较大，则应采用时间复杂度为O(nlgn)的排序方法：快速排序、堆排序或归并排序。
<!-- endtab -->
{% endtabs %}
<!-- endtab -->
{% endtabs %}

## Arrays工具类的使用
> `java.util.Arrays`类即为操作数组的工具类，包含了用来操作数组（比如排序和搜索）的各种方法。 比如：
{% tabs Arrays工具类 %}
<!-- tab 数组元素拼接 -->
- `static String toString(int[] a)` ：字符串表示形式由数组的元素列表组成，括在方括号（"[]"）中。相邻元素用字符 ", "（逗号加空格）分隔。形式为：[元素1，元素2，元素3。。。]
- `static String toString(Object[] a)` ：字符串表示形式由数组的元素列表组成，括在方括号（"[]"）中。相邻元素用字符 ", "（逗号加空格）分隔。元素将自动调用自己从Object继承的toString方法将对象转为字符串进行拼接，如果没有重写，则返回类型@hash值，如果重写则按重写返回的字符串进行拼接。
<!-- endtab -->
<!-- tab 数组排序 -->
* `static void sort(int[] a)` ：将a数组按照从小到大进行排序
* `static void sort(int[] a, int fromIndex, int toIndex)` ：将a数组的[fromIndex, toIndex)部分按照升序排列
* `static void sort(Object[] a)` ：根据元素的自然顺序对指定对象数组按升序进行排序。
* `static <T> void sort(T[] a, Comparator<? super T> c)` ：根据指定比较器产生的顺序对指定对象数组进行排序。
<!-- endtab -->
<!-- tab 数组元素的二分查找 -->
- `static int binarySearch(int[] a, int key)`  、`static int binarySearch(Object[] a, Object key)` ：要求数组有序，在数组中查找key是否存在，如果存在返回第一次找到的下标，不存在返回负数。
<!-- endtab -->
<!-- tab 数组的复制 -->
* `static int[] copyOf(int[] original, int newLength)`  ：根据original原数组复制一个长度为newLength的新数组，并返回新数组
* `static <T> T[] copyOf(T[] original,int newLength)`：根据original原数组复制一个长度为newLength的新数组，并返回新数组
* `static int[] copyOfRange(int[] original, int from, int to)` ：复制original原数组的[from,to)构成新数组，并返回新数组
* `static <T> T[] copyOfRange(T[] original,int from,int to)`：复制original原数组的[from,to)构成新数组，并返回新数组
<!-- endtab -->
<!-- tab 比较两个数组是否相等 -->
* `static boolean equals(int[] a, int[] a2)` ：比较两个数组的长度、元素是否完全相同
* `static boolean equals(Object[] a,Object[] a2)`：比较两个数组的长度、元素是否完全相同
<!-- endtab -->
<!-- tab 填充数组 -->
* `static void fill(int[] a, int val)` ：用val值填充整个a数组
* `static void fill(Object[] a,Object val)`：用val对象填充整个a数组
* `static void fill(int[] a, int fromIndex, int toIndex, int val)`：将a数组[fromIndex,toIndex)部分填充为val值
* `static void fill(Object[] a, int fromIndex, int toIndex, Object val)` ：将a数组[fromIndex,toIndex)部分填充为val对象
<!-- endtab -->
{% endtabs %}
**举例**：`java.util.Arrays`类的`sort()`方法提供了数组元素排序功能：
```java
import java.util.Arrays;
public class SortTest {
	public static void main(String[] args) {
		int[] arr = {3, 2, 5, 1, 6};
        System.out.println("排序前" + Arrays.toString(arr));
        Arrays.sort(arr);
        System.out.println("排序后" + Arrays.toString(arr));
	}
}
```

## 数组中的常见异常

{% tabs 数组中常见异常%}
<!-- tab 数组角标越界异常 -->
> 当访问数组元素时，下标指定超出`[0, 数组名.length-1]`的范围时，就会报数组下标越界异常：`ArrayIndexOutOfBoundsException`。
> ```java
> public class TestArrayIndexOutOfBoundsException {
>     public static void main(String[] args) {
>         int[] arr = {1,2,3};
>        // System.out.println("最后一个元素：" + arr[3]);//错误，下标越界
>       //  System.out.println("最后一个元素：" + arr[arr.length]);//错误，下标越界
>         System.out.println("最后一个元素：" + arr[arr.length-1]);//对
>     }
> }
> ```

> 创建数组，赋值3个元素，数组的索引就是0，1，2，没有3索引，因此我们不能访问数组中不存在的索引，程序运行后，将会抛出 `ArrayIndexOutOfBoundsException`  数组越界异常。在开发中，数组的越界异常是**不能出现**的，一旦出现了，就必须要修改我们编写的代码。
> {% asset_img 05_31.png%}
<!-- endtab -->
<!-- tab 空指针异常 -->
> 观察一下代码，运行后会出现什么结果。
> ```java
> public class TestNullPointerException {
>     public static void main(String[] args) {
>         //定义数组
>         int[][] arr = new int[3][];
> 
>         System.out.println(arr[0][0]);//NullPointerException
>     }
> }
```

> 因为此时数组的每一行还未分配具体存储元素的空间，此时arr\[0\]是null，此时访问arr\[0\]\[0\]会抛出`NullPointerException` 空指针异常。
> {% asset_img 05_32.png%}

**空指针异常在内存图中的表现**
{% asset_img 05_33.png%}

**小结：空指针异常情况**
```java
		//举例一：
//		int[] arr1 = new int[10];
//		arr1 = null;
//		System.out.println(arr1[9]);
		
		//举例二：
//		int[][] arr2 = new int[5][];
//		//arr2[3] = new int[10];
//		System.out.println(arr2[3][3]);
		
		//举例三：
		String[] arr3 = new String[10];
		System.out.println(arr3[2].toString());
```
<!-- endtab -->
{% endtabs %}

---

# 面向对象

## 引入

## 类

### 类的成员

### 抽象类

### 枚举类

### 内部类

### 包装类

## 接口

## 注解

## 面向对象特征

## 关键字使用


