# 💅 Appearance
## Prefering the Dark Theme

You can easily enable the dark mode from the `config.toml` all you have to do is to set the parameter `displayMode` to `dark`. If you don't specify any `displayMode`, then the light version will be loaded.

Please also note that returning visitors will see the theme that was last displayed to them on your site. If your user has his system configured to dark mode, then this will also take precedence over the `displayMode` set in the `config.toml`.

```toml
[params]
displayMode = "dark"
```

## Disabling the Ligh/Dark Mode Switch

You can easily disable the theme switcher from the `config.toml`. All you have to do is to set the parameter `disableThemeSwitcher` to `true`.

```toml
[params]
disableThemeSwitcher = true # Theme switcher is enabled by default
```

## Disabling Animations

You can easily disable the animations from the `config.toml`. All you have to do is to set the parameter `doNotLoadAnimations` to `true`.

```toml
[params]
doNotLoadAnimations = true # Animations are loaded by default
```

## Disabling Medium Like Zoom for Images

Enabled by default, the medium like zoom for images can be disabled by adding the following config under `[params]`.

```toml
[params]
enableMediumZoom = false
```

## Adjusting the Sidebar/Content Ratio

By default, the content fills up 60% of the screen width on devices with a full HD resolution. If you want to change the ratio, adjust the `contentratio` variable. Let's, for example, set the content ratio to 70%:

```toml
[params]
contentratio = 0.7
```


## Enabling the Syntax Highlighting

This theme has support for Hugo's lightning-fast Chroma code highlighting. See the [Hugo docs](https://gohugo.io/content-management/syntax-highlighting/) for more information.

To enable Chroma, add the following to your site parameters:

```toml
pygmentsCodeFences = true
pygmentsUseClasses = true
```

Then, you can generate a different style by running:

```shell
hugo gen chromastyles --style=monokailight > assets/css/syntax.css
```

If you get any errors, make sure the `assets/css/` directory exists within your sites root folder.
Include the newly generated `syntax.css` like a standard custom CSS script:

```toml
[params]
customCss = ["css/syntax.css"]
```

## Modifying the Date and Time Format
You can change the default date formatting for the `list.html`, the `single.html` and the `index.html`. Simply configure the matching parameters.

```toml
[params]
singleDateFormat = "Mon, Jan 2, 2006"
indexDateFormat = "Mon, Jan 2, 2006"
listDateFormat = "Jan 2"
```