# JAVA-Note
JAVA 学习笔记

## 2020.06.14
[2020.06.14](https://github.com/hanhan1207/JAVA-Note/issues/1) 
  - 包装类型
  - 自动装箱、拆箱
  - String
  - StringBuilder
  - StringJoiner
  - 编码
  
## 2020.06.15
[2020.06.15](https://github.com/hanhan1207/JAVA-Note/issues/2)
  - JavaBean
  - 枚举类：Enum
  
## 2020.06.27 
  - 堆（Heap):存放对象实例，所有对象实例及数组都要在堆上分配。
  - 栈（Stack):指虚拟机栈，用于存储局部变量，例如基本数据类型、引用类型。方法执行完，自动释放。
  - 方法区（Method Area）：存储已被虚拟机加载的类信息、常量、静态变量、编译后的代码等。
  
## 2020.06.28
  - 属性（成员变量） vs 局部变量
    - 相同点
      - 定义变量格式：数据类型 变量名 = 变量值
      - 先声明，后使用
      - 变量都有其对应的作用域
    - 不同点
      - 类中声明的位置不同
        - 属性：定义在类中
        - 局部变量：声明在方法内、方法形参、代码块内、构造器形参、构造器内部变量
      - 权限修饰符的不同
        - 属性：可以在声明属性时，使用权限修饰符。
        - 常用的权限修饰符：private、public、缺省、protected  ---> 封装性
        - 局部变量：不可以使用修饰符
      - 默认初始化值不同
        - 属性：整型（byte、short、int、long）：0  
               浮点型（float、double）：0.0  
               字符型（char）：0（或'\u0000'）  
               布尔型（boolean）：false  
               引用数据类型（类、数组、接口）：null  
        - 局部变量：没有默认初始化值，使用前必须先赋值；特别地，形参在方法调用时赋值
      - 内存中加载位置不同
        - 属性：加载到堆（非static）
        - 局部变量：加载到栈
## 2020.06.29
  - 方法的重载（Overload）：
    - 一个类中可以有多个同名方法，只需要方法的参数个数或者参数类型不同即可
    - 例如Arrays类重载的sort() / binarySearch()
    
## 2020.06.30
  - 可变个数形参的方法
    - 格式：数据类型 ... 变量名
    - 例如String ... strs，即String[] strs
    - 调用可变个数形参的方法时，传入参数可以是0，1，2...个
  - 方法参数的值传递机制
    - 如果变量时基本数据类型，赋值的是变量所保存的数据值
    - 如果是引用数据类型，赋值的是变量所保存的数据的地址值
    - 例：swap()方法的形参
      - 基本数据类型，则只是复制了一份，复制后的交换成功，原数据交换失败
      - 引用数据类型，原数据的地址复制给形参，交换成功

        
