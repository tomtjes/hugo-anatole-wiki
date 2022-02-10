Welcome to the anatole wiki!

# Setting up the Anatole theme
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
2. Set the theme in your `config.toml` to anatole.

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

***

# First Steps
## Setting up a Profile Picture and Slogan
Ìn this section, I'll discuss the custom parameters available within the `config.toml`. The complete [sample](https://github.com/lxndrblz/anatole/tree/master/exampleSite/config/_default) can be found in the exampleSite folder.

```toml
[params]
title = "I'm Jane Doe"
author = "Jane Doe"
description = "Call me Jane"
profilePicture = "images/profile.jpg"
```

Please note that the title under the `[params]` only adjusts the page title in the sidebar. If you wish to adjust the HTML title (i.e. name of the tab), you will have to adjust the Hugo's title variable, as shown in the `config.toml`.

Please note that the slogan can be multi-lined (note the three quotes at the beginning and end):

```toml
[params]
description = """
Call me Jane
Blogging from Texas
"""
```

## Setting up a Social Icons in the Sidebar
You can add social media based icon links under your profile picture by using the `socialIcons` parameter.

[Font Awesome](https://fontawesome.com/) is used for the icons.

If you are using brand icons, prefix the icon value with `fab` if you are using a standard icon use `fas` instead.

Ordering in the `config.toml` will determine the display order on the webpage.

Sample branded social entry:

```toml
[[params.socialIcons]]
icon = "fab fa-linkedin"
title = "Linkedin"
url = "https://de.linkedin.com/"
```

Sample standard social entry:

```toml
[[params.socialIcons]]
icon = "fas fa-envelope"
title = "e-mail"
url = "mailto:mail@example.com"
```
## Setting up a Favicon

Add your favicons to `static/favicons`. Anatole currently employs following favicon files:

- `favicon.ico`
- `favicon-16x16.png`
- `favicon-32x32.png`
- `apple-touch-icon.png` (resolution should be 180x180)

## Setting up Copyright information

By default, the copyright will show the authors name followed by the current year, but you can change this by configuring the `copyright` parameter. If this method is used, the string `{{ YEAR }}` will be replaced with the current year during site generation.

```toml
copyright = "2020-{{ YEAR }}"
```

## Setting up Navigation Items

Non-content entries can be added right from the `config.toml` file.

```toml
[menu]

  [[menu.main]]
  name = "Home"
  identifier = "home"
  weight = 100
  url = "/"

  [[menu.main]]
  name = "Posts"
  weight = 200
  identifier = "posts"
  url = "/post/"

  [[menu.main]]
  name = "About"
  weight = 300
  identifier = "about"
  url = "/about/"
```
## Setting up a Portfolio
You can create an optional portfolio page that allows showcasing recent projects and publications. The entries within your portfolio are controlled by the `portfolio.yml` inside of your `data` folder. The `portfolio.yml` may look similar to the following structure:

```yaml
portfolioitems:
  # portfolio category
  - title: Coding Projects
    # items within a category
    portfolioitem:
      - name: Project 1
        image: '/images/portfolio/code.jpg'
        link: https://gohugo.io/
        description: 'Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat.'
        tags:
          - Tag 1
          - Tag 2
        status: 'Finished'
        start: '2020'
        end: '2021'
        authors:
          - Author 1
          - Author 2
```

Please note that fields such as start, end, authors, and tags will only appear if they have been populated. The image path defined under `image` parameter is relative to the static folder, similarly to images included in the post.


