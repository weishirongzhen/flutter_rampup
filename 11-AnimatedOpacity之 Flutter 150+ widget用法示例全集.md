---
*Flutter 150+ widget 系列示例，持续更新ing~~，更新顺序为按A-Z排序，目前代码中已包含151个示例。*<br>
*[查看代码](https://github.com/memtopia/flutter_rampup_demo_app) 或者 [查看web完整示例](https://memtopia.github.io)*<br>
*目前有部分widget在web端还有问题，如想查看更完整的例子Android 和 iOS用户可同步代码后编译安装到手机上查看*

---

让child的透明度变化有一个动画过程

AnimatedOpacity的参数
* 【child】child节点
* 【opacity】透明度值
* 【curve】参考[Curves](https://api.flutter-io.cn/flutter/animation/Curves-class.html)
* 【duration】一个动画周期的持续时间
* 【onEnd】动画结束的无参回调
* 【alwaysIncludeSemantics】是否包含children的语义信息，暂不明用法



部分代码

```dart
double _opacity = 1.0;

Column(
  children: [
    AnimatedOpacity(
      duration: Duration(seconds: 1),
      opacity: _opacity,
      child: FlutterLogo(
        size: 200,
      ),
    ),
    RaisedButton(
      child: Text('Click me'),
      onPressed: () {
        setState(() {
          _opacity = _opacity == 0 ? 1.0 : 0.0;
        });
      },
    ),
  ],
)
```
![AnimatedOpacity](https://github.com/memtopia/flutter_rampup/raw/master/images/AnimatedOpacity.gif)


