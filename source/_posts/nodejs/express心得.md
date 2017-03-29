---
title: express心得
date: 2017-03-29 20:35:16
tags:
- express 
- nodejs
category: nodejs
---
### pug语法是利器
express是nodejs的一套web开发框架,当我开始用jade开发的时候，很快喜欢上了她的简洁,精简的语法,发现以前的满屏混乱的标签居然可以忍受这么长时间，不能忍！
### typescript快速开发可维护的应用程序
这里使用gulp 来监听 src目录下的所有typescript文件,一旦发生改变就会自动编译,而我们还选择了用nodemon守护构建后的build目录下www.js文件

```js
var gulp = require("gulp");
var tsc = require("gulp-typescript-compiler");
var ts = require('gulp-typescript');
var nodemon = require("gulp-nodemon");
/** gulp-bootstrap  */

var gulp = require('gulp');


var tsProject = ts.createProject('tsconfig.json');

gulp.task("default", ["compile", "watch",
    "nodemon"
]);


gulp.task("watch", function () {

    return gulp.watch(["./src/**/*.ts"], ["compile"]);

});
gulp.task("watch-scss", () => {
    return gulp.watch(['./sass/**/*.scss', './sass/bootstrap-sass/assets/**/*.scss'], ['css', 'fonts']);
})

gulp.task("compile", function () {
    return gulp.src('src/**/*.ts')
        .pipe(tsProject())
        .pipe(gulp.dest('build'));

});

gulp.task("nodemon", function () {
    nodemon({
        script: "build/www",
        exec: ' set DEBUG=*,-not_this &node --debug ',
        env: {
            'NODE_ENV': 'production'
        }

    });
});




var config = {
    bootstrapDir: './sass/bootstrap-sass',
    publicDir: './public',
};

gulp.task('css', function () {
    return gulp.src('./sass/app.scss')
        .pipe(sass({
            includePaths: [config.bootstrapDir + '/assets/stylesheets'],
        }))
        .pipe(gulp.dest(config.publicDir + '/css'));
});
gulp.task('fonts', function () {
    return gulp.src(config.bootstrapDir + '/assets/fonts/**/*')
        .pipe(gulp.dest(config.publicDir + '/fonts'));
});
```
