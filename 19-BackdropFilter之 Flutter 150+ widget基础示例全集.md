---
*Flutter 150+ widget 系列示例，持续更新ing~~，更新顺序为按A-Z排序，目前代码中已包含150+个示例。*<br>
*[查看代码](https://github.com/memtopia/flutter_rampup_demo_app) 或者 [查看web完整示例](https://memtopia.github.io)*<br>
*目前有部分widget在web端还有问题，如想查看更完整的例子Android 和 iOS用户可同步代码后编译安装到手机上查看*

---

为当前child添加一个滤镜 

BackdropFilter的参数
* 【child】child节点
* 【filter】滤镜

部分代码

```dart
Stack(
  alignment: Alignment.bottomRight,
  children: <Widget>[
    Image.asset(
      'assets/images/butterfly.webp',
    ),
    ///毛玻璃效果，左上角设置圆角
    ClipRRect(
      borderRadius: BorderRadius.only(
        topLeft: Radius.circular(40),
      ),
      child: BackdropFilter(
        filter: ImageFilter.blur(
          sigmaX: 10.0,
          sigmaY: 10.0,
        ),
        child: Container(
          alignment: Alignment.center,
          width: 200.0,
          height: 100.0,
          child: Text('Hello Flutter'),
        ),
      ),
    ),
  ],
)
```
以上代码实现了一个给背景图片盖上一层毛玻璃的效果

![BackdropFilter](https://github.com/memtopia/flutter_rampup/raw/master/images/BackdropFilter.png)


