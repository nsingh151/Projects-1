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

1. [User-User collaborative filtering](https://github.com/navjotsingh151/Projects/wiki/User--User-Collaborative-Filtering)
2. [Item-Item collaborative filtering](https://github.com/navjotsingh151/Projects/wiki/Item---Item-Collaborative-Filtering)
