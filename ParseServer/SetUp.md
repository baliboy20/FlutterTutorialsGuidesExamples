
### Resources
[Flutter and Parse](https://www.youtube.com/playlist?list=PL_lJrbgUtzde_SbjfOaSmHyUCIQ00mhim)



### Setup


``pubspec.yaml``
````

parse_server_sdk_flutter: ^3.1.3
````

````
main async (
const keyApplicationId = 'fZTnKcHmI10Bqv2avtNiRQzaxFotKVFMLTF9tR7i';
  const keyClientKey = 'xdcHhnASGBrlsGcbB205RMIcqF0cUEeQTv0NCUI9';
  const keyParseServerUrl = 'https://parseapi.back4app.com';
  
  await Parse().initialize(keyApplicationId, keyParseServerUrl, clientKey: keyClientKey, autoSendSessionId: true);
  
  runApp()
  ...
````

