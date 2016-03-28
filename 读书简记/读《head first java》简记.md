##读《head first java》简记
听说这本很适合作为java入门书籍，特来瞻仰瞻仰.  
####1、方法的调用，正在执行的方法在栈的最上方，方法执行完毕后会就死释放栈空间；不正常的递归会导致一个非常长的方法链，栈空间不够了就报栈溢出。。outOfMemory
####2、new Example（）对象，对于下面两种情况，请问这个对象的堆空间占用有区别么？
    public class Example{
    	private Person person;
    }
    public class Example{
    	private Person person = new Person();
    }
>  无区别，inner只是一个引用变量而已，它的指向不管有没有实际对象，都不会影响占用的内存。  

那么问题来了，一个对象到底占用多少内存空间？
> 参考 - - [一个Java对象到底占用多大内存？](http://blog.csdn.net/aaa1117a8w5s6d/article/details/42400061)（仅做参考之用）  
 
####3、外部类以外如何创建内部类的实例？

    Outer.Inner inner =  new outer().new Inner();
    
关于内部类的一些说明：
> [知乎：Java 中引入内部类的意义？](https://www.zhihu.com/question/21373020/answer/18039107)  
> [java中内部类总结](http://www.cnblogs.com/nerxious/archive/2013/01/24/2875649.html)
