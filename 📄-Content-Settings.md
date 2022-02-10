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
