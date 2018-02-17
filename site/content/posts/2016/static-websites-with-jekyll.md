---
title:  "Static websites with Jekyll"
date: 2016-08-13T10:40:35Z
draft: false
---

<img alt="Some reeaaally basic outlines" data-src="/assets/images/sketch_wireframes.jpg">

I put aside a few weekends recently to work on developing a simple new blog and portfolio site from scratch. 
My old blog was a basic template that I set up after DroidCon Montréal, so I thought it'd be fun to dig into Jekyll
and play with a few new tools, while sprucing it up a bit.

I worked on a few mock-up ideas, starting from mobile-first, and decided to let it evolve from there. Depending on
how long it's been since I wrote this article, the site could look quite a bit different now.

Lately I've been using new tools for creating wireframes, partly to avoid the subscription to Adobe CC, but also
because there are some great tools being built by small teams at the moment. My two favourites so far are 
[Affinity Designer][affinity], a direct illustrator replacement, and [Sketch][sketch] which is more focused on 
wireframing and prototyping.

<div class="mt4"></div>

<img alt="Incredibly straightforward, and highly recommendeds" data-src="/assets/images/github_pages_jekyll.jpg">

Having spent some time working with Joomla, Wordpress, and Drupal, I was far more interested in building a static site 
than deploying another bloated CMS. The three I found most appealing were [Jekyll][jekyll], [Middleman][middleman], 
and [Ghost][ghost]. As Github provides free hosting of static sites through Jekyll, the decision was pretty easy. 

As a digression, I've always bought and managed my domain names through [Gandi][gandi], whose slogan is _No Bullshit™_ 
and is pretty accurate in my experience. A CNAME file added to the root of the repo, and the site would have a custom 
domain. Super stuff.

<div class="mt4"></div>

<img alt="Admittedly, I can't handle how slow Atom is. SublimeText ftw" data-src="/assets/images/development.jpg">

I initially used [Yeoman][yeo] to scaffold a [Gulp][gulp]-based workflow; however, it was a little opinionated in what 
it generated, so instead I used **Jekyll new** to create a basic structure and then build a simple workflow from there.
Jekyll's watch command, with compressed [Sass][sass] output, and [Browsersync][browsersync] running under a single Gulp 
command was all I needed.

I decided to use [Bourbon][bourbon], [Neat][neat], and [Bitters][bitters] to assist with mixins, grids, and typography. 
Overall I enjoyed the experience and they work well without much hassle.
I would like to try [Susy][susy] for my next project though, as I like the grids-on-demand approach, 
rather than an entire framework.

<div class="mt4"></div>

<img alt="It'll do, until I have time to do something better" data-src="/assets/images/v2_site.jpg">

A week or two later, I had some free time and cleaned it up a bit more.

Having this goal completed, it seemed like the right time to start optimising what I'd built, so I started with 
removing dependencies to unnecessary external files, such as using four SVGs for my footer rather than import 
FontAwesome, and then losslessly compressed all the images on the site.

Anything that could be done in CSS rather than using an image (like the original rainbow strip in the header) was 
also fixed. I did make small compromises, however. I replaced TypeKit's async Javascript with Google Fonts stylesheet 
reference, as the [FOUT][fout] was proving too irritating and I was willing to take the tiny performance hit.

One of the most useful decisions I made was to sign up for a [CloudFlare][cloudflare] account, which allowed me to 
control caching, content delivery over HTTPS, and further minification of resources. It also provides excellent 
statistics, protection, and a wealth of other options. 

An unexpected lesson to learn was Jekyll's lack of support for html minification without additional plugins.
A bit of searching later, and this [incredibly smart Liquid-based hack][mini] sealed the deal.

My next steps are to work on a Projects section, potentially using a [Masonry][masonry] grid to display work items. 
I could probably do with adding an About section, and there's always some typographic styling to adjust.

There are a few other things too, such as [asyncronously loading CSS][async] and blog images, adding a lightbox for 
proper image viewing, and perhaps giving TypeKit another go, but they aren't an immediate priority. 


[affinity]: https://affinity.serif.com/en-us/designer/
[sketch]: https://www.sketchapp.com/
[ux_menu]: https://lmjabreu.com/post/why-and-how-to-avoid-hamburger-menus/

[yeo]: http://yeoman.io/
[sass]: http://sass-lang.com/
[browsersync]: https://www.browsersync.io/
[gulp]: http://gulpjs.com/
[bourbon]: http://bourbon.io/
[neat]: http://neat.bourbon.io/
[bitters]: http://bitters.bourbon.io/
[susy]: http://susy.oddbird.net/
[liquid]: https://shopify.github.io/liquid/

[jekyll]: https://jekyllrb.com/
[middleman]: https://middlemanapp.com/
[ghost]: https://ghost.org/
[dillinger]: http://dillinger.io/
[gandi]: https://www.gandi.net/

[knuth]: https://xkcd.com/1691/
[fout]: http://www.html5rocks.com/en/tutorials/webfonts/quick/#toc-fout
[cloudflare]: https://blog.cloudflare.com/secure-and-fast-github-pages-with-cloudflare/
[mini]: http://jch.penibelst.de/

[async]: https://jakearchibald.com/2016/link-in-body/

[masonry]: http://masonry.desandro.com/
