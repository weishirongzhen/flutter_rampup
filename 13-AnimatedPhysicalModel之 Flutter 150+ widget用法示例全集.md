---
*Flutter 150+ widget 系列示例，持续更新ing~~，更新顺序为按A-Z排序，目前代码中已包含151个示例。*<br>
*[查看代码](https://github.com/memtopia/flutter_rampup_demo_app) 或者 [查看web完整示例](https://memtopia.github.io)*<br>
*目前有部分widget在web端还有问题，如想查看更完整的例子Android 和 iOS用户可同步代码后编译安装到手机上查看*

---

代表一个物理层的widget并将其child裁切为某种形状，并带动画过度

AnimatedPhysicalModel的参数
* 【child】child节点
* 【shape】形状
* 【clipBehavior】裁切类型
* 【borderRadius】描边圆角
* 【elevation】z轴高度
* 【color】颜色
* 【animateColor】颜色变化是否带动画
* 【shadowColor】阴影颜色
* 【animateShadowColor】阴影颜色变化是否带动画
* 【curve】参考[Curves](https://api.flutter-io.cn/flutter/animation/Curves-class.html)
* 【duration】一个动画周期的持续时间
* 【onEnd】动画结束的无参回调



部分代码

```dart
Column(
  mainAxisAlignment: MainAxisAlignment.center,
  children: <Widget>[
    ///点击后 改变Z轴海拔高度
    AnimatedPhysicalModel(
      duration: const Duration(milliseconds: 500),
      curve: Curves.easeOutQuad,
      elevation: _change ? 0 : 20,
      shape: BoxShape.rectangle,
      shadowColor: Colors.redAccent,
      color: Colors.white,
      child: Container(
        height: 200,
        width: 200,
        color: Colors.blue[50],
        child: FlutterLogo(
          size: 60,
        ),
      ),
    ),
    SizedBox(
      height: 20,
    ),
    RaisedButton(
      child: const Text('Click me'),
      onPressed: () {
        setState(() {
          _change = !_change;
        });
      },
    ),
  ],
)
```
![AnimatedPhysicalModel](https://github.com/memtopia/flutter_rampup/raw/master/images/AnimatedPhysicalModel.gif)


