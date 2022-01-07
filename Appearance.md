# Prefer Dark Theme

You can easily enable the dark mode from the `config.toml` all you have to do is to set the parameter `displayMode` to `dark`. If you don't specify any displayMode, then the light version will be loaded.

Please also note that returning visitors will see the theme that was last displayed to them on your site. If your user has his system configured to dark mode, then this will also take precedence over the `displayMode` set in the `config.toml`.

```toml
[params]
displayMode = "dark"
```

# Disable Theme Switcher

You can easily disable the theme switcher from the `config.toml`. All you have to do is to set the parameter `disableThemeSwitcher` to `true`.

```toml
[params]
disableThemeSwitcher = true # Theme switcher is enabled by default
```

# Disable Animations

You can easily disable the animations from the `config.toml`. All you have to do is to set the parameter `doNotLoadAnimations` to `true`.

```toml
[params]
doNotLoadAnimations = true # Animations are loaded by default
```

# Control the Date Format

You can change the default date formatting for the `list.html`, the `single.html` and the `index.html`. Simply configure the matching parameters.

```toml
[params]
singleDateFormat = "Mon, Jan 2, 2006"
indexDateFormat = "Mon, Jan 2, 2006"
listDateFormat = "Jan 2"
```