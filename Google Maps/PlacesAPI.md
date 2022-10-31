### Google Maps Places API

#### 1) Make sure api is setup in the google cloud console
#### 2) Initiate the Map
````
Expanded(
            flex: 1,
            child: GoogleMap(
              mapType: MapType.normal,
              onMapCreated: (GoogleMapController clr) =>
                  _controller.complete(clr),
              initialCameraPosition: SearchLocationWidget._initCameraPosition,
              markers: {
                Marker(
                    infoWindow: InfoWindow(title: 'Marker in one'),
                    markerId: MarkerId('mk1'),
                    position: LatLng(51.487959286430495, -0.11130227330012202))
              },
            ),
          )

````

inside the stateful widgets state class need to define a future for the
controller

``
Completer<GoogleMapController> _controller = Completer();
``
 #### 3) Create a Places Service

````
import 'dart:convert';
import 'dart:developer';
import 'dart:convert' as convert;
import 'package:flutter_polyline_points/flutter_polyline_points.dart';

import 'package:http/http.dart' as http;
final String key = "AIzaSyABjEoS3sOCrgtKIW94o9cxTfN_xvVtehQ";
class PlacesService {
Future<String> getPlaceId(String input) async {
String url =
'https://maps.googleapis.com/maps/api/place/findplacefromtext/json?input=$input&inputtype=textquery&key=$key';    try {
http.Response response = await http.get(Uri.parse(url));
var json = jsonDecode(response.body);
print('json__ ======>: $json');
dynamic placeId = json['candidates'][0]['place_id']  ?? "Not found";
log('placeid  ======>:  $placeId');
return placeId as String;
} catch ( e){
print('error!!!!!!! $e');
return 'error';
}
}
Future<Map<String, dynamic>> getPlace(String input) async {
final placeId = await getPlaceId(input);

    final String url =
        'https://maps.googleapis.com/maps/api/place/details/json?place_id=$placeId&key=$key';

    var response = await http.get(Uri.parse(url));
    var json = convert.jsonDecode(response.body);
    print('RESULTS $json');
    var results = json['result'] as Map<String, dynamic>;

    print(results);
    return results;
}

Future<Map<String, dynamic>> getDirections(
String origin, String destination) async {
final String url =
'https://maps.googleapis.com/maps/api/directions/json?origin=$origin&destination=$destination&key=$key';

    var response = await http.get(Uri.parse(url));
    var json = convert.jsonDecode(response.body);

    var results = {
      'bounds_ne': json['routes'][0]['bounds']['northeast'],
      'bounds_sw': json['routes'][0]['bounds']['southwest'],
      'start_location': json['routes'][0]['legs'][0]['start_location'],
      'end_location': json['routes'][0]['legs'][0]['end_location'],
      'polyline': json['routes'][0]['overview_polyline']['points'],
      'polyline_decoded': PolylinePoints()
          .decodePolyline(json['routes'][0]['overview_polyline']['points']),
    };
    
    return results;
}
}
````

#### 4) Call places from the Custom Map widget and reset the camera with the new coordinates.

````dart
IconButton(
icon: Icon(Icons.search),
onPressed:  () async
{
Map<String, dynamic> place = await PlacesService().getPlace(this._textEditingController.text);
_goToPlace(place);
},
),

````
and then call this private method inside the state class of the custom map widget.
````dart
   Future<void >_goToPlace( Map<String, dynamic> place) async {
  final double lat = place['geometry']['location']['lat'];
  final double lng = place['geometry']['location']['lng'];
  final GoogleMapController controller = await _controller.future;
  controller.animateCamera(
      CameraUpdate.newCameraPosition(
        CameraPosition(target: LatLng(lat, lng), zoom: 12),
      ));
}
````
