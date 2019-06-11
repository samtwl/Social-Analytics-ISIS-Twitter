# Social-Analytics-ISIS-Twitter
This repository contains the analysis of ISIS network on twitter.

## Background and Objective
The Islamic State in Iraq and Syria (ISIS) is a well-known terrorist organization that has been using the power of social media to spread propaganda, influence people who are susceptible to radicalization and enlist new fighters (Alfifi, Kaghazgaran, Caverlee, & Morstatter, 2018). More recently, with ISIS gradually losing their major bases with the fall of Mosul and Raqqa, there is greater concern that more fighters would turn to social media to continue spreading radical beliefs (Hussain, 2019).

By understanding how terrorists and their supporters use social media, identifying these users and their relationships, as well as evaluating the impact that social media has had in enabling terrorism through influence, we can formulate strategies to counter their methods and reduce the number of people being radicalized online (Bodine-Baron, Helmus, Magnuson, & Winkelman, 2016). Our objective is therefore to analyse Twitter data to understand how extremist ideology is spread on the platform, determine key ISIS influencers and analyze the relationships between these influencers and ISIS supporters. 

## Our Main Datasets
The following table delineates the metadata of the three main datasets that our project will be using:

| How ISIS Uses Twitter from Kagle | ACLED Anti-Civilian Violence | List of terrorist incidents linked to ISIL |
| --- | --- | --- |
| <br>1.	Name</br> <br>2.	Username</br> <br>3.	Description</br> <br>4.	Location</br> <br>5.	Number of followers at the time the tweet was downloaded</br> <br>6.	Number of statuses by the user when the tweet was downloaded</br> <br>7.	Data and timestamp of the tweet</br> <br>8.	The tweet itself</br> | <br>1.	Event Date</br> <br>2.	Actor1 (i.e. Islamic State (Egypt))</br> <br>3.	Actor2 (i.e. Civilians (Egypt))</br> <br>4.	Region</br> <br>5.	Country</br> <br>6.	Latitude</br> <br>7.	Longitude</br> <br>8.	Number of Fatalities</br> | <br>1.	Country</br> <br>2.	Date</br> <br>3.	Article</br> <br>4.	Description</br> <br>5.	Dead</br> <br>6.	Injured</br> <br>7.	Status</br> |

## Our Approach for the Main Datasets
### 1.   Data Pre-Processing Exploration
Prior to generating graphs for network analysis, we have to first perform the following data pre-processing steps:
A.	Check that there are no duplicate tweets based on exact string matching
B.	Separate original tweets and retweets. Tweets that contain “RT” at the beginning are to be classified as retweets. 
C.	After separating the original tweets and retweets, they are grouped based on the usernames. Each username’s original tweets will then be iterated through to identify mentioned usernames.
D.	Having identified the sender and receiver relationship between usernames, each username will be represented by a node, and we will map edges between these nodes based on their interaction with each other (tweets and retweets). Furthermore, edges will be weighted based on the number of tweets sent between usernames.

Next, basic data exploration will be performed to generate basic network statistics such as the number of nodes and edges, and the distribution of node degrees.

### 2.   Pro-ISIS Network Influence Analysis 
This approach aims to identify the major players (determine by few criteria, such as number of followers, number of tweets & retweets, frequency mentioned, etc.) in the pro-ISIS twitter network and to study the relationship structure that links individual followers (users who retweet or mentioned in the message) to these major players, and the interdependencies (with the weight measures by the frequency of the retweet or mentioned) between them. Additionally, we want to visualize how the number of followers for each major influencer changes over time.

### 3.     Keyword and Sentiment Analysis
Upon identifying the major influencers and their significance in the pro-ISIS network, we want to understand the choice of words that they used to influence their followers and to understand its coincidental rate with major ISIS attack events. For example, keywords derived from the tweets may coincide right after major ISIS events as a means to instigate or incite further violence.
 
Further to keyword analysis, we want to identify the religious leader that pro-ISIS users quote the most, and to understand towards which religious leader they show positive, neutral or negative sentiments to.

### 4.     Data Categorization of Links and Network Diffusion Analysis 
In this approach, we want to understand which external media (mainstream media and Jihadist websites) ISIS fanatics link to, and to investigate how these links propagate throughout the pro-ISIS network.

### 5.     Time-series Analysis 
To conclude, we aim to visualize the number of tweets over a timeline, and to track the changes in the major players in the network over time.


