# Container comparison

## Questions
>    a) when to use?
 
>   b) alternatives?

>    c) downsides?

>    d) key properties?


### Multichild Containers
1. Column
2. row
3. Flow
4. Card
5. LayoutBuilder/ builder
6. Wrap
7. CustomSingleChildLayout
8. CustomMultiChildLayout
9. CustomScrollView   

Column
### Row
Horizontal, cross-axis,troubleshooting with expanded/flexible
###  Flow
###  Card
###  LayoutBuilder/ builder
###  Wrap
###  CustomSingleChildLayout
###  CustomMultiChildLayout
###  CustomScrollView



___
## Containers for positioning children  
1. Align
> Aligns its child with respect to its parent.
> Will size it parent by the factor of the height of the child.
> if no height is set for the container.
   
  ````
   return Container(
      constraints: BoxConstraints(maxHeight: 200),
      color: Colors.green.shade200.withOpacity(.8),
      child:Align(
      heightFactor: 10,
      child: Text('$text', style: TextStyle(fontSize: 22, color: Colors.orange),),
      )
   );
````



---

2. Center
3. Positioned


### Self sizing containers



### Containes that Size/ constrians their children
#### 1. AspectRatio


#### 2. Container
   > 1. Key Properties: constraints,color,width/height, alignment, paddding, margin
   >> a. what happens if you dont set the height/width, with and without child?

#### 3. ConstrainedBox
   Used in Slivers or in  
4. Expanded
5. Flexible
6. FittedBox
7. FractionallySizedBox
8. Intrinsic


9. PreferredSize
10. SafeArea
11. SizedBox
12. Stack
13. UnconstrainedBox
14. OverflowBar
15. OverflowBox
