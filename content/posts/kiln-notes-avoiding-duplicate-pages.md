---
cvs: "$Id: kiln-notes-avoiding-duplicate-pages.md,v 1.3 2024/01/11 18:12:48 mcornick Exp $"
author: Mark Cornick
title: "Kiln notes: avoiding duplicate pages"
date: 2023-06-24
---
I'm using [Kiln](https://git.sr.ht/~adnano/kiln) to manage this site. Kiln is a static site generator that has especially good support for the Gemini format, which I'm trying to get back into (tip: for those of you who want to view this site on Gemini, [here you go!](gemini://mcornick.com/))

Kiln is very flexible about what types of inputs it will accept and what outputs it will create from them. However, it's not always easy to get good-looking HTML and good-looking Gemini text (aka GMI) from the same input, so sometimes I want to have a Markdown version for HTML output, in addition to the native GMI format.

I initially did this using [this Kiln config setting](https://git.sr.ht/~mcornick/mcornick.srht.site/tree/main/item/config.toml#L20), which mostly worked, except that when there was both a Markdown and GMI version of the input, the resulting HTML would be listed twice in the posts index. This is, obviously, not what I wanted. What I wanted was for HTML to be generated from a Markdown source if available, and only if no Markdown was available, for a GMI source to be used.

It turns out there's a way to do this. In the frontmatter of input files, you can set the [`outputs`](https://git.sr.ht/~adnano/kiln/tree/master/item/docs/kiln.1.scd#L119) variable, which specifies which formats should be generated from that input. (Technically, it specifies which Kiln "tasks" to run, but since I have one task for each output format, it amounts to the same thing.) By default, if `outputs` isn't set, it gets generated for all formats. So all I needed to do was, for each GMI file that has a corresponding Markdown file, set `outputs: ["Gemini"]` in that file's frontmatter.  And bam, no more duplicated posts! For example, compare [the Markdown source for this page](https://git.sr.ht/~mcornick/mcornick.srht.site/blob/main/content/posts/kiln-notes-avoiding-duplicate-pages.md) with [the GMI source](https://git.sr.ht/~mcornick/mcornick.srht.site/blob/main/content/posts/kiln-notes-avoiding-duplicate-pages.gmi).

I don't know how many people use Kiln, so this post may be of very limited interest to anyone other than me, but I figured I'd share it and let the search engines find it, in case someone else has this same problem in the future. Teamwork, dreamwork and all that.
