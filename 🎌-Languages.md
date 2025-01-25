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

## Localizing Dates
To use translated names of months and days of the week, simply add:

```toml
[params]
localizedDates = true
```
