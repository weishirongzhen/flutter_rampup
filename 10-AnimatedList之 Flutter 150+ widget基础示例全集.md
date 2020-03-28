---
*Flutter 150+ widget 系列示例，持续更新ing~~，更新顺序为按A-Z排序，目前代码中已包含150+个示例。*<br>
*[查看代码](https://github.com/memtopia/flutter_rampup_demo_app) 或者 [查看web完整示例](https://memtopia.github.io)*<br>
*目前有部分widget在web端还有问题，如想查看更完整的例子Android 和 iOS用户可同步代码后编译安装到手机上查看*

---

一个可滚动的容器，当插入或移除时可以设置动画效果。

AnimatedList的参数
* 【itemBuilder】创建list的每个item的构造方法
* 【initialItemCount】初始列表长度
* 【scrollDirection】list滑动方向，竖向 或 纵向， Axis.vertical, Axis.horizontal
* 【reverse】是否逆序显示
* 【controller】滚动controller，用于使用代码滚动list或者监听list位置
* 【primary】设置是否是主滚动view， 如果parent存在其他的滚动控件
* 【physics】滚动的物理效果
* 【shrinkWrap】是否只占有list本身的大小， 如果是false，则会占用滚动方向的最大可用空间，反之
* 【padding】list周围的padding


部分代码

```dart
final GlobalKey<AnimatedListState> listKey = GlobalKey<AnimatedListState>();

List<String> _items = List();

Widget _buildItem(BuildContext context, int index, animation) {
  String item = _items[index];
  return SlideTransition(
    position: Tween<Offset>(
      begin: const Offset(-1, 0),
      end: Offset.zero,
    ).animate(animation),
    child: Padding(
      padding: const EdgeInsets.all(8.0),
      child: Text(
        item,
        textAlign: TextAlign.center,
      ),
    ),
  );
}

@override
Widget buildBody(BuildContext context) {
  return SafeArea(
    child: Row(
      crossAxisAlignment: CrossAxisAlignment.center,
      children: <Widget>[
        Expanded(
          child: Container(
            height: double.infinity,
            child: AnimatedList(
              key: listKey,
              initialItemCount: _items.length,
              itemBuilder: (context, index, animation) {
                return _buildItem(context, index, animation);
              },
            ),
          ),
        ),
        Column(
          crossAxisAlignment: CrossAxisAlignment.center,
          children: <Widget>[
            RaisedButton(
              onPressed: () {
                setState(() {
                  listKey.currentState.insertItem(
                    0,
                    duration: const Duration(milliseconds: 300),
                  );
                  _items.add('Hello flutter');
                });
              },
              child: Text(
                "插入一条",
              ),
            ),
            RaisedButton(
              onPressed: () {
                if (_items.length <= 1) return;
                listKey.currentState.removeItem(
                  0,
                  (_, animation) => _buildItem(context, 0, animation),
                  duration: const Duration(milliseconds: 300),
                );
                setState(() {
                  _items.removeAt(0);
                });
              },
              child: Text(
                "删除一条",
              ),
            )
          ],
        )
      ],
    ),
  );
}
```
![AnimatedIcon](https://github.com/memtopia/flutter_rampup/raw/master/images/AnimatedList.gif)


