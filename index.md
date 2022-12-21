---
layout: post
title:  "Once upon a time..."
author: Melanie Brtan, Yehya El Hassan, Antoine Métivier, Etienne Monnin
cover:  "/assets/logo.jpg"
---

Movies have the unique ability to take us on an emotional journey and transport us to different worlds. Whether we're laughing at the antics of a comedy, rooting for the hero in an action flick, or shedding a tear at a heart-wrenching drama, the silver screen has the power to move us in ways that few other forms of entertainment can. 

The film industry is a multi-billion dollar business, with millions of people around the globe flocking to theaters each year to be entertained and touched by the magic of movies. Movies have the power to shape and reflect culture and society, and some films become cultural touchstones that leave a lasting impact on the world. No matter what genre you prefer or what kind of story you enjoy, there is a movie out there for everyone to love and cherish.

![storry telling image](/assets/story_telling.jpeg)

Have you ever been completely captivated by a movie, hanging on every twist and turn of the plot until the very end? That's the power of a well-crafted narrative. But have you ever stopped to think about the types of stories that tend to capture our attention and hold it until the credits roll? In this blog, we set out to investigate the most popular narratives in the film industry, how profitable they are, and how these storylines evolve over time.

To do this, we will examine the movie plots in the CMU Movie Corpus dataset and split them into sentences. We will then perform sentiment analysis on each sentence to construct the various movie arcs and analyze the emotions present in each film. This will allow us to see how these emotions evolve throughout the course of the movie and understand the most prevalent narrative arcs.

Join us as we delve into the world of movie storytelling and uncover the secrets of the most compelling plots. Who knows, maybe we'll even discover the formula for the perfect movie!

## Let us tell you a little story about data

The CMU Movie Summary Corpus Dataset consists of 42,306 movie plot summaries and its meta data. It varies from drama to adventure all the way to fantasy and musicals. 

{% include genres.html %}
Drama, Comedy, Thriller/Action, Romance, and Horror are the kings and queens of the genre world! No shocker there, right? These categories always come out on top and dominate the charts. They're just too darn popular to ignore!

We will create four datasets for analysis, focusing on the genres of drama, comedy, thriller/action, and horror. Horror was chosen over romance because romantic movies often overlap with both drama and comedy in their secondary genre classification

### Movie arcs
For groupying the four main genres, we do not need to explain what the difference between them is. No one would put a comedy movie and a horror movie in the same category. They seem very different from each other, but are they really? We are analyzing the plot of every movie from those four genres. In this little data story, sentiment analysis plays the main role. For every movie, each sentence in the summary gets a continuous sentiment value assigned. This shapes the arc throughout the plot summary.


### (Clustering)
Not only do the arcs differ between the genres but also in the genre itself. With the help of Kmeans clustering, the three most common arcs are derived. By clicking on each genre, the most common clusters and their fraction are shown.



### Emotions in Movies (Rate the feeling)
Every time we watch, rate or talk about a movie, we influence its success. But where does our opinion come from? There could be an subconscious preference and or mutuality for the feeling a movie tries to radiate. Let's have a closer look...

(shorten questions)
#### What is the effect of the presence of emotions on the success of the movie, do emotional movies have a higher IMDB rating? Does the effect differ between genres?

#### What is the effect of the positive/negative emotions on the success of the movie, do movies that are predominently positive (more than 50% of the lines are positive) have a higher IMDB rating? or is the opposite effect true? and do the observed effect vary per genre?




#### What is the most profitable movie arc per genre, is their a clear winner among the various clusters?



#### What is the most rated movie arc per genre, is their a clear winner among the various clusters?



#### Does the most typical movie arc change over time? If so, what are the various movie arcs that take place in various time periods, and what are their profitability and rating?


### emotional vs non-emotional and positive vs negative discussion

### movie arc analysis

