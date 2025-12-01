Browse to <https://pukkachomby.github.io>

### Theme
* https://themes.gohugo.io/themes/mainroad/
* https://github.com/Vimux/Mainroad

### Example Post/Formatting
* Thumbnail yaml: `thumbnail: "img/pic2.png"`

### Favicon Colors
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
