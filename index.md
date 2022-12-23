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
Drama, Comedy, Thriller/Action, Romance, and Horror are the kings and queens of the genre world! No shocker there, right? These categories always come out on top and dominate the charts. They're just too darn popular to ignore! In fact this can be visualized by the follow pie chart that presents the distribution of the genres present in at least 5 movies in the top 100 rated movies. 

{% include pie_distribution.html %}

We will create four datasets for analysis, focusing on the genres of drama, comedy, thriller/action, and horror. Horror was chosen over romance because romantic movies often overlap with both drama and comedy in their secondary genre classification. With that, the corresponding constructed dataset consists of:

| Genre | Dataset Size |
| --- | --- |
| Action | 2476 |
| Horror | 1273 |
| Drama | 7511|
| Comedy | 4602 |


### Movie arcs
The emotional story arc of a movie plot refers to the way the emotions of the characters and the audience change over the course of the film. It is often depicted through a character's journey as they experience a range of emotions, including happiness, sadness, anger, fear, and others.

There are many different variations on the emotional story arc, and the specific emotions that are evoked can vary widely depending on the genre and themes of the film. However, at its core, the emotional story arc is about exploring the emotional experiences of the characters and the way those emotions change and evolve over the course of the story. An American writer Kurt Vonnegut characterized the main story plots into 6 different types: 

 * **Rags to Riches** in which the protagonist rises to success 
 * **Riches to Rags** in which the protagonist falls from success
 * **Man in a Hole** in which the protagonist falls and then rises again 
 * **Icarus** in which the protagonist rises and then falls
 * **Cinderella** in which the protagonist rises, falls, and then rises again
 * **Oedipus** in which the protagonist falls, rises, and then falls again

A pretty interresting video showing Kurt Vonnegut discribing the characterizations can be found [here](https://www.youtube.com/watch?v=oP3c1h8v2ZQ&t=1s "here")

Accordingly, in our analysis, we construct the movie arcs as follows. Let us consider the following plot 

>"The film opens in 1991, with the funeral of a World War II veteran. The man's daughter Marie  delivers the eulogy to a church full of veterans who knew and loved her father, while her mother Ethel Ann  is sitting out on the church porch, smoking and nursing a hangover. When Ethel Ann begins acting strangely, only her friend Jack  seems to understand why. It quickly emerges that there is a lot Marie does not know about her mother's past and the true story of her love life. The movie flips to a time when this mother was young, lively, and optimistic . She is in love with a young farmer, Teddy Gordon , who goes off to war with his best friends Jack, Gregory, Smith  and Chuck, but not all of them make it back alive. The plot lines intertwine with the story of a young Ulsterman in Belfast, Jimmy, who finds a ring in the wreckage of a crashed B-17 and is determined to return it to the woman who once owned it. Inadvertently caught up in cross-border troubles, Jimmy flees Belfast, travelling to Michigan to give Ethel the ring. Ethel reveals a wall covered in souvenirs of Teddy, which Jack and Chuck boarded up for her in 1944. Marie is shocked and furious to learn that her mother loved not Chuck, but Teddy's memory. Ethel travels to Belfast with Jimmy. She holds the hand of a dying British soldier caught in a car-bomb attack. Quinlan  tells Ethel that he was on the hill when Teddy died, and that Teddy's dying words freed Ethel from her promise to love him forever. Joining Ethel in Belfast, Jack admits that he has always loved her. They begin a romance.s." - Closing the Ring, 2007.

We perform sentiment analysis on each line in the plot and smooth the results using a third-order polynomial. The resulting emotion arc is generated accordingly.

{% include emotional_arc.html %}

We created emotional arcs for all the movies in the dataset. The following visualization shows the emotional arcs for a randomly choosen movie in every genre.

{% include emotional_arcs_various.html %}

Visualizing the emotional arc of a single movie may not accurately represent the overall trend for a genre. To get a more accurate picture, it can be helpful to calculate the average sentiment scores for all the movies in the genre.

{% include typical_emotional_arcs_various.html %}

Did you see those plots? They are absolutely mesmerizing! I can't stop staring at them. Do you know why? 

By closely observing the typical movie arcs, we can see that the typical **Action** movie follows a **"Cinderella"** story arc, while a typical **Drama** movie falls between a **"Man in a Hole"** and **"Cinderella"** story arcs. A typical **Comedy** movie on the otherhand follows a **"Man in a Hole"** and the typical **Horror** movie follows a **"Oedipus"** story arc.

The results accurately reflect reality. To demonstrate this, let's compare them to the drama movie "Parasite," released in 2019. "Parasite" follows a poor family who initially lives peacefully but becomes intertwined with a wealthy family. As the movie progresses, increasingly dramatic events unfold, culminating in a murder by a member of the poor family. This marks the most negative point in the movie. The poor family then goes into hiding until the end of the movie, when they are finally free. This can be accurately depicted with the Drama Movie Arc! 

As humans, we crave happy endings and the results reflect this desire. All four genres, even horror, though less clearly, demonstrate an increase in score at the end of the movie.

### A Deeper Dive into each Typical Story arc

The story arcs in different genres can vary significantly. To identify the most common arcs within a genre, we used Time series Kmeans clustering and the Tslearn Library with the soft dynamic time wrapping distance metric. After running the clustering algorithm, each movie in the genre is assigned to a cluster. By finding the barycenter of these clusters, we were able to determine the representative story arc for each cluster.

The representative story arcs for the 3 different clusters found in the Action genre are:

{% include Action_clusters.html %}

The representative story arcs for the 4 different clusters found in the Drama genre are:

{% include Drama_clusters.html %}

The representative story arcs for the 3 different clusters found in the Comedy genre are:

{% include Comedy_clusters.html %}

The representative story arcs for the 3 different clusters found in the Horror genre are:

{% include Horror_clusters.html %}

We used the tslearn library to cluster the emotional arcs of movies by genre using two different representations of time series data and the Silhouette score to evaluate the quality of the clusters and choose the optimal number of clusters. 

{% include silhoutte.html %}

According to the silhouette graph, the optimal number of clusters for action movies is 3, for drama movies is 4, for comedy movies is 3, and for horror movies is 3. Additionally, using discrete features rather than continuous features results in a higher silhouette score. Therefore, we use the resulting number of clusters and discrete features to perform timeseries clustering.

You may be wondering which cluster within each genre is the most successful in terms of profitability and IMDB rating. Let's continue uncovering the perfect recipe for a successful movie in each genre.

### Emotions in Movies (better title needed)
Now that we know, how the most present clusters look like, it appears that some genres are more emotional compared to others. But how does emotion affect the movie in terms of success by ratings and revenue? First of all, we need to classify the different emotions. A movie is considered either positive, neutral, or negative when more than 50% of the sentences are assigned to the corresponding sentiment value (+1/0/-1). 
To categorize this further, emotional movies include positive and negative movies, whereas non-emotional movies consist of only neutral movies.

{% include emo_pl.html %}

add that many drama's exist

As shown above, clearly more emotional movies exist in every genre. Whereas the negative movies dominate for all all genres except for Drama. Does this mean, that the demand for movies with negative sentiments is higher than for positive movies? To include the viewer’s ratings, an additional dataset from IMDb was used. So, we can compare the mean rating for emotional and non-emotional movies in every genre:

{% include bars_ratings_emo_nonemo.html %}

As well as for the ratings of positive and negative movies:

{% include bars_ratings_pn.html %}

The higest rated genre is in both cases Drama, which is also contains the highest number of movies, while Horror movies are not something for everybody. The interesting point is that, for all genres, people tend to prefer emotional movies, to be more specific, emotional movies with negative scences. For some genres like Action, the difference is not as high in the comparison of emotional and non-emotional movies as it is for positive and negative movies. 

#### Is it possible for a film to excel without tugging at our heartstrings?
To discuss, wheather the presence of emotions impact on the success of the movie, in form of leading to a higher IMDB rating, we have performed statistical tests to find a correlation. For every genre, the confidence level in reference to emotions and ratings in the movies were obtained and their p-values. 

add table or any kind of cool matrix about p vals
(why pval of horror so high even though the difference is visible?)

Unfortunately, no p-value smaller of equal 0.05 were obtained, so that no effect could have been observed. But to examine this result a little further, we performed the same tests exept by distinguishing by positive and negative movies. 

add table or any kind of cool matrix

Eureka! For the emotional movies a significant effect has been found. In Action and Drama movies it shows that negative movies have an effect on the rating. In both cases the negative movies are higher rated. (add why do people prefer negative sentiments?) For the categories Horror and Comedy, the lacking correlation is due to the fact that the performed sentiment analysis, which was performed on the plot, does not reflect the emotions during the movie itself. As the jokes from a comedy movie won't be written in the plot discription.

(are the plots of ratings and counts over the years necessary? -> if yes, i need to change because title not right)

//{% include timeline_rating_en_action.html %}
//
//{% include timeline_rating_en_horror.html %}
//
//{% include timeline_rating_en_drama.html %}
//
//{% include timeline_rating_en_comedy.html %}
//
//
//{% include timeline_ID_en_action.html %}
//
//{% include timeline_ID_en_horror.html %}
//
//{% include timeline_ID_en_drama.html %}
//
//{% include timeline_ID_en_comedy.html %}

//explain a little more for question 2.1 and 2.2



### Movie Arc analysis/Noah's Arc to success (better title needed)
The best way to measure success in the movie industry, are ratings and revenues. After getting to know about the ratings, it is time to talk about buisness. Based on the sales of the movie's box office, the revenue determines the profitability of a movie. Going back to the beginning of this data story, where we have identified the most common movie arcs in every genre, we want to know for which movie arc will predict success. 

##### Revenue
To find the most profitable movie arc, we have analyzed the box office over the year for each arc by calculating the confidence level and p-value. It presents, which arc has the most sales over a certain amount of time and its significance. (the analsysis results also already explain for question 2.5?) 

plots and confusion matrix or so for the many values

(add analysis which one it is)


##### Ratings
With the same aim to find the best movie arc but in terms of ratings, we we want to find the most rated one among the others. Following the same procedure as before we obtain those findings:

plots and confusion matrix or so for the many values

(add analysis which one it is)


(Sum up which ones are the best from ratings and profit)
Much has changed over the years and so did cinema. But did the story lines/movie arcs change too? By presenting the best arcs in relation to revenue and ratings, we show the evolution of the arc in a timeline. Comparing the rating and revenue in the same plot, indicates certain changes over time and visualizes its commonalities.

add plots over time of only best arc per genre with box office and ratings in same plot to compare

### Conclusion
