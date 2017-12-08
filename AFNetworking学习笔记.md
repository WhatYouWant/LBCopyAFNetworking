#AFNetworking学习笔记
###1. FOUNDATION_EXPORT
一般定义常量的两种方法
####1.
.h文件中

```
FOUNDATION_EXPORT NSString * const kMyConstantString;
```
.m文件中

```
NSString * const kMyConstantString = @"hello";
```
####2.
define kMyConstantString @"hello"

*区别：*使用第一种方法检测的字符串是否相等的时候更快。对于第一种可以直接使用(stringInstance == MyFirstConstant)来比较，而define则使用的是 isEqualToString: 。显然第一个直接比较指针地址会快很多。
###2. NS_ASSUME_NONNULL_BEGIN NS_ASSUME_NONNULL_END
__nullable && __nonnull
__nullable指代对象可以为NULL或者NIL
__nonnull指代对象不能为null
属性声明中可以添加 nullable 和 nonnull
NS_ASSUME_NONNULL_BEGIN和NS_ASSUME_NONNULL_END，在这两个宏之间的代码，所有简单指针对象都被假定为nonnull，因此只需要去指定那些nullable的指针。

