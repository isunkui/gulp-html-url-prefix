<!-- [![NPM version][npm-img]][npm-url]
[![Build status][travis-img]][travis-url]
[![Test coverage][coveralls-img]][coveralls-url]
[![License][license-img]][license-url]
[![Dependency status][david-img]][david-url] -->

### gulp-html-url-prefix
a plugin of gulp for cdn prefix or suffix version url

### install
```bash
npm i @isunkui/gulp-html-url-prefix-suffix -D
```

### options

* options - type: `object`
  - prefix: `String`, default ` `
  - suffix: `Boolean`, default `false`
  - attrdata: `Array`, default `["img:src", "img:srcset", "img:s-src", "img:data-src", "script:src", "link:href"]`

```js
urlPrefix({
  prefix: '//cdn.xxx.com'
})
```

### example

index.html
```html
<!DOCTYPE html>
<html>
  <head>
    <link href="./css/example.css" />
  </head>
  <body>
    <img src="./example.jpg" />
    <script type="text/javascript" src="./js/example.js"></script>
  </body>
</html>
```

gulpfile.js
```js
var urlPrefix = require('gulp-html-url-prefix'),
  gulp = require('gulp');

gulp.task('url', function() {
  gulp.src(['index.html'])
    .pipe(urlPrefix({
      prefix: '//cdn.xxx.com',
      suffix: true, // url末尾追加 ?v=1545376218218
      attrdata: ["img:src", "img:srcset", "img:s-src", "img:data-src", "script:src", "link:href"]  //自定义标签属性
    }))
    .pipe(gulp.dest('./'));
});
```

and the result is:
```html
<!DOCTYPE html>
<html>
  <head>
    <link href="//cdn.xxx.com/css/example.css?v=1545376218218" />
  </head>
  <body>
    <img src="//cdn.xxx.com/example.jpg?v=1545376218218" />
    <script type="text/javascript" src="//cdn.xxx.com/js/example.js?v=1545376218218"></script>
  </body>
</html>
```


### License
MIT
<!-- 
[npm-img]: https://img.shields.io/npm/v/gulp-file-include.svg?style=flat-square
[npm-url]: https://npmjs.org/package/gulp-file-include
[travis-img]: https://img.shields.io/travis/coderhaoxin/gulp-file-include.svg?style=flat-square
[travis-url]: https://travis-ci.org/coderhaoxin/gulp-file-include
[coveralls-img]: https://img.shields.io/coveralls/coderhaoxin/gulp-file-include.svg?style=flat-square
[coveralls-url]: https://coveralls.io/r/coderhaoxin/gulp-file-include?branch=master
[license-img]: http://img.shields.io/badge/license-MIT-green.svg?style=flat-square
[license-url]: http://opensource.org/licenses/MIT
[david-img]: https://img.shields.io/david/coderhaoxin/gulp-file-include.svg?style=flat-square
[david-url]: https://david-dm.org/coderhaoxin/gulp-file-include
[gitter-img]: https://badges.gitter.im/Join%20Chat.svg
[gitter-url]: https://gitter.im/coderhaoxin/gulp-file-include?utm_source=badge&utm_medium=badge&utm_campaign=pr-badge
 -->