# Example Post
* Note the thumbnail yaml
* `<!--more-->` indicates the preview cutoff
* Images
    * Note the image path in the markdown doc
    * Images placed in `/static/img/`
```md
---
title: "(Hu)go Template Primer"
date: 2014-04-01
tags:
  - "go"
  - "golang"
  - "templates"
  - "themes"
  - "development"
categories:
  - "Development"
  - "golang"
thumbnail: "img/pic2.png"
---

Hugo uses the excellent library for its template engine. It is an extremely lightweight engine that provides a very small amount of logic. In our experience that it is just the right amount of logic to be able to create a good static website. If you have used other template systems from different languages or frameworks you will find a lot of similarities in Go templates.

<!--more-->

More text.

![pic](/img/pic.png)
```

# Favicon colors

There is no way to do this on the fly with Hugo, but you can use the one-liners below with some preparations:

1. Copy:
    * `./themes/mainroad/static/favicon.ico` to `./static/favicon.ico`
    * `./themes/mainroad/static/apple-touch-icon.png` to `./static/apple-touch-icon.png`
1. At the beginning of each script, replace the color in the variable with your preferred color. You must use
six-digit hex triplet notation (e.g., `#E22D30`) to make it work properly.

Go to the root of your project directory in the terminal and execute these two commands accordingly.

```
a=#5300ff;a=\\x${a:5:2}\\x${a:3:2}\\x${a:1:2};for i in 98 274 578;do printf $a|dd of=static/favicon.ico bs=1 seek=$i conv=notrunc;done
```

```
a=#5300ff;a=$(echo 504C54452A2A2A${a:1:6}|sed -e 's/../\\x&/g');printf $a|gzip|tail -c8|od -tx4 -N4 -An|xargs|sed -e 's/../\\x&/g'|printf $a$(cat -)|dd of=static/apple-touch-icon.png bs=1 seek=37 conv=notrunc
```


# Theme Info
## Mainroad (current)
* https://themes.gohugo.io/themes/mainroad/
* https://github.com/Vimux/Mainroad

## Yin Yang (alt)
* Minimal but not optimized for mobile
* Ref
    * https://themes.gohugo.io/themes/hugo-theme-yinyang/
    * https://github.com/joway/hugo-theme-yinyang
