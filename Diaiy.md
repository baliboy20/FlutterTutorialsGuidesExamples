

### Mon Oct 31

#### 1. Projects worked on
##### Project zz_places
Exploration of the Googlemaps Places api
uses both inbuilt serchbar and custom widget typeahead. callling the results using http request
the blocs and repo code will be abtracted into a library for generic for future use with other projects



2. ##### Things and tips
   1. Completer in Futures
   2. Empty space Widget use a SizedBox with no measure ``SizedBox()``.
   3. Create a space between Widgets use ``Spacer()``.
   5. To set size of widget in relation to its parent, use Positioned widget :-
      
      
         Positioned(
         //search input bar
         top: 10,
         left: 0,
         right: 0,
         height: 55,
         child: SomeWidget(
          
      
2. Using the ``Builder`` widget to ensure the context including any ``Providers`` are propogated down the widget tree.
