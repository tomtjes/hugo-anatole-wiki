Welcome to the anatole wiki!

# Quickstart
## Route 1 (recommended): use theme as Hugo module

1. Install prerequisites [git](https://git-scm.com/downloads) and [go](https://go.dev/dl/) (>= 1.12)
2. Turn your Hugo Project into a Hugo module: `hugo mod init github.com/me/my-project`
3. Declare the `Anatole` module as a dependency of your site: `hugo mod get github.com/lxndrblz/anatole`
4. Add the following lines at the end of your `config.toml`:

```
[module]
  # uncomment line below for temporary local development of module
  # replacements = "github.com/lxndrblz/anatole -> ../../anatole"
  [[module.imports]]
    path = "github.com/lxndrblz/anatole"
    disable = false
```

## Route 2 (traditional): install theme as Git submodule

1. Add the repository into your Hugo Project repository as a submodule: `git submodule add https://github.com/lxndrblz/anatole.git themes/anatole`.

## Start up your site

1. Configure your `config.toml`. Feel free to copy the demo [`config.toml`](https://github.com/lxndrblz/anatole/blob/master/exampleSite/config/_default/config.toml) and some content from the [exampleSite](https://github.com/lxndrblz/anatole/tree/master/exampleSite).
2. Build your site with `hugo serve` and admire the result at [`http://localhost:1313/`](http://localhost:1313/).

# Update your installation

If you want to get the latest update of the `Anatole` theme, please follow the instructions below:

## Theme as Hugo module

```shell
hugo mod get -u github.com/lxndrblz/anatole
```

## Theme as Git submodule

```shell
git submodule update --remote --merge
```