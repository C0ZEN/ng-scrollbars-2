# Readme

This is an Angularjs plugin wrapper of
[Malihu's custom content scrollbar by Manos Malihutsakis](http://manos.malihu.gr/jquery-custom-content-scroller/).
I needed an AngularJS scrollbar that worked well with a dark theme and was consistently styled across different browsers.
I found several Angular scrollbars listed below but in general the styling didn't fit or they were lacking
features.

Ultimately I found a [Stackoverflow post](http://stackoverflow.com/questions/21306853/using-a-directive-to-make-an-element-scrollable-in-angularjs) by JMaylin that inspired me to finish
the integration effort he/she started.

# Demo

[http://minhongrails.github.io/ng-scrollbars/](http://minhongrails.github.io/ng-scrollbars/)

# Usage

1. Add ng-scrollbars and its dependencies to your main file (index.html)

  you can download this by:
  * using bower and running `bower install ng-scrollbars`
  * Download the [production version][min] or the [development version][max].

  [min]: https://github.com/minhongrails/ng-scrollbars/blob/master/dist/scrollbars.js
  [max]: https://github.com/minhongrails/ng-scrollbars/blob/master/src/scrollbars.js

  In your web page:

  ```html
  <link rel="stylesheet" href="bower_components/malihu-custom-scrollbar-plugin/jquery.mCustomScrollbar.min.css" type="text/css"/>
  <script src="bower_components/jquery/dist/jquery.min.js"></script>
  <script src="bower_components/angular/angular.min.js"></script>
  <script src="bower_components/malihu-custom-scrollbar-plugin/jquery.mCustomScrollbar.concat.min.js"></script>
  <script src="bower_components/ng-scrollbars/dist/scrollbars.js"></script>
  ```

2. Set `ngScrollbars` as a dependency in your module
  ```javascript
  var app = angular.module('app', ['ngScrollbars'])
  ```

3. Add ng-scrollbar directive to any elements:
  ```html
  <div ng-scrollbar ng-scrollbars ng-scrollbars-config="config"> .... </div>
  ```

4. Specify the configuration as an object visible within the directive's scope:

For example, the 'config' object referenced in step 3 could be configured like the following:

	```javascript
	$scope.config = {
		autoHideScrollbar: false,
		theme: 'light',
		advanced:{
			updateOnContentResize: true
		},
			setHeight: 200,
			scrollInertia: 0
		}
	}
	```

Some system-wide settings, such as enabling the buttons, can also be set by configuring the
ScrollBarsProvider that's included in the ngScrollbars module as referenced in step 2:

	```javascript
	var app = angular.module('app', ['ngScrollbars'])
	app.config(function (ScrollBarsProvider) {
		ScrollBarsProvider.defaults = {
			scrollButtons: {
				enable: true //enable scrolling buttons by default
			},
			axis: 'yx' //enable 2 axis scrollbars by default
		};
	});
	```

All configuration options available to Malihu's scrollbar are available as directive
attributes or passed in through as a configuration object as described in step 4 above. See
[Malihu's page](http://manos.malihu.gr/jquery-custom-content-scroller/) for more details

# Other options

In my search for angularjs scrollbars, I also came across a few others:

* [Ng-scrollbar](https://github.com/asafdav/ng-scrollbar)
* [Angular-perfect-scrollbar](https://github.com/itsdrewmiller/angular-perfect-scrollbar)
* [ngTinyScrollbar](https://github.com/yads/ngTinyScrollbar)

# License

MIT 