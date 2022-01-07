# Appearance
## Prefer Dark Theme

You can easily enable the dark mode from the `config.toml` all you have to do is to set the parameter `displayMode` to `dark`. If you don't specify any displayMode, then the light version will be loaded.

Please also note that returning visitors will see the theme that was last displayed to them on your site. If your user has his system configured to dark mode, then this will also take precedence over the `displayMode` set in the `config.toml`.

```toml
[params]
displayMode = "dark"
```

## Disable Theme Switcher

You can easily disable the theme switcher from the `config.toml`. All you have to do is to set the parameter `disableThemeSwitcher` to `true`.

```toml
[params]
disableThemeSwitcher = true # Theme switcher is enabled by default
```

## Disable Animations

You can easily disable the animations from the `config.toml`. All you have to do is to set the parameter `doNotLoadAnimations` to `true`.

```toml
[params]
doNotLoadAnimations = true # Animations are loaded by default
```

## Control the Date Format

You can change the default date formatting for the `list.html`, the `single.html` and the `index.html`. Simply configure the matching parameters.

```toml
[params]
singleDateFormat = "Mon, Jan 2, 2006"
indexDateFormat = "Mon, Jan 2, 2006"
listDateFormat = "Jan 2"
```
# Analytics
## Google Analytics

To use Google Analytics, a valid tracking code has to be added. If you don't want to load the code, then commend out the parameter.

```toml
googleAnalytics = "UA-123-45"
```

To use the modern Google Analytics 4, include the following under `[params]`, replacing the id with your own.

```toml
[params]
gtagId = "G-XXXXXXXXXX"
```

## Simple Analytics

To use Simple Analytics, it has to be enabled by setting the parameter to true. If you are using a custom subdomain to evade Adblockers, then specify the URL without a trailing slash.

```toml
[params.simpleAnalytics]
enable = true
# customurl = "https://analytics.example.com"
```