# Appearance
## Prefer Dark Theme

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

## Sidebar/Content Ratio

By default, the content fills up 60% of the screen width on devices with a full HD resolution. If you want to change the ratio, adjust the `contentratio` variable. Let's, for example, set the content ratio to 70%:

```toml
[params]
contentratio = 0.7
```


## Syntax Highlighting

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

## Date and Time Format
You can change the default date formatting for the `list.html`, the `single.html` and the `index.html`. Simply configure the matching parameters.

```toml
[params]
singleDateFormat = "Mon, Jan 2, 2006"
indexDateFormat = "Mon, Jan 2, 2006"
listDateFormat = "Jan 2"
```
# Custom JavaScript and CSS
## Custom CSS

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

## Custom JavaScript

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
## Plausible Analytics

To use Plausible Analytics, include the following section and change the domain to your site's domain. If you self-host Plausible, you can optionally specify the URL of your instance.

```toml
[params.plausibleAnalytics]
domain = "example.com"
# serverURL = "https://analytics.example.com"
```
## Umami Analytics

To use Umami Analytics, include the following section and change the `serverURL` to your self-hosted Umami server URL. Additionally, you will need to provide your website ID.

```toml
[params.umami]
serverURL = "example.com"
id = "94db1cb1-74f4-4a40-ad6c-962362670409"
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

If certain sites should be excluded from being accessed, you might want to set up a custom robots.txt file within your `static` folder of your site.
# Comments
## Disqus

No comment section is shown on the `single.html` unless a Disqus code is specified in the `config.toml` file.

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

## Disabling Comments Per Page

Comments can be disabled per page by setting `disableComments: true` on the pages [Front Matter](https://gohugo.io/content-management/front-matter/)

# Content Settings

## Setting up Post Thumbnails

Thumbnails can be enabled easily by setting the `thumbnail` parameter in the frontmatter of a post to an image such as `"images/landscape.jpg"`.

```md
+++
...
tags = [
"thumbnail",
]
thumbnail= "images/landscape.jpg"
+++
```

Make sure to put the image in the `static/images/` directory.

## Using a Static Page as your Home Page

If you prefer having a static page as your home page rather than a listing of the latest posts, then make sure you leave the `mainSections` parameter blank:

```toml
[params]
  mainSections = []
```

Put any content into the `_index.md` file located in the content directory. If you want, you can also have some static text and the posts below. In such case, simply keep the `mainSections = ["post"]` and put any static content in the `_index.md`.

## Enabling Read-more Links

You can enable read-more links for truncated posts by setting the `readMore = true`. The length of the preview is controlled by Hugo's `summarylength`. Read-more links are disabled by default.

```toml
[params]
  readMore = true
```

## Renaming your Post Section

If you want to have a different post section identifier, such as `/blog`, you can specify the section name using `postSectionName`:

```toml
[params]
  postSectionName = "blog"
```

If the parameter is not set, it will default to `post`. Be sure to check the name of the folder containing your post files and change it accordingly in order for links to reflect the new post section name.

## Showing the Full Post Content on the Home Page

If you prefer the full content of your posts to appear on the home page rather than a summary of each post, then set the parameter `fullPostContent` to `true`.

```toml
[params]
fullPostContent = true
```

## Enabling Math Functions (Katex, Mathjax)

```toml
## Math settings
[params.math]
enable = false  # options: true, false. Enable math support globally, default: false. You can always enable math on per page.
use = "katex"  # options: "katex", "mathjax". default is "katex".
```

## Setting up External Redirect URLs

You can create pages which redirect to another (external) URL with a short delay. This can be useful for migrating previously indexed URLs, which no longer exist, or for communicating complex external URLs to your readers.

You will have to define a `redirectUrl` in the markdown header of the post or page, which you want to forward. An example can be found in the [redirect.md](https://github.com/lxndrblz/anatole/blob/master/exampleSite/content/english/post/redirect.md). The page will be automatically redirected with a delay of one second.

Additionally, you can include the `{{% loading %}}` shortcode, which will display a spinner on the page that will be redirected. If it does not display, make sure that unsafe mode is enabled for `markup.goldmark.renderer`.

## Adding a Table of Contents

You can enable a table of contents on a per post basis by adding the following parameter into the front matter of the posts you want the table of contents to appear on.

```md
+++
...
toc = true
+++
```

Please note that only "## H2 Headings" and "### H3 Headings" will appear in the table of contents.

## Post Series

You can enable series, which allows splitting up a considerable post into a set of multiple blog posts that are still linked. This would also provide a unique link to the full series of blog posts. Each individual post in the series will also contain links to the other parts under the heading `Posts in this Series`.

First, we need to enable the `series` taxonomy in the config.

```toml
[taxonomies]
    category = "categories"
    series = "series"
    tag = "tags"
```

With this enabled, we can now proceed to specify the series in the Front Matter of each post of that series.

```md
series: - series-name
```

If you want to share the full series, you can do so by sharing the link `<base-url>/series/<series-name>`

## Showing a Warning for outdated content

You can provide an outdated warning for viewers reading posts older than a certain number of days. This is useful if your posts have time-sensitive information that may become incorrect over time.

Enable the warning in the configuration and specify the duration (in days):

```toml
[params]
oldContentWarning = true
oldContentDuration = 365
```

You can optionally override the trigger duration on a given post by adding the following parameter in the front matter:

```md
+++
...
old_content_duration: 0
+++
```

A duration of 0 disables the warning.

By default, this warning only shows on posts. You can override this behavior by setting the `old_content_duration` parameter in the front matter of pages you want this warning to be displayed on.

## Adding Twitter Cards Information

In order to use the full functionality of Twitter cards, you will have to define a couple of settings in the `config.toml` and the frontmatter of a page.

In the `config.toml` you can configure a site feature image. This image will be displayed if no image is defined in the frontmatter of a page.

```toml
[params]
  images = ["images/site-feature-image.png"]
```

To define a custom image for a page, you will have to add the following to the frontmatter of a post.

```toml
images = ["images/post-cover.png"]
```

# Languages
## Multilingual Support

Anatole supports multilingual page setups. All you need to do is to add the languages to your 'config.toml'. For each language, you can set the custom options like title or description. It's important to include a `LanguageName` as it will be displayed in the main menu.

```toml
[Languages]
  [Languages.en]
  title = "My blog"
  weight = 1
  LanguageName = "EN"

  [Languages.de]
  title = "Mein blog"
  description = "Ich bin Jane"
  weight = 2
  LanguageName = "DE"
```

There are two ways of translating your content, either by adding a suffix in the filename, e.g. `mypost.de.md`, or by setting a contentDir (a certain directory) for each language. [Link to the Hugo documentation](https://gohugo.io/content-management/multilingual/). If you want to use the option with the `contentDir`, you will have to add the `contentDir` parameter for each language:

```toml
[languages]
  [languages.en]
    contentDir = "content/english"
    languageName = "EN"
    weight = 1
```

To make sure your menu is linking to the correct localized content, make sure that you customize the menu items to include the language prefix. Your menu might look like the following:

```toml
[[Languages.de.menu.main]]
url    = "/de/"
identifier = "home"
name   = "Startseite"
weight = 100

[[Languages.de.menu.main]]
name = "Beiträge"
weight = 200
identifier = "posts"
url = "/de/post/"

[[Languages.de.menu.main]]
name = "Über"
weight = 300
identifier = "about"
url = "/de/about/"
```

Anatole currently ships with support for some basic languages. Contributions for other language translations are welcome.

## RTL Support

Anatole supports RTL languages and flips the whole theme for that. To enable the RTL-mode for a specific language, it's enough to write the following code in the language params.

```toml
LanguageDirection = "rtl"
```

## Configuring the Language Names in the Language Switcher
The language names displayed on the main menu are controlled by the variables `LanguageName`. You can set these to shortcode, full name or a flag emoji by simply changing the parameter. In the following example, English will be displayed as "EN" and Arabic will be displayed as "Arabic".

```toml
[languages]
[en]
LanguageName = "EN"


[ar]
LanguageName = "Arabic"
```

# Contact Form
## Formspree

Step 1: Configure the `contactFormAction` in the `config.toml`

```toml
[params]
#contactFormAction = "https://formspree.io/f/your-form-hash-here"
```

Step 2: Activate the `contact: true` or `contact=true` in the frontmatter of a page. See `exampleSite/content/contact.html` as an example.

# Security
## Content Security Policy

The theme is compliant with the most strict CSP policies out of the box. A sample CSP for an Anatole-based site would look something like this:

```text
Content-Security-Policy "
  base-uri 'self';
  connect-src 'self';
  default-src 'self';
  frame-ancestors 'none';
  font-src 'self' cdnjs.cloudflare.com;
  img-src 'self';
  object-src 'none';
  script-src 'self';
  style-src 'self' cdnjs.cloudflare.com;
"
```

If you want to configure the security headers for a site running on Netlify, you want to make sure you create a special `_headers` file in your site's static folder. The content might look like the following:

```text
/*
  X-Frame-Options: DENY
  X-Clacks-Overhead: "GNU Terry Pratchett"
  X-XSS-Protection: 1; mode=block
  X-Content-Type-Options: nosniff
  Referrer-Policy: same-origin
  Content-Security-Policy:  base-uri 'self'; connect-src 'self'; default-src 'self'; frame-ancestors 'none'; font-src 'self' cdnjs.cloudflare.com; img-src 'self'; object-src 'none'; script-src 'self'; style-src 'self' cdnjs.cloudflare.com;
  Strict-Transport-Security: max-age=63072000; includeSubDomains; preload
```

# Output Formats
## RSS

Hugo natively supports RSS. To generate a feed for a given page, append `index.xml` to the page URL.

Note that the RSS feed at the base of your website will include all of the pages on your website. To only include posts in your RSS feed, generate the feed within the `posts/` subdirectory with the URL `posts/index.xml`.

To only generate an RSS feed for your posts, disable the RSS output for the other page types:

```toml
[outputs]
  home = ["HTML"]
  section = ["HTML", "RSS"]
  taxonomy = ["HTML"]
  term = ["HTML"]
```

By default, the RSS feed contains a brief summary of each page. If you prefer to show the entire contents for each page, then use the `rssFullContent` parameter:

```toml
[params]
rssFullContent = true
```

