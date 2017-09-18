# 第一章 初识RxJava

## 什么是RxJava

RxJava在其github上的定义

> a library for composing asynchronous and event-based programs using observable sequences for the Java VM
>
> 一个在 Java VM 上使用`可观测的序列`来组成`异步`的、`基于事件`的程序的库

## ![](/assets/观察者模式.png)RxJava的优势

在我的理解当中，RxJava主要有一下三个方面的优势：

### 错误处理

```java
Observer<? super XXX> observer = new Observer<XXX>(){
    @Override
    public void onCompleted(){
        //流结束时的处理
    }
    @Override
    public void onError(Throwable throwable){
        //在整个事件流的过程中所有出现的一场都会汇总到这里
    }
    @Override
    public void onNext(XXX xx){
        //对事件流当中每一个事件的处理
    }
}
```

在上边的代码中，·observer·是一个

### 线程调度

### 链式调用



