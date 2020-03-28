---
*Flutter 150+ widget 系列示例，持续更新ing~~，更新顺序为按A-Z排序，目前代码中已包含150+个示例。*<br>
*[查看代码](https://github.com/memtopia/flutter_rampup_demo_app) 或者 [查看web完整示例](https://memtopia.github.io)*<br>
*目前有部分widget在web端还有问题，如想查看更完整的例子Android 和 iOS用户可同步代码后编译安装到手机上查看*

---

当child的size变化时，产生一个自身的过渡动画，并不是child的过渡动画。

AnimatedSize的参数
* 【child】child节点
* 【alignment】对齐方式，参考[Align](https://juejin.im/post/5e79aeba6fb9a07cda099648)
* 【curve】参考[Curves](https://api.flutter-io.cn/flutter/animation/Curves-class.html)
* 【duration】一个动画周期的持续时间
* 【reverseDuration】一个逆序动画周期的持续时间
* 【vsync】垂直同步



部分代码

```dart
Column(
  mainAxisAlignment: MainAxisAlignment.center,
  children: <Widget>[
    Container(
      height: 200,
      child: Center(
        child: AnimatedSize(
          duration: const Duration(milliseconds: 500),
          reverseDuration: const Duration(milliseconds: 200),
          curve: Curves.easeIn,
          child: Container(
            width: _width,
            height: _height,
            color: Colors.red,
          ),
          vsync: this,
        ),
      ),
    ),
    SizedBox(
      height: 20,
    ),
    RaisedButton(
      child: const Text('Click me!'),
      onPressed: () {
        setState(() {
          _width = _change ? 100 : 200;
          _height = _change ? 100 : 200;
          _change = !_change;
        });
      },
    ),
  ],
)
```
![AnimatedSize](https://github.com/memtopia/flutter_rampup/raw/master/images/AnimatedSize.gif)

从小变大是有过渡动画的， 从大变小却没有，为什么呢？原因是AnimatedSize只会过度自己的child的size， 而不是child本身的size，看下边的图理解，AnimatedSize本身确实在变大变小都有过度， 但是他的child没有。

![AnimatedSize](https://github.com/memtopia/flutter_rampup/raw/master/images/AnimatedSize1.gif)

如果要实现放大缩小都可以，建议使用AnimatedContainer
