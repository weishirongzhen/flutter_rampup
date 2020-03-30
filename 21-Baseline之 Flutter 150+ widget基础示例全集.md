---
*Flutter 150+ widget 系列示例，持续更新ing~~，更新顺序为按A-Z排序，目前代码中已包含150+个示例。*<br>
*[查看代码](https://github.com/memtopia/flutter_rampup_demo_app) 或者 [查看web完整示例](https://memtopia.github.io)*<br>
*目前有部分widget在web端还有问题，如想查看更完整的例子Android 和 iOS用户可同步代码后编译安装到手机上查看*

---

根据child的baseline定位child的小部件，即使得不同的child都处在规定的基线位置，尤其是多用在文字排版中，比如使得不同大小的文字处于同一水平线。

Baseline的参数
* 【child】child节点
* 【baseline】banner上的文字
* 【baselineType】文字方向

部分代码

```dart
Row(
  children: <Widget>[
    Baseline(
        baseline: 0,
        // 对齐的对象类型
        baselineType: TextBaseline.alphabetic,
        child: Text(
          'hello',
        )),
    Baseline(
        baseline: 20,
        baselineType: TextBaseline.alphabetic,
        child: Text(
          'flutter',
        )),
    Baseline(
        baseline: 50,
        // 对齐的对象类型
        baselineType: TextBaseline.alphabetic,
        child: Text(
          'hello',
        )),
    Baseline(
        baseline: 80,
        baselineType: TextBaseline.alphabetic,
        child: Text(
          'flutter',
        )),
    Baseline(
        baseline: 90,
        // 对齐的对象类型
        baselineType: TextBaseline.alphabetic,
        child: Text(
          'hello',
        )),
    Baseline(
        baseline: 100,
        baselineType: TextBaseline.alphabetic,
        child: Text(
          'flutter',
        )),
  ],
)
```
通过设置不同的Baseline可以让text的排版实现自定义对齐。<br>
![Baseline](https://github.com/memtopia/flutter_rampup/raw/master/images/Baseline.png)


