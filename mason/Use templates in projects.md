# Use existing Bricks/ Templates


### 1. Install Mason_cli
    > brew install mason
    > mason update

### 2. init
Create a mason project files e.g. mason.yaml.
    > Mason init

### 3. Create Brick (new command)
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




### 4. Usinging existing bricks.
Once you create a new brick using the mason new command, make sure to add the new brick
in the __mason.yaml__ file. Let’s add our widget brick in the mason.yaml file.

        bricks:
            bricktemplate:
                path: ./_bricktemplate/

> ``> mason get``



### 5. Create from bricks

> ``> mason make bloc_template -c ./config.json -o lib/blocs --on-conflict overwrite``

### 6 . Getting update versions of brick
>  ``> mason update ``
