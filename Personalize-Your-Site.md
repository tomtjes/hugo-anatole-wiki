# Custom Content
## Profile Picture and Slogan

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

## Favicon

Add your favicons to `static/favicons`. Anatole currently employs following favicon files:

- `favicon.ico`
- `favicon-16x16.png`
- `favicon-32x32.png`
- `apple-touch-icon.png` (resolution should be 180x180)

## Copyright

By default, the copyright will show the authors name followed by the current year, but you can change this by configuring the `copyright` parameter. If this method is used, the string `{{ YEAR }}` will be replaced with the current year during site generation.

```toml
copyright = "2020-{{ YEAR }}"
```

# Navigation Items

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