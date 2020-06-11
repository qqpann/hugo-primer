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
git clone https://github.com/qqhann/hugo-primer.git themes/hugo-primer

hugo server --theme=hugo-primer
```

## Usage

### exampleSite

You can refer to `exampleSite/` to get started.
Reading `exampleSite/_index.md` is good too.

For a quick start:

```sh
cp -av themes/hugo-primer/exampleSite/* .
```

### Customizing

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
# You can use favicon by adding `favicon-64.png` to `static` directory.
# You can also add `apple-touch-icon.png` and `pinned-icon.svg`.  
useIcon = true
useTwitterCard = true
# Use MathJax.js. Disabling site-wide and you still can enable in indivisual pages
math = true

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

#### page-level params

hugo-primer also comes with some custom page level parameters

- __showDate__ (default: __true__)  
shows the date on a post

- __comments__ (default: __true__)  
setting to false will hide disqus comments

- __toc__ (default: __true__)  
display the table of contents

- __categories__ (default: __an empty list__)  
a list of categories to display in the sidebar

- __tags__ (default: __an empty list__)  
a list of tags to display in the sidebar

- __math__ (default: __false__)  
If math.js is disabled for the site you can use this setting to enable it for a single page

- __keywords__ (default: __an empty list__)  
This adds a metatag to the page for listing keywords. This can be useful for SEO. 


Example usage where the defaults are overridden:

```md
---
showdate: false
comments: false
toc: false
categories:
- Diary
tags:
- Shopping
- Health
math: true
keywords:
- Cheese
- Milk
---
```


#### ruby annotation

[ruby annotation](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/ruby) allows you to show pronunciation of characters. Ruby in hugo-primer is like this:

![ruby](https://github.com/qqhann/hugo-primer/blob/master/images/ruby.png)

You just need one line shortcodes code:

```html
{{< ruby rb="深表遗憾" rt="Xi Wen Le Jian" >}}

{{< ruby rb="My heart is broken." rt="I'm happy for that." >}}
```

## Contributing

Issues and PRs are welcome. :)

## License

MIT
