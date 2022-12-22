# List of layout widgets

2. Align
1. AspectRatio
2. Baseline
1. Center
2. Card
3. Container
4. Column
5. ConstrainedBox
6. CustomSingleChildLayout
8. CustomMultiChildLayout
1. Expanded
7. Flexible
8. FittedBox
10. Flow
9.  FractionallySizedBox
10. GridView
11. IndexedStack
10. Intrinsic Widget (Height and Width)
11. LayoutBuilder
12. LimitedBox
13. ListBody
14. ListView
13. OffStage
14. OverflowBox
11. Positioned
12. Padding
12. PreferredSize
12. Row
15. SafeArea
1.  SizedBox
2. SizedOverflowBox
14. Stack
15. Spacer
16. Table
16. UnconstrainedBox
17. Wrap
18. Transform
19. OverflowBox

__Key Constrained layouts widgets__

[Flutter - Using OverflowBox Widget Examples](https://www.woolha.com/tutorials/flutter-using-overflowbox-widget-examples)
1. OverflowBox
   [Overflowbox](https://teta.so/overflowbox/)

2. Sizedbox
3. UnconstrainedBox
4. ConstrainedBox
5. IntrinsicHeight
6. FittedBox
7. FractionallySizedBox




### Align
### AspectRatio
A widget that attempts to size the child to a specific aspect ratio.

The widget first tries the largest width permitted by the layout constraints. The height of the widget is determined by applying the given aspect ratio to the width, expressed as a ratio of width to height.


###  Center
A widget that centers its child within itself.

This widget will be as big as possible if its dimensions are constrained and widthFactor and heightFactor are null

> **Key properties**: HeightFactor, WidthFactor


###  Card
A Material Design card: a panel with slightly rounded corners and an elevation shadow.


### Container
A convenience widget that combines common painting, positioning, and sizing widgets.
>  **Key properties**: color, padding, constraints (BoxConstriants.expand etc)
> , alignment (Alignment.topCenter etc), width, height
> transform (Matrix4.rotationZ), decoration (BoxDecoration)

```
 child: Container(
    width: 150,
    height: 50,
    constraints: BoxConstraints(maxWidth: 250, maxHeight: 250),
    alignment: Alignment.bottomCenter,
```
Constraints and width act upon itself, alignment upon its children

### Column
> **Key properties**:
>
> Axis alignment properties. VerticalDirection

###  ConstrainedBox
A widget that imposes additional constraints on its child.
>  [Excellent Example](https://www.woolha.com/tutorials/flutter-using-constrainedbox-widget-examples)
```
    ConstrainedBox(
      constraints: const BoxConstraints(
      minHeight: 50.0,
      minWidth: 200.0,
),

```


For example, if you wanted child to have a minimum height of 50.0 logical pixels, you could use const BoxConstraints(minHeight: 50.0) as the

### CustomSingleChildLayout

### CustomMultiChildLayout

###   Expanded
Using an Expanded widget makes a child of a Row, Column, or Flex expand to fill the available space along the main axis (e.g., horizontally for a Row or vertically for a Column). If multiple children are expanded, the available space is divided among them according to the flex factor.
###   Flow

###   Flexible
Using a Flexible widget gives a child of a Row, Column, or Flex the flexibility to expand to fill the available space in the main axis (e.g., horizontally for a Row or vertically for a Column), but, unlike Expanded, Flexible does not require the child to fill the available space.
Flexible has the Fit property to adjust the widget to be its own prefferred size.
###  FittedBox
Scales and positions its child within itself according to fit.

###  FractionallySizedBox
A widget that sizes its child to a fraction of the total available space. For more details about the layout algorithm, see RenderFractionallySizedOverflowBox.

###   LayoutBuilder
Builds a widget tree that can depend on the parent widget's size.

Similar to the Builder widget except that the framework calls the builder function at layout time and provides the parent widget's constraints. This is useful when the parent constrains the child's size and doesn't depend on the child's intrinsic size. The LayoutBuilder's final size will match its child's size.

###   Positioned
A widget that controls where a child of a Stack is positioned.

###   Row
same as column.

###  SizedBox
A box with a specified size.
If given a child, this widget forces it to have a specific width and/or height. These values will be ignored if this widget's parent does not permit them.
###  Stack
A widget that positions its children relative to the edges of its box.

This class is useful if you want to overlap several children in a simple way
###  SafeArea
A widget that insets its child by sufficient padding to avoid intrusions by the operating system.

### Spacer

###  UnconstrainedBox
A widget that imposes no constraints on its child, allowing it to render at its "natural" size.
Stops a parent widget imposing it dimensions on the child will be set according to its
intrinsic values.

__[Excellent example](https://www.woolha.com/tutorials/flutter-using-unconstrainedbox-widget-examples)__

This allows a child to render at the size it would render if it were alone on an infinite canvas with no constraints
### Wrap
A widget that displays its children in multiple horizontal or vertical runs. The widget will take up all the space provided by its parent
> **Key properties**: direction (Axis.vertical), alignment, runAlignment, spacing, runSpacing, TextDirection

A Wrap lays out each child and attempts to place the child adjacent to the previous child in the main axis, given by direction, leaving spacing space in between. If there is not enough space to fit the child, Wrap creates a new run adjacent to the existing children in the cross axis.

### Overflowbar
A widget that lays out its children in a row unless they "overflow" the available horizontal space, in which case it lays them out in a column instead.

### Overflowbox

A widget that imposes different constraints on its child than it gets from its parent, possibly allowing the child to overflow the parent.
A widget


### Positioned
A widget that controls where a child of a Stack is positioned.

> A Positioned widget must be a descendant of a Stack, and the path from the Positioned widget to its enclosing Stack must contain only StatelessWidgets or StatefulWidgets (not other kinds of widgets, like RenderObjectWidgets).


### PreferredSize
This widget does not impose any constraints on its child, and it doesn't affect the child's layout in any way. It just advertises a preferred size which can be used by the parent.
> Parents like Scaffold use PreferredSizeWidget to require that their children implement that interface. To give a preferred size to an arbitrary widget so that it can be used in a child property of that type, this widget, PreferredSize, can be used.


See also:


RenderConstrainedOverflowBox for details about how OverflowBox is rendered.
SizedOverflowBox, a widget that is a specific size but passes its original constraints through to its child, which may then overflow.
ConstrainedBox, a widget that imposes additional constraints on its child.
UnconstrainedBox, a container that tries to let its child draw without constraints.
SizedBox, a box with a specified size.



### 19. Intrinsic Widget (Height and Width)
