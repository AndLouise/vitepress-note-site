# Java 基础知识

## Java 语言概述

Java 是一种面向对象的编程语言，由 Sun Microsystems 公司于 1995 年推出。Java 语言具有简单、面向对象、分布式、健壮、安全、平台无关、可移植、高性能、多线程和动态等特性。

### Java 平台体系
- **Java SE** (Standard Edition) - 标准版，包含核心类库
- **Java EE** (Enterprise Edition) - 企业版，用于企业级应用开发
- **Java ME** (Micro Edition) - 微型版，用于嵌入式设备开发

## 基础语法

### 数据类型

#### 基本数据类型
- **整型**: `byte`(1字节), `short`(2字节), `int`(4字节), `long`(8字节)
- **浮点型**: `float`(4字节), `double`(8字节)
- **字符型**: `char`(2字节)
- **布尔型**: `boolean`(1位)

#### 引用数据类型
- 类 (Class)
- 接口 (Interface)
- 数组 (Array)

### 变量与常量

```java
// 变量声明
int age = 25;
double salary = 5000.0;
String name = "张三";

// 常量声明
final double PI = 3.14159;
final int MAX_SIZE = 100;
```

### 运算符

- **算术运算符**: `+`, `-`, `*`, `/`, `%`
- **关系运算符**: `==`, `!=`, `>`, `<`, `>=`, `<=`
- **逻辑运算符**: `&&`, `||`, `!`
- **赋值运算符**: `=`, `+=`, `-=`, `*=`, `/=`
- **位运算符**: `&`, `|`, `^`, `~`, `<<`, `>>`

## 流程控制

### 条件语句

```java
// if-else 语句
if (score >= 90) {
    System.out.println("优秀");
} else if (score >= 60) {
    System.out.println("及格");
} else {
    System.out.println("不及格");
}

// switch 语句
switch (day) {
    case 1:
        System.out.println("星期一");
        break;
    case 2:
        System.out.println("星期二");
        break;
    default:
        System.out.println("其他日子");
}
```

### 循环语句

```java
// for 循环
for (int i = 0; i < 10; i++) {
    System.out.println(i);
}

// while 循环
int i = 0;
while (i < 10) {
    System.out.println(i);
    i++;
}

// do-while 循环
int j = 0;
do {
    System.out.println(j);
    j++;
} while (j < 10);
```

## 面向对象编程

### 类与对象

```java
// 类定义
public class Student {
    // 属性（成员变量）
    private String name;
    private int age;
    
    // 构造方法
    public Student(String name, int age) {
        this.name = name;
        this.age = age;
    }
    
    // 方法
    public void study() {
        System.out.println(name + "正在学习");
    }
    
    // Getter 和 Setter 方法
    public String getName() {
        return name;
    }
    
    public void setName(String name) {
        this.name = name;
    }
}

// 创建对象
Student student = new Student("李四", 20);
student.study();
```

### 面向对象三大特性

#### 封装 (Encapsulation)
将数据和行为包装在一起，隐藏实现细节，只暴露必要的接口。

#### 继承 (Inheritance)
子类继承父类的属性和方法，实现代码复用。

```java
class Person {
    String name;
    int age;
    
    public void eat() {
        System.out.println("吃饭");
    }
}

class Teacher extends Person {
    String subject;
    
    public void teach() {
        System.out.println("教学");
    }
}
```

#### 多态 (Polymorphism)
同一操作作用于不同的对象，可以有不同的解释和执行结果。

```java
// 方法重载（编译时多态）
class Calculator {
    public int add(int a, int b) {
        return a + b;
    }
    
    public double add(double a, double b) {
        return a + b;
    }
}

// 方法重写（运行时多态）
class Animal {
    public void makeSound() {
        System.out.println("动物叫");
    }
}

class Dog extends Animal {
    @Override
    public void makeSound() {
        System.out.println("汪汪汪");
    }
}
```

### 抽象类与接口

```java
// 抽象类
abstract class Shape {
    // 抽象方法
    abstract double calculateArea();
    
    // 具体方法
    public void display() {
        System.out.println("这是一个形状");
    }
}

// 接口
interface Drawable {
    void draw();  // 默认 public abstract
    default void setColor(String color) {
        System.out.println("设置颜色: " + color);
    }
}

class Circle extends Shape implements Drawable {
    private double radius;
    
    public Circle(double radius) {
        this.radius = radius;
    }
    
    @Override
    double calculateArea() {
        return Math.PI * radius * radius;
    }
    
    @Override
    public void draw() {
        System.out.println("绘制圆形");
    }
}
```

## 异常处理

```java
public class ExceptionDemo {
    public static void main(String[] args) {
        try {
            int result = divide(10, 0);
            System.out.println("结果: " + result);
        } catch (ArithmeticException e) {
            System.out.println("除数不能为零: " + e.getMessage());
        } finally {
            System.out.println("程序执行完毕");
        }
    }
    
    public static int divide(int a, int b) {
        if (b == 0) {
            throw new ArithmeticException("除数不能为零");
        }
        return a / b;
    }
}
```

## 集合框架

### 常用集合类

```java
import java.util.*;

public class CollectionDemo {
    public static void main(String[] args) {
        // List - 有序可重复
        List<String> list = new ArrayList<>();
        list.add("苹果");
        list.add("香蕉");
        list.add("橙子");
        
        // Set - 无序不重复
        Set<Integer> set = new HashSet<>();
        set.add(1);
        set.add(2);
        set.add(1);  // 重复元素不会被添加
        
        // Map - 键值对
        Map<String, Integer> map = new HashMap<>();
        map.put("张三", 20);
        map.put("李四", 22);
        map.put("王五", 25);
        
        // 遍历集合
        for (String fruit : list) {
            System.out.println(fruit);
        }
        
        for (Map.Entry<String, Integer> entry : map.entrySet()) {
            System.out.println(entry.getKey() + ": " + entry.getValue());
        }
    }
}
```

## 输入输出

```java
import java.util.Scanner;
import java.io.*;

public class IODemo {
    public static void main(String[] args) {
        // 控制台输入
        Scanner scanner = new Scanner(System.in);
        System.out.print("请输入您的姓名: ");
        String name = scanner.nextLine();
        System.out.println("您好, " + name);
        
        // 文件读写
        try {
            // 写入文件
            FileWriter writer = new FileWriter("test.txt");
            writer.write("Hello, World!");
            writer.close();
            
            // 读取文件
            FileReader reader = new FileReader("test.txt");
            BufferedReader br = new BufferedReader(reader);
            String line;
            while ((line = br.readLine()) != null) {
                System.out.println(line);
            }
            br.close();
        } catch (IOException e) {
            e.printStackTrace();
        }
    }
}
```

## 多线程编程

```java
class MyThread extends Thread {
    private String threadName;
    
    public MyThread(String name) {
        this.threadName = name;
    }
    
    @Override
    public void run() {
        for (int i = 0; i < 5; i++) {
            System.out.println(threadName + " 运行: " + i);
            try {
                Thread.sleep(1000);  // 休眠1秒
            } catch (InterruptedException e) {
                e.printStackTrace();
            }
        }
    }
}

public class ThreadDemo {
    public static void main(String[] args) {
        MyThread thread1 = new MyThread("线程1");
        MyThread thread2 = new MyThread("线程2");
        
        thread1.start();  // 启动线程
        thread2.start();
    }
}
```

## Java 8 新特性

### Lambda 表达式
```java
List<String> names = Arrays.asList("张三", "李四", "王五");

// 传统方式
Collections.sort(names, new Comparator<String>() {
    @Override
    public int compare(String a, String b) {
        return a.compareTo(b);
    }
});

// Lambda 表达式
Collections.sort(names, (a, b) -> a.compareTo(b));

// 方法引用
names.forEach(System.out::println);
```

### Stream API
```java
List<Integer> numbers = Arrays.asList(1, 2, 3, 4, 5, 6, 7, 8, 9, 10);

// 使用 Stream 进行处理
int sum = numbers.stream()
                .filter(n -> n % 2 == 0)  // 过滤偶数
                .mapToInt(n -> n * 2)     // 每个元素乘以2
                .sum();                   // 求和

System.out.println("结果: " + sum);
```

## 最佳实践

1. **命名规范**: 使用有意义的变量名和方法名
2. **代码注释**: 为重要的类和方法添加文档注释
3. **异常处理**: 不要忽略异常，要适当处理或抛出
4. **资源管理**: 使用 try-with-resources 自动管理资源
5. **代码复用**: 合理使用继承和组合，避免代码重复
6. **性能优化**: 避免在循环中创建对象，合理使用字符串拼接

---
