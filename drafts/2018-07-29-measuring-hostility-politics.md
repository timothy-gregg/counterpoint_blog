---
layout: post
title: "Measuring hostility in Australian politics"
---

Has politics become more adversarial in recent years? Many people seem to think so. It's commonplace to observe that our political system has become more fractured. 

Hostility is not an easy thing to measure. We need a quantifiable metric. One that comes to mind is the frequency with which the prime minister mentions the opposition leader's name. 

Listening to Malcolm Turnbull speak these days, I get the impression that he spends far too much time talking about Bill Shorten. In opposition, it's your job to criticise the government. But in government, it's your job to do your job. Stop talking about the other guy and get on with it. By that criteria Turnbull seems subjectively to be doing badly. But how does Turnbull stack up against his predecessors? That's something we can measure. 

The Prime Minister and Cabinet website has an archive with the transcript of every PM public appearance since the Menzies era. By analysing the frequency of opposition leader mentions, we can get some sense of how the thing has changed over time.

Using the Python programming language, I wrote a web scraper that downloaded a copy of every interview and press release transcript since Howard took office in Month 1996. The code is here. I started with Howard because the archive only became properly digital in 1995. Prior to that, the transcripts are OCR PDF etc, not reliable. 

I also focused on interviews and press conferenences, rather than speeches and other formal statements. I'm not interested so much in the PM's prepared remarks, but rather in spotaneous response to a journalist's questions, because this gives a better indication of the PM's natural speaking style. 

Once I had the transcripts, I wrote another Python script to break the text into chunks and isolate those sections of text spoken by the prime minister, while ignoring those spoken by the journalist. 
I then saved the isolated sections of disalogue in a text file, one for each prime minister since Howard. The files are here. 