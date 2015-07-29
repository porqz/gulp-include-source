# gulp-include-source

Gulp plugin to include scripts, styles and favicons into your HTML files automatically.



## Install

Install with [npm](https://npmjs.org/package/gulp-ngmin)

```
npm install porqz/gulp-include-source --save-dev
```



## Example

#### gulpfile.js

```js
gulp.task('html', function() {
    return gulp.src('./client/index.html')
        .pipe(includeSources({ baseUrl: 'http://localhost:3000/assets' }))
        .pipe(gulp.dest('./build/'));
});
```

#### index.html

```html
<html>
<head>
    <!-- include:favicon(img/favicon.ico) -->
    <!-- include:css(style/**/*.css) -->
</head>
<body>
    <!-- include:js(list:vendorList) -->
    <!-- include:js(script/**/*.js) -->
</body>
</html>
```

#### scriptList

```
bower_components/jquery/dist/jquery.js
bower_components/angular/angular.js
```

#### Result:

```html
<html>
<head>
    <link rel="icon" type="image/x-icon" href="http://localhost:3000/assets/img/favicon.ico">
    <link rel="stylesheet" href="http://localhost:3000/assets/style/main.css">
</head>
<body>
    <script src="http://localhost:3000/assets/bower_components/jquery/dist/jquery.js"></script>
    <script src="http://localhost:3000/assets/bower_components/angular/angular.js"></script>
    <script src="http://localhost:3000/assets/app.js"></script>
    <script src="http://localhost:3000/assets/controllers/LoginController.js"></script>
    <script src="http://localhost:3000/assets/controllers/MainController.js"></script>
    <script src="http://localhost:3000/assets/services/LoginService.js"></script>
</body>
</html>
```



## API

### includeSources(options)

#### options.cwd

Type: `String`

Base directory from where the plugin will search for source files.

#### options.baseUrl

Type: `String`

URL which the plugin will prefix to paths.

#### options.scriptExt

Type: `String`

When available, will override script extension in resulted HTML code.

#### options.styleExt

Type: `String`

When available, will override style extension in resulted HTML code.

#### options.faviconExt

Type: `String`

When available, will override favicon extension in resulted HTML code.



## License

MIT © [André Gil](http://somepixels.net)