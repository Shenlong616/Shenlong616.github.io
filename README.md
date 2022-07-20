[![GitHub Pages](https://github.com/Shenlong616/Shenlong616.github.io/actions/workflows/gh-pages.yml/badge.svg)](https://github.com/Shenlong616/Shenlong616.github.io/actions/workflows/gh-pages.yml)

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
 ┃ ┃ ┣ extend_head.html
 ┃ ┃ ┗ [home_info.html]()
 ┃ ┣ 📂_default
 ┃ ┃ ┗ list.html
 ┃ ┗ 404.html
 ┣ 📂static
 ┃ ┗ 📂favicon
 ┗ config.yml
```

```
# https://github.com/adityatelange/hugo-PaperMod/blob/87ffee9fcf6dc3255b5d7346122ba32606430dcf/layouts/_default/list.html#L47

{{- if and .IsHome site.Params.homeInfoParams }}
```

### home_info.html

```html
<svg
  aria-hidden="true"
  xmlns="http://www.w3.org/2000/svg"
  viewBox="0 0 24 24"
  width="24"
  height="24"
>
  <path
    d="M7.75 11c-.69 0-1.25.56-1.25 1.25v1.5a1.25 1.25 0 102.5 0v-1.5C9 11.56 8.44 11 7.75 11zm1.27 4.5a.469.469 0 01.48-.5h5a.47.47 0 01.48.5c-.116 1.316-.759 2.5-2.98 2.5s-2.864-1.184-2.98-2.5zm7.23-4.5c-.69 0-1.25.56-1.25 1.25v1.5a1.25 1.25 0 102.5 0v-1.5c0-.69-.56-1.25-1.25-1.25z"
  ></path>
  <path
    fill-rule="evenodd"
    d="M21.255 3.82a1.725 1.725 0 00-2.141-1.195c-.557.16-1.406.44-2.264.866-.78.386-1.647.93-2.293 1.677A18.442 18.442 0 0012 5c-.93 0-1.784.059-2.569.17-.645-.74-1.505-1.28-2.28-1.664a13.876 13.876 0 00-2.265-.866 1.725 1.725 0 00-2.141 1.196 23.645 23.645 0 00-.69 3.292c-.125.97-.191 2.07-.066 3.112C1.254 11.882 1 13.734 1 15.527 1 19.915 3.13 23 12 23c8.87 0 11-3.053 11-7.473 0-1.794-.255-3.647-.99-5.29.127-1.046.06-2.15-.066-3.125a23.652 23.652 0 00-.689-3.292zM20.5 14c.5 3.5-1.5 6.5-8.5 6.5s-9-3-8.5-6.5c.583-4 3-6 8.5-6s7.928 2 8.5 6z"
  ></path>
</svg>
```
