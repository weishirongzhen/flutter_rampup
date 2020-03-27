---
*Flutter 150+ widget 系列示例，持续更新ing~~，更新顺序为按A-Z排序，目前代码中已包含151个示例。*<br>
*[查看代码](https://github.com/memtopia/flutter_rampup_demo_app) 或者 [查看web完整示例](https://memtopia.github.io)*<br>
*目前有部分widget在web端还有问题，如想查看更完整的例子Android 和 iOS用户可同步代码后编译安装到手机上查看*

---

让padding的变化有一个动画过程

AnimatedPadding的参数
* 【child】child节点
* 【padding】padding值
* 【curve】参考[Curves](https://api.flutter-io.cn/flutter/animation/Curves-class.html)
* 【duration】一个动画周期的持续时间
* 【onEnd】动画结束的无参回调



部分代码

```dart
Column(
  mainAxisSize: MainAxisSize.min,
  children: <Widget>[
    Container(
      height: 200.0,
      width: 200.0,
      color: Colors.blue,
      child: AnimatedPadding(
        duration: Duration(milliseconds: 500),
        padding: _padding,
        curve: Curves.easeOutQuad,
        child: Container(
          color: Colors.redAccent,
        ),
      ),
    ),
    RaisedButton(
      onPressed: () {
        setState(() {
          _change = !_change;
          _padding = _change == true ? EdgeInsets.all(50) : EdgeInsets.all(0);
        });
      },
      child: Text(
        "Click me",
      ),
    )
  ],
)
```
![AnimatedOpacity](https://github.com/memtopia/flutter_rampup/raw/master/images/AnimatedPadding.gif)


