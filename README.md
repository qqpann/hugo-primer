# Hugo-Primer

**A simple and beautiful Hugo theme based on GitHub's Primer CSS** | **[日本語記事](https://qqhann.dev/blog/theer-stroy/)**

This theme would be a perfect fit if you are used to GitHub style pages.  
Hugo-Primer is a theme based on GitHub style css: Primer, and adds some blog like features onto it.

Try it now, and leave me a star if you like it!

![screenshot](https://github.com/qqhann/hugo-primer/blob/master/images/screenshot.png)

## Features
- [x] Primer css like theme
- [x] Menu bar header
- [x] Colored code pen
- [x] Math inline
- [x] Awesome TOC
- [x] Tags & Categories
- [x] Social Share buttons

## Installation
Clone to your theme directory:
```terminal
$ git clone https://github.com/qqhann/hugo-primer.git themes/hugo-primer

$ hugo server --theme=hugo-primer
```

## Usage

#### config.toml
You can configure Hugo-Primer behavior with these params in your blog's `config.toml`. Shown are defaults and most recommended configs.
```config.toml
# config.toml

hasCJKLanguage = true
# Code pen
pygmentsCodeFences = true
pygmentsUseClasses = true

# Enter a copyright notice to display in the site footer.
# To display a copyright symbol, type `&copy;`.
copyright = ""

[params]
# Chose Social Sharing Buttons you want to use.
shareTo = ["Twitter", "Hatena", "Facebook", "Pocket"]
# You may disable copyright sentence by setting this to false.
showFooterCredits = true
```

That being said, below is all recommended configuration example.
```config.toml
# config.toml

baseURL = "https://your_web_site"
title = "Your Blog"
theme = "hugo-primer"
languageCode = "ja"
# If you are using Chinese, Japanese, or Korean, I highly recommend you to set this true.
hasCJKLanguage = true
summaryLength = 70
# Code pen
pygmentsCodeFences = true
pygmentsUseClasses = true
googleAnalytics = "U-12345678-0"

# Enter a copyright notice to display in the site footer.
# To display a copyright symbol, type `&copy;`.
copyright = "&copy;Your Name 2019"

[frontmatter]
# update sitemap.xml's lastmod datetime by file change time, instead of git.
lastmod = ["lastmod", ":fileModTime", ":default"]

[params]
description = "Describe what your web page is about"
twitter = "your_twitter_id"
# You can use favicon by addin them manually.
useIcon = true
useTwitterCard = true

shareTo = ["Twitter", "Hatena", "Facebook", "Pocket"]
showFooterCredits = true
```

#### archetypes/default.md
It is also recommended to remove your site's `archetypes/default.md`, or copy Hugo-Primer's `archetypes/default.md` to your site.
```archetypes/default.md
---
title: "{{ replace .Name "-" " " | title }}"
date: {{ .Date }}
draft: true
categories:
tags:
keywords:
---
```

Example usage:
```
---
categories:
- Diary
tags:
- Shopping
- Health
---
```
Set keywords for seo.

#### ruby annotation

[ruby annotation](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/ruby) allows you to show pronunciation of characters. Ruby in hugo-primer is like this:

![ruby](/images/ruby.png)

You just need one line shortcodes code:

```
{{< ruby rb="深表遗憾" rt="Xi Wen Le Jian" >}}

{{< ruby rb="My heart is broken." rt="I'm happy for that." >}}
```

## Contributing
Issues and PRs are welcome. :)

## License
MIT
