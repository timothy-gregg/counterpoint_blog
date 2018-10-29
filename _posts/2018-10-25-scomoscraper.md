---
layout: post
title: How to scrape ScoMo
author: Tim Gregg
---

I'm working on a research project that requires some heavy-duty web scraping. My goal is to build a dataset of every public word spoken by every Prime Minister since Howard. I'm interested in using natural language processing tools like [spaCy](https://spacy.io/){:target="_blank"} and [NLTK](https://www.nltk.org/){:target="_blank"} to analyse the vocabularies of our recent PMs. 

But first I need the data.  

Researching our former leaders is easy enough. The Department of Prime Minister and Cabinet maintains an archive of interviews, speeches, and media releases dating back to the early 1940s. Every transcript is available as an XML file, which you can access by passing the transcript's sequential ID number as a URL query string. (Check out the [developers page](https://pmtranscripts.pmc.gov.au/developers){:target="_blank"} for more info.)  

With this architecture, it's easy to write a for-loop or while-loop that iterates through every transcript and extracts the relevant content from the XML file. I'll publish that code in a separate post. 

The [website of the current Prime Minister](https://pm.gov.au/media){:target="_blank"} is much harder to navigate. There's no logical or sequential structure to the URLs, and the transcripts are only available as raw HTML. To get around this limitation, I wrote a web scraper in Python, using an excellent HTML-parsing library called [BeautifulSoup](https://www.crummy.com/software/BeautifulSoup){:target="_blank"}. 

Basically, here's what the program does:

1. Creates a database
2. Crawls through the PM's website and reads the latest transcript
3. Strips all the metadata and HTML tags from the file 
4. Saves the transcript's title, date, and text in the database
5. Moves on to the next transcript and repeats steps 2-4

My code is neither elegant nor efficient, but it gets the job done. By running this script two or three times a week, I can keep my database up-to-date with ScoMo's latest utterances. 

The gist is below, and the full repo is on [GitHub](https://github.com/timothy-gregg/ScoMoScraper){:target="_blank"}. Enjoy. 
  
    

<script src="https://gist.github.com/timothy-gregg/7e06d581e096ca7e93d6df3a1412c336.js"></script>