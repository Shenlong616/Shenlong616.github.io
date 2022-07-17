```
._hugo/
├── assets/
├── config.yml
├── content/
├── layouts/
├── static/

```

```
// show quote single page
_hugo\layouts\_default\list.html

// https://github.com/adityatelange/hugo-PaperMod/blob/87ffee9fcf6dc3255b5d7346122ba32606430dcf/layouts/_default/list.html#L47
{{- if and .IsHome site.Params.homeInfoParams (eq $paginator.PageNumber 1) }}


{{- if and .IsHome site.Params.homeInfoParams }}
```
