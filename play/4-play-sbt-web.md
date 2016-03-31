# sbt-web

---

## sbt-web brings the notion of a highly configurable asset pipeline to build files

```scala
pipelineStages := Seq(rjs, digest, gzip)
```

- The above will order the RequireJs optimizer (sbt-rjs), the digester (sbt-digest) and then compression (sbt-gzip)
- These tasks will execute in the order declared, one after the other
- Tasks operate on source files, e.g, _LESS to CSS_, or operate on web assets, e.g, _gzip_.

---

# Folder layout

- _assets_ includes files to be processed, e.g, _LESS_ to _CSS_
- _public_ includes static assets
- _main_ and _test_ include the same structure

```
+ src
--+ main
----+ assets
------+ js
------+ css
----+ public
------+ css
------+ images
------+ js
```

---

# Asset pipelines[^1]

**Example asset pipeline:**

* Source file → 
* 1. Linting → 
* 2. Uglification/minification → 
* 3. Fingerprinting →
* 4. Concatenation (optional)

![right fit](https://dl.dropboxusercontent.com/u/14279899/Deckset/play_workshop/sbt-web-staging.png)

[^1]: Pipeline visualization from [http://www.mariussoutier.com/blog/2014/10/20/intro-sbt-web](http://www.mariussoutier.com/blog/2014/10/20/intro-sbt-web)

---

# Key terms

- **Linting** - Inspect source code for suspicious language usage
- **Uglification/minification** - Mangle and compress source files, e.g, remove whitespace, etc
- **Fingerprinting** - Change the filename to reflect the contents of the file for cache busting
- **Concatenation** - Combine multiple source files to reduce browser load times

---

# Asset fingerprinting

- Asset fingerprinting makes the name of a file dependent on the contents of the file
- HTTP headers can be set to encourage caches to keep their own copy of the content
- When the content is updated, the fingerprint will change
- This will cause the remote clients to request a new copy of the content
- Known as _cache busting_

---

# Asset fingerprinting

- Enabling asset fingerprinting requires one additional route

```
GET    /assets/*file  controllers.Assets.versioned(path="/public", file: Asset)
```

- Then request each asset as _versioned_

```html
<link rel='stylesheet' href='@routes.Assets.versioned("assets/images/example.png")'>
```

- A digest file and new file will be created based on MD5

```
./target/web/digest/images/23dcc403b263f262692ac58437104acf-example.png
./target/web/digest/images/example.png.md5
```

---

# sbt-web plugins

sbt-coffeescript, **sbt-concat**, sbt-css-compress, **sbt-digest**, sbt-filter, **sbt-gzip**, sbt-handlebars, sbt-html-minifier, sbt-imagemin, sbt-jshint, sbt-jst, sbt-less, sbt-mocha, sbt-purescript, sbt-reactjs, sbt-rjs, sbt-stylus, **sbt-uglify**
