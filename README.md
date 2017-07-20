# file-rev-replace-webpack-plugin

实现给模板文件中引用`css`, `js`的资源添加版本号功能， 通过替换文件内容中的指定路径为webpack生成asset的文件路径来实现。

目前提供一下选项

```js
assetsDomain: '//test.domain.com/static', //
context: path.resolve(__dirname),
cwd: path.resolve(__dirname),
src: '**/*/*.pug',
exts: ['js', 'css', 'jpg', 'png', 'gif', 'jpeg', 'webp', 'svg', 'ico'],
dest: '../build/template',
devMode: process.env.NODE_ENV === 'production' ? false : true,
publicPath: '#{server_cdn_prefix}',
glob: { // 排除某些文件
    ignore: ['node_modules/**/*']
}
```
## bugs fixed

#### v0.0.2

* [add] 不需要long term cache时，判断逻辑不够完整

#### v0.0.3

* [add] 对于需要依靠server动态去设置cdn域名提供支持，通过添加`publicPath`选项来设置替换模板中的文件的替换的前缀，而不是去`output`中的`publicPath`
