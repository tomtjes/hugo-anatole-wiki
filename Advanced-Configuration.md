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
## Sidebar/Content Ratio

By default, the content fills up 60% of the screen width on devices with a full HD resolution. If you want to change the ratio, adjust the `contentratio` variable. Let's, for example, set the content ratio to 70%:

```toml
[params]
contentratio = 0.7
```

## Date and Time Format
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

# SEO
## Google Site Verification

To use Google Site Verification, add the following line:

```toml
[params]
googleSiteVerify = "ABCDEFGHIJKLMNOPQRSTUVWXYZ0123456789"
```

Replace the hash with the one Google provided you.

## Robots.txt

If you want Hugo to generate a robots.txt, you will have to set the `enableRobotsTXT` in the `config.toml` to `true`. By default, a robots.txt, which allows search engine crawlers to access to any page, will be generated. It will look like this:

```text
User-agent: *
```

If certain sites should be excluded from being accessed, you might want to setup a custom robots.txt file within your `static` folder of your site.
# Comments
## Disqus

No comment section is shown on the `single.html`, unless a Disqus code is specified in the `config.toml` file.

```toml
disqusShortname = "XXX"
```

## Utteranc.es

No comment section is shown on the `single.html` unless a `repo` is specified in the `config.toml` file. If uncertain how parameter to configure, check out the official [documentation](https://utteranc.es/).

```toml
[params.utterances]
repo = "githubuser/reponame"
issueTerm = "pathname"
theme= "preferred-color-scheme"
# label =
```

Two notes on the security of Utteranc.es

- If you are using a strict CSP, you'll have to add the domain to it.
- The script currently has no built-in integrity check due to limitations of [Utterances](https://github.com/utterance/utterances/issues/40).

## Commento

You can use [Commento](https://commento.io/) as an alternative to Disqus. All you need to do is to configure a `CommentoURL`:

```toml
[params]
CommentoURL = "https://commento.example.com/js/commento.js"
```

## Gitalk

No comment section is shown on the `single.html` unless a `repo` is specified in the `config.toml` file. If uncertain how parameter to configure, check out the official [documentation](https://github.com/gitalk/gitalk).

```toml
[params.gitalk]
clientID = "GitHub Application Client ID"
clientSecret = "GitHub Application Client Secret"
repo = "Repository name to store issues"
owner = "GitHub repo owner"
admin = "GitHub repo owner and collaborators, only these guys can initialize gitHub issues"
```

## Disable Comments Per Page

Comments can be disabled per page by setting `disableComments: true` on the pages [Front Matter](https://gohugo.io/content-management/front-matter/)