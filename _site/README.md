#How to

###Setup
#####--1-- Set up jekyll folders 
`$ jekyll new .`

#####--2-- npm init 
```sh 
#  
$ npm install
$ npm install --save-dev gulp gulp-shell browser-sync
```

#####--3-- create & configure gulp 
in `gulpfile.js`
```js
import gulp...
import shell...
import browserSync...

gulp.task('build', function(){
  shell.task([
    'jekyll build --watch'
  ])
})

gulp.task('serve',function(){
    browserSync.init({
      server: {
        baseDir: '_site/'
      }
    })

    gulp
      .watch('_site/**/*.*')
      .on('change', function(){
        browserSync.reload()
      })
})

gulp.task('dev', ['build', 'serve'])

```

in `_config.yml`
```
exclude: [node_modules, gulpfile.js]
```

#####--4-- configure `_config.yml`
```
exclude: [node_modules, gulpfile.js]
```


#####--4-- bower install bootstrap `_config.yml`
