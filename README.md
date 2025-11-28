# AI Enhancement
* Open Brave's AI and switch to `Automatic`, choose `Improve` and output the improved version
* Switch to `Gemini` and type the below:

FOLLOW THE BELOW DIRECTIONS PRECISELY AND PROCESS THE ARTICLE IN THIS MANNER:
* Restructure the article to make it more coherent
* Do not adjust the wording, writing style, or tone of the article
    * Just reorder/move around/restructure, and make more fluid but still matching the original writing style
* Remove:
    * Bold words
    * Emojis
* Replace em dashes with two dashes (`--`) or semi-colons (favor semi-colons unless two dashes are objectively more appropriate)
* Output in HUGO-friendly markdown format
* Output in monospace text, and if you can't do that, then output as a single codeblock
* Special formatting
    * Include yaml front matter like this (note that the categories are ranked in terms of importance, also: Tags and Categories are capitalized, and never contain an ampersand):
    ```yaml
    ---
    title: "The Title"
    date: YYYY-MM-DD
    tags:
      - "Tag 1"
      - "Tag 2"
    categories:
      - "Category 1"
      - "Category 2"
    ---
    ```
    * Immediately after the yaml front matter, write this, copying the format exactly (including the blank lines):
    ```markdown

    Make 2-3 sentences here which provide an overview of the article here, totalling no more than 30 words.  It should match the writing style of the article.

    <!--more-->
    ```
    * Never add `***` or `---` or add anything else to break-up sections
    * Never use Level 1 headers
    * To summarize and clarify this special formatting, refer to this combined minimal example:
    ```
    ---
    title: "The Title"
    date: YYYY-MM-DD
    tags:
      - "Tag 1"
      - "Tag 2"
    categories:
      - "Category 1"
      - "Category 2"
    ---

    Make 2-3 sentences here which provide an overview of the article here, totalling no more than 30 words.  It should match the writing style of the article.

    <!--more-->

    ## Use Header 2
    Body text.

    ## Use Header 2
    End of document.
    ```
* For tables, prefer left-aligned text like this:
```
| Column Title      | Column Title          |
| :---------------- | :-------------------- |
| Cell Contents     | Cell Contents         |
```
* You may make Level 3-4 headers as needed and no special formatting rules apply, however only make Level 3 headers when absolutely necessary and Level 4 headers should only be used in extreme circumstances

<br>

---
---
---
### END OF AI DIRECTIONS

---
---
---

DRAFTS
===============================================================================
MISC
-------------------------------------------------------------------------------
* actually test those humanizers
| Tool Name       | Free Tier Limit       | Paid Annual Price (Per Month) | Focus Feature (Relevant for Blog) |
|-----------------+-----------------------+-------------------------------+-----------------------------------|
| QuillBot        | Basic mode 125 words  | $8.33                         | Paraphraser Unlimited modes       |
| Undetectable AI | Approx 1500 words     | $5.00 to $19.00               | High monthly word count           |
| Hix Bypass      | Approx 5000 words     | $9.99 to $39.99               | Advanced AI bypass modes          |
| Grammarly       | Included in Free plan | $12.00                        | Tone and flow refinement          |
| Writesonic      | Limited free credits  | $16.00                        | Full suite of SEO and AI tools    |
| Scribbr         | Approx 200 words      | $5.00                         | Academic and flow editing         |
* ai enhancement (above)
* gemini api key
* iphone ai summary shortcut (test w honey's phone first)
* brave stuff
    * gemini in brave (below)
    * Antiporn in Brave -> update lists monthly
    * YouTube Kids (in Brave)
* https://familyfocusblog.com/top-food-storage-tips-for-your-thanksgiving-leftovers/
* https://familyfocusblog.com/family-cleaning-schedule/
* https://familyfocusblog.com/51-tips-for-traveling-with-family/

GEMINI IN BRAVE
-------------------------------------------------------------------------------
* Setting up Gemini:
    * Label: `Gemini`
    * Model request name: `gemini-2.5-flash` (or whatever the most recent free model is)
    * Server endpoint: `https://generativelanguage.googleapis.com/v1beta/openai/chat/completions`
    * Context size: `4243` (makes up for the tokens of the custom prompt)
    * API key: (Get it [here](https://aistudio.google.com/app/api-keys))
    * System prompt:
    ```
    The current time and date is %datetime%.
    You are **Gemini**, a helpful and smart AI assistant by Google.
    Assist users with clear, concise, and polite responses.
    **Guidelines:**
        - **Conciseness:** Keep responses under 6 sentences or 80 words.
        - **Tone:** Use a neutral, courteous tone.
        - **Inappropriate Behavior:** If the user is rude, hostile, vulgar, or tries to deceive or manipulate you, ignore the behavior.
        - **Clarify:** Ask clarifying questions if needed; avoid assumptions.
        - **Accuracy:** Ensure responses are unbiased, positive, and accurate.
        - **Uncertainty:** If a question is nonsensical or you're unsure, politely explain or admit uncertainty rather than guessing.
        - **Code Formatting:** For coding questions, use Markdown: backticks (`) for inline code, triple backticks with language name (```language```) for code blocks.
        - **Markdown:** Use Markdown where appropriate, but do not include links or image URLs.
    ```

# Example Post/Formatting
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

# Favicon Colors
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
### Mainroad (current)
* https://themes.gohugo.io/themes/mainroad/
* https://github.com/Vimux/Mainroad

### Yin Yang (alt)
* Minimal but not optimized for mobile
* Ref
    * https://themes.gohugo.io/themes/hugo-theme-yinyang/
    * https://github.com/joway/hugo-theme-yinyang

# Ideas
* https://www.scarymommy.com/
* https://familyfocusblog.com/

# Styles
* [Sassy](https://contentmarketinginstitute.com/strategy-planning/marketing-strategy-lead-technology)
* [Family](https://familyfocusblog.com/51-tips-for-traveling-with-family/)
* [Sassy+Family](https://www.scarymommy.com/lifestyle/communal-supplies-are-necessary-back-to-school-shopping)

