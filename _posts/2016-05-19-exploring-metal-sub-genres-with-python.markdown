---
layout: post
title: "Exploring metal sub-genres with Python"
---

The internet lets people share music from all over the world. I know a lot of
the metal I listen to is made by bands from many different countries. I can
think of metal bands I love from Sweden, France, Germany, Italy, Canada,
Brazil, the UK, and Norway just off the top of my head. While specific genres
often grow out of a certain regional scene, there is no absolute rule that
confines genres geographically. For instance, you don't have to be from Norway
to start a black metal band.

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

Luckily, there is the [Metal Archives](http://www.metal-archives.com). An
extraordinarily comprehensive user-contributed repository of information on
metal bands. It has everything from band names with countries of origin, to
timelines of lineup changes, to numerically scored album reviews. They also have
a genre description for each band on their site.

### So what exactly gets scraped?

The script downloads only the information presented when you browse bands
alphabetically. This includes each band's name (with a link to the band's M-A
page), country of origin, genre, and status (active, split-up, changed name, on
hold, unknown, or disputed). The data was scraped on 2016-03-14 at around 10PM
and consists of 107,015 bands.

As far as I know, the Metal Archives is the largest compendium of data on metal
bands and I believe it is all user-contributed. That said, a huge thank you to
the maintainers of the Metal Archives and all of the users who have contributed
information to the site!

### What are we looking for again?

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

### Follow along

As always, check out the html rendering of the notebook [here](NOTEBOOK HTML LINK)
or run the code yourself by cloning my [ma-scraper repo](https://github.com/jonchar/ma-scraper)

### A note on inspiration

A good amount of inspiration for the analysis I ended up doing came from reading
[Alex Kras' post](http://www.alexkras.com/i-tried-to-virtually-stalk-mark-zuckerberg/)
where he analyzes comments from a single post by Mark Zuckerberg after trying to
figure out how to be the first commenter on one of his posts. I really liked the
graph visualization used and how he found the subset asking Zuckerberg for
money. Oh and the word cloud was cool too!

### Next level

In the future I hope to dig further and scrape the site a bit more for things
like releases, band member timelines / overlap, lyrics, reviews, etc.

Who wouldn't want to answer questions about their favorite musical genre with
data?
