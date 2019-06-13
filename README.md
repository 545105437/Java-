# Java- InterviewQuestions
## 每日六道JAVA常见面试题分享
# 2019-06-01 
### 腾讯的Java面试题
1.TCP和UDP的区别，TCP为什么是三次握手，不是两次。

        因为tcp是全双工协议，区别在于前者可靠，后者不可靠，以及效率更高。
        
### Dubbo面试题
2.dubbo和dubbox之间的区别？

        Dubbox 和Dubbo本质上没有区别，名字的含义扩展了Dubbo而已，以下扩展出来的功能
        支持REST风格远程调用（HTTP + JSON/XML)；
        支持基于Kryo和FST的Java高效序列化实现；
        支持基于Jackson的JSON序列化；
        支持基于嵌入式Tomcat的HTTP remoting体系；
        升级Spring至3.x；
        升级ZooKeeper客户端；
        支持完全基于Java代码的Dubbo配置；
        
        
### Java List面试题
3.ArrayList和LinkedList的区别？分别用在什么场景？

        ①ArrayList和LinkedList可想从名字分析，它们一个是Array(动态数组)的数据结构，一个是Link(链表)的数据结构，此外，它们两个都是对List接口的实现。
        前者是数组队列，相当于动态数组；后者为双向链表结构，也可当作堆栈、队列、双端队列
        ②当随机访问List时（get和set操作），ArrayList比LinkedList的效率更高，因为LinkedList是线性的数据存储方式，所以需要移动指针从前往后依次查找。
        ③当对数据进行增加和删除的操作时(add和remove操作)，LinkedList比ArrayList的效率更高，因为ArrayList是数组，所以在其中进行增删操作时，会对操作点之后所有数据的下标索引造成影响，需要进行数据的移动。
        ④从利用效率来看，ArrayList自由性较低，因为它需要手动的设置固定大小的容量，但是它的使用比较方便，只需要创建，然后添加数据，通过调用下标进行使用；而LinkedList自由性较高，能够动态的随数据量的变化而变化，但是它不便于使用。
        ⑤ArrayList主要控件开销在于需要在lList列表预留一定空间；而LinkList主要控件开销在于需要存储结点信息以及结点指针信息。
        场景：
        链表，插入删除快，查找修改慢。  适用于频繁增删的场景。
        数组，查找快，插入删除慢。  适用于频繁查找和修改的场景。

### Java Map集合面试题
4.Collection集合接口和Map接口有什么关系？

        没有直接关系，但是一些子类会有依赖，Collection是最基本的集合接口，声明了适用于JAVA集合（只包括Set和List）的通用方法。Map接口并不是Collection接口的子接口，但是它仍然被看作是Collection框架的一部分。

###Spring面试题
5.什么是Spring的内部bean？

        当一个bean只能被某一个类使用时，称该bean为内部bean。

###Zookeeper面试题
6.zookeeper是什么框架？

        ZooKeeper是一个分布式的，开放源码的分布式应用程序协调服务。


#2019-06-02 
###腾讯的Java面试题
1.说说Java中异常的分类。

        异常分类：
        Throwable -> Error,Exception
        Error:严重问题，例如内存溢出
        Exception ->运行时异常： RuntimeException，编译时异常
        AWTError
        
###Dubbo面试题
2.一般使用什么注册中心，还有别的选择吗？

        Dubbo 一般用zookeeper做注册中心
        还可以用：Redis,数据库，consul
        
        
###Java List面试题
3.怎么给List排序？

        List 如何排序：
        ①：使用  Collections.sort 默认正序，可以传第二个参数自定义排序
        ②：自定义bean实现 Comparable 接口。
        ③： 实现Comparator接口自定义比较器

###Java Map集合面试题
4.你都知道哪些Map集合？

        HashMap、HashTable、TreeMap、LinkedHashMap

###Spring面试题
5.为什么说Spring是一个容器？

        Spring的核心理念就是更方便地管理Java Bean，而被管理的Java Bean存缓存在一个Map中，这个Map就可以理解为用来装Java Bean的容器，即IOC容器。

###JVM面试题
6.说说Java虚拟机的生命周期及体系结构？

        JVM的生命周期：
        JVM实例：一个独立运行的java程序，是进程级别
        JVM执行引擎：用户运行程序的线程，是JVM实例的一部分
        1.  JVM实例的诞生
        当启动一个java程序时.一个JVM实例就诞生了，任何一个拥有public static void main(string[] args)的函数都可以作为实例的运行启点
        2.  JVM实例运行
        main作为程序初始化线程的起点,任何其他线程由其启动。
        JVM有两种线程：守护线程和非守护线程。守护线程由JVM使用。main启动后将是非守护线程。
        3.  JVM实例消亡
        当程序中所有非守护线程都中止时,JVM退出；若安全管理器允许，程序也可以使用Runtime类或者System.exit()退出。
        
        JVM的体系结构:
        1.  Class Loader 类加载器
        类加载器的作用是加载类文件到内存，ClassLoader只管加载，只要符合文件结构就加载，至于说能不能运行，则不是它负责的，那是由Execution Engine负责，只要符合《JVM Specification》中式这样定义Class文件的结构。
        2.  Execution Engine 执行引擎
        执行引擎也叫做解释器(Interpreter)，负责解释命令，提交操作系统执行。
        3.  Native Interface本地接口
        本地接口的作用是融合不同的编程语言为Java所用，它的初衷是融合C/C++程序，的具体做法是Native Method Stack中登记native方法，在Execution Engine执行时加载native libraies。
        4.  Runtime data area运行数据区
        运行数据区是整个JVM的重点。我们所有写的程序都被加载到这里，之后才开始运行。
        整个JVM框架由加载器加载文件，然后执行器在内存中处理数据，需要与异构系统交互是可以通过本地接口进行。
   
#2019-06-03 
###
1.Java 是如何实现跨平台的？
######注意：跨平台的是 Java 程序，而不是 JVM。JVM 是用 C/C++ 开发的，是编译后的机器码，不能跨平台，不同平台下需要安装不同版本的 JVM
        答：我们编写的 Java 源码，编译后会生成一种 .class 文件，称为字节码文件。Java 虚拟机（JVM）就是负责将字节码文件翻译成特定平台下的机器码然后运行，也就是说，只要在不同平台上安装对应的 JVM，就可以运行字节码文件，运行我们编写的 Java 程序。
        而这个过程，我们编写的 Java 程序没有做任何改变，仅仅是通过 JVM 这一 “中间层” ，就能在不同平台上运行，真正实现了 “一次编译，到处运行” 的目的。
        
###
2.什么是 JVM ？
######解析：不仅仅是基本概念，还有 JVM 的作用。
        答：JVM，即 Java Virtual Machine，Java 虚拟机。它通过模拟一个计算机来达到一个计算机所具有的的计算功能。
        JVM 能够跨计算机体系结构来执行 Java 字节码，主要是由于 JVM 屏蔽了与各个计算机平台相关的软件或者硬件之间的差异，使得与平台相关的耦合统一由 JVM 提供者来实现。
        
        
###
3.JVM 由哪些部分组成？
######解析：这是对 JVM 体系结构的考察
        答：JVM 的结构基本上由 4 部分组成：
        类加载器，在 JVM 启动时或者类运行时将需要的 class 加载到 JVM 中
        执行引擎，执行引擎的任务是负责执行 class 文件中包含的字节码指令，相当于实际机器上的 CPU
        内存区，将内存划分成若干个区以模拟实际机器上的存储、记录和调度功能模块，如实际机器上的各种功能的寄存器或者 PC 指针的记录器等
        本地方法调用，调用 C 或 C++ 实现的本地方法的代码返回结果

###
4.类加载器是有了解吗？
######解析：底层原理的考察，其中涉及到类加载器的概念，功能以及一些底层的实现。
        答：顾名思义，类加载器（class loader）用来加载 Java 类到 Java 虚拟机中。一般来说，Java 虚拟机使用 Java 类的方式如下：Java 源程序（.java 文件）在经过 Java 编译器编译之后就被转换成 Java 字节代码（.class 文件）。
        
        类加载器负责读取 Java 字节代码，并转换成 java.lang.Class类的一个实例。每个这样的实例用来表示一个 Java 类。通过此实例的 newInstance()方法就可以创建出该类的一个对象。实际的情况可能更加复杂，比如 Java 字节代码可能是通过工具动态生成的，也可能是通过网络下载的。

###
5.Java 虚拟机是如何判定两个 Java 类是相同的？
   
        答：Java 虚拟机不仅要看类的全名是否相同，还要看加载此类的类加载器是否一样。只有两者都相同的情况，才认为两个类是相同的。即便是同样的字节代码，被不同的类加载器加载之后所得到的类，也是不同的。
        比如一个 Java 类 com.example.Sample，编译之后生成了字节代码文件 Sample.class。两个不同的类加载器 ClassLoaderA和 ClassLoaderB分别读取了这个 Sample.class文件，并定义出两个 java.lang.Class类的实例来表示这个类。
        这两个实例是不相同的。对于 Java 虚拟机来说，它们是不同的类。试图对这两个类的对象进行相互赋值，会抛出运行时异常 ClassCastException。
        
###
6.类似-Xms、-Xmn这些参数的含义：

        答：
        堆内存分配：
        JVM初始分配的内存由-Xms指定，默认是物理内存的1/64
        JVM最大分配的内存由-Xmx指定，默认是物理内存的1/4
        默认空余堆内存小于40%时，JVM就会增大堆直到-Xmx的最大限制；空余堆内存大于70%时，JVM会减少堆直到 -Xms的最小限制。
        因此服务器一般设置-Xms、-Xmx相等以避免在每次GC 后调整堆的大小。对象的堆内存由称为垃圾回收器的自动内存管理系统回收。
        非堆内存分配：
        JVM使用-XX:PermSize设置非堆内存初始值，默认是物理内存的1/64；
        由XX:MaxPermSize设置最大非堆内存的大小，默认是物理内存的1/4。
        -Xmn2G：设置年轻代大小为2G。
        -XX:SurvivorRatio，设置年轻代中Eden区与Survivor区的比值。
       
#2019-06-04 
###
1.sleep()和wait(n)、wait()的区别？

        答：sleep 方法： 
        是 Thread 类的静态方法，当前线程将睡眠 n 毫秒，线程进入阻塞状态。当睡眠时间到了，会解除阻塞，进行可运行状态，等待 CPU 的到来。睡眠不释放锁（如果有的话）；
        
        wait 方法： 
        是 Object 的方法，必须与 synchronized 关键字一起使用，线程进入阻塞状态，当 notify 或者 notifyall 被调用后，会解除阻塞。但是，只有重新占用互斥锁之后才会进入可运行状态。睡眠时，释放互斥锁。
        
        
###
2.synchronized关键字？

        答：底层实现：
        进入时，执行 monitorenter，将计数器 +1，释放锁 monitorexit 时，计数器-1；
        当一个线程判断到计数器为 0 时，则当前锁空闲，可以占用；反之，当前线程进入等待状态。
        含义：（monitor 机制）
        Synchronized 是在加锁，加对象锁。对象锁是一种重量锁（monitor），synchronized 的锁机制会根据线程竞争情况在运行时会有偏向锁（单一线程）、轻量锁（多个线程访问 synchronized 区域）、对象锁（重量锁，多个线程存在竞争的情况）、自旋锁等。
        该关键字是一个几种锁的封装。
        
###
3.volatile关键字？
######解析：关于指令重排序的问题，可以查阅 DCL 双检锁失效相关资料。
        答：该关键字可以保证可见性不保证原子性。
        功能：     
        主内存和工作内存，直接与主内存产生交互，进行读写操作，保证可见性；
        禁止 JVM 进行的指令重排序。
        

###
4.volatile能使得一个非原子操作变成原子操作吗？

        答：能。
        一个典型的例子是在类中有一个 long 类型的成员变量。如果你知道该成员变量会被多个线程访问，如计数器、价格等，你最好是将其设置为 volatile。为什么？因为 Java 中读取 long 类型变量不是原子的，需要分成两步，如果一个线程正在修改该 long 变量的值，另一个线程可能只能看到该值的一半（前 32 位）。但是对一个 volatile 型的 long 或 double 变量的读写是原子。
        
###
5.ThreadLocal(线程局部变量)关键字？
   
        答：当使用 ThreadLocal 维护变量时，其为每个使用该变量的线程提供独立的变量副本，所以每一个线程都可以独立的改变自己的副本，而不会影响其他线程对应的副本。
        ThreadLocal 内部实现机制：
        每个线程内部都会维护一个类似 HashMap 的对象，称为 ThreadLocalMap，里边会包含若干了 Entry（K-V 键值对），相应的线程被称为这些 Entry 的属主线程；
        Entry 的 Key 是一个 ThreadLocal 实例，Value 是一个线程特有对象。Entry 的作用即是：为其属主线程建立起一个 ThreadLocal 实例与一个线程特有对象之间的对应关系；
        Entry 对 Key 的引用是弱引用；Entry 对 Value 的引用是强引用。
        
###
6.我们为什么要使用线程池？核心线程池内部实现了解吗？

        答： 
        减少创建和销毁线程的次数，每个工作线程都可以被重复利用，可执行多个任务。
        可以根据系统的承受能力，调整线程池中工作线程的数目，放置因为消耗过多的内存，而把服务器累趴下（每个线程大约需要 1 MB 内存，线程开的越多，消耗的内存也就越大，最后死机）
        
        对于核心的几个线程池，无论是 newFixedThreadPool() 方法，newSingleThreadExecutor() 还是 newCachedThreadPool() 方法，虽然看起来创建的线程有着完全不同的功能特点，
        但其实内部实现均使用了 ThreadPoolExecutor 实现，其实都只是 ThreadPoolExecutor 类的封装。
        
        
#2019-06-05
###
1.解释AOP模块？

        答：AOP（Aspect-Oriented Programming）指一种程序设计范型，该范型以一种称为切面（aspect）的语言构造为基础，切面是一种新的模块化机制，用来描述分散在对象、类或方法中的横切关注点（crosscutting concern）。
        
###
2.有哪些不同的IOC(依赖注入)方式？

        答：构造器依赖注入： 构造器依赖注入通过容器触发一个类的构造器来实现的，该类有一系列参数，每个参数代表一个对其他类的依赖。 
          Setter方法注入： Setter方法注入是容器通过调用无参构造器或无参static工厂 方法实例化bean之后，调用该bean的setter方法，即实现了基于setter的依赖注入。
        
###
3.你怎样定义类的作用域？

        答：当定义一个 在Spring里，我们还能给这个bean声明一个作用域。它可以通过bean 定义中的scope属性来定义。如，当Spring要在需要的时候每次生产一个新的bean实例，bean的scope属性被指定为prototype。另一方面，一个bean每次使用的时候必须返回同一个实例，这个bean的scope 属性 必须设为 singleton。
        

###
4.Spring框架的事务管理有哪些优点？

        答：它为不同的事务API 如 JTA，JDBC，Hibernate，JPA 和JDO，提供一个不变的编程模式。 
          它为编程式事务管理提供了一套简单的API而不是一些复杂的事务API如 
          它支持声明式事务管理。 
          它和Spring各种数据访问抽象层很好得集成。
        
###
5.什么是SpringMVC框架的控制器？
   
        答：控制器提供一个访问应用程序的行为，此行为通常通过服务接口实现。控制器解析用户输入并将其转换为一个由视图呈现给用户的模型。Spring用一个非常抽象的方式实现了一个控制层，允许用户创建多种用途的控制器。
        
###
6.在SpringAOP中，关注点和横切关注的区别是什么？

        答： 
        关注点是应用中一个模块的行为，一个关注点可能会被定义成一个我们想实现的一个功能。 
        横切关注点是一个关注点，此关注点是整个应用都会使用的功能，并影响整个应用，比如日志，安全和数据传输，几乎应用的每个模块都需要的功能。因此这些都属于横切关注点。
   
              
#2019-06-10
###
1.使用Spring框架的好处是什么？

        答：轻量： Spring 是轻量的，基本的版本大约2MB。 
        控制反转： Spring通过控制反转实现了松散耦合，对象们给出它们的依赖，而不是创建或查找依赖的对象们。 
        面向切面的编程(AOP)： Spring支持面向切面的编程，并且把应用业务逻辑和系统服务分开。 
        容器： Spring 包含并管理应用中对象的生命周期和配置。 
        MVC框架： Spring的WEB框架是个精心设计的框架，是Web框架的一个很好的替代品。 
        事务管理： Spring 提供一个持续的事务管理接口，可以扩展到上至本地事务下至全局事务（JTA）。 
        异常处理： Spring 提供方便的API把具体技术相关的异常（比如由JDBC，Hibernate or JDO抛出的）转化为一致的unchecked 异常。
        
###
2.Spring由哪些模块组成？

        答：以下是Spring 框架的基本模块：
        Core module 
        Bean module 
        Context module 
        Expression Language module 
        JDBC module 
        ORM module 
        OXM module 
        Java Messaging Service(JMS) module 
        Transaction module 
        Web module 
        Web-Servlet module 
        Web-Struts module 
        Web-Portlet module

        
###
3.BeanFactory-BeanFactory实现举例？

        答：Bean 工厂是工厂模式的一个实现，提供了控制反转功能，用来把应用的配置和依赖从正真的应用代码中分离。
        最常用的BeanFactory 实现是XmlBeanFactory 类。

###
4.什么是SpringIOC容器？

        答：Spring IOC 负责创建对象，管理对象（通过依赖注入（DI），装配对象，配置对象，并且管理这些对象的整个生命周期。
        
###
5.IOC的优点是什么？
   
        答：IOC 或 依赖注入把应用的代码量降到最低。它使应用容易测试，单元测试不再需要单例和JNDI查找机制。最小的代价和最小的侵入性使松散耦合得以实现。IOC容器支持加载服务时的饿汉式初始化和懒加载。
        
###
6.什么是基于注解的容器配置？

        答：相对于XML文件，注解型的配置依赖于通过字节码元数据装配组件，而非尖括号的声明。
        开发者通过在相应的类，方法或属性上使用注解的方式，直接组件类中进行配置，而不是使用xml表述bean的装配关系。
        
#2019-06-11
###
1.什么是Spring MVC框架的控制器？

        答：控制器提供一个访问应用程序的行为，此行为通常通过服务接口实现。控制器解析用户输入并将其转换为一个呦视图呈现给用户的模型。
        Spring用一个非常抽象的方法实现了一个控制层，允许用户创建多种用途的控制器。
        
###
2.什么是基于注解的容器配置？

        答：相对于XML文件，注解型的配置依赖于通过字节码元数据装配组件，而非尖括号的声明。
        开发者通过在相应的类，方法或属性上使用注解的方式，直接组件类中进行配置，而不是使用xml标书bean的装配关系。

        
###
3.怎样开启注解装配？

        答：注解装配在默认情况下是不开启的，为了使用注解装配，我们必须在Spring配置文件中配置元素。

###
4.@Required注解？

        答：这个注解表明bean的属性必须在配置的时候设置，通过一个bean定义的显式的属性值或通过自动装配，若@Required注解的bean属性
        未被设置，容器将抛出BeanInitializationException。
        
###
5.@Autowired注解？
   
        答：@Autowired注解提供了更细粒度的控制，包括在何处以及如何完成自动装配。它的用法和@Required一样，修饰setter方法、构造器、属性或者
        具有任意名称和/或多个参数的PN方法。
        
###
6.@Qualifier注解？

        答：当有多个相同类型的bean却只有一个需要自动装配时，将@Qualifier注解和@Autowire注解结合使用以消除这种混淆，指定需要装配的确切的bean。


#2019-06-12
###
1.什么是Mybatis？

        答：（1）Mybatis是一个半ORM（对象关系映射）框架，它内部封装了JDBC，开发时只需要关注SQL语句本身，不需要花费精力去处理加载驱动、创建连接、创建statement等繁杂的过程。程序员直接编写原生态sql，可以严格控制sql执行性能，灵活度高。       
          （2）MyBatis 可以使用 XML 或注解来配置和映射原生信息，将 POJO映射成数据库中的记录，避免了几乎所有的 JDBC 代码和手动设置参数以及获取结果集。
          （3）通过xml 文件或注解的方式将要执行的各种 statement 配置起来，并通过java对象和 statement中sql的动态参数进行映射生成最终执行的sql语句，最后由mybatis框架执行sql并将结果映射为java对象并返回。（从执行sql到返回result的过程）。
        
###
2.Mybaits的优点？

        答：（1）基于SQL语句编程，相当灵活，不会对应用程序或者数据库的现有设计造成任何影响，SQL写在XML里，解除sql与程序代码的耦合，便于统一管理；提供XML标签，支持编写动态SQL语句，并可重用。
          （2）与JDBC相比，减少了50%以上的代码量，消除了JDBC大量冗余的代码，不需要手动开关连接；
          （3）很好的与各种数据库兼容（因为MyBatis使用JDBC来连接数据库，所以只要JDBC支持的数据库MyBatis都支持）。
          （4）能够与Spring很好的集成；
          （5）提供映射标签，支持对象与数据库的ORM字段关系映射；提供对象关系映射标签，支持对象关系组件维护。
        
###
3.MyBatis框架的缺点？

        答：（1）SQL语句的编写工作量较大，尤其当字段多、关联表多时，对开发人员编写SQL语句的功底有一定要求。
          （2）SQL语句依赖于数据库，导致数据库移植性差，不能随意更换数据库。

###
4.MyBatis框架适用场合？

        答：（1）MyBatis专注于SQL本身，是一个足够灵活的DAO层解决方案。
          （2）对性能的要求很高，或者需求变化较多的项目，如互联网项目，MyBatis将是不错的选择。
        
###
5.MyBatis与Hibernate有哪些不同？
   
        答：（1）Mybatis和hibernate不同，它不完全是一个ORM框架，因为MyBatis需要程序员自己编写Sql语句。
          （2）Mybatis直接编写原生态sql，可以严格控制sql执行性能，灵活度高，非常适合对关系数据模型要求不高的软件开发，因为这类软件需求变化频繁，一但需求变化要求迅速输出成果。但是灵活的前提是mybatis无法做到数据库无关性，如果需要实现支持多种数据库的软件，则需要自定义多套sql映射文件，工作量大。 
          （3）Hibernate对象/关系映射能力强，数据库无关性好，对于关系模型要求高的软件，如果用hibernate开发可以节省很多代码，提高效率。
        
###
6.Mybatis是如何进行分页的？分页插件的原理是什么？

        答：Mybatis使用RowBounds对象进行分页，它是针对ResultSet结果集执行的内存分页，而非物理分页。可以在sql内直接书写带有物理分页的参数来完成物理分页功能，也可以使用分页插件来完成物理分页。
          分页插件的基本原理是使用Mybatis提供的插件接口，实现自定义插件，在插件的拦截方法内拦截待执行的sql，然后重写sql，根据dialect方言，添加对应的物理分页语句和物理分页参数。
          
