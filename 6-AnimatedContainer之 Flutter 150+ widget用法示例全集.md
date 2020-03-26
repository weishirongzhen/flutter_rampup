---
*Flutter 150+ widget 系列示例，持续更新ing~~，更新顺序为按A-Z排序，目前代码中已包含151个示例。*<br>
*[查看代码](https://github.com/memtopia/flutter_rampup_demo_app) 或者 [查看web完整示例](https://memtopia.github.io)*<br>
*目前有部分widget在web端还有问题，如想查看更完整的例子Android 和 iOS用户可同步代码后编译安装到手机上查看*

---


动画版本的Container<br>

AnimatedContainer的参数
* 【child】child节点
* 【alignment】参考[Align](https://juejin.im/post/5e79aeba6fb9a07cda099648)
* 【padding】包含于decoration或者child之内的空白空间，类似于android的padding属性
* 【color】container背景色（注意，如果使用了decoration则不能在这里设置这个属性，需要在decoration中设置color的属性，否则异常）
* 【decoration】container的装饰，例如圆角，背景色，背景图片等等
* 【foregroundDecoration】显示在child之上的decoration
* 【width】宽度
* 【height】高度
* 【constraints】为child添加额外的布局约束
* 【margin】包裹decoration或者child的空白空间，类似于android的margin属性
* 【transform】绘制参数的相关属性，之后会讲到
* 【curve】参考[Curves](https://api.flutter-io.cn/flutter/animation/Curves-class.html)
* 【duration】一个动画周期的持续时间
* 【onEnd】动画结束的无参回调

部分代码

```dart
///点击后改变颜色和高度，还有边框的弧度，除了这些出行， AnimatedContainer其他的任何属性改变都会有动画效果
GestureDetector(
  onTap: () {
    setState(() {
      _selected = !_selected;
    });
  },
  child: AnimatedContainer(
    height: _selected ? _value : 100,
    width: _selected ? _value : 100,
    decoration: BoxDecoration(
      color: _selected ? Colors.brown : Colors.blueGrey,
      borderRadius: _selected ? BorderRadius.circular(100) : BorderRadius.circular(0),
    ),
    duration: Duration(milliseconds: 200),
    child: Center(
        child: Text(
      'Click me',
      style: TextStyle(fontSize: 20, color: Colors.white),
    )),
    onEnd: (){print("动画结束");},
  ),
),

```
![AnimatedContainer](https://github.com/memtopia/flutter_rampup/raw/master/images/AnimatedContainer.gif)

