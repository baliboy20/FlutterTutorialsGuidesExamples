
## Correctly sizing an image

#### Use fitted box
* Fitted box(https://api.flutter.dev/flutter/widgets/FittedBox-class.html) 

```
Container(
              width: MediaQuery.of(context).size.width * .5,
              height: MediaQuery.of(context).size.width * .5 * .63,
              color: Colors.amber,
              child: ImageWidget(),
            ),  ...
 /** Image Widget */
class ImageWidget  extends StatelessWidget {
const Image({Key? key}) : super(key: key);

@override
Widget build(BuildContext context) {
return
FittedBox(
fit: BoxFit.fitWidth,
child: Image.asset(
'../images/pnc8.jpeg'),
);
}

}
````
