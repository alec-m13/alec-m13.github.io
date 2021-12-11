---
defines: jekyll
title: 'Jekyll'
description: 'Jekyll is a static site builder.'
---

# Static Sites

[Jekyll](https://jekyllrb.com/) is an engine for building static sites. All static sites are websites, but not all websites are static. Static means there is a one-way flow of information from the server to the user; users can't do anything which requires modification of data on the server. Static sites can still be highly interactive -- text editors, video games, even program compilers can be hosted as static sites -- but nothing one user does on a static site will affect other users. That means no comment sections, no scoreboards, and no cloud storage.

Static sites are much easier to operate from the server's perspective. Once the website files have been uploaded to the server, all it has to do is give the requested files whenever someone visits the site. It doesn't have to handle incoming data from the user because there is none. Free web hosting services like [GitHub Pages](https://pages.github.com/) (which this site uses) are often for static sites only.

# Website Files

Websites are primarily split into three components:

 - Content (HTML)
 - Presentation (CSS)
 - Functionality (JS)

These are the core languages of the web. Building a website consists of generating HTML, CSS, and JS files. They were created in the 90s along with the internet as we know it and they are what allows for such variety in website usage. We aren't going to focus much on JS for now since the user doesn't actually see it -- it's there to allow for internal processing in the browser. What the user sees is the HTML and CSS, so that's what we will focus on.

Simply put, HTML contians the content of the page and CSS contains the directions for presentation. If you want some text to be big, blue, and bold (BBB), you write the text in HTML and flag it as intended to be displayed with the BBB style. Then in CSS you write exactly what you mean by BBB, namely you specify that BBB means big, blue, and bold.

Separating content from presentation is super important in web design. The principle even has its own [Wikipedia page](https://en.wikipedia.org/wiki/Separation_of_content_and_presentation). Content should be content -- the information which is to be shared. Presentation should be separated so that it can be modified or reused elsewhere without changing the content.

Separating the two means that the content developers can really focus on what ideas they are actually trying to get across with their content. Presentation developers can focus on how to make it look good. They can also develop different presentation styles for different users of the same content, and the content generator doesn't need to know or care about the different ways their content can be consumed. They just make their content.

# Web Development

The core languages are great for constructing websites, but they are not the most ergonomic in terms of development. This is a real problem because websites have real value in modern life. Developers should be focusing on what they want their websites to get across, not focusing on syntactical mechanics of the language. And writing HTML by hand means most of your time is spent focusing on syntactical mechanics.

Hence there is a reason for web site engines like Jekyll. These engines essentially do just one thing: further separate content from presentation. It's another layer on the cake of web design. With Jekyll you write your content in an alternate language (primarily [Markdown](https://www.markdownguide.org/)) and let the engine create the HTML files for you.

It's much more than just a Markdown compiler, though. What if you want to have a logo displayed on all your web pages across the site? Without an engine you have to include instructions on each page to include the image. It's possible to forget or make a mistake on one page, and then the only way to discover that mistake is to open that one page and notice the problem. With Jekyll there are ways to encode that you want that image on every page and then Jekyll will put it in place automatically. This saved you time and ensures site-wide consistency.

That's the point of Jekyll. The same problem which the HTML/CSS split addresses -- the separation of content and presentation -- is taken a step farther by splitting HTML *and* CSS off as presentation and using instead a more direct format for content. The benefit is ultimately that the entire website is consistent in look and feel, and less buggy, because the content is separated from the presentation.