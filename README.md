# JavaStudyNote

## 1. List any five features of Java?
* Object Oriented
* Platform Independent
* Robust 有异常处理机制，可以检查错误
* Interpreted
* Multi-threaded

## 2. What is Java Virtual Machine and how it is considered in context of Java’s platform independent
feature?
* When Java is compiled, it is not compiled into platform specific machine, rather into platform
independent byte code. This byte code is distributed over the web and interpreted by virtual
Machine JVM on whichever platform it is being run. 跨平台，用什么系统都能跑。无论当前平台是什么，java编译后的文件是在虚拟机上跑的。

## 3. 一个类中有多少种变量？
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







Book: http://www.tutorialspoint.com/java/pdf/java_interview_questions.pdf
