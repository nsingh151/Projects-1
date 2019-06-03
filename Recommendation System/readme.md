## What are recommendation engines?
Till recently, people generally tended to buy products recommended to them by their friends or the people they trust. This used to be the primary method of purchase when there was any doubt about the product. But with the advent of the digital age, that circle has expanded to include online sites that utilize some sort of recommendation engine.

**A recommendation engine filters the data using different algorithms and recommends the most relevant items to users. It first captures the past behavior of a customer and based on that, recommends products which the users might be likely to buy.**

## How does a recommendation engine work?
Before we deep dive into this topic, first we’ll think of how we can recommend items to users:

1. We can recommend items to a user which are most popular among all the users
2. We can divide the users into multiple segments based on their preferences (user features) and recommend items to them based on the segment they belong to

## Content based filtering
This algorithm recommends products which are similar to the ones that a user has liked in the past.

![](https://github.com/navjotsingh151/Projects/blob/master/Recommendation%20System/Images/Content%20Based%20Filtering.PNG)

**For example**, if a person has liked the movie “Inception”, then this algorithm will recommend movies that fall under the same genre. But how does the algorithm understand which genre to pick and recommend movies from?

<img class="aligncenter wp-image-44895 " src="https://s3-ap-south-1.amazonaws.com/av-blog-media/wp-content/uploads/2018/05/Screenshot-from-2018-05-31-14-28-18.png" alt="" width="275" height="73" srcset="https://s3-ap-south-1.amazonaws.com/av-blog-media/wp-content/uploads/2018/05/Screenshot-from-2018-05-31-14-28-18.png 339w, https://s3-ap-south-1.amazonaws.com/av-blog-media/wp-content/uploads/2018/05/Screenshot-from-2018-05-31-14-28-18-300x80.png 300w" sizes="(max-width: 275px) 100vw, 275px">

Based on the cosine value, which ranges between -1 to 1, the movies are arranged in descending order and one of the two below approaches is used for recommendations:

1. Top-n approach: where the top n movies are recommended (Here n can be decided by the business)
2. Rating scale approach: Where a threshold is set and all the movies above that threshold are recommended

## Collaborative filtering

Let us understand this with an example. If person A likes 3 movies, say Interstellar, Inception and Predestination, and person B likes Inception, Predestination and The Prestige, then they have almost similar interests. We can say with some certainty that A should like The Prestige and B should like Interstellar. The collaborative filtering algorithm uses “User Behavior” for recommending items. This is one of the most commonly used algorithms in the industry as it is not dependent on any additional information. There are different types of collaborating filtering techniques and we shall look at them in detail below.

1. User-User collaborative filtering
2. Item-Item collaborative filtering

### User-User collaborative filtering

This algorithm first finds the similarity score between users. Based on this similarity score, it then picks out the most similar users and recommends products which these similar users have liked or bought previously.

<img aria-describedby="caption-attachment-44903" class="wp-image-44903 " src="https://s3-ap-south-1.amazonaws.com/av-blog-media/wp-content/uploads/2018/05/0o0zVW2O6Rv-LI5Mu1.png" alt="" width="714" height="391" srcset="https://s3-ap-south-1.amazonaws.com/av-blog-media/wp-content/uploads/2018/05/0o0zVW2O6Rv-LI5Mu1.png 1520w, https://s3-ap-south-1.amazonaws.com/av-blog-media/wp-content/uploads/2018/05/0o0zVW2O6Rv-LI5Mu1-300x164.png 300w, https://s3-ap-south-1.amazonaws.com/av-blog-media/wp-content/uploads/2018/05/0o0zVW2O6Rv-LI5Mu1-768x421.png 768w, https://s3-ap-south-1.amazonaws.com/av-blog-media/wp-content/uploads/2018/05/0o0zVW2O6Rv-LI5Mu1-850x466.png 850w" sizes="(max-width: 714px) 100vw, 714px">

Following steps are followed to do so:

1. For predictions we need the similarity between the user u and v. We can make use of Pearson correlation.
2. First we find the items rated by both the users and based on the ratings, correlation between the users is calculated.
3. The predictions can be calculated using the similarity values. This algorithm, first of all calculates the similarity between each 4. user and then based on each similarity calculates the predictions. Users having higher correlation will tend to be similar.
4. Based on these prediction values, recommendations are made. Let us understand it with an example:


Consider the user-movie rating matrix:

<tbody>
<tr>
<td style="text-align: center;">User/Movie</td>
<td>x1</td>
<td>x2</td>
<td>x3</td>
<td>x4</td>
<td>x5</td>
<td>Mean User Rating</td>
</tr>
<tr>
<td style="text-align: center;">A</td>
<td>4</td>
<td>1</td>
<td>–</td>
<td>4</td>
<td>–</td>
<td style="text-align: center;">3</td>
</tr>
<tr>
<td style="text-align: center;">B</td>
<td>–</td>
<td>4</td>
<td>–</td>
<td>2</td>
<td>3</td>
<td style="text-align: center;">3</td>
</tr>
<tr>
<td style="text-align: center;">C</td>
<td>–</td>
<td>1</td>
<td>–</td>
<td>4</td>
<td>4</td>
<td style="text-align: center;">3</td>
</tr>
</tbody>


Here we have a user movie rating matrix. To understand this in a more practical manner, let’s find the similarity between users (A, C) and (B, C) in the above table. Common movies rated by A/[ and C are movies x2 and x4 and by B and C are movies x2, x4 and x5.

<img class="aligncenter wp-image-45280 size-full" src="https://s3-ap-south-1.amazonaws.com/av-blog-media/wp-content/uploads/2018/06/Screenshot-from-2018-06-21-10-52-35.png" alt="" width="764" height="77" srcset="https://s3-ap-south-1.amazonaws.com/av-blog-media/wp-content/uploads/2018/06/Screenshot-from-2018-06-21-10-52-35.png 764w, https://s3-ap-south-1.amazonaws.com/av-blog-media/wp-content/uploads/2018/06/Screenshot-from-2018-06-21-10-52-35-300x30.png 300w" sizes="(max-width: 764px) 100vw, 764px">


The correlation between user A and C is more than the correlation between B and C. Hence users A and C have more similarity and the movies liked by user A will be recommended to user C and vice versa.

It has the following drwabacks

 This algorithm is quite time consuming as it involves calculating the similarity for each user and then calculating prediction for each similarity score. One way of handling this problem is to select only a few users (neighbors) instead of all to make predictions, i.e. instead of making predictions for all similarity values, we choose only few similarity values.There are various ways to select the neighbors:

1. Select a threshold similarity and choose all the users above that value
2. Randomly select the users
3. Arrange the neighbors in descending order of their similarity value and choose top-N users
4. Use clustering for choosing neighbors


This algorithm is useful when the number of users is less. Its not effective when there are a large number of users as it will take a lot of time to compute the similarity between all user pairs. This leads us to **item-item collaborative filtering**, which is effective when the number of users is more than the items being recommended.



