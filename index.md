---
layout: page
title: Mind the (Gender) Gap
order: 1
aside:
  toc: true
---

# Introduction

This is the final project for the Applied Data Analysis course, EPFL.

## What?
In this project we plan to explore the differences in representation of different genders in quotations from news websites, from January 2015 to April 2020, using data from [Quotebank](https://dlab.epfl.ch/people/west/pub/Vaucher-Spitz-Catasta-West_WSDM-21.pdf).  We will explore the following genders: male, female, transgender male, transgender female, non-binary and genderfluid.

## Why?

> **"Gender equality is the goal that will help abolish poverty that will create more equal economies, fairer societies and happier men, women and children"**
>
> --Graça Machel (former *First Lady of South Africa*)

Gender equality is a long-fought battle, one that has already taken long strides in the past centuries, be it in representation in the workplace, wage gaps and legislations. **But has it been enough?** And specifically in online journalism, are all genders given a fair shake when quoted in articles?

According to [this study](https://www.pewresearch.org/fact-tank/2021/01/12/more-than-eight-in-ten-americans-get-news-from-digital-devices/) conducted in 2020, **34% of North Americans often get their news from news websites**. 

{:refdef: style="text-align: center;"}
![top_speakers]({{ "/assets/images/news_source.png" | absolute_url }})
{: refdef}

This is a huge audience, and by being able to choose what speakers they quote, and what quotes they select, journalists are holding a power that many may underestimate, and are able to influence millions of opinions. With great power comes great responsibility[^1], and we plan to investigate how this power is being used to represent different genders.

[^1]: Uncle Ben, 2002

## How?
The dataset from Quotebank consisted of a list of around 100 million quotes featured in news articles, from January 2015 to April 2020. It included information such as the most probable speakers for each quote, the number of total quotations, and the date of the first occurrence. Using data from [Wikidata](https://www.wikidata.org/wiki/Wikidata:Main_Page), we were able to get the gender of each speaker.

<br/>
<br/>

# Initial Analysis

## Not your usual 80-20 rule
Just to see how things are generaly doing, we'll plot the percentage of quotations by gender (the total number of times speakers of different genders were quoted) and the percentage of speakers by gender.

<iframe src="plots/perc_quotations.html" height="600" width="100%" style="border:none;" scrolling="no"> </iframe>

Yikes. From the <em> percentage of quotations</em> plot we see that **men get quoted around 80% of the time**. This percentage is about **4x bigger than the one for women**. However, not everything is lost, as we do see a slight decreasing trend in male quotations, with 84% in 2015 and 81% in 2020. We also see an increase of about 3% in quotes from women.

All the other genders are massively underrepresented in news articles, most of them resting below 0.1% of quotations. We also don't see any increasing tendencies, only distinct peaks. For example, Caitlyn Jenner [came out as a transgender woman in April 2015](https://www.nbcnews.com/pop-culture/celebrity/bruce-jenner-comes-out-transgender-woman-n348181), so there are peaks in the transgender female plot in that time. Another example, Miley Cyrus [revealed she is genderfluid](https://www.billboard.com/music/pop/miley-cyrus-gender-fluid-nothing-to-do-with-any-parts-6598191/) in June 2015, so we also observe peaks there.

<iframe src="plots/perc_speakers.html" height="600" width="100%" style="border:none;" scrolling="no"> </iframe>

Now you might be thinking: "Of course men way more quotations, because that includes very influential people like Donald Trump and Barack Obama". Well yes but also no. If we look at the <em>percentage of speakers by gender</em>, it looks just about the same. Around **80% of quoted speakers are male**, with a very slight decrease of 2% over time. **In genders other than male and female, transgender female speakers dominate at around 0.08%**.

## [Top speakers by month title]
<iframe src="plots/top_speakers.html" height="700" width="100%" style="border:none;" scrolling="no"> </iframe>

