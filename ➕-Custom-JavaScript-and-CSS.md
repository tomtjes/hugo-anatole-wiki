## Adding Custom CSS

You can add your custom CSS files with the `customCss` parameter of the configuration file. Put your files into the `assets/css` directory.

```toml
customCss = ["css/custom.css", "css/styles.css"]
```

On the user-side, it will look like this:

```text
.
└── assets
    └── css
        ├── custom.css
        └── styles.css
```

## Adding Custom JavaScript

You can add your custom JS files with the `customJs` parameter of the configuration file. Put your files into the `assets/js` directory.

```toml
[params]
customJs = ["js/hello.js", "js/world.js"]
```

On the user-side, it will look like this:

```text
.
└── assets
    └── js
        ├── hello.js
        └── world.js
```

`hello.js` and `world.js` will be bundled into a `custom.min.js`.

You can also include links to remote javascript files (hosted on CDNs for example). But be aware that integrity settings and minification won't be applied. Further, make sure to adjust your CSP. You can load a remote script like this:

```toml
[params]
customJs = ["http://cdn.exmple.org/fancyscript.js"]
```

Both approaches can even be mixed:

```toml
[params]
customJs = ["https://cdn.exmple.org/fancyscript.js", "js/world.js"]
```