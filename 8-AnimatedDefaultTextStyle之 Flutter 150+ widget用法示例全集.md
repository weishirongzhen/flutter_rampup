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
bool _change = true;
double _fontSize = 60;
Color _color = Colors.blue;
FontWeight _fontWeight = FontWeight.bold;

Column(
  mainAxisSize: MainAxisSize.min,
  children: <Widget>[
    ///改变字体 sized color weight
    AnimatedDefaultTextStyle(
      curve: Curves.bounceOut,
      duration: const Duration(milliseconds: 300),
      style: TextStyle(
        fontSize: _fontSize,
        color: _color,
        fontWeight: _fontWeight,
      ),
      child: Column(
        children: <Widget>[
          Text('Flutter'),
          Text('Flutter'),
        ],
      ),
      onEnd: () {
        print('动画结束回调');
      },
    ),
    RaisedButton(
      onPressed: () {
        setState(() {
          _fontSize = _change ? 90 : 60;
          _color = _change ? Colors.blue : Colors.red;
          _change = !_change;
          _fontWeight = _change ? FontWeight.bold : FontWeight.w100;
          _style = _change ? GoogleFonts.sigmarOne(fontSize: 60, color: Colors.blue) : GoogleFonts.macondo(fontSize: 40, color: Colors.blue);
        });
      },
      child: Text(
        "Click me!",
      ),
    )
  ],
)
```
![AnimatedDefaultTextStyle](https://github.com/memtopia/flutter_rampup/raw/master/images/AnimatedDefaultTextStyle.gif)


