---
title: "Humanized By AI"
date: 2025-11-30
tags:
  - "AI"
  - "Gemini"
  - "Content & Writing"
categories:
  - "Tech"
---

In our last post we talked about paid alternatives to turn AI slop into text akin to something that a human would write.  In this post, I want to see what a regular, free AI chatbot can do.

<!--more-->

## Choose Your Weapon
When choosing a chatbot to use, I only have 2 criteria:

1. The chatbot's company needs to let me make an account
2. The chatbot must not want to make me rip my hair out

So right off the bat, we eliminate ChatGPT, Claude, and Perplexity.

Since I'm using Brave right now, and since am I now an Apple fanboy, and since Apple is talking with Google about Gemini integration, I'll go with Leo and Gemini.

## Leo
Leo isn't an AI per se, it's more of a manager for AIs glued together with intelligent prompting.  It can alter text similar to Grammarly (eg changing the tone, length, context), and they make such rewording options readily available to the end user.

After testing a lot of the presets on sample text, I discovered that with Leo, less is more -- the best thing to do is write a fairly coherent draft yourself then pipe it through the `Improve` preset to perform various tasks like spelling/grammar check, fluidity improvements, and gentle paraphrasing to generally make the text sound more refined and professional/academic.

## Gemini
As in the last post, the fewer directions you give to Gemini, the better.  Even if you follow the rules I previously recommended when it comes to handling Gemini for writing tasks, Gemini will still get seriously bogged down if the ruleset you impart becomes too complex, and the end product will suffer massively as a result.

## Specific Use-Case
Of course, I'm testing this on blog post creation.  Not that I'm trying to make AI slop, though.  As I previously said, **writers still need to do the bulk of the work** because the best AI can do reliably is make minor touch-ups here and there.

After some playing around, I think I have a simple but effective procedure for honing blog posts to give them some extra fairy dust.

#### Procedure
1. Open Leo, switch to `Automatic`, choose `Improve` and output the improved version
2. Paste the output into Gemini and type the below:

---

**FOLLOW THE BELOW DIRECTIONS PRECISELY AND PROCESS THE ARTICLE IN THIS MANNER:**

* Do not adjust the writing style (INCLUDING WORDING) or tone of the article; just do minor restructuring to make it more fluid and coherent but still match the original writing style
* Remove:
    * Bold words
    * Emojis
* Replace em dashes with two dashes (`--`) or semi-colons (favor semi-colons unless two dashes are objectively more appropriate)
* Output in HUGO-friendly markdown format
* Output in a single monospace text field, even for code, and code should not be placed in separate code blocks ever
* Special formatting
    * Include yaml front matter like this (note that the categories are either "Family" and/or "Tech", also: Tags and Categories are capitalized, and never contain an ampersand):
    ```
    ---
    title: "The Title"
    date: YYYY-MM-DD
    tags:
      - "Tag 1"
      - "Tag 2"
    categories:
      - "Family"
      - "Tech"
    ---
    ```
    * Immediately after the yaml front matter, write this, copying the format exactly (including the blank lines):
    ```

    Make 2-3 sentences here which provide an overview of the article here, totalling no more than 30 words.  It should match the writing style of the article.

    <!--more-->
    ```
    * Never add `***` or `---` or add anything else to break-up sections
    * Headers
        * Never use Level 1 headers (use Level 2 instead)
        * Never use Level 3 headers (use Level 4 instead)
        * You may make Level 4 headers as needed and no special formatting rules apply, however only make Level 4 headers when absolutely necessary
    * To summarize and clarify this special formatting, refer to this combined minimal example:
    ```
    ---
    title: "The Title"
    date: YYYY-MM-DD
    tags:
      - "Tag 1"
      - "Tag 2"
    categories:
      - "Family"
      - "Tech"
    ---

    Make 2-3 sentences here which provide an overview of the article here, totalling no more than 30 words.  It should match the writing style (INCLUDING WORDING) of the article.

    <!--more-->

    ## Header 2
    Body text.

    ## Header 2
    #### Header 4
    Body text.
    #### Header 4
    End of document.
    ```
* For tables, prefer left-aligned text like this:
```
| Column Title      | Column Title          |
| :---------------- | :-------------------- |
| Cell Contents     | Cell Contents         |
```

---
