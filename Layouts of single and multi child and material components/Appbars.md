# Appbars

### 1. Appbar

### 1. PreferredSpace
   A widget with a preferred size.

This widget does not impose any constraints on its child, and it doesn't affect the child's layout in any way. It just advertises a preferred size which can be used by the parent.

Parents like Scaffold use PreferredSizeWidget to require that their children implement that interface. To give a preferred size to an arbitrary widget so that it can be used in a child property of that type, this widget, PreferredSize, can be used.

Widgets like AppBar implement a PreferredSizeWidget, so that this PreferredSize widget is not necessary for them.

[PreferredSpace](https://api.flutter.dev/flutter/widgets/PreferredSize-class.html) Docs.


###  Appbar

 - Scaffold, which displays the AppBar in its Scaffold.appBar slot.
 - SliverAppBar, which uses AppBar to provide a flexible app bar that can be used in a CustomScrollView.
- TabBar, which is typically placed in the bottom slot of the AppBar if the screen has multiple pages arranged in tabs.
- IconButton, which is used with actions to show buttons on the app bar.
- PopupMenuButton, to show a popup menu on the app bar, via actions.
- FlexibleSpaceBar, which is used with flexibleSpace when the app bar can expand and collapse.
- material.io/design/components/app-bars-top.html
- m3.material.io/components/top-app-bar
- Cookbook: Place a floating app bar above a list

### Bottom NavigationBar
