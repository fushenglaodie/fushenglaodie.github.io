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

<!-- tab 初始化 -->
**静态初始化**
> 
```java

```
<!-- endtab -->

{% endtabs %}

#### 一维数组的初始化
> 测试12的dD
#### 一维数组的使用
#### 一维数组的遍历
#### 数组元素的默认值