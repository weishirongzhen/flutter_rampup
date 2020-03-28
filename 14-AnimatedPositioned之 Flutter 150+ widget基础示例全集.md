---
*Flutter 150+ widget 系列示例，持续更新ing~~，更新顺序为按A-Z排序，目前代码中已包含150+个示例。*<br>
*[查看代码](https://github.com/memtopia/flutter_rampup_demo_app) 或者 [查看web完整示例](https://memtopia.github.io)*<br>
*目前有部分widget在web端还有问题，如想查看更完整的例子Android 和 iOS用户可同步代码后编译安装到手机上查看*

---

动画版本的Positioned，在给定的duration内变化位置

AnimatedPositioned的参数
* 【child】child节点
* 【left】左部坐标
* 【top】上部坐标
* 【right】右部坐标
* 【bottom】底部坐标
* 【width】宽度
* 【height】高度
* 【curve】参考[Curves](https://api.flutter-io.cn/flutter/animation/Curves-class.html)
* 【duration】一个动画周期的持续时间
* 【onEnd】动画结束的无参回调



部分代码

```dart

bool _change = true;
double _left = 0;
double _top = 0;
double _right = 100;
double _bottom = 0;

Column(
  mainAxisAlignment: MainAxisAlignment.start,
  children: <Widget>[
    Container(
      height: 200,
      child: Stack(
        children: <Widget>[
          AnimatedPositioned(
            duration: const Duration(milliseconds: 200),
            curve: Curves.easeOutQuad,
            left: _left,
            top: _top,
            right: _right,
            bottom: _bottom,
            child: Container(
              color: Colors.brown,
            ),
          ),
        ],
      ),
    ),
    SizedBox(
      height: 20,
    ),
    RaisedButton(
      child: const Text('Click me!'),
      onPressed: () {
        setState(() {
          _left = _change ? 100 : 0;
          _top = _change ? 0 : 0;
          _right = _change ? 0 : 100;
          _bottom = _change ? 0 : 0;
          _change = !_change;
        });
      },
    ),
  ],
)
```
![AnimatedPositioned](https://github.com/memtopia/flutter_rampup/raw/master/images/AnimatedPositioned.gif)


