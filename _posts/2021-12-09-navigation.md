---
layout: post
category: jekyll
title:  "Navigation"
---

I took an available GitHub Pages theme, the [Time Machine](https://pages-themes.github.io/time-machine/), and wanted to make some major customizations. The first, obvious one is to relativize dimensions so it works better on a range of screen sizes. The more custom customization is that I love the banner but as provided it has content for downloading the repository from GitHub. This is a great feature, sure, but I don't think it will be very useful for me. I will repurpose this banner to have navigational links.

Getting the banner to display navigational links is easy enough when I know what the links are. It was a simple matter of putting three `<span>` elements in and styling them with flexbox. The challenge was in getting the links themselves.

I will be learning many technologies and presenting them here, and I want to separate them into different threads. I want the homepage to have a list of all the languages, and then clicking on them should take you to a list of the blog entries for that language. Jekyll is perfectly capable of categorizing posts into categories and that part was easy, but getting a `next` and `previous` button was not as straightforward as it seems.

Jekyll has a built-in `next post` feature but it doesn't consider category, it's purely chronological. I found a post on a [Jekyll forum](https://talk.jekyllrb.com/t/how-to-link-to-next-and-previous-posts-for-same-blog-category/629) which helped immensely. This led to a quick crash course on [Liquid](https://shopify.github.io/liquid/) and [Jekyll collections](https://jekyllrb.com/docs/collections/) with which I was able to achieve my desired result.

## Solution

Here's the structure: in the default layout there is a call to include a `nav`. The `nav` is a snippet of html (enhanced with Liquid and Jekyll) I wrote which finds which links to put into the navigation banner and puts them in. It does this by cases, depending on what variables are declared in the front matter of the page.

If the page has a `category` then it is a blog post which should link to other blog posts in the same category. The category itself is the language involved in this post. This is more or less directly taken from the Jekyll forum post. But `nav` also finds the home page for that language and presents it as the up direction, and that took a little figuring out of my own.

If the page instead has a `defines` field in its front matter then it is a home page for a language. The navigation should point to other language home pages, and the up direction should go to the homepage of the website. There was a lot of fussing about with Jekyll variable structure -- I had an annoying issue where accessing pages from the `site` variable kept giving me just the content and not the metadata like url/title/etc -- but with enough Liquid for loops I was able to get the navigation bar to work.

This navigation bar should be the end of my customization of the theme. I learned quite a bit about Jekyll site structure and Liquid syntax, and hopefully any other customizations I'll be able to do without changing the theme files themselves. I would like to eventually isolate my modifications from the original theme so that I can revert back to the remotely accessed theme approach, but that's not high priority at the moment.