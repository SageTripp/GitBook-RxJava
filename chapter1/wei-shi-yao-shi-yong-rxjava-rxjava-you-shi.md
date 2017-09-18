## RxJava的优势

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

在上边的代码中，`observer`是一个观察者对象，在`observer`当中有过一个`onError` 方法，用来统一处理在整个事件流过程中出现的所有异常。

### 线程调度

RxJava中的另外一大优势就是对线程的调度，使用RxJava的时候切换线程是一件相当方便与优雅的事情。

线程的调度主要使用两个方法`subscribeOn` ,`observeOn` 这两个方法分别指定了数据源发射的线程和事件处理的线程。

```java
someThingUseRx()
    .subscribeOn(Schedus.newThread())
    ...//一些RxJava操作符
    .observeOn(AndroidSchecus.mainThread())
    ...//一些RxJava操作符
    .subscribe(observer);
```

从上边的代码可以看到RxJava的线程调度非常的灵活和简单，具体的使用在后边详细讲解

### 链式调用



