---
*Flutter 150+ widget 系列示例，持续更新ing~~，更新顺序为按A-Z排序，目前代码中已包含150+个示例。*<br>
*[查看代码](https://github.com/memtopia/flutter_rampup_demo_app) 或者 [查看web完整示例](https://memtopia.github.io)*<br>
*目前有部分widget在web端还有问题，如想查看更完整的例子Android 和 iOS用户可同步代码后编译安装到手机上查看*

---

按钮条，类似于 Row中的若干button布局， 也可以单个


ButtonBar的参数
* 【alignment】button的排列方式， 默认MainAxisAlignment.end排列
* 【mainAxisSize】水平方向占用多少空间
* 【buttonTextTheme】button中文字主题
* 【buttonMinWidth】button最小宽度
* 【buttonHeight】button高度
* 【buttonPadding】button 之间padding
* 【buttonAlignedDropdown】暂不明用法
* 【layoutBehavior】决定buttonbar的size由最小size决定还是padding决定
* 【overflowDirection】overflow方向
* 【overflowButtonSpacing】如果overflow, button之间的空间大小
* 【children】若干个按钮


部分代码

```dart
Column(
  children: <Widget>[
    ///默认排序
    ButtonBar(
      children: <Widget>[
        FlatButton(
          child: Text('Ok'),
          color: Colors.blue,
          onPressed: () {},
        ),
        FlatButton(
          child: Text('Cancel'),
          color: Colors.red,
          onPressed: () {},
        ),
      ],
    ),
    ///spaceEvenly排列
    ButtonBar(
      alignment: MainAxisAlignment.spaceEvenly,
      children: <Widget>[
        FlatButton(
          child: Text('Ok'),
          color: Colors.blue,
          onPressed: () {},
        ),
        FlatButton(
          child: Text('Cancel'),
          color: Colors.red,
          onPressed: () {},
        ),
      ],
    ),
    ///spaceAround 排列
    ButtonBar(
      alignment: MainAxisAlignment.spaceAround,
      children: <Widget>[
        FlatButton(
          child: Text('Ok'),
          color: Colors.blue,
          onPressed: () {},
        ),
        FlatButton(
          child: Text('Cancel'),
          color: Colors.red,
          onPressed: () {},
        ),
      ],
    ),
  ],
);

```
![ButtonBar](https://github.com/memtopia/flutter_rampup/raw/master/images/ButtonBar.png)


