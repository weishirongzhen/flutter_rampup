---
*Flutter 150+ widget 系列示例，持续更新ing~~，更新顺序为按A-Z排序，目前代码中已包含151个示例。*<br>
*[查看代码](https://github.com/memtopia/flutter_rampup_demo_app) 或者 [查看web完整示例](https://memtopia.github.io)*<br>
*目前有部分widget在web端还有问题，如想查看更完整的例子Android 和 iOS用户可同步代码后编译安装到手机上查看*

---


对齐与相对定位<br>

Align的参数
* 【child】child节点
* 【alignment】Alignment类型，控制对齐方式，支持topLeft,topCenter,topRight,centerLeft,center,centerRight,bottomLeft,bottomCenter,bottomRight
* 【widthFactor】double类型，如果不为空，设置其width为child的width的倍数，不能为负数
* 【heightFactor】double类型，如果不为空，设置其height为child的height的倍数，不能为负数

部分代码

```dart
Container(
  height: 150,
  width: 200,
  color: Colors.blue,

  ///让text内容在container的顶部居右
  child: Align(
    alignment: Alignment.topRight,
    child: Text(
      'Hello Flutter',
      style: TextStyle(
        backgroundColor: Colors.white,
        fontSize: 24,
      ),
    ),
  ),
)

```
![Align](https://github.com/memtopia/flutter_rampup/raw/master/images/Align1.png)

widthFactor的 用法则有点特别，通过设置这个属性，可以实现一些特殊的布局

```dart
///Align宽度为child的0.7倍， 此时Text 位置已经改变， 更多请参考 ClipRect
Row(
  mainAxisAlignment: MainAxisAlignment.center,
  children: <Widget>[
    Align(
      alignment: Alignment.topLeft,
      widthFactor: 0.7,
      child: Container(
        width: 100,
        height: 100,
        color: Colors.pinkAccent,
      ),
    ),
    Text("Hello Flutter"),
  ],
),
```
![Align](https://github.com/memtopia/flutter_rampup/raw/master/images/Align2.png)

