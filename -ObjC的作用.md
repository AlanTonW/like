## "-ObjC" 的使用场景

一般情况下，如果集成有category的静态库，有可能出现以下错误

>  selector not recognized

## What causes those exceptions?

An impedance mismatch between UNIX static libraries and the dynamic nature of Objective-C can cause category methods in static libraries to not be linked into an app, resulting in "selector not recognized" exceptions when the methods aren't found at runtime.

这段话的意思就是：链接器在处理包含Category方法的UNIX的静态库时，没有将Category的方法链接到APP中，造成这个错误。



