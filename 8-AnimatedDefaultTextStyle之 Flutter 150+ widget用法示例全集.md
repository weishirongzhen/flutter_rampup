---
*Flutter 150+ widget 系列示例，持续更新ing~~，更新顺序为按A-Z排序，目前代码中已包含151个示例。*<br>
*[查看代码](https://github.com/memtopia/flutter_rampup_demo_app) 或者 [查看web完整示例](https://memtopia.github.io)*<br>
*目前有部分widget在web端还有问题，如想查看更完整的例子Android 和 iOS用户可同步代码后编译安装到手机上查看*

---


DefaultTextStyle的动画版本，当字体风格变化时产生一个动画效果<br>

AnimatedDefaultTextStyle的参数
* 【child】child节点
* 【style】字体风格
* 【textAlign】text对齐方式
* 【softWrap】是否自适应换行
* 【overflow】当字体长度超出布局宽度时，文字的显示方式
* 【maxLines】显示的最大行数
* 【textWidthBasis】计算文字宽度的策略，默认值TextWidthBasis.parent
* 【textHeightBehavior】暂时不明白这个属性的用途
* 【curve】参考[Curves](https://api.flutter-io.cn/flutter/animation/Curves-class.html)
* 【duration】一个动画周期的持续时间
* 【onEnd】动画结束的无参回调

部分代码

```dart
Column(
  children: <Widget>[
    ///淡入淡出的切换两个widget
    AnimatedCrossFade(
      duration: const Duration(milliseconds: 700),
      firstChild: const FlutterLogo(
        style: FlutterLogoStyle.horizontal,
        size: 200.0,
      ),
      secondChild: const FlutterLogo(
        style: FlutterLogoStyle.stacked,
        size: 200.0,
      ),
      crossFadeState: _first ? CrossFadeState.showFirst : CrossFadeState.showSecond,
    ),
    ///点击后改变要显示的widget
    RaisedButton(
      onPressed: () {
        setState(() {
          _first = !_first;
        });
      },
      child: Text('Click me'),
    ),
  ],
)

```
![AnimatedCrossFade](https://github.com/memtopia/flutter_rampup/raw/master/images/AnimatedCrossFade.gif)


