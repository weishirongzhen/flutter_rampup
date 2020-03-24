
# 【1】AbsorbPointer之Flutter 150+ widget用法示例全集


---
**Flutter 150+ widget 系列示例，持续更新ing~~，更新顺序为按A-Z排序**<br>
[github地址](https://github.com/memtopia/flutter_rampup_demo_app) https://github.com/memtopia/flutter_rampup_demo_app<br>
android用户可直接安装仓库中flutter_book.apk查看效果，iOS用户可同步代码后编译安装到手机上查看

---

如果要让一个按钮不可点击一般可以让onPressed = null， 但是这个会改变按钮的风格
```dart
RaisedButton(
        child: Text('Click me'),
        onPressed: null,)
```
有时候会遇到的需求是，让某一片区域不可点击。<br>
当absorbing为true时，用户输入事件被吸收，不会再把事件传递给RaisedButton，一般用来禁止某一片区域的点击事件

AbsorbPointer的参数
* 【child】child节点
* 【absorbing】是否吸收用户输入
部分代码
```dart
AbsorbPointer(
  absorbing: true,
  child: Column(
    children: <Widget>[
      RaisedButton(
        child: Text('Click me'),
        onPressed: () {
          showToast('clicked!');
        },
      ),
      RaisedButton(
        child: Text('Click me'),
        onPressed: () {
          showToast('clicked!');
        },
      ),
      RaisedButton(
        child: Text('Click me'),
        onPressed: () {
          showToast('clicked!');
        },
      ),
    ],
  ),
)
```
![AbsorbPointer](https://github.com/memtopia/flutter_rampup/raw/master/images/AbsorbPointer.png)


