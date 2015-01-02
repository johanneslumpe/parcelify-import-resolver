# parcelify-import-resolver

A parcelify transform, which allows you to import files using the node resolve algorithm.

# example

You have a parent module with a `_settings.scss` file and want to use those settings in a plugin for said module:

``` scss
@import "!resolve(parent-module/scss/_settings.scss)";

body {
  background: $main-color;
}
```

Without the resolver, this would fail, because sass cannot import the file. The resolver replaces the path with an absolute path in order to allow sass to load the file without issues.

# how to use

Just add the transformer to your `transforms` property in your `package.json`:

```
"transforms" : [ "parcelify-import-resolver"]
```

(Of course it will mainly make sense in combination with `sass-css-stream`. Make sure though that you load it _before_ `sass-css-stream`.)

Now you can import your dependencies using the `!resolve(path)` syntax.

# install

With [npm](https://npmjs.org) do:

```
npm install parcelify-import-resolver
```

# license

MIT
