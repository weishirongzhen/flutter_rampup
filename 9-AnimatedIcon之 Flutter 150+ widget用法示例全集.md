---
*Flutter 150+ widget 系列示例，持续更新ing~~，更新顺序为按A-Z排序，目前代码中已包含151个示例。*<br>
*[查看代码](https://github.com/memtopia/flutter_rampup_demo_app) 或者 [查看web完整示例](https://memtopia.github.io)*<br>
*目前有部分widget在web端还有问题，如想查看更完整的例子Android 和 iOS用户可同步代码后编译安装到手机上查看*

---


有过场动画的Icon

AnimatedIcon的参数
* 【icon】AnimatedIcon类型， Flutter官方提供了很多，可直接使用
* 【progress】动画进度控制
* 【color】icon颜色
* 【size】icon大小
* 【semanticLabel】描述标签，暂无用处
* 【textDirection】方向参数， 如果这是为 rtl， 则变成镜像显示


部分代码

```dart

_animation = AnimationController(vsync: this)..duration = Duration(milliseconds: 500);

Center(
  child: GestureDetector(
    onTap: () {
      _change = !_change;
      _change ? _animation.forward() : _animation.reverse();
    },
    child: AnimatedIcon(
      size: 100,
      color: Colors.lightBlue,
      icon: AnimatedIcons.arrow_menu,
      progress: _animation,
    ),
  ),
)
```
![AnimatedIcon](https://github.com/memtopia/flutter_rampup/raw/master/images/AnimatedIcon.gif)


