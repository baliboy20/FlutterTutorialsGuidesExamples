## Actions and Intents

follow the example in [Actions Class](https://api.flutter.dev/flutter/widgets/Actions-class.html)

__Key steps__
1) Subclass an Actions from Actions and implement the invoke override

```dart
   
class MyActionPressed extends Action<MyIntentPressed> {
    @override
    Object? invoke(covariant MyIntentPressed intent) {
        print('invoked !!!!!');
       }   
    }

```


2) Subtype Intents form Intents base class


```dart   
class MyIntentPressed extends Intent {
  final String moosh;

  MyIntentPressed({required this.moosh}) : super() {
    print('MyIntentPressed value:  $moosh');
  }
}

```
3) Map Intents to Actions in Actions() Widget.

```dart
  return Actions(
        actions: <Type, Action<Intent>>{
          ModifyIntent: ModifyAction(model),
          SaveIntent: SaveAction(model),
          MyIntentPressed: MyActionPressed(),
        },
        child: Builder(
           builder: (context) => Center(
            child: Column(
              mainAxisAlignment: MainAxisAlignment.center,
              children: [
```

4) Use Builder if Required to propogate the Actions Config to the trigger in the widgets.

` builder: (context) => Center(
   child: Column(`

5) Invoke the Actions.

```dart
    ElevatedButton(
                  onPressed: () {
                            Actions.invoke(context, MyIntentPressed(moosh: 'quigly'));
                  },
                  child: Icon(Icons.add)),
```
