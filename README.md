### Tree vieuw

```
📦main
 ┣ 📂assets
 ┃ ┣ 📂css
 ┃ ┃ ┣ 📂core
 ┃ ┃ ┃ ┗ license.css
 ┃ ┃ ┣ 📂extended
 ┃ ┃ ┃ ┣ dracula.css
 ┃ ┃ ┃ ┣ pokey.css
 ┃ ┃ ┃ ┗ _main.css
 ┃ ┃ ┗ 📂includes
 ┃ ┃ ┃ ┗ scroll-bar.css
 ┃ ┗ 📂js
 ┃ ┃ ┗ license.js
 ┣ 📂content # contains post content
 ┣ 📂layouts
 ┃ ┣ 📂partials
 ┃ ┃ ┣ extend_footer.html
 ┃ ┃ ┗ extend_head.html
 ┃ ┣ 📂_default
 ┃ ┃ ┗ list.html
 ┃ ┗ 404.html
 ┣ 📂static
 ┃ ┗ 📂favicon
 ┗ 📜config.yml
```

```
# https://github.com/adityatelange/hugo-PaperMod/blob/87ffee9fcf6dc3255b5d7346122ba32606430dcf/layouts/_default/list.html#L47

{{- if and .IsHome site.Params.homeInfoParams }}
```
