npm install gulp --save-dev //gulp开发时需要创建的环境
npm install gulp-less --save-dev //glup-less编译创建的环境

npm install gulp-cssnano --save-dev//css压缩
npm install gulp-concat --save-dev//css，js合并
npm install gulp-uglify --save-dev//js合并压缩

npm install gulp-htmlmin --save-dev//html压缩




var gulp=require("gulp");//gulp
var less=require("gulp-less");//less编译
var cssmin=require("gulp-cssnano");//css压缩
var concat=require("gulp-concat");//合并
var htmlmin=require("gulp-htmlmin");//html压缩
var uglify=require("gulp-uglify");//js合并压缩

gulp.task("less",function(){
    gulp.src("src/css/*.*")
    .pipe(less())
    .pipe(cssmin())
    .pipe(gulp.dest("deit/css"));
});
gulp.task("html",function(){
    gulp.src("src/*.html")
    .pipe(htmlmin())
    .pipe(gulp.dest("deit/"));
});
gulp.task("uglify",function(){
    gulp.src("src/js/*.js")
    .pipe(uglify())
    .pipe(gulp.dest("deit/js"));
});
