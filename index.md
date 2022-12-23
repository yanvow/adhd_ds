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
Drama, Comedy, Thriller/Action, Romance, and Horror are the kings and queens of the genre world! No shocker there, right? These categories always come out on top and dominate the charts. They're just too darn popular to ignore! In fact this can be visualized by the following pie chart that presents the distribution of the genres present in at least 5 movies in the top 100 rated movies. 

{% include pie_distribution.html %}

We focused on analyzing four datasets of the genres drama, comedy, thriller/action, and horror. Horror was chosen over romance because romantic movies often overlap with both drama and comedy in their genre classification. The corresponding dataset we constructed consists of:

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

>"<span style="color:red">The film opens in 1991, with the funeral of a World War II veteran</span>. <span style="color:green">The man's daughter Marie delivers the eulogy to a church full of veterans who knew and loved her father, while her mother Ethel Ann is sitting out on the church porch, smoking and nursing a hangover </span>. <span style="color:green"> When Ethel Ann begins acting strangely, only her friend Jack  seems to understand why. It quickly emerges that there is a lot Marie does not know about her mother's past and the true story of her love life </span>. <span style="color:green"> The movie flips to a time when this mother was young, lively, and optimistic</span>. <span style="color:green"> She is in love with a young farmer, Teddy Gordon, who goes off to war with his best friends Jack, Gregory, Smith  and Chuck, but not all of them make it back alive</span>. <span style="color:green"> The plot lines intertwine with the story of a young Ulsterman in Belfast, Jimmy, who finds a ring in the wreckage of a crashed B-17 and is determined to return it to the woman who once owned it</span>. <span style="color:red"> Inadvertently caught up in cross-border troubles, Jimmy flees Belfast, travelling to Michigan to give Ethel the ring. <span style="color:orange"> Ethel reveals a wall covered in souvenirs of Teddy, which Jack and Chuck boarded up for her in 1944</span>. <span style="color:red"> Marie is shocked and furious to learn that her mother loved not Chuck, but Teddy's memory </span>. <span style="color:orange"> Ethel travels to Belfast with Jimmy</span>. <span style="color:orange">She holds the hand of a dying British soldier caught in a car-bomb attack</span>. <span style="color:green"> Quinlan  tells Ethel that he was on the hill when Teddy died, and that Teddy's dying words freed Ethel from her promise to love him forever </span>. <span style="color:green">Joining Ethel in Belfast, Jack admits that he has always loved her </span>. <span style="color:green">They begin a romance. </span>" - <span style = "color:#333">Closing the Ring, 2007.</span>

We do sentiment analysis on each line in the plot. As a result, the above plot has been marked with green meaning positive, orange neutral, and red denoting negative. The sentiment scores are saved in two formats: continuous scores and discrete classifications. The discrete class representation will be utilized to classify the type of movie, as will be detailed later. The resultant emotion arc is formed as a result.

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

### The Emotional Influence of Movies: How Does Sentiment Affect Success?

Now that we have a better understanding of the most prevalent clusters, it appears that certain genres tend to be more emotional compared to others. But how does the presence of emotion impact the success of a movie, as measured by ratings and revenue? To analyze this, we will first classify the different emotions present in a movie. A movie can be classified as positive, neutral, or negative if over 50% of the sentences in the movie are assigned one of these sentiment values (positive +1 / neutral 0 /negative -1). We can further categorize these movies as emotional (including both positive and negative movies) or non-emotional (consisting only of neutral movies).

{% include emo_pl.html %}

As shown above, clearly more emotional movies exist in every genre. Whereas the negative movies dominate for all all genres except for Drama. Does this mean, that the demand for movies with negative sentiments is higher than for positive movies? To include the viewer’s ratings, an additional dataset from IMDb was used. So, we can compare the mean rating for emotional and non-emotional movies in every genre:

{% include bars_ratings_emo_nonemo.html %}

As well as for the ratings of positive and negative movies:

{% include bars_ratings_pn.html %}
  

#### Is it possible for a film to excel without tugging at our heartstrings?
  
It's interesting to see that drama is the highest rated genre, while horror is the lowest. Some possible reasons for why drama might be more highly rated could include:

 * Drama films often explore complex, relatable themes and emotions, which can be highly compelling for many viewers.
 * Many drama films are based on true stories or historical events, which can be highly engaging for viewers who are interested in learning more about the world around them.

On the other hand, there could be a variety of reasons why horror films are not as highly rated as drama films. Some possible reasons could include:

  * Horror films are designed to be scary and unsettling, which can be off-putting for some viewers.
  * Horror films often feature graphic violence or gore, which can be too much for some people to handle.

#### Is it possible for a film to excel without tugging at our heartstrings?
We conducted statistical tests to investigate whether the presence of emotions in a movie impacts its success, as measured by its IMDB rating. We examined the correlation between emotions and ratings for each film genre and obtained p-values to gauge the confidence level of our findings.

Unfortunately, we did not observe any significant effect, as none of the p-values were smaller than or equal to 0.05. However, we conducted additional tests to further examine this result by distinguishing between positive and negative movies. The results of these tests are currently being analyzed.

{% include em_pm.html %}

#### Okay then!... Which do we prefer: positive or negative themed movies?
  
We are thrilled to announce that our analysis has uncovered a significant impact of emotions on movie ratings in the Action and Drama genres! Our findings indicate that negative movies in these genres tend to be rated higher than positive movies.

It is worth noting that our analysis did not reveal a correlation between emotions and ratings in the Horror and Comedy genres. This may be because the sentiment analysis we conducted, which was based on the movie plot descriptions, does not accurately reflect the emotions experienced during the movie itself. For example, the jokes in a comedy movie may not be conveyed in the plot description.

### Let's proceed! ...Let us add the Movie Arcs into our Analysis.
Movie clusters within the same genre can be evaluated by visualizing their average ratings. This can help us find the most popular and highly rated movies within a genre. Try exploring your favorite genres and see which clusters come out on top.

{% include cluster_ratings.html %}

From the bar plots, it is clear that there is no clear winner between the clusters in the Action and Horror genres. However, in the Drama and Comedy genres, a significant difference in ratings between clusters exists. Specifically, cluster 3, which represents the 'Cinderella' story arc, is the highest rated in the Drama genre. In the Comedy genre, cluster 3, the 'Man in the Hole' arc, is also the highest rated.

##### Ratings
With the same aim to find the best movie arc but in terms of ratings, we we want to find the most rated one among the others. Following the same procedure as before we obtain those findings:
  
{% include most_rated_arc.html %}


##### Revenue
The best way to measure success in the movie industry, are ratings and revenues. After getting to know about the ratings, it is time to talk about buisness. Based on the sales of the movie's box office, the revenue determines the profitability of a movie. Going back to the beginning of this data story, where we have identified the most common movie arcs in every genre, we want to know for which movie arc will predict success. 
  
To find the most profitable movie arc, we have analyzed the box office over the year for each arc by calculating the confidence level and p-value. It presents, which arc has the most sales over a certain amount of time and its significance. (the analsysis results also already explain for question 2.5?) 

{% include most_profitable_arc.html %}

(add analysis which one it is)
plots and confusion matrix or so for the many values

(add analysis which one it is)


(Sum up which ones are the best from ratings and profit)
Much has changed over the years and so did cinema. But did the story lines/movie arcs change too? By presenting the best arcs in relation to revenue and ratings, we show the evolution of the arc in a timeline. Comparing the rating and revenue in the same plot, indicates certain changes over time and visualizes its commonalities.

add plots over time of only best arc per genre with box office and ratings in same plot to compare

### Conclusion
