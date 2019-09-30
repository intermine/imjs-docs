# ABOUT
This library abstracts the functionality of InterMine's web service layer. It is meant for those wishing to build in communication layers to intermine servers, build graphical widgets on top of the webservice APIs, or perform client side scripting.

The purpose of this library is to expose a uniform interface to the web-service API for both node.js and browser based programming, wrapping some of the minor unpleasantness of dealing with raw HTTP requests, as well as the more major issue of dealing with the path-query format, which is complex.

# INSTALLING

## Prerequisites
 - Node.js (preferrably 6.10.2 or greater) (assuming you want to build from latest source or contribute)

### Using NPM
Assuming that Node.js is already installed, run `npm init` to create `package.json` for your application in the valid directory, in case it is not already created. Make sure that your current working directory is the same containing `package.json`, and run the following command. It adds `imjs` to the dependency list.
```
npm install imjs --save
```
To import the library and use it in the script files, add the following line of code at the top of the file, along with other imports (if any).
```javascript
const intermine = require('imjs');
```

### Using CDN
Add the following `script` tag to the HTML file before using any of the `imjs` functionality.
```
<script src="https://cdn.rawgit.com/intermine/CDN/feb5bb77/js/intermine/imjs/3.15.0/im.js"></script>

<!-- For the minified version-->
<script src="https://cdn.rawgit.com/intermine/CDN/feb5bb77/js/intermine/imjs/3.15.0/im.min.js"></script>

<!-- The library and its functionality will be imported as the global variable, imjs-->
```


### Building from the source
_NOTE: Use this only if you are sure of what you are doing. Latest version of imjs might not be always stable._
```
$ git clone https://github.com/intermine/imjs
$ cd imjs
$ npm install
$ grunt build
```
The files would be present in `dist/`.
(NOTE: In case `grunt` is not found, make sure to install `grunt` and `grunt-cli` globally using `npm install -g grunt grunt-cli`).
