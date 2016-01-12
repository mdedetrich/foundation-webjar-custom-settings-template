# Foundation Webjar Custom Settings Template

This is a Foundation Webjar Template based on https://github.com/webjars/foundation, however it has the ability to customize the foundation `_settings.scss`/`foundation.scss` file to produce a customized `foundation.css`.

Due to this, unlike the original Foundation Webjar this uses various maven plugins to build the package rather than just repacking assets.

# Directions

* Modify `input/_settings.scss` and `input/foundation.scss` to your liking.
* Modify the other attributes of `pom.xml` (i.e your organization,artifactId, foundation version, publish information etc)
* Publish/Install with `mvn publish` or `mvn install`

# Notes

* Uses [maven libsass](https://github.com/warmuuh/libsass-maven-plugin) to compile `.scss` sources. This is supported by foundation, however since it uses the dynamic compiled native library [libsass](http://sass-lang.com/libsass) it may not work on all platforms that Java works on. As of now, it only works with Linux x64, Windows x64 and MacOSX x64.
* Uses [yui-compressor](https://github.com/davidB/yuicompressor-maven-plugin) to compress js/css assets. Note that this may not be the same compressor used by foundation when they make their own release, however it shouldn't be an issue.
* The custom `_settings.scss` and `foundation.scss` is also copied into the `.jar`, so you can see the custom settings without needing to reference the source.
* This template uses Foundation `5.5.3`, however it should work with any other version of foundation. Note that if you change the version, you should copy the default `_settings.scss` and `foundation.scss` over from the version you are using.
* This follows the same templates that classic webjars follow, meaining you can use any webjar related tools with it
* The resulting output is made to mimic the [foundation webjar](https://github.com/webjars/foundation) as much as possible. The only notable difference is there is an extra `foundation.js` (the official version only has `foundation.min.js`). This was left in there for convenience. This means you should be able to replace the official foundation webjar with this one without any code changes.
  * Only exception is the altered `_settings.scss`/`foundation.scss`, these files will be in slightly different locations in the package compared to the original.
