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
      
## 2020.07.02
  - this关键字
    - this表示当前对象
    - this调用属性/方法
      - 如果方法的形参和属性不同名，则可以省略this；否则，必须加上this
    - this调用构造器
      - 在类的构造器中，使用this(形参列表)调用本类中指定的其它构造器
      - 构造器不能使用this(形参列表)调用自己
      - 构造器调用必须放在首行
      - 构造器最多调用一个其它的构造器
      
## 2020.07.03
  - 完成客户信息管理软件，复习巩固面向对象基础知识：类、对象、构造器、封装性等。
  
## 2020.07.15
  - 继承性的好处
    - 减少代码冗余，提高了代码的服用性
    - 便于功能的扩展
    - 为多态性的使用提供前提
  
  - 继承性的格式： class A extends B {}
    - A：子类、派生类、subclass  
      B：父类、超类、基类、superclass
    - 子类 A 继承了 父类 B 的所有属性和方法  
      特别地，如果父类 B 定义了 private 属性或方法，子类 A 仍然继承了，只是由于封装性，不能直接调用该属性或方法（需要用get()/set()）
      
  - Java不支持多继承（C++支持），Java中所有类都继承于Object类（除了java.lang.Object自己)
  
## 2020.07.19
  - 方法的重写（Override / Overwrite）
    - 子类继承父类后，对同名同参数的方法进行覆盖操作。
    - 子类重写的方法与被重写方法必须同名同参数
    - 子类重写的方法的权限修饰符 >= 被重写方法的的权限修饰符
    - 子类不能重写父类中 private 修饰的方法
    - 返回值类型
      - 父类如果是 void；子类只能是 void
      - 父类：A类型；子类：A类型或A的子类
      - 父类：基本数据类型（double）；子类：相同的基本数据类型（double）
    - 异常类型： 子类重写方法抛出异常类型 <= 父类被重写方法的 ~
    
## 2020.07.26
  - 多态性
    - 对象的多态性：父类的引用指向子类的对象     
      > Person p = new Man(); p.eat(); p.walk(); 当调用子父类同名同参数的方法时，执行的是子类重写后的方法
    - 多态的使用：虚拟方法调用  
        - 编译期，只能调用父类中声明的方法，实际运行期，执行的是子类重写父类的方法
        - 有了对象的多态性以后，内存中（堆中）实际上加载了子类特有的属性和方法，但是变量类型声明为父类类型，导致编译时，只能调用父类中声明的属性和方法，而子类的不能调用。  
          > 使用强制类型转换: Person p1 = new Man();//此时有了多态性，但是p1不能调用 Man 类特有的属性和方法  
            Man m1 = (Man)p1;//将p1强制转换为Man,此时即可调用
    - 多态性的使用前提
      - 类的继承关系
      - 方法的重写
      - 多态性不适用于属性
    - 为什么要利用多态性？  
      精简代码，提高代码复用性，例如 func(父类对象){父类方法;} 调用 func(传入子类对象){实际运行的是子类方法;}
      
## 2020.07.27
  - 多态性的补充
    - 强制类型转换：父类转子类（向下转型）
      - 避免使用强转时出现ClassCastException异常，使用instanceof关键字  
        a instanceof A: 判断对象 a 是否时类 A 的实例，是则返回true,反之返回false
        
  - == 的使用
    - 可以使用在基本数据类型和引用数据类型变量中
    - 基本数据类型：比较变量的值是否相同
    - 引用数据类型：比较变量指向的地址是否相同
    
  - equals() 的使用
    - 对象/引用.equals(对象/引用)
    - Object类的equals()返回this.obj == obj，所以仍是比较地址，如果要对两个对象的实体内容比较，需要重写（String类重写了该方法）
  
  - toString()的使用
    - Object类返回的是对象的类名+对象所在的内存地址
    - String,Date等类均对toString()进行了重写
    
## 2020.07.28
  - 基本数据类型、包装类和String三者之间的相互转换
    - 自动装箱、拆箱: 基本数据类型和包装类相互转换
    - 基本数据类型、包装类 -> String: valueOf(Xxx xx)
    - String -> 基本数据类型、包装类：parseXxx(String s)
    
## 2020.07.31
  - static关键字的使用
    - static可修饰属性、方法、代码块、内部类
    - static修饰属性（类属性）
      - 该属性为所有类的对象共享，某一对象对其修改后，所有对象调用此属性都是修改后的
      - 静态属性随着类的加载而加载，可通过 类.静态变量 调用；因为类只加载一次，所以静态属性也只加载一次
    - static修饰方法
      - 类加载后就可以调用, 类.静态方法
      - 静态方法中，只能调用静态的方法或属性
      - 静态方法中，不能使用this,super关键字
    - 生命周期：类加载 -> 对象创建 -> 对象销毁 -...> 类销毁
    
## 2020.08.01
  - 设计模式   
    > 大量实际中总结和理论化后优选的代码结构、编程风格和解决问题的思考方式
    - 单例模式（Singleton）   
      保证某个类**只能存在一个对象实例**
      - 饿汉式实现
        - 私有化类的构造器（private），避免在该类之外使用 new 创建对象
        - 内部创建类的对象，要求此对象也声明为静态和私有的（private static）
        - 提供公共的静态方法，返回类的对象
        - 缺点：对象加载时间过长，有可能长时间不用
        - 优点：饿汉式是线程安全的
      - 懒汉式实现
        - 私有化类的构造器
        - 声明当前类对象（private static），没有初始化（null）
        - 提供公共的静态方法，判断当前是否有对象，有则直接返回，无则创建一个对象
        - 缺点：线程不安全，多线程场景需要做修改
        - 优点：延迟对象的创建，节省内存资源
      - 应用场景
        - 网站计数器
        - 应用程序的日志应用
        - 数据库连接池
        - 读取配置文件的类
        - Application
        - Win的任务管理器和回收站
        
## 2020.08.02
  - main()方法的使用
    - main()方法作为程序的入口
    - main()方法作为普通的静态方法
    
  - 代码块
    - 初始化类、对象
    - 无修饰符/static修饰
      - 静态代码块（static）
        - 可以有输出语句
        - 随着类的加载而执行（只执行一次）
        - 如果一个类中定义了多个静态代码块，则按照声明的先后顺序执行
        - 作用：初始化类的信息
      - 非静态代码块
        - 可以有输出语句
        - 随着对象创建而执行（每创建一次对象，就执行一次）
        - 作用：可以在创建对象时，给对象的属性初始化
        
  - final关键字
    - final可以用来修饰类、变量、方法
    - final修饰一个类：此类不能被其他类继承   
      > 例如String类,StringBuffer类,System类
    - final修饰一个方法：此方法不能被重写
    - final修饰变量：此时变量就称为常量  
      - final修饰属性，可以考虑赋值的位置有：显示初始化、代码块中初始化、构造器中初始化
      - final修饰局部变量（形参）
    - static final 用来修饰属性：全局常量
     
  - 属性的赋值顺序  
    > 默认初始化 -> 显式初始化/代码块中赋值 -> 构造器中初始化 -> 对象创建后，使用对象.属性/方法赋值
      
## 2020.08.03
  - abstract关键字
    - abstract可以用来修饰类、方法
    - abstract修饰类：抽象类
      - 此类不能实例化
      - 抽象类中仍有构造器，便于子类实例化调用
      - 开发中，都会提供抽象类的子类，让子类实例化
    - abstract修饰方法：抽象方法
      - 抽象方法只有方法的声明，没有方法体，不可被对象调用
      - 包含抽象方法的类一定是抽象类，反之不然
      - 若子类重写了父类中的所有抽象方法后，此子类方可实例化；反之此子类仍必须为抽象类
    - abstract使用上的注意点
      - abstract不能修饰属性、构造器
      - abstract不能修饰私有方法、静态方法、final方法/类
        
  - 接口（interface）
    - 为什么要使用接口
      - 有时一个类要继承多个类的特性，但是Java不支持多继承，所以需要接口来实现
      - 类与类之间不是 is-a 关系，用继承不合适
    - Java中类和接口是并列的接口，类可以实现多个接口
    - 如何定义接口：定义接口中的成员
      - JDK7及以前：只能定义全局常量和抽象方法(书写可省略 public abstract final)
      - JDK8: 还可以定义静态方法、默认方法
      - 接口不能定义构造器，接口不能实例化
    - 接口是通过类去实现（implements）的方式来使用  
      如果实现类覆盖了接口所有抽象方法，则该类可以实例化；反之，则实现类仍是抽象类
    - 接口与接口之间可以继承，并且可以多继承
    - 接口的具体使用，体现多态性
    - 接口中定义的静态方法，只能通过接口来调用
    - 通过实现类的对象，调用接口中的默认方法
    - 如果子类（或实现类）继承的父类和实现的接口中声明了同名同参数的方法，那么子类在没有重写该方法时，调用的是父类的同名同参数的方法
    - 如果实现类实现了多个接口，且接口中定义了同名同参数的默认方法，则必须在实现类中重写此方法
    
## 2020.08.05
  - 内部类
    - 在一个类中定义类
      - 局部内部类：方法体、代码块、构造器内定义类
      - 成员内部类：静态、非静态
        - 作为外部类的成员
          - 调用外部类的结构
          - 可以被static修饰
          - 可以被4种权限修饰符修饰
        - 作为类
          - 具备类的基本特性
          - 可以被final修饰
          - 可以被abstract修饰
      - 实例化成员内部类的对象
      - 在成员内部类种区分调用外部类的结构
      - 开发局部内部类的使用
      
## 2020.08.11
  - 异常
    - Error：JVM无法解决的严重问题，比如：JVM内部错误、资源耗尽等，StackOverflowError,OutOfMemoryError。
    - Exception：因编程错误或偶然的外在因素导致的一般性问题，可以用针对性的代码进行处理
        - 编译时异常（checked）
          - IOException
            - FileNotFoundException
          - ClassNotFoundException
          - ...
        - 运行时异常（unchecked）
          - NullPointerException
          - ArrayIndexOutOfBoundsException
          - ClassCastException
          - ...
        - 异常处理机制
          - try-catch-finally
              - finally 不是必要的
              - 使用 try 将可能出现异常的代码包装起来，执行过程中，一旦出现异常，就会生成一个对应异常类的对象，根据此对象的类型，去catch中匹配
              - 一旦 try 中的异常匹配到一个 catch 时，进入该 catch 方法体内运行，并跳出try-catch结构(无finally时)，执行后面的代码
              - catch 中的异常类型如果无子父类关系，则无先后顺序分别；如果有子父类关系，则子异常应放在父异常之前
              - 常用的异常对象的处理方式
                - String getMessage(e)
                - printStackTrace(e)
              - try 结构中声明的变量，try外部不可调用
              - finally 中声明的一定是会被执行的代码。即使 catch 中也出现了异常，或 try 中有 return 语句，或 catch 中有 return 语句
              - 像数据库链接、输入输出流、Socket连接等资源，JVM不能自动回收，需要手动释放资源，此时需要在finally中实现释放资源
              - try-catch-finally结构可以嵌套
              - 开发中，由于运行时异常比较常见，所以不针对运行时异常编写try-catch-finally；针对编译时异常，一定要考虑异常的处理
          - throws + 异常类型
            - throws + 异常类型写在方法声明处，指明此方法执行时，可能会抛出的异常类型。如果方法体执行时，出现异常，则会在异常代码出生成一个异常类对象；   
              如果此对象为throws后异常类型，就会被抛出。异常代码后续的代码，不再执行
            - try-catch-finally：真正将异常处理掉了
            - throws：只是把异常抛给了方法的调用者
            - 如果父类中被重写的方法没有使用throws处理异常，则子类重写的方法也不能使用thorws，只能用try-catch-finally处理异常
          - 异常对象的产生
            - 自动生成异常对象
            - 手动生成一个异常对象，并抛出（throw）
          
          
      
    
    
    
    
    
      
        
     
    
   

        
