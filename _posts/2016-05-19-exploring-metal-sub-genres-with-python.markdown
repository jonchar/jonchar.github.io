---
layout: post
title: "Exploring metal sub-genres with Python"
date: 2016-05-20
categories: [scraping, data exploration, metal, clustering]
---

Today's post is about an exploratory analysis of metal band sub-genres based
on data scraped from the web. If you're too impatient and want to dive right in,
choose one of the links below. If you like context, or are confused right now,
read on. Fear not, you don't have to like metal music to appreciate the
analysis.

**[Github repo containing the Jupyter notebook and some data](https://github.com/jonchar/ma-scraper)**

**[HTML rendering of the notebook](/notebooks/MA-Exploratory-Analysis)**

## Metal sub-genres?

The internet lets people share music from all over the world. I am a huge fan
of metal music, as there is often high standard of musicianship. I have also
been playing guitar for going on 15 years. I know a lot of the metal I listen
to is made by bands from many different countries. I can think of metal bands
I love from Sweden, France, Germany, Italy, Canada, Austrailia, the UK, and
Norway just off the top of my head. While specific genres often grow out of a
certain regional scene, there is no absolute rule that confines genres
geographically. For instance, you don't have to be from Norway to start a
black metal band.

Within the blanket of metal there are numerous sub-genres that overlap, separate
out, and merge with one another over time. Go to any metal forum on the internet
and you're bound to find flame wars debating where certain bands fall within
subgenres or where the boundary of one subgenre ends and another begins. The
truth of it is that these categorizations are fuzzy and subjective. A single
band can often traverse genres across subsequent albums or even within a single
song. Or they might be the same throughout their entire career. Music is very
personal as well, readily stoking the flames of debate. On top of it all, the
words we use to describe metal subgenres can also be limiting compared to the
information contained in a sound, a song, or an album. Despite all this, it is
generally accepted that *distinct subgenres do exist*.

Luckily, there is the [Metal Archives](http://www.metal-archives.com) (M-A). An
extraordinarily comprehensive user-contributed repository of information on
metal bands. It has everything from band names with countries of origin, to
timelines of lineup changes, to numerically scored album reviews. They also have
a genre description for each band on their site. Just what we need to make
definitive conclusions about genre memberships! As far as I know, the Metal
Archives is the largest compendium of data on metal bands and I believe it is
all user-contributed. That said, a huge thank you to the maintainers of the
Metal Archives and all of the users who have contributed to it!

## Scraping

The script `MA_scraper.py` downloads only the information presented when you
browse bands alphabetically. This includes each band's name (with a link to the
band's M-A page), country of origin, genre, and status (active, split-up,
changed name, on hold, unknown, or disputed). The data was scraped on
2016-04-01 and consists of a little over 100,000 bands.

## Exploring

I started out just wanting to write a web scraper for the Metal Archives. After
realizing that there was an incredibly huge amount of information up there, I
decided to start with just basic band information. The most interesting of which
to me was the genre description. Initial exploration of the data led me to three
general questions:

1. What groups of subgenres exist semantically?
2. What words or terms define these groups?
3. How are they all related?

The exploratory analysis I ended up with hits on these primary questions with a
few interesting detours along the way. This took me through topics such as NLP,
dimensionality reduction, clustering, basic graph theory, and of course data
visualization.

## What I found

Through exploring the data it became obvious that distinct groups or clusters
of metal sub-genres existed within the data set. These clusters are all
based on semantic relationships between genre labels. What was surprising
was the degree of structure within the data. There are some groups that
overlap with neighboring groups, while there are other groups that are almost
entirely isolated. This is a very exicting result given that the only
underlying assumption I held was that sub-genres exist (a fairly benign
and obvious statement).

While I'm sure there are more interesting perspectives to be extracted from
this particular data set, I decided to tie it off here but may come back to it
in the future (predicting album review scores using NLP anyone?).

Is any of this useful? Well you could check out that
[section in the notebook](/notebooks/MA-Exploratory-Analysis#Conclusion)
and see for yourself!

## A note on inspiration

A good amount of inspiration for the analysis I ended up doing came from reading
[Alex Kras' post](http://www.alexkras.com/i-tried-to-virtually-stalk-mark-zuckerberg/)
where he analyzes comments from a single post by Mark Zuckerberg after trying to
figure out how to be the first commenter on one of his posts. I really liked the
graph visualization used and how he found the subset asking Zuckerberg for
money. Oh and the word cloud was cool too!

Special thanks to [Eric Ma](http://www.ericmajinglong.com/) for brainstorming
analysis approaches & visualization techniques with me. Also thanks to
[Boston Python](http://bostonpython.com) for holding great meetups where ideas
for blog posts like this are born.
