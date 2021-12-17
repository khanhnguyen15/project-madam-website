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
In this project we plan to explore the differences in representation of different genders in quotations from news websites, from January 2015 to April 2020, using data from [Quotebank](https://dlab.epfl.ch/people/west/pub/Vaucher-Spitz-Catasta-West_WSDM-21.pdf).  We will explore the following genders: male, female, transgender male, transgender female, non-binary and genderfluid, but mostly focusing on men and women.

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
The dataset from Quotebank consisted of a list of around 100 million quotes featured in news articles in English, from January 2015 to April 2020. It included information such as the most probable speakers for each quote, the number of total quotations, and the date of the first occurrence. Using data from [Wikidata](https://www.wikidata.org/wiki/Wikidata:Main_Page), we were able to get the gender of each speaker.

<br/>
<br/>

# Initial Analysis

## Not your usual 80-20 rule
Just to see how things are generally doing, we'll plot the percentage of quote occurrences by gender (the total number of times speakers of different genders were quoted) and the percentage of speakers by gender.

<iframe src="plots/perc_quotations.html" height="600" width="100%" style="border:none;" scrolling="no"> </iframe>

From this plot, we see that **men get quoted around 80% of the time**. This percentage is about **4x bigger than the one for women**. Yikes. However, not everything is lost, as we do see a slight decreasing trend in male quotations, with 84% in 2015 and 81% in 2020. We also see an increase of about 3% in quotes from women.

All the other genders are massively underrepresented in news articles, most of them resting below 0.1% of quotations. We also don't see any increasing tendencies, only distinct peaks. For example, Caitlyn Jenner [came out as a transgender woman in April 2015](https://www.nbcnews.com/pop-culture/celebrity/bruce-jenner-comes-out-transgender-woman-n348181), so there are peaks in the transgender female plot in that time. Another example, Miley Cyrus [revealed she is genderfluid](https://www.billboard.com/music/pop/miley-cyrus-gender-fluid-nothing-to-do-with-any-parts-6598191/) in June 2015, so we also observe peaks there.

<iframe src="plots/perc_speakers.html" height="600" width="100%" style="border:none;" scrolling="no"> </iframe>

Now you might be thinking: "Of course men get quoted way more often, because they have very influential people like Donald Trump and Barack Obama". Well, yes but actually no. If we look at the <em>percentage of speakers by gender</em>, it looks just about the same. Around **80% of quoted speakers are male**, with a very slight decrease of 2% over the past 5 years. **In genders other than male and female, transgender female speakers dominate at around 0.08%**.

## Trump, Trump and more Trump

<iframe src="plots/top_speakers.html" height="700" width="110%" style="border:none;" scrolling="no"> </iframe>

Above are the top speakers of every month by gender and, to no one’s surprise, **Trump is the most quoted speaker of the last 5 years**. Since the beginning of 2016, when the presidential race started going strong, the former President of the USA has consistently been the most quoted speaker almost every month. In the months when he is the top speaker, **Trump averages around 117,000 monthly quote occurrences**. That is more than **6 times the amount for the top speakers of all other genders <em>combined</em>**.

## First Impressions: Not great...
These initial numbers don't look too promising. Men dominate in every plot we've seen, by a big margin. Now that we have a general idea of how (badly) things are going, let's dive deeper and try to find how exactly <em>what</em> each gender is talking about.

<br/>
<br/>

# Topic Analysis

We've seen that not everybody is getting the same platform to speak from. But what exactly are speakers talking about? To look into that, let's consider a few key topics, presented here in no particular order.

- Business
- Sports
- Government
- Climate Change
- LGBT
- Money
- Family
- Health

## Business runs the world

Let’s start with the percentage of words from different genders that fall into these topics.

<iframe src="plots/topic_in_gender.html" height="750" width="100%" style="border:none;" scrolling="no"> </iframe>

The main takeaways from here are: 
 - **Men tend to talk more about business and sports**
 - **Women tend towards business and government**
 - **The topics men and women talk the least about are LGBT and Climate Change** 

As far as the minority genders are concerned, they present a lot more fluctuations (partly due to the smaller sample size). Surprisingly, they follow the trends set by the men and women fairly well. In fact, their least significant topics are LGBT and Climate Change (with the exception of some occasional spikes).

Now, for the distributions of genders in each topic, see the plot below.

<iframe src="plots/gender_in_topic.html" height="750" width="100%" style="border:none;" scrolling="no"> </iframe>

Well this is worrying… **Business has about 20x more words than Climate Change, and 500x more words than LGBT.** There isn't a clear positive trend in the evolution of the number of words for LGBT and Climate Change, which is a sign that they are not having the exposure they require.  

This shows that despite [some claims](https://www.investors.com/politics/editorials/media-bias-left-study/) that media is saturated with a "liberal agenda", these issues are clearly much less represented than any of the main "traditional" topics, like business, sports and money.

<br/>
<br/>

# Sentiment Analysis

Not everything in the world is about business though... On a more emotional note, we want to explore the sentiment present in these quotes: are they mainly positive, negative or neutral?

For this analysis, we compare quotes by their sentiment scores, which can take values between -1 and 1 [^2]. A sentiment score of 0 can be regarded as a neutral quote, while positive and negative scores represent positive and negative sentiment in quotes, respectively.

[^2]: For sentiment score calculation we used nltk's sentiment intensity analyzer.[nltk sentiment intensity analyzer](https://www.nltk.org/api/nltk.sentiment.vader.html)

<iframe src="plots/sent_vs_time_allgenders.html" height="700" width="100%" style="border:none;" scrolling="no"> </iframe>

The sentiment scores for men and women lie between 0.15 and 0.26, which is close to neutral but still positive. However, **male quotes tend to be more positive than female ones** pretty consistently throughout the years.

On the other hand, quotes belonging to transgender-male, transgender-female, genderfluid and non-binary genders, which are aggregated in a single group named "others", tend to have more oscillating average sentiment scores. Still, **quotes from other genders tend to be more negative than for men and women**, sometimes dipping into the negative scores. For these genders, we can observe both positive and negative average scores that cover a wider range from -0.15 to 0.32. This was to be expected since most of the times we hear, say, transgender speakers in the news, they're talking about problems like [discrimination](https://www.nbcnews.com/feature/nbc-out/laughed-out-interviews-trans-workers-discuss-job-discrimination-n1063041), [bad healthcare](https://www.ncbi.nlm.nih.gov/pmc/articles/PMC4802845/) or [unfair legislation](https://www.nbcnews.com/nbc-out/out-news/two-transgender-children-sue-tennessee-school-bathroom-law-rcna1558).

## Liberal vs Conservative

Focusing on male and female, we'll see if the difference we have seen in sentiment scores continues when we divide news sources into two categories: liberal and conservative. We have created 2 lists that contain some of the most popular liberal and conservative news sources according to ThoughtCo and Aelieve Digital Marketing.

 - Liberal news sources: CNN, Huffington Post, The New York Times, Politico, Slate, ABC News, Daily Kos, The Washington Post,
                         Time Magazine, The Atlantic.
 - Conservative news sources: National Review, The American Spectator, The American Conservative, The New American,
                              The Washington Times, FrontPage Magazine, The Washington Free Beacon, The Blaze, 
                              Cybercast News Service (CNS News), Human Events.
    
First, we make an overall comparison between liberal (denoted by L) and conservative (denoted by C) news sources, then take a deep dive into each website separately. 

<iframe src="plots/sent_vs_time_vs_lib&cons_male&female.html" height="700" width="100%" style="border:none;" scrolling="no"> </iframe>

Here are some facts we take from this analysis:
> **In liberal news sources, women speak on average 16% more positively than men**.

> **In conservative news sources, men speak on average 35% more positively than women**. Although this is not a good thing to see, it isn't completely unexpected.

To observe these differences a bit more clearly, observe the box plot below.

<iframe src="plots/box_sent_lib&cons_male&female.html" height="700" width="100%" style="border:none;" scrolling="no"> </iframe>

For all the statistics enthusiasts out there: don't be worried. We performed a hypothesis test on the claims above and they are statistically significant with a confidence level of 95%.

## News Source Deep Dive

Now that we had an overview of the sentiment score differences with respect to gender and news source category, let's have a closer look into the behavior of individual news sources within our representative news source lists.

<iframe src="plots/websites_L.html" height="700" width="100%" style="border:none;" scrolling="no"> </iframe>

We can see that among the selected liberal news sources The New York Times is the one that portrays quotes with the most similar sentiment scores from males and females, followed by Slate, The Atlantic, Politico and CNN. Whereas Huffington Post is the one with the biggest difference in sentiment scores, followed by Time Magazine. We can also note that 9 out of 10 of the representative liberal news sources have quotes with higher sentiment scores from females, only 1 has a reversed trend, which is The Washington Post.

<iframe src="plots/websites_C.html" height="700" width="100%" style="border:none;" scrolling="no"> </iframe>

We can see that among the selected conservative news sources National Review is the one that portrays quotes with the most similar sentiment scores from males and females, followed by The American Conservative, The American Spectator and The Blaze. Whereas Human Events and The Washington Times are the ones having the biggest difference in sentiment scores. The Washington Times also constitutes the majority of the quotes in the conservative group and therefore is an important factor in the trend towards more positive quotes from men in conservative news sources. By looking at the sizes of the data points in the graphs, in addition to the sentimental differences, we can see that conservative news sources make less use of quotations than liberal news sources.


# Text Complexity

Another metric which can be used to spot bias is the text complexity[^3]. It is true that quotes are, by their very nature, unchangeable. However, the quotes chosen can be very representative of the point of view, or the bias, of a news source. One of the possible choices is the complexity (or difficulty) of the quotes used. In fact, using very complex quotes might alienate the public from the speaker. On the other hand, a systematic usage of very simplistic quotes might give of the illusion of trivial and basic speech. So a systematic usage of too difficult or too simple quotes can project the wrong impression of a group of people.

[^3]: There are several formulas to calculate text complexity. For our purposes, we used the [Dale-Chall Reability Formula](https://en.wikipedia.org/wiki/Dale%E2%80%93Chall_readability_formula)

Here we will focus mainly on the differences between men and women, as we didn't find any significant trends on the minority genders. Moreover, we will split our sources into liberal and conservative, and see how they handle the text complexity for men and women. On the graphs below we show the differences in text complexity by men and women, for a series of conservative and liberal news sources. These results were obtained by averaging out the data from the 6 years available, and the error bars represent the standard deviation of the difference between the two complexities.

<iframe src="plots/text_complexity_cons.html" height="500" width="100%" style="border:none;" scrolling="no"> </iframe>

<iframe src="plots/text_complexity_libr.html" height="500" width="100%" style="border:none;" scrolling="no"> </iframe>

The bars show the difference of complexity between men and women, and hovering over the bars we may see the actual values for men and women. There is a [conversion table](https://en.wikipedia.org/wiki/Dale%E2%80%93Chall_readability_formula) that translates these numbers into an approximation of school level needed to understand the text. We present it below for convenience.

<style>
.tablelines table, .tablelines td, .tablelines th {
        border: 1px solid black;
        padding: 5px;
        }
</style>

| Score        | Interpretation                                                       |
|--------------|----------------------------------------------------------------------|
|4.9 or lower  | easily understood by an average 4th-grade student or lower           |
|5.0 - 5.9     | easily understood by an average 5th or 6th-grade student             |
|6.0 - 6.9     | easily understood by an average 7th or 8th-grade student             |
|7.0 - 7.9     | easily understood by an average 9th or 10th-grade student            |
|8.0 - 8.9     | easily understood by an average 11th or 12th-grade student           |
|9.0 or higher | easily understood by an average 13th to 15th-grade (college) student |
{: .tablelines}

We can see that, comparing the liberal to the conservative websites, the liberal ones are more prone to choose quotes of higher complexity for men than the conservatives. To compare the results we have summarised the key findings in the table below.

| Category     | Metric             | Value  |
|--------------|--------------------|--------|
| Liberal      | Mean Difference    | +0.298 |
| Liberal      | Mean Male Scores   | 9.707  |
| Liberal      | Mean Female Scores | 9.410  |
| Conservative | Mean Difference    | +0.119 |
| Conservative | Mean Male Scores   | 10.458 |
| Conservative | Mean Female Scores | 10.339 |
{: .tablelines}

The results above would appear to present a slight leaning towards higher complexity for male, however a quick statistical test will prove that there is no statistical difference neither in the results Male vs Female neither in Liberal vs Conservative. So we cannot claim that there are any gender biases in the way quotes are handled by the news sources we selected here. 

This is a good sign! At least in the metric of text complexity we cannot spot biases, so there seems to be some equality here :)

# Conclusion
