# Create Template


### 1. Install Mason_cli
    > brew install mason
    > mason update

### 2. init
    > Mason init

### 3. Create Brick
create a templated directory in your project. Cd into it
and make a brick with the desired name.

    > mkdir templates
    > cd templates
    > mason new bricktemplate

the template layout should be as thus.

    |- templates
        |- bricktemplate
            |- __brick__
                |- Hello.md

        |- brick.yaml
        |- README.md


Once you create a new brick using the mason new command, make sure to add the new brick
in the __mason.yaml__ file. Let’s add our widget brick in the mason.yaml file.

        bricks:
            bricktemplate:
                path: ./_bricktemplate/

### 4. prepare a basic template

In the __brick__ directory

    > mkdir {{wname.lowercase()}}.dart

edit the file for an initial test

```
import 'package:flutter/cupertino.dart';
import 'package:flutter/material.dart';


class {{wname.pascalCase()}} extends StatelessWidget {
const wname.pascalCase() ({Key? key}) : super(key: key);

@override
Widget build(BuildContext context) {
return Container(child: Text('template'),);
}
}
```


### 5. get the template
  
        >  mason get


### 6 user the template

> mason make template_name -o ./dest/dir

### 7. Advanced template concepts.
#### 7.1 Conditional Template
in the template
````
{{#conditionVar}}
void doitMethod() {
const String  {{screenName}};
}
{{/conditionVar}}
````


in the brick.yaml declare the variable

```text
  conditionVar:
    type: boolean
    prompt: include doitMethod?
    default: false
```

















