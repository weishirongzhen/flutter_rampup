---
*Flutter 150+ widget 系列示例，持续更新ing~~，更新顺序为按A-Z排序，目前代码中已包含150+个示例。*<br>
*[查看代码](https://github.com/memtopia/flutter_rampup_demo_app) 或者 [查看web完整示例](https://memtopia.github.io)*<br>
*目前有部分widget在web端还有问题，如想查看更完整的例子Android 和 iOS用户可同步代码后编译安装到手机上查看*

---

界面顶部导航栏，一般用作 Scaffold的appBar的child
特别提示：默认的，当使用 Navigator.push(), 打开另一个页面时， AppBar的 leading 默认是一个返回icon，如果使用Navigator.pushReplace(), 则leading不会显示。

AppBar的参数
* 【leading】AppBar最左侧child
* 【automaticallyImplyLeading】 是否自动添加leading 如果 leading=null，默认为true
* 【title】AppBar 标题
* 【actions】AppBar 右侧菜单，通常是一个IconButton
* 【flexibleSpace】一个显示在 AppBar 下方的控件，高度和 AppBar 高度一样，
* 【bottom】一个 AppBarBottomWidget 对象，通常是 TabBar
* 【elevation】z轴高度
* 【shape】边框形状
* 【backgroundColor】背景色
* 【brightness】appbar 明暗类型
* 【iconTheme】icon的颜色，形状，透明度，通常和brightness一起使用
* 【actionsIconTheme】右侧菜单的主题风格， 同iconTheme
* 【textTheme】appbar 文字风格
* 【primary】是否是主appbar
* 【centerTitle】标题是否居中
* 【excludeHeaderSemantics】 暂不明用途
* 【titleSpacing】title 左右空白空间
* 【toolbarOpacity】 appbar中toolbar透明度
* 【bottomOpacity】 appbar中bottom widget的透明度



部分代码

```dart
AppBar(
  backgroundColor: Colors.blue,
  toolbarOpacity: 0.9,
  leading: IconButton(
    icon: const Icon(Icons.arrow_back),
    onPressed: () {},
  ),
  title: const Text('AppBar'),
  centerTitle: true,
  automaticallyImplyLeading: false,
  actions: <Widget>[
    IconButton(
      icon: const Icon(Icons.email),
      onPressed: () {},
    ),
    IconButton(
      icon: const Icon(Icons.more_vert),
      onPressed: () {},
    ),
  ],
)
```
![AppBar](https://github.com/memtopia/flutter_rampup/raw/master/images/AppBar.png)



```dart
AppBar(
  bottom: TabBar(
    controller: TabController(length: 3,vsync: this),
    tabs: <Widget>[
      Tab(child: Text('one')),
      Tab(child: Text('two')),
      Tab(child: Text('three')),
    ],
  ),
  backgroundColor: Colors.brown,
  toolbarOpacity: 0.9,
  leading: IconButton(
    icon: const Icon(Icons.arrow_back),
    onPressed: () {},
  ),
  title: const Text('AppBar'),
  centerTitle: true,
  automaticallyImplyLeading: false,
  actions: <Widget>[
    IconButton(
      icon: const Icon(Icons.email),
      onPressed: () {},
    ),
    IconButton(
      icon: const Icon(Icons.more_vert),
      onPressed: () {},
    ),
  ],
)
```
添加了bottom的AppBar
![AppBar](https://github.com/memtopia/flutter_rampup/raw/master/images/AppBar1.png)


