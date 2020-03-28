---
*Flutter 150+ widget 系列示例，持续更新ing~~，更新顺序为按A-Z排序，目前代码中已包含150+个示例。*<br>
*[查看代码](https://github.com/memtopia/flutter_rampup_demo_app) 或者 [查看web完整示例](https://memtopia.github.io)*<br>
*目前有部分widget在web端还有问题，如想查看更完整的例子Android 和 iOS用户可同步代码后编译安装到手机上查看*

---

子widget重绘时，让重绘有一个动画效果

AnimatedSwitcher的参数
* 【child】child节点
* 【duration】一个动画周期的持续时间
* 【reverseDuration】一个逆序动画周期的持续时间
* 【switchInCurve】过渡到下一个child时的 curve，参考[Curves](https://api.flutter-io.cn/flutter/animation/Curves-class.html)
* 【switchOutCurve】出现上一个child时的 curve，参考[Curves](https://api.flutter-io.cn/flutter/animation/Curves-class.html)
* 【transitionBuilder】动画构造器
* 【layoutBuilder】用于定位child的builder， 默认值AnimatedCrossFade.defaultLayoutBuilder



部分代码

```dart
Column(
  mainAxisAlignment: MainAxisAlignment.center,
  crossAxisAlignment: CrossAxisAlignment.center,
  children: <Widget>[
    AnimatedSwitcher(
      duration: const Duration(milliseconds: 500),
      switchInCurve: Curves.easeIn,
      switchOutCurve: Curves.easeInOut,
      transitionBuilder: (Widget child, Animation<double> animation) {
        return ScaleTransition(child: child, scale: animation);
      },
      child: Text(
        '$_count',
        key: ValueKey<int>(_count),
        style: TextStyle(fontSize: 100),
      ),
    ),
    RaisedButton(
      child: const Text('Click me'),
      onPressed: () {
        setState(() {
          _count += 1;
        });
      },
    ),
  ],
)
```
![AnimatedSwitcher](https://github.com/memtopia/flutter_rampup/raw/master/images/AnimatedSwitcher.gif)


