```
📦main
 ┣ 📂assets
 ┃ ┣ 📂css
 ┃ ┃ ┣ 📂core
 ┃ ┃ ┃ ┗ 📜license.css
 ┃ ┃ ┣ 📂extended
 ┃ ┃ ┃ ┣ 📜dracula.css # highlight.js style: dracula
 ┃ ┃ ┃ ┣ 📜pokey.css
 ┃ ┃ ┃ ┗ 📜_main.css
 ┃ ┃ ┗ 📂includes
 ┃ ┃ ┃ ┗ 📜scroll-bar.css
 ┃ ┗ 📂js
 ┃ ┃ ┗ 📜license.js
 ┣ 📂content
 ┣ 📂layouts
 ┃ ┣ 📂partials
 ┃ ┃ ┣ 📜extend_footer.html # Custom CSS & JavaScript
 ┃ ┃ ┗ 📜extend_head.html # Custom CSS & JavaScript
 ┃ ┣ 📂_default
 ┃ ┃ ┗ 📜list.html
 ┃ ┗ 📜404.html
 ┣ 📂static
 ┃ ┗ 📂favicon
 ┗ 📜config.yml
```

```
// https://github.com/adityatelange/hugo-PaperMod/blob/87ffee9fcf6dc3255b5d7346122ba32606430dcf/layouts/_default/list.html#L47
{{- if and .IsHome site.Params.homeInfoParams }}
```
