## Adding Disqus

No comment section is shown on the `single.html` unless a Disqus code is specified in the `config.toml` file.

```toml
disqusShortname = "XXX"
```

## Adding Utteranc.es

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

## Adding Commento

You can use [Commento](https://commento.io/) as an alternative to Disqus. All you need to do is to configure a `CommentoURL`:

```toml
[params]
CommentoURL = "https://commento.example.com/js/commento.js"
```

## Adding Gitalk

No comment section is shown on the `single.html` unless a `repo` is specified in the `config.toml` file. If uncertain how parameter to configure, check out the official [documentation](https://github.com/gitalk/gitalk).

```toml
[params.gitalk]
clientID = "GitHub Application Client ID"
clientSecret = "GitHub Application Client Secret"
repo = "Repository name to store issues"
owner = "GitHub repo owner"
admin = "GitHub repo owner and collaborators, only these guys can initialize gitHub issues"
```

## Adding Giscus
You can use [Giscus](https://giscus.app/) as an alternative to Disqus. You can set it up as follows:
```toml
[params.giscus]
repo = "githubuser/reponame"
repoID = "Github Repo ID"
category = "Discussions Category"
categoryID = "Discussions Category ID"
# <Optional Params>
# mapping = "pathname"
# strict = "0"
# reactionsEnabled = "1"
# emitMetadata = "0"
# inputPosition = "bottom"
# lang = "en"
# loading = "lazy"
```

## Disabling Comments Per Page

Comments can be disabled per page by setting `disableComments: true` on the pages [Front Matter](https://gohugo.io/content-management/front-matter/)