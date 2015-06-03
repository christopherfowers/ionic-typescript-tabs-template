# Tabs Template

An application using Apache Cordova, Ionic Framework, and Typescript. Currently supporting iOS and Android.

## Requirements
 1. [node.js 0.10.33](http://nodejs.org/dist/v0.10.33/)
 2. Cordova and Ionic - ```$ [sudo] npm install -g cordova ionic```
 3. TypeScript 1.4 - ```$ [sudo] npm install -g typescript ```
     1. If in windows, download [typescript 1.4](http://www.typescriptlang.org/#Download)
 4. Gulp - ```$ [sudo] npm install -g gulp```
 5. Bower - ```$ [sudo] npm install -g bower```

## Tools
 1. [WebStorm](https://www.jetbrains.com/webstorm/)
 2. [SourceTree](https://www.atlassian.com/software/sourcetree/overview)
 3. [Invision](http://www.invisionapp.com/)
 4. [Sketch](http://bohemiancoding.com/sketch/)


## How to update Ionic Framework
1. ```$ [sudo] npm install ionic -g```
2. Change bower.json to latest version: "ionic": "driftyco/ionic-bower#master"
3. ```$ bower update```
4. (```$ ionic lib update```) might also work

##Adding Crosswalk
```$ ionic browser add crosswalk```

###Set up
1. Navigate via the terminal (or cmd) to the root directory
2. ```$ [sudo] npm install``` (Installs dependencies)
3. ```$ ionic state reset``` (Removes all plugins, if any, and re-adds them.  Grabs list from package.json)
4. ```$ gulp tsc``` (Compiles typescript)
5. ```$ ionic serve [--lab]``` (Serves app in a node instance)

####Architecture
 - The architecture of this template is a modified MVC framework. All application code is contained in the /www/app folder.
 - Models are placed in a models folder (e.g. /www/app/models/). 
 - Views and Controllers are placed in their own folder together (e.g. /www/app/playlist/). 
 - Services are placed in the common folder (e.g. /www/app/common/).  
 - Main app views, models, and controller are just placed in the /www/app/ folder (e.g. /www/app/app-controller.ts).

####Extras
 - When adding a plugin, make sure to use ````ionic plugin add <plugin>```` rather than ````cordova plugin add <plugin>```` in order to ensure that the plugin is added to the package.json.
 - To add a plugin without saving it to the package.json, add the --nosave argument to the add plugin command (e.g. ````$ ionic plugin add <plugin> --nosave ````)
 - [Install tsd](https://github.com/DefinitelyTyped/tsd)
  - ````$[sudo] npm install tsd@next -g````
  - Use tsd
    - ````$ cd www/app````
    - ````$ tsd init````(this creates the typings folder and the tsd.json file
  - Installing the packages
    - ````$ tsd install angular cordova-ionic cordova --save --resolve````