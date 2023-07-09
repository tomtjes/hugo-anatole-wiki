## Adding Google Analytics

To use Google Analytics, a valid tracking code has to be added. If you don't want to load the code, then commend out the parameter.

```toml
googleAnalytics = "UA-123-45"
```

To use the modern Google Analytics 4, include the following under `[params]`, replacing the id with your own.

```toml
[params]
gtagId = "G-XXXXXXXXXX"
```

## Adding Simple Analytics

To use Simple Analytics, it has to be enabled by setting the parameter to true. If you are using a custom subdomain to evade Adblockers, then specify the URL without a trailing slash.

```toml
[params.simpleAnalytics]
enable = true
# customurl = "https://analytics.example.com"
```
## Adding Plausible Analytics

To use Plausible Analytics, include the following section and change the domain to your site's domain. If you self-host Plausible, you can optionally specify the URL of your instance.

```toml
[params.plausibleAnalytics]
domain = "example.com"
# serverURL = "https://analytics.example.com"
```
## Adding Umami Analytics

To use Umami Analytics, include the following section and change the `id` to the Website ID from Umami. If you self-host Umami, also change the `serverURL` and `tracerScriptName` to fit your installation.

```toml
[params.umami]
serverURL = "analytics.umami.is"
id = "94db1cb1-74f4-4a40-ad6c-962362670409"
trackerScriptName = "script.js"
```