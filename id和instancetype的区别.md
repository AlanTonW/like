## id和instancetype的区别

> [http://www.jianshu.com/p/37c0060fbe27][参考]

instancetype和id的异同
1、相同点
都可以作为方法的返回类型
2、不同点
①instancetype可以返回和方法所在类相同类型的对象，id只能返回未知类型的对象；
②instancetype只能作为返回值，不能像id那样作为参数，比如下面的写法：

```
//err,expected a type  
- (void)setValue:(instancetype)value  
{  
    //do something  
} 
```
就是错的，应该写成：
```
- (void)setValue:(id)value  
{  
    //do something  
}
```







