# MultiTab_MyBrowser
一个多标签页、可输入网址可前进后退刷新的简易浏览器

![示例照片](https://github.com/wangying2016/MultiTab_MyBrowser/raw/master/demo.png)

因为本人之前做过一个单标签页的简易浏览器，所以与标签页逻辑处理无关的介绍就不再赘述了，想要了解的可以查看这里[单标签页简易浏览器实现](http://blog.csdn.net/u012814856/article/details/60800383)。

此程序的功能如下：

- 可输入网址，敲击Enter或者点击Go按钮发起浏览
- 可记录标签页的浏览痕迹，可前进后退
- 可以刷新当前网页
- 标签页可以新建、删除、切换，网页内容也随之变动

## 如何实现多标签页

多标签页该如何实现呢？考虑了很久，以每个标签页为一个单位，这个标签页与一个wke对象也就是一个界面对象一一对应。也就是说，在我们看来，多标签页其实就是多个wke对象而已，我们只需要对于这些wke对象进行增删查的管理工作就可以了。

那么要实现对于wke对象的管理，最好的办法就是使用一个std::map对象进行管理。将标签页的标号设为key值，以wke对象设置为对应的value值，以此建立一个映射表，并且在标签页被点击、切换、新建、删除时，执行相应的逻辑处理即可。

## 总结思路

思路其实很简单，将多标签抽象为管理一个动态的map映射，代码细节还有许多需要注意的，都是些很小的问题，也就不再赘述了。这个程序还有继续完善的想法，待有空再好好优化、整理下。