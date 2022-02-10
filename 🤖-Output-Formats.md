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

