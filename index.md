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

## Got it... now what?
Before doing anything too fancy, we'll start by doing some initial analyses on the available data.

<br/>
<br/>

# Initial Analysis

## Not your usual 80-20 rule
Just to see how things are generaly doing, we'll plot the percentage of quotations by gender (the total number of times speakers of different genders were quoted) and the percentage of speakers by gender.

<iframe src="plots/general_quotations_speakers.html" height="300px" width="100%" style="border:none;"> </iframe>


Plot 2

{% include top_speakers.html %}


