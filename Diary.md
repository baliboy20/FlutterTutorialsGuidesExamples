#### 1. Projects worked on
1) Updated  __Project: animated_list__ eg /Users/will/flutterProjects/Examples/Lists/animated_list to include > infinite scroll with a ``NestedScrollView``
 displaying multiple tabs. resting on a ``Stack`` widget that has a ``floatingActionButtion`` positined on the left center.
2) Created __Project: BlocFormIntegration

###
### Wed 14 Dec
1) Project: Multitab_pages
- Demo of PageView(), TabBar(), TabBarView(),TabPageSelector()
- Demo routing transitions with recomended Routing patterns. __See__ *Routing/MaterialPageRoute.md*
- Project  *__Exercises/various_containers__*: showcasing various widgets including
  'home',form1',flexibleWidget': showMaterialBanner indexedStack': 
  ListViewExample': StepperExample': TabPageSelectorEx RadioListTileExam RefreshIndicatorE
  TabBarExample':  PageViewExample': SnackBarExample': WrapExample':  UnconstrainedBoxE
  ConstrainedBox CompareContainers TabLayoutExample'
### Tue 8 Nov
1) Study of Actions and intent usage. documented in flutter FTGE. Demo'd in zz_actions.
2) Study of DebugFieldProperties in FTGE Debug.

### Thur 3 Nov
##### Project zz_firebase
Implementing simple Firebase flutter.

__Checkout:__ flutter_flow package. What's it for?


### Mon Oct 31


##### Project zz_places
Exploration of the Googlemaps Places api
uses both inbuilt serchbar and custom widget typeahead. callling the results using http request
the blocs and repo code will be abtracted into a library for generic for future use with other projects



2. #### Things and tips
   1. __Completer__ in Futures
   2. __Zero space widget__: Empty space Widget use  with no measure ``SizedBox()``.
   3. __Spacer()__: Create a space between Widgets use ``Spacer()``.
   5. __Setting relative widget dimensions__:to its parent, use Positioned widget :-


         Positioned (
            top: 10,
            left: 0,
            right: 0,
            height: 55,
            child: SomeWidget()
         )
          
      
2. __Using Builder()__ widget to ensure the context including any ``Providers`` are propogated down the widget tree. adding a blocklistener can also help.

