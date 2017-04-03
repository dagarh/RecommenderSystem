# Recommender System

A **recommender system** or a **recommendation system** (sometimes replacing "system" with a synonym such as platform or engine) is a subclass of **information filtering system** that seeks to predict the "rating" or "preference" that a user would give to an item.

**Recommender systems** have become increasingly popular in recent years, and are utilized in a variety of areas including movies, music, news, books, research articles, search queries, social tags, and products in general. There are also recommender systems for experts,collaborators,jokes, restaurants, garments, financial services,life insurance, romantic partners (online dating), and Twitter pages. 

<href> https://en.wikipedia.org/wiki/Recommender_system; http://blogs.gartner.com/martin-kihn/how-to-build-a-recommender-system-in-python/ </href>

a) **Content Based Filtering** >> Item -Item 

    This doesn’t need much prerequisite data (ratings given by user and implicit user preference).Thus avoid cold-start </br>    problem. They can detect and recommend very well on Items similar to what a user has already liked or rated. But not         so good at suggesting something new, altogether different which might be a potential like for a user.

    Distance based Metric can be used based on similarity or dissimilarity. Distance based algorithm like - Euclidean,           Pearson, Cosine similarity are some of main measures. Neighbour or cluster based approaches can be taken. K-means             clustering for similarity assessment.

b) **Collaborative Filtering** >> Item-Item, User-Item.

    Item-Item Collaborative Technique: Market-Basket - i.e. Items which are tends to be purchased along with other items.         Frequent ride-along items.

    $$ For each item in your catalog - For each customer who bought it - For each other item bought by this customer - >>         Record that customer bought both items; After this we have to figure/measure similarity between/among these items, based     on above handy record.

    Steps to do>> Have a list of item, Calculate a distance between each item, recommend items that were close to items that     user liked/bought.

    >> Here in this Happy World, users have explicitly told us what they like and what they don’t. But here we have horrible     sparsity problem. Our solution to this would be to get a list of users who have rated Item-1, Item-2 separately; and find     out where they overlap (this will give a list of reviewers who have rated both items); Using scikit-learn it can be done     as mentioned below.

    In this way, we can determine if people who like Item1 are also likely to like Item2. This evaluation works in opposite       direction as well, if a person like Item1 and hates Item2 (high distance). 

c) **Collaborative Filtering** >> User- Item filtering technique. 

    It works like this: Take a bunch of people who have rated things, calculate the distance between each pair of people         based on their ratings, Find other people who are most similar to you, Recommend things to you that ‘people like you’         also have liked.

    In simplistic manner, way to calculate similarity between two users-

    This function just subtracts all the reviews of user 1 from user 2’s and returns the average. That’s it. It’s Euclidean.     Here to deal with problem of sparsity, it has been assumed - a missing review was actually equal to the mean rating for       that item. So everybody rated everything whether they wanted to or not — either in reality or by assuming the mean. 

    $$ Netflix prize for predicting start ratings for movies - for which user has not provided ratings yet. Here solid           collaborative filtering technique was used. 

    Here out of available lot of star ratings, one approach is to deconstruct the start ratings into different components,       as-

    Average Rating for an item- this is the best starting point we have;  User Bias- some individual people can be easier or     harder grader than the average;  User Similarity to (fans or haters)- reflecting how much we look like people ‘who have       liked/disliked item’;

    These 3 things can be put together in a formula that gives/churns out a star rating recommendation. 

    “user_bias,” which is simply the average of that user’s rating difference from the mean of all raters.


    Now, the user similarity to fans or haters is just a similarity calculation that we saw above. In this case, it’s applied     to a subset of users who count as “fans” (which could be defined as people who rated the item above the mean) or “haters”     (the opposite). For kicks, it might look something like this:

    simple function that added up the item mean, the user bias, and the adjustment for similarity to fans or haters.
