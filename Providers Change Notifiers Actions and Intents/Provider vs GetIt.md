## Providers vs GetIt

Provider as an alternative to GetIt
The provider is a powerful alternative to GetIt. But there are some reasons why people use GetIt for Dependency injection:

Provider needs a BuildContext to access the registered objects, so you can’t use it inside business objects outside the Widget tree or in a pure dart package.
The provider adds its own Widget classes to the widget tree without GUI elements needed to access the in Provider registered objects.
