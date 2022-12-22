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
Drama, Comedy, Thriller/Action, Romance, and Horror are the kings and queens of the genre world! No shocker there, right? These categories always come out on top and dominate the charts. They're just too darn popular to ignore! In fact this can be visualized by the follow pie chart that presents the distribution of the genres present in at least 5 movies in the top 100 movies. 

{% include pie_distribution.html %}

We will create four datasets for analysis, focusing on the genres of drama, comedy, thriller/action, and horror. Horror was chosen over romance because romantic movies often overlap with both drama and comedy in their secondary genre classification.

### Movie arcs
The emotional story arc of a movie plot refers to the way the emotions of the characters and the audience change over the course of the film. It is often depicted through a character's journey as they experience a range of emotions, including happiness, sadness, anger, fear, and others.

The emotional story arc usually follows a predictable pattern, with the characters starting in a state of normalcy or equilibrium, facing challenges or conflicts that bring about change, and ultimately resolving those conflicts and reaching a new state of equilibrium or understanding. This pattern is often referred to as the "hero's journey" or the "monomyth," and it has been used in countless films and other forms of storytelling.

There are many different variations on the emotional story arc, and the specific emotions that are evoked can vary widely depending on the genre and themes of the film. However, at its core, the emotional story arc is about exploring the emotional experiences of the characters and the way those emotions change and evolve over the course of the story. An American writer Kurt Vonnegut characterized the main story plots into 6 different types: 

 * "Rags to Riches," in which the protagonist rises to success 
 * "Riches to Rags," in which the protagonist falls from success
 * "Man in a Hole," in which the protagonist falls and then rises again 
 * "Icarus," in which the protagonist rises and then falls
 * "Cinderella," in which the protagonist rises, falls, and then rises again
 * "Oedipus," in which the protagonist falls, rises, and then falls again

A pretty interresting video showing Kurt Vonnegut discribing the characterizations can be found here ![story plot characterization] (https://www.youtube.com/watch?v=oP3c1h8v2ZQ&t=1s)

Accordingly, in our analysis, we construct the movie arcs as follows. Let us consider the following plot 

>"The film opens in 1991, with the funeral of a World War II veteran. The man's daughter Marie  delivers the eulogy to a church full of veterans who knew and loved her father, while her mother Ethel Ann  is sitting out on the church porch, smoking and nursing a hangover. When Ethel Ann begins acting strangely, only her friend Jack  seems to understand why. It quickly emerges that there is a lot Marie does not know about her mother's past and the true story of her love life. The movie flips to a time when this mother was young, lively, and optimistic . She is in love with a young farmer, Teddy Gordon , who goes off to war with his best friends Jack, Gregory, Smith  and Chuck, but not all of them make it back alive. The plot lines intertwine with the story of a young Ulsterman in Belfast, Jimmy, who finds a ring in the wreckage of a crashed B-17 and is determined to return it to the woman who once owned it. Inadvertently caught up in cross-border troubles, Jimmy flees Belfast, travelling to Michigan to give Ethel the ring. Ethel reveals a wall covered in souvenirs of Teddy, which Jack and Chuck boarded up for her in 1944. Marie is shocked and furious to learn that her mother loved not Chuck, but Teddy's memory. Ethel travels to Belfast with Jimmy. She holds the hand of a dying British soldier caught in a car-bomb attack. Quinlan  tells Ethel that he was on the hill when Teddy died, and that Teddy's dying words freed Ethel from her promise to love him forever. Joining Ethel in Belfast, Jack admits that he has always loved her. They begin a romance.s." - Closing the Ring, 2007.

We perform a sentiment Analysis for every line in the plot and then smoothed using a polynomial of order 3, accordingly the generated emotion arc is

{% include emotional_arc.html %}

We created emotional arcs for all the movies in the dataset. The following visualization shows the emotional arcs for a randomly choosen movie in every genre.

{% include emotional_arcs_various.html %}

Visualizing the emotional arc of a single movie may not accurately represent the overall trend for a genre. To get a more accurate picture, it can be helpful to calculate the average sentiment scores for all the movies in the genre.

{% include typical_emotional_arcs_various.html %}

Did you see those plots? They are absolutely mesmerizing! I can't stop staring at them. Do you know why? 

By closely observing the typical movie arcs, we can see that the typical action movie follows a "Cinderella" story arc, while both the Drama and Comedy follows a "Man in a Hole" and the horror movie follows a "Oedipus" story arc.

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

