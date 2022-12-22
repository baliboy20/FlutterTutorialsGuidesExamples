# SliverMenubar
A Material Design app bar that integrates with a CustomScrollView.

An app bar consists of a toolbar and potentially other widgets, such as a TabBar and a FlexibleSpaceBar. App bars typically expose one or more common actions with IconButtons which are optionally followed by a PopupMenuButton for less common operations.

    return Scaffold(
      body: CustomScrollView(
        slivers: [
          SliverAppBar(
            title: Text('The King of Sweden'),
            pinned: false,
            floating: false,
            collapsedHeight: 60,
            expandedHeight: 200,
          ),
          SliverList(
            delegate:
                SliverChildBuilderDelegate(
                        childCount: 20,
                        (BuildContext context, int idx) {
              return Container(
                height: 60,
                color: idx % 2 == 0 ? Colors.pink : Colors.red,
              );
            }),
          )
        ],
      ),
    );
}
