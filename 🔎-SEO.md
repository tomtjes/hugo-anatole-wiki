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