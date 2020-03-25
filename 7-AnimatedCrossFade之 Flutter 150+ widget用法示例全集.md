
---
**Flutter 150+ widget 系列示例，持续更新ing~~，更新顺序为按A-Z排序**<br>
[github](https://github.com/memtopia/flutter_rampup_demo_app)，
android用户可直接安装仓库中flutter_book.apk查看效果，iOS用户可同步代码后编译安装到手机上查看<br>
如果喜欢请star一下~

---


为两个widget的切换添加cross-fades的效果<br>

AnimatedCrossFade的参数
* 【firstChild】当 crossFadeState = CrossFadeState.showFirst 时显示的child
* 【secondChild】当 crossFadeState = CrossFadeState.showSecond 时显示的child
* 【firstCurve】firstChild显示时的Curve参数，参考[Curves](https://api.flutter-io.cn/flutter/animation/Curves-class.html)
* 【secondCurve】secondChild显示时的Curve参数，参考[Curves](https://api.flutter-io.cn/flutter/animation/Curves-class.html)
* 【sizeCurve】当firstChild和secondChild size 不一样时的Curve参数，参考[Curves](https://api.flutter-io.cn/flutter/animation/Curves-class.html)
* 【alignment】参考[Align](https://juejin.im/post/5e79aeba6fb9a07cda099648)
* 【crossFadeState】决定当前显示的child，值为 CrossFadeState.showFirst 或 CrossFadeState.showSecond
* 【duration】一个动画周期的持续时间
* 【reverseDuration】一个逆向动画周期的持续时间
* 【layoutBuilder】用于定位child的builder， 默认值AnimatedCrossFade.defaultLayoutBuilder

部分代码

```dart
Column(
  children: <Widget>[
    ///淡入淡出的切换两个widget
    AnimatedCrossFade(
      duration: const Duration(milliseconds: 700),
      firstChild: const FlutterLogo(
        style: FlutterLogoStyle.horizontal,
        size: 200.0,
      ),
      secondChild: const FlutterLogo(
        style: FlutterLogoStyle.stacked,
        size: 200.0,
      ),
      crossFadeState: _first ? CrossFadeState.showFirst : CrossFadeState.showSecond,
    ),
    ///点击后改变要显示的widget
    RaisedButton(
      onPressed: () {
        setState(() {
          _first = !_first;
        });
      },
      child: Text('Click me'),
    ),
  ],
)

```
![AnimatedCrossFade](https://github.com/memtopia/flutter_rampup/raw/master/images/AnimatedCrossFade.gif)


