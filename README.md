# JavaStudyNote - JavaInterviewQuestions test

#### List any five features of Java?
* Object Oriented
* Platform Independent
* Robust 有异常处理机制，可以检查错误
* Interpreted
* Multi-threaded

#### What is Java Virtual Machine and how it is considered in context of Java’s platform independent feature?
* When Java is compiled, it is not compiled into platform specific machine, rather into platform independent byte code. This byte code is distributed over the web and interpreted by virtual Machine JVM on whichever platform it is being run. 跨平台，用什么系统都能跑。无论当前平台是什么，java编译后的文件是在虚拟机上跑的。

#### 一个类中有多少种变量？
* Local Variable - Variables defined inside methods, constructors or blocks are called local variables. The variable
will be declared and initialized within the method and it will be destroyed when the method has completed.
* Instance Variable - Instance variables are variables within a class but outside any method. These variables are
instantiated when the class is loaded.实例变量在类里面但是方法外面
* Class Variable - These are variables declared with in a class, outside any method, with the static keyword.
* 类变量和实例变量有什么区别？
  * 存储地方不一样
  * class variable只创建一次，在改变的时候都在同一个上变化。instance variable在每次新建一个class的实例的时候就创建一次。
  * <img width="639" alt="wx20180329-193706 2x" src="https://user-images.githubusercontent.com/20292261/38119659-06e603be-3389-11e8-8227-fb3890f33b91.png">
  * 结果：
  
  staticVar = 1, instanceVar = 1
  
  staticVar = 2, instanceVar = 1
  
#### What is Singleton class? What do you mean by Constructor?
* Singleton class control object creation, limiting the number to one but allowing the flexibility to create more objects if the situation changes. 
* Constructor gets invoked when a new object is created. Every class has a constructor. If we do not explicitly write a constructor for a class the java compiler builds a default constructor for that class.

#### What do you mean by Access Modifier?
* Java provides access modifiers to set access levels for classes, variables, methods and constructors. A member has package or default accessibility when no accessibility modifier is specified. - public private protect 权限
* private 类内部访问
* protected 保护，该类内部和继承类中可以访问
* public

#### Why is String class considered immutable?
* The String class is immutable, so that once it is created a String object cannot be changed. Since String is immutable it can safely be shared between many threads ,which is considered very important for multithreaded programming. 因为多线程之间share string要immutable

#### Why is StringBuffer called mutable?
* The String class is considered as immutable, so that once it is created a String object cannot be
changed. If there is a necessity to make alot of modifications to Strings of characters then
StringBuffer should be used. 因为string不能变，如果需要改变string就要用到stringbuffer 

#### What is the difference between StringBuffer and StringBuilder class?
* Use StringBuilder whenever possible because it is faster than StringBuffer. But, if thread safety is necessary then use StringBuffer objects. 因为StringBuffer可以在多线程中使用（mutable）但是StringBuilder不能在多线程中使用，也是mutable的。不可改变的东西一定是线程安全的，可以改变的东西不一定是线程安全的。在非多线程中使用StringBuffer浪费资源，简化成StringBuilder
* ![image](https://user-images.githubusercontent.com/20292261/38705750-42e52a10-3e70-11e8-88da-9abd5b629372.png)

#### What is finalize method? How finally used under Exception Handling? What is final class?
* It is possible to define a method that will be called just before an object's final destruction by the garbage collector. This method is called finalize, and it can be used to ensure that an object terminates cleanly.对象销毁时候调用finalize方法，确保对象被正常结束，清理掉空间
* 什么时候调用finalize方法：当对象unreachable的时候 - The garbage collector invokes an object's finalize method when it detects that the object has become unreachable.
* The finally keyword is used to create a block of code that follows a try block. A finally block of code always executes, whether or not an exception has occurred. 一个一定会被执行的块
* final class : 这个class里所有函数不能被改变／不能重写／不能继承
* 一个构造函数不能是final的
* 只要被final修饰的东西都不可以被改变，可以修饰方法，class，变量
* ![image](https://user-images.githubusercontent.com/20292261/38706224-0411df0c-3e72-11e8-8092-9261f0591158.png)

#### Exception
* CheckedException : try catch 程序员无法预见的异常，比如打开文件IOException，不知道能不能打开（无法预见）需要try catch捕获异常
* Unchecked Exception / RuntimeException : 程序员可以避免的，通过自己编程避免，比如空指针异常，跑程序时候会报错

#### throws & throw
* throws 在方法声明时候写，可以抛出多个异常，方法末尾写throws keyword。If a method does not handle a checked exception, the method must declare it using the throwskeyword.
* throw 在方法体中实现，只能抛出单个异常

#### What things should be kept in mind while creating your own exceptions in Java?
* 必须继承Exception : extend Exception。如果是要写个RuntimeException，就extend RuntimeException

#### Java 三大特性?
* Inheritance 一个object需要另一个object的属性
* Polymorphism : Polymorphism is the ability of an object to take on many forms. The most common use of polymorphism in OOP occurs when a parent class reference is used to refer to a child class object. -> override 
* Encapsulation : It is the technique of making the fields in a class private and providing access to the fields via public methods. If a field is declared private, it cannot be accessed by anyone outside the class, thereby hiding the fields within the class. Therefore encapsulation is also referred to as data hiding.
* 封装好处？The main benefit of encapsulation is the ability to modify our implemented code without breaking the code of others who use our code. With this Encapsulation gives maintainability, flexibility and extensibility to our code. 可扩展性，灵活性

#### overload & override
* overloading : 不同方法，同样名字，参数不同
* overriding : 子类重写父类方法

#### super?
* If the method overrides one of its superclass's methods, overridden method can be invoked through the use of the keyword super. It can be also used to refer to a hidden field.

#### Abtract class?
* 不能被实例化的类，可以部分实现or不实现，包含一个或多个抽象方法。
* 抽象类不能用new创建对象
* abstract方法只能声明不能实现，抽象类不一定非要包含抽象方法，但是包含抽象方法的一定是抽象类
* 抽象类的实现子类必须实现抽象类中所有abstract方法
* Abstract method 什么时候用 : 继承类中实现，parent类不实现只定义。If you want a class to contain a particular method but you want the actual implementation of that method to be determined by child classes, you can declare the method in the parent class as abstract.

#### Interface?
* 抽象方法的集合 An interface is a collection of abstract methods. A class implements an interface, thereby
inheriting the abstract methods of the interface.
* 特性 : 接口不能被实例化，接口没有构造函数，接口的所有方法都是抽象的 - 只能声明不能实现

#### 抽象类和接口的相同点
* 都是抽象的，都不能实例化
* interface 实现类以及abstract class的子类都必须要实现已经声明的抽象方法

#### 抽象类和接口的不同点
* 抽象函数中可以定义变量，接口只能定义static／final的成员变量
* 接口需要实现用implements，抽象类需要继承用extends
* 一个类可以实现多个接口，但只能继承一个抽象类
* 接口强调特定功能的实现，抽象类强调所属关系

#### static block? static method 和 static block的限制?
* It is used to initialize the static data member, It is excuted before main method at the time of classloading.
* static method / block 不能引用类中的成员变量or成员方法，除非类已经进行了创建，在main函数中已经实例化了这个类，成员变量已经被分配了内存。

#### static and non-static variables?
* static variable不属于某个类虽然写在类中，但并不跟类走 A static variable is associated with the class as a whole rather than with specific instances of a class.
* non-static variable是属于某个object instance的 Non-static variables take on unique values with each object instance.

#### Explain garbage collection in Java? Does garbage collection guarantee that a program will not run out of memory?
* It uses garbage collection to free the memory. By cleaning those objects that is no longer reference by any of the program.
* Garbage collection does not guarantee that a program will not run out of memory. It is possible for programs to use up memory resources faster than they are garbage collected. It is also possible for programs to create objects that are not subject to garbage collection.




Book: http://www.tutorialspoint.com/java/pdf/java_interview_questions.pdf

YouTube: https://www.youtube.com/playlist?list=PLvyIyKZVcfAnGitjgY7xwL61GK0J39Pp7
