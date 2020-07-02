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
  - 堆（Heap):存放对象实例，所有对象实例及数组都要在堆上分配
  - 栈（Stack):指虚拟机栈，用于存储局部变量，例如基本数据类型、引用类型。方法执行完，自动释放
  - 方法区（Method Area）：存储已被虚拟机加载的类信息、常量、静态变量、编译后的代码等
  
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
      - 基本数据类型，将实参复制一份传给形参，在栈中开辟新的空间存入复制的值，复制值交换成功，原数据并没有交换
      - 引用数据类型，实参的地址复制给形参，即形参也指向实参在堆中的地址空间，交换成功
    
## 2020.07.01
  - 值传递机制的补充
    - 对于String类型的的值传递，因为字符串对象不可变，所以方法体内对原字符串的修改不成功，会开辟一个新的地址并赋值给形参
  - 封装与隐藏
    - 通常对对象属性赋值以 对象.属性 赋值，实际上需要对属性进行限制， 不能随意赋值，则需要将属性设为 private ，并使用 setter() 方法赋值或加上限制条件
    - 同理，使用 getter() 方法获取属性值
    - 封装性的体现之一，将属性设置为 private ，将 getter()/setter() 方法设置为 public。
    - 封装性需要修饰符来声明
      - 四种修饰符的最大使用范围，从小到大
        - privated:同一个类使用
        - 缺省:同一个包内使用
        - protected:不同包的子类可使用
        - public:同一个工程下使用
      - 修饰符可用于类、属性、方法、构造器和内部类
        - 特殊地，类只能用 public 和缺省修饰
    - 构造器（构造方法）
      - 作用：1.创建对象 2.初始化对象属性
      - 如果没有显示定义，则系统提供默认无参的构造器
      - 定义构造器的格式：权限修饰符 类名（形参）{}
      - 构造器也可以重载，一个类中可以定义多个构造器
      - 一旦显示地定义了构造器，系统不再提供默认的无参构造器
      
        
     
    
   

        
