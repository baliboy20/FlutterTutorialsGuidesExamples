# TabBar

## Resources
* [Flutter: TabBarView](https://api.flutter.dev/flutter/material/TabBarView-class.html)

## Main Classes & methods
- TickerProviderStateMixin, vsync
- TabBarView
- TabBar

```dart
 late TabController _controller;

  @override
  void initState() {
    // TODO: implement initState
    _controller = TabController(vsync: this, length:3);
    super.initState();
  }

  @override
  Widget build(BuildContext context) {
    return Scaffold(
      drawer: AppDrawer(),
      appBar: AppBar(
        title: Text('Home'),
        bottom: TabBar(
          indicatorSize: TabBarIndicatorSize.tab,
          indicatorColor: Colors.pink,
          controller: _controller,
          isScrollable: true,
          padding: EdgeInsets.symmetric(vertical: 3, horizontal: 28),
          tabs: [
            Tab(

              icon: Icon(Icons.account_circle),
              text: 'will',
            ),
            Tab(
              icon: Icon(Icons.duo),
              text: 'alice',
            ),
            Tab(
              icon: Icon(Icons.person),
              text: 'suz',
            ),
          ],
        ),
      ),
      body: TabBarView(
        controller: _controller,
        children: [
          Text('will'),
          Text('alice'),
          Text('suz'),
        ],
      ),
    );
  }
```





