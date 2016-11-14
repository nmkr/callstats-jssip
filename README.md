# callstats-jssip

[JsSIP](http://jssip.net) interface to [callstats.io](http://callstats.io/).


## Install

_TODO:_ NPM/Bower libraries must be published to the NPM/Bower registries by callstats.io once they own this project.

* Using NPM: `$ npm install callstats-jssip`
* Using Bower: `$ bower install callstats-jssip`
* Adding a `<script>` tag in the HTML.

When using Bower or a `<script>` tag, the provided library is built with [browserify](http://browserify.org), which means that it can be used with any kind of JavaScript module loader system (AMD, CommonJS, etc) or, in case no module loaded is used, a global `window.callstatsjssip` is exposed.

_NOTE:_ This library does not include the **callstats.io** library (it must be added separetely).


## Documentation

* Read the full [documentation](docs/index.md) in the docs folder.


## Usage example

In the HTML:

```html
<!DOCTYPE html>
<html>
  <head>
    <!-- Load callstats.io library (it provides window.callstats -->
    <script src="https://api.callstats.io/static/callstats.min.js"></script>
    <!-- Load JsSIP library -->
    <script src="js/jssip.js"></script>
    <!-- Load callstats-jssip library (it provides window.callstatsjssip) -->
    <script src="js/callstats-jssip.js"></script>
    <!-- Load our app code -->
    <script src="js/app.js"></script>
  </head>

  <body>
    <!-- your stuff -->
  </body>
</html>
```

In `app.js`:

```javascript
// Create a JsSIP.UA instance
var ua = new JsSIP.UA(config);

// Run it
ua.start();

// Run the callstats-jssip library for this UA
callstatsjssip(ua, AppID, AppSecret);
```


## Development

Install NPM development dependencies:

```bash
$ npm install
```

Install `gulp-cli` globally (which provides the `gulp` command):

```bash
$ npm install -g gulpjs
```

* `gulp prod` generates a production/minified `dist/callstats-jssip.min.js` bundle.
* `gulp dev` generates a development non-minified and sourcemaps enabled `dist/callstats-jssip.js` bundle.


## Author

Iñaki Baz Castillo at Nimble Ape LTD (https://nimblea.pe).
