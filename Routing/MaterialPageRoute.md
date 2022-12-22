# Routing

### resources:
*    [Animate a page route transition](https://docs.flutter.dev/cookbook/animation/page-route-animation).
     
- [Medium: Page Transitions in Flutter](https://medium.flutterdevs.com/page-transitions-in-flutter-5236a8afae92)  👍.
- [Woolha: Using SlideTransition Widget Examples](https://www.woolha.com/tutorials/flutter-using-slidetransition-widget-examples) 👍

### Key Classes 
- PageRouteBuilder()
- xxxTransition() e.g. SizeTransition()

## 1. Create a route config file
```dart
class AppRouter {
  static Route onGenerate(RouteSettings settings){
    switch (settings.name) {
      case '/':
        return PageviewAnimation.route();
      case PageviewAnimation.routeName:
        return PageviewAnimation.route();
      default:
        return _errorRoute();
  }

    static Route _errorRoute() {
      return MaterialPageRoute(
        settings: const RouteSettings(name: '/error'),
        builder: (_) => Scaffold(
          appBar: AppBar(
            title: const Text('Error'),
          ),
          body: const Center(
            child: Text('Something went wrong!'),
          ),
        ),
      );

```
## 2. Insert static method 'generateRoute' in the Screen widget.

### A  route with transitions.
```dart
 return PageRouteBuilder(
      settings: RouteSettings(name: routeName),
      pageBuilder: (context, animation, second) => PageviewAnimation(),
      transitionsBuilder: (context, animation, secondaryAnimation, child) {
        print('building page route animated');
        const begin = Offset(0.0, 1.0);
        const end = Offset.zero;
        const curve = Curves.ease;

        var tween =
            Tween(begin: begin, end: end).chain(CurveTween(curve: curve));

        return SlideTransition(
          position: animation.drive(tween),
          child: child,
        );
      },
    );
  }
```

### A simple route.

```dart
static Route route() {
      return MaterialPageRoute(
        settings: RouteSettings(name: routeName),
        builder: (context) => PageviewAnimation(),
      );
    }
```

### Trigger the route.
```dart
ListTile(
      onTap: () =>
            Navigator.pushNamed(context, '/TabLayoutExample'),
      title: Text('TabLayoutExample'),
      leading: Icon(Icons.access_alarm),
                  ),

```

