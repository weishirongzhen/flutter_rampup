---
*Flutter 150+ widget 系列示例，持续更新ing~~，更新顺序为按A-Z排序，目前代码中已包含150+个示例。*<br>
*[查看代码](https://github.com/memtopia/flutter_rampup_demo_app) 或者 [查看web完整示例](https://memtopia.github.io)*<br>
*目前有部分widget在web端还有问题，如想查看更完整的例子Android 和 iOS用户可同步代码后编译安装到手机上查看*

---

页面底部导航栏，

bottomNavigationBar的参数
* 【items】导航栏的items，类型是BottomNavigationBarItem
* 【onTap】点击回调，回调参数为当前选中的index
* 【currentIndex】当前选中index
* 【elevation】z轴高度
* 【type】BottomNavigationBarType.fixed item固定， BottomNavigationBarType.shifting item有移动效果。
* 【fixedColor】selectedItemColor 的值 不能和 selectedItemColor 同时出现
* 【backgroundColor】背景色, 如果type = BottomNavigationBarType.shifting， BottomNavigationBarItem的背景色会覆盖这个值
* 【iconSize】icon大小
* 【selectedItemColor】选中时的颜色
* 【unselectedItemColor】未选中的颜色
* 【selectedIconTheme】选中的icon的主题，默认IconThemeData()
* 【unselectedIconTheme】未选中的icon的主题，默认IconThemeData()
* 【selectedFontSize】选中时，字体大小
* 【unselectedFontSize】未选中时，字体大小
* 【selectedLabelStyle】选中时，字体风格
* 【unselectedLabelStyle】未选中时，字体风格
* 【showSelectedLabels】是否显示选中的item的文字
* 【showUnselectedLabels】是否显示未选中的item的文字

部分代码

```dart
int _selectedIndex = 0;
PageController _pageController = PageController(initialPage: 0);

@override
Widget buildBody(BuildContext context) {
  return Scaffold(
     body: PageView(
       physics: NeverScrollableScrollPhysics(),
       controller: _pageController,
       children: <Widget>[
         Text(
           '$_selectedIndex',
           style: TextStyle(fontSize: 40),
         ),
         Text(
           '$_selectedIndex',
           style: TextStyle(fontSize: 40),
         ),
         Text(
           '$_selectedIndex',
           style: TextStyle(fontSize: 40),
         ),
       ],
     ),
     bottomNavigationBar: BottomNavigationBar(
       backgroundColor: Colors.pinkAccent.withOpacity(0.5),
       type: BottomNavigationBarType.shifting,
       items: const <BottomNavigationBarItem>[
         BottomNavigationBarItem(
           icon: Icon(Icons.home),
           title: Text('Home'),
         ),
         BottomNavigationBarItem(
           icon: Icon(Icons.business),
           title: Text('Business'),
         ),
         BottomNavigationBarItem(
           icon: Icon(Icons.school),
           title: Text('School'),
         ),
       ],
       currentIndex: _selectedIndex,
       unselectedItemColor: Colors.grey,
       selectedItemColor: Colors.blue,
       onTap: (index) {
         setState(() {
           _selectedIndex = index;
         });
         _pageController.animateToPage(
           index,
           duration: Duration(milliseconds: 200),
           curve: Curves.ease,
         );
       },
     ),
   );
}
```
shifting类型
![bottomNavigationBar](https://github.com/memtopia/flutter_rampup/raw/master/images/BottomNavigationBar.gif)
fixed类型
![bottomNavigationBar](https://github.com/memtopia/flutter_rampup/raw/master/images/BottomNavigationBar2.gif)


