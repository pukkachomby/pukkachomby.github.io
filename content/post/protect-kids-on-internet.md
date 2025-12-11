---
title: Protecting Kids on the Internet
date: 2026-03-04
tags:
  - Parenting
  - Safety
  - Security
categories:
  - Family
  - Tech
---

My personal notes for protecting kids on the internet.

<!--more-->

There's a lot of negative content and harmful individuals on the internet, so I want to know what measures Big Tech will implement to safeguard my Boo Boo when she grows up and starts using tech like a big girl.

While the knee-jerk reaction might be to completely shun technology like Ted Kaczynski and retreat to a cabin in the woods, it's probably better to tackle this issue from a pragmatic standpoint by adopting intelligent training and strategic usage of available resources to achieve the results we're looking for.

## Discuss Responsible Tech Use
It’s essential to talk to kids about using technology responsibly. This includes taking proper precautions to avoid scammers and harmful individuals. For more information, here are some helpful site:
* [Kids Health](https://kidshealth.org/en/parents/social-media-smarts.html)
* [Be Internet Awesome](https://beinternetawesome.withgoogle.com/en_us/families)
* [Connect Safely](https://connectsafely.org/controls)

## iPhone Parental Controls
To set up parental controls on an iPhone, first enable Family Sharing and add your child to the Family Sharing group.

You can find a variety of options in the [Apple Support guide](https://support.apple.com/en-us/105121), most of which are accessible through the Screen Time app. These features include location sharing, adult site blocking, communication safety, app install blocking, and more.

## YouTube Kids
YouTube Kids is specifically designed for children aged 2 to 12, providing a content selection that is tailored based on their age.

Parents have the ability to approve only the content they deem appropriate for their children, ensuring a safer viewing experience. The app includes a timer that helps limit screen time, and parents can also block specific videos or channels if they choose. For additional control, there is an option to turn off the search function, allowing for a more curated viewing experience.

Visit [YouTube Kids](https://youtubekids.com) for further details.

## Facebook for Minors
When it comes to Facebook for minors, individuals under the age of 13 are prohibited from creating an account. The app also includes additional safety information for children, and location settings are turned off by default to enhance privacy.

All teens aged 13 to 17 automatically have Teen Accounts on Facebook and Messenger, which come with protective settings designed to ensure their safety. For those teens under the age of 16, parental approval is required if they wish to reduce these protective measures.

The protection features of these accounts include limited visibility and contact, meaning that teens can only interact with friends and established connections. Additionally, there is content filtering in place that helps to block sensitive and potentially offensive material, ensuring a safer environment for young users. To promote healthy usage habits, there are also time limits in effect. Teens receive reminders to log off between the hours of 10 PM and 7 AM and after one hour of continuous use. Moreover, parents have the ability to enforce additional time controls if they deem it necessary.

For further guidance, Facebook provides resources such as the [Family Center]((https://familycenter.facebook.com/dashboard)), a [supervision setup guide](https://www.facebook.com/help/1381198796134370?helpref=faq_content), and [time limit settings](https://www.facebook.com/help/326039493343393/?helpref=uf_permalink&parent_cms_id=1079477105456277) to help parents manage their children’s use of the platform.

## Messenger Kids (Ages 6–12)
Messenger Kids, aimed at children between the ages of 6 to 12, offers a child-friendly communication platform where parents maintain control over their kids’ interactions. This app allows children to video chat, message, and collaborate with friends and family in a safe environment that ensures age-appropriate content.

Messenger Kids is controlled by parents via their Facebook account which is linked to the app. Parents have the ability to approve contacts, monitor messaging, and set usage limits, among other things.  Moreover, to protect kids' privacy, data is deleted when an account is deactivated and kids are not given a public profile.

However, the app does have some drawbacks: it cannot fully filter inappropriate language, images, or screenshots, and some data about the child is collected.

Maybe the biggest annoyance that people complain about is the constant notifications that they get every time their child messages with their friends (which they may do a lot).  To remove such notifications, it seems like [the solution](https://www.reddit.com/r/facebook/comments/hx239q/messenger_kids_is_there_a_way_to_prevent_mine_and/) is to log out of the child's device from the Facebook app.

## Brave Browser Content Filtering
While there is definitely some overlap between this topic and the parental controls available on iPhones, it is still worth mentioning.

Not many people realize that you can filter content in the Brave browser, similar to how you would use uBlock Origin on Firefox. To access Brave's content filters, browse to <brave://settings/shields> and click on the `Content filtering` menu.

Under `Filter lists`, you can reveal the complete list of content you are able to block. For children's safety, some recommended options to check include:
* AdGuard URL Tracking Protection Features
* Fanboy's Social
* Fanboy's Anti-Chat Apps
* The YouTube-related filters (if you're not using YouTube Kids)
* Anti-Porn Blocklists
* Country-specific ad blocking

## Pi-hole
Perceptive readers may have noticed that Brave offers the option to add custom filters. However, instead of only adding custom filters to Brave and securing that specific browser, you might consider implementing network-level protection instead.

After all, even if you prevent your kids from downloading additional apps via the app store on their phone, there's still the possibility that existing app on their phone (like Facebook) may have a built-in web browser that remains unprotected.

Additionally, it's generally more convenient to connect all of your kids' devices to a protected network rather than configuring each device (or possibly each app) individually.

This is where Pi-hole comes in. Pi-hole is a well-known DNS server replacement and blocklist filtering tool that runs on Docker.

To get started with Pi-hole, simply run the Docker container, set it up, add some filters, and change the DNS settings of each device to point to Pi-hole's IP address.

There is an abundance of [filter lists](https://github.com/zachlagden/Pi-hole-Optimized-Blocklists) available on the internet, and a quick web search for "Pi-hole filter list" will reveal many options.

## Google Support
Google offers a family plan, but it's just for Android users, unfortunately.  One work-around is making a Google account for your child, then turning on [SafeSearch](https://support.google.com/websearch/answer/510?hl=en&co=GENIE.Platform%3DDesktop&sjid=8738416387922779742-NA) to block harmful images from coming up in the Google search results.

Of course, this only works while the child is signed in!  *I haven't tested this,* but supposedly there's an option in iPhone's Screen Time to prevent account changes (`Allow Changes` → `Account Changes` → `Don't Allow`).

Regarding non-explicit child images that you want removed from Google search, Google [does have a channel](https://support.google.com/websearch/answer/10949130?hl=en#:~:text=Google%20removes%20images%20of%20anyone,compelling%20public%20interest%20or%20newsworthiness) that handles the removal of such photos.

## DNS Filtering Services
In a [past blog post](https://pukkachomby.github.io/post/block-the-bad-sites/) I mentioned the AdGuard's Family protection servers which you can can definitely use in conjunction with Apple's Screen Time to block bad sites.  Of course, it may not be of use at all if Apple's content blockers are comprehensive, but it's still worth looking into if 1) you want to be sure all your bases are covered 2) you want to use it as a backup, 3) you have non-Apple devices at the house that kids can access the internet from.

In addition to AdGuard, a quick Google search will reveal a lot of other options.  Some standouts are Cloudflare for Families (probably just as good as AdGuard) and also OpenDNS Family Shield which may be slower but also more privacy-friendly.

## Create Your Own Infrastructure
Instead of exposing kids to the actual internet you can simulate a kid-safe internet at home.  I'm not going to go too in-depth right now about this topic because it really should be its own blog post, but generally speaking, if you're tech-inclined then there are a lot of options to replace a lot of the infrastructure on the internet.  Here are some ideas:
* [Replace Wikipedia](https://www.mediawiki.org/wiki/MediaWiki)
* Replace YouTube
    * [ChannelTube](https://github.com/TheWicklowWolf/ChannelTube)
    * [MeTube](https://github.com/alexta69/metube)
    * Pre-download select videos and store in a media library
* Replace Netflix (lock children from the admin account to prevent unwanted downloading)
    * [Sonarr](https://sonarr.tv/)
    * [Radarr](https://radarr.video/)
    * [Jellyfin](https://jellyfin.org/)
    * [Kodi](https://kodi.tv/)
* Replace P2P chatting with AI chatting by running a pre-configured Llama or Mistral model locally
* Replace Google with a pre-configured SearXNG or Whoogle
* Check out some [other options](https://github.com/awesome-selfhosted/awesome-selfhosted)

