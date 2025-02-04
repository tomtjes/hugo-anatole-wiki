Welcome to the Anatole wiki!

# Setting Up The Anatole Theme
## Route 1 (Recommended): Use Theme as Hugo Module

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

## Route 2 (Traditional): Install Theme as Git Submodule

1. Add the repository into your Hugo Project repository as a submodule: `git submodule add https://github.com/lxndrblz/anatole.git themes/anatole`.
2. Set the theme in your `config.toml` to Anatole.

# Updating Your Anatole Installation

If you want to get the latest update of the `Anatole` theme, please follow the instructions below:

## Theme as Hugo Module

```shell
hugo mod get -u github.com/lxndrblz/anatole
```

## Theme as Git Submodule

```shell
git submodule update --remote --merge
```

***

# First Steps
## Setting up a Profile Picture and Slogan
In this section, I'll discuss the custom parameters available within the `config.toml`. The complete [sample](https://github.com/lxndrblz/anatole/tree/master/exampleSite/config/_default) can be found in the exampleSite folder.

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

## Setting up the Social Icons in the Sidebar
You can add social media icon under your profile picture by using the `socialIcons` parameter.

[Font Awesome](https://fontawesome.com/) is used for the icons.

If you are using brand icons, prefix the icon value with `fab`. If you are using a standard icon, use `fas` instead.

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

Add your favicons to `static/favicons`. Anatole currently employs the following favicon files:

- `favicon.ico`
- `favicon-16x16.png`
- `favicon-32x32.png`
- `apple-touch-icon.png` (resolution should be 180x180)

## Setting up the Navigation Items

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

You can also add a dropdown navigation with subitems by defining a `parent` property within your `config.toml` file. In the following example, Awards and Certifications would be a subitem of Accomplishments.

```toml
[[main]]
name = "Accomplishments"
weight = 500
identifier = "accomplishments"

[[main]]
name = "Awards"
weight = 510
identifier = "awards"
url = "/awards/"
parent = "accomplishments"

[[main]]
name = "Certifications"
weight = 520
identifier = "certifications"
url = "/certifications/"
parent = "accomplishments"
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

## Setting up the Copyright information

By default, the copyright will show the author's name followed by the current year, but you can change this by configuring the `copyright` parameter. If this method is used, the string `{{ YEAR }}` will be replaced with the current year during site generation.

```toml
copyright = "2020-{{ YEAR }}"
```


