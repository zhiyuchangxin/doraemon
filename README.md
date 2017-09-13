## 纯 css3 绘制 doraemon


### 为何而做

喜欢绘画的我刚好借助此次机会，用 css3 绘制了一只可爱的哆啦 A 梦，进一步巩固了 css3 的部分特性。

不管工作多么忙，基础不可朦胧，兴致不能搁浅，时刻开启任意门出发吧！

### 页面预览
![avatar](http://ow73fkxqs.bkt.clouddn.com/doraemon.png)

### 总结与思考
1. 绘制半圆使用的方法是先绘两个椭圆，然后将其进行叠加实现（初步）。
2. 后来只使用 border-radius 设置不同个数的参数直接实现。
3. 但是在 less 编译的过程中，css3 中的 calc 却被当成计算了。困惑了好久，原来 less 的计算方式跟 calc 方法有重叠，两者发生冲突。
4. 解决方法：在 less 中把 calc 的写法改成 ~"" 的形式，如下的例子：

``` bash
border-radius: 50% / 0 0 100% 100%;	 // 编译后变成：border-radius: Infinity% 0 100% 100%;

border-radius: ~"50% / 0 0 100% 100%";  // 改写后正常编译
```
