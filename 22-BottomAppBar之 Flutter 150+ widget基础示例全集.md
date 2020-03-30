---
*Flutter 150+ widget 系列示例，持续更新ing~~，更新顺序为按A-Z排序，目前代码中已包含150+个示例。*<br>
*[查看代码](https://github.com/memtopia/flutter_rampup_demo_app) 或者 [查看web完整示例](https://memtopia.github.io)*<br>
*目前有部分widget在web端还有问题，如想查看更完整的例子Android 和 iOS用户可同步代码后编译安装到手机上查看*

---

页面底部栏

BottomAppBar的参数
* 【child】child节点
* 【color】背景色
* 【elevation】z轴高度
* 【shape】外形
* 【clipBehavior】有关裁切的属性，暂不明应用场景
* 【notchMargin】镂空padding

部分代码

```dart
Scaffold(
  floatingActionButtonLocation: FloatingActionButtonLocation.endDocked,
  floatingActionButton: FloatingActionButton(
    child: Text('OK'),
    onPressed: () {},
  ),
  bottomNavigationBar: BottomAppBar(
    elevation: 10,
    notchMargin: 10,
    shape: CircularNotchedRectangle(),
    color: Colors.blueGrey,
    child: SizedBox(
        height: 100,
        child: Text(
          'Hello Flutter',
          style: TextStyle(fontSize: 50),
        )),
  ),
)
```
通过设置shape = CircularNotchedRectangle(),配合FloatingActionButton可实现如下效果。<br>

![BottomAppBar](https://github.com/memtopia/flutter_rampup/raw/master/images/BottomAppBar.png)


