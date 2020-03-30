---
*Flutter 150+ widget 系列示例，持续更新ing~~，更新顺序为按A-Z排序，目前代码中已包含150+个示例。*<br>
*[查看代码](https://github.com/memtopia/flutter_rampup_demo_app) 或者 [查看web完整示例](https://memtopia.github.io)*<br>
*目前有部分widget在web端还有问题，如想查看更完整的例子Android 和 iOS用户可同步代码后编译安装到手机上查看*

---

标签，banner 

Banner的参数
* 【child】child节点
* 【message】banner上的文字
* 【textDirection】文字方向
* 【location】banner位置
* 【layoutDirection】布局方向
* 【color】banner颜色
* 【textStyle】滤镜

部分代码

```dart
Column(
  children: <Widget>[
    Container(
      margin: const EdgeInsets.all(10.0),
      height: 100,
      child: Banner(
        message: "Flutter",
        location: BannerLocation.topStart,
        color: Colors.deepPurpleAccent,
        child: Container(
          color: Colors.blueGrey,
          height: 100,
          child: Center(
            child: Text("Hello Flutter"),
          ),
        ),
      ),
    ),
    ///切边
    Container(
      margin: const EdgeInsets.all(10.0),
      height: 100,
      child: ClipRect(
        child: Banner(
          message: "Flutter",
          location: BannerLocation.topEnd,
          color: Colors.red,
          child: Container(
            color: Colors.blueGrey,
            height: 100,
            child: Center(
              child: Text("Hello Flutter"),
            ),
          ),
        ),
      ),
    ),
  ],
)
```

![Banner](https://github.com/memtopia/flutter_rampup/raw/master/images/Banner1.png)


