### Scaffold

#### Uses

 add a lot of functionality.

- Text
- body 
- topbar
- BottomNavigationBar
- floating action button
- snackbar
- drawer

 

#### BottomNavigationBar
```
return Scaffold(
      floatingActionButtonLocation: _location,
      bottomNavigationBar: BottomAppBar(
        shape: _notch ? const CircularNotchedRectangle() : null ,
       color: Colors.blue,
        child: Row(
          children: [
            IconButton(onPressed: ()=> null, icon: Icon(Icons.menu)),
            if (_location == FloatingActionButtonLocation.centerDocked) const Spacer(),
            IconButton(onPressed: ()=> null, icon: Icon(Icons.search)),
            IconButton(onPressed: ()=> null, icon: Icon(Icons.favorite)),

          ],
        ),
      ) ,
```

