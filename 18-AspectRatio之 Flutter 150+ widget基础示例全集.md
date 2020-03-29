---
*Flutter 150+ widget 系列示例，持续更新ing~~，更新顺序为按A-Z排序，目前代码中已包含150+个示例。*<br>
*[查看代码](https://github.com/memtopia/flutter_rampup_demo_app) 或者 [查看web完整示例](https://memtopia.github.io)*<br>
*目前有部分widget在web端还有问题，如想查看更完整的例子Android 和 iOS用户可同步代码后编译安装到手机上查看*

---

创建有固定比例的widget

AspectRatio的参数
* 【aspectRatio】比例  width:height
* 【child】child节点


部分代码

```dart
Container(
  height: 100,
  child: AspectRatio(
    aspectRatio: 4 / 3,
    child: Container(
      color: Colors.blue,
    ),
  ),
),
Container(
  height: 100,
  child: AspectRatio(
    aspectRatio: 4 / 2,
    child: Container(
      color: Colors.red,
    ),
  ),
),
```
![AspectRatio](https://github.com/memtopia/flutter_rampup/raw/master/images/AspectRatio.png)


