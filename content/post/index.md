# Posts
[the-perfect-diet](the-perfect-diet)
[gemini-in-brave](gemini-in-brave)
[ai-humanizers](ai-humanizers)
[ai-prompting](ai-prompting)
[apple-and-linux](apple-and-linux)
[block-the-bad-sites](block-the-bad-sites)
[brew-notes](brew-notes)
[gemini-flavors](gemini-flavors)
[humanized-by-ai](humanized-by-ai)
[thankgiving-reheating](thankgiving-reheating)


DRAFTS
===============================================================================
MISC
-------------------------------------------------------------------------------
* Meal planning: no worry about spoilage. Less shit I need to worry about.  Nutrient dispersion better.
* iphone ai summary shortcut (test w honey's phone first)
* elon musk speech in admin wiki
* cloudflared copyparty notes
* brave stuff
    * Antiporn in Brave -> update lists monthly
    * YouTube Kids (in Brave)
* Future app ideas
    * **Obsidian** with iCloud sync.
    * https://netnewswire.com/ (rss, macos/ios, free sync)
    * copyparty
        * homebrew formulae
        * brew install copyparty ffmpeg -- https://formulae.brew.sh/formula/copyparty
        * should work on all macs (both intel and apple silicon) and all relevant macos versions
        * the homebrew package is maintained by the homebrew team (thanks!)
* https://familyfocusblog.com/family-cleaning-schedule/
* https://familyfocusblog.com/51-tips-for-traveling-with-family/
* Ideas
    * https://www.scarymommy.com/
    * https://familyfocusblog.com/
* Styles
    * [Sassy](https://contentmarketinginstitute.com/strategy-planning/marketing-strategy-lead-technology)
    * [Family](https://familyfocusblog.com/51-tips-for-traveling-with-family/)
    * [Sassy+Family](https://www.scarymommy.com/lifestyle/communal-supplies-are-necessary-back-to-school-shopping)



# Mainroad Theme
## Ref
* https://themes.gohugo.io/themes/mainroad/
* https://github.com/Vimux/Mainroad

## Example Post/Formatting
* Thumbnail yaml: `thumbnail: "img/pic2.png"`

## Favicon Colors
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
