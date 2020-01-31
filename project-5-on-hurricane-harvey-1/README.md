# Project 5: Utilizing Social Media to Provide Disaster Relief

---
## **Problem Statement**

 Using trending hashtags and keywords, can a model read through social media posts and locate users in need of emergency assistance in a disaster?

---
## **Executive Summary**

Due to the availability and access to Twitter users tweets we decided to start our idea simple. There are many social media platforms out there and with additional time most can be scraped and analyzed into a similar format we collected from Twitter.  One of the major benefits of developing the app the way we did was that all of the information that was collected is openly available to any public users. 

Although our training data was gathered from Kaggle.com we did include the scraper that was developed to search and scrape keywords from Twitter. We decided to start with a local storm that we knew had a large presence on social media when it took place. Hurricane Harvey was our primary target when training and testing our model. The Kaggle training set that was selected included a larger scope of storms and keywords, but it also included a human verified column that listed whether the tweet was “relevant” or not to our problem statement. We decided to start broad due to this data set being the most convenient and later focus our efforts on specific storms/events in the future. 

Our plan was to train a model on the relevant tweets and test on a new data set of unseen tweets that we could then review and verify how our model was doing.  Once our test tweets had been separated into relevant and non relevant, we planned to filter the relevant ones to find “urgent” tweets. Urgent tweets we would define as users being in immediate danger or calling for assistance.  Once we’ve separated the urgent tweets we had planned to look for locational data to map the users. Unfortunately we were unable to collect any geo location data from our tweet data set. Although Twitter does keep this information private, there was no way our team had any access to it. We had planned to continue on with out idea and eventually be able to plot the urgent users on a heat map for emergency teams to review and locate neighborhoods to allocate more resources towards.


---
## **Data Information**
|Feature|Type|Description|
|:---|:---|:---|
|**id**|*int*|unique user twitter id|
|**tweets**|*object*|user posts|
|**date**|*datetime*|date and time of posted tweet|

---
## **Our Model**
Looking at the data, we knew that we would need to find a method to quickly and efficently classify a large number of tweets for use by emergency responders. To do this we started by training a model with pre-labeled tweets. The dataset looked at a variety of disasters, not limited to natural disasters. We evaluated the performance of various models and saw that the most accurate performance on the training dataset was form a ensemble model. This idea combined three classifying models together.

When the Harvey twitter dataset was applied to model performance suffered in the sense that, the model felt that 58% of all tweets were being classified as disaster tweets. This breaks down to over 228,000 tweets. Far too many for emergency responders to look at efficiently. Looking at the tweets that were classified we noticed that if a word deemed relevant by the model was repeated more than once the model felt it was a relevant tweet. This made it very difficult to see what could be considered an eergency.

From this point we took a list of words from CrisisNLP that were considered to be releveant in emergency situations. We cut the list down to words we felt were relevant to this particular disaster, and words people might use when in need of help. Doing this cut the number of tweets down to just over 13,000. The tweets in this set were predominently from individual humans, instead of news agencies, but the model was still unable to filter out tweets that were form those needing rescue.

---
## **Conclusions/Recommendations**
For any future development of this idea we would recommend gathering a significantly larger size data set to train the model on. In order to go any further with our model you would also need to verify the new larger data set. We would also recommend trying to focus the data on only social media posts that have location data that way the mapping side of things can be developed further.

While in theory our app should have been relatively straightforward. We’ve come across many hurdles in the data collection side of things. In the future, we’d like to try an unsupervised model instead of attempting to have humans verify each individual tweet in our data set. We’d like to attempt to search for “relevant” and “urgent” tweet clusters and target those. Our “go” words that we use to filter those urgent tweets also needs to be expanded upon. Additionally, another major future improvement would be language support. We understand that not everyone in the U.S. speaks English and we felt it unrealistic to only search and model for those users. For the sake of simplicity and the time constraints, English is the only language supported at this time. 

Twitter blocks the access to users location data and this has completely hindered us from being able to provide a visual representation of how our app will eventually work once fully developed. We have good scraper for social media (Twitter), a good model for finding actual storm tweets from users, and we have a good idea of where we’d like to go in the future. This project is not yet complete but we believe it shows a great amount of potential for future development.

---
## Sources
* https://comptroller.texas.gov/economy/fiscal-notes/2018/special-edition/impact.php
* https://www.forbes.com/sites/greatspeculations/2017/09/05/we-looked-into-the-effects-of-hurricane-harvey-and-heres-what-we-found/#d68034e76f13
* https://www.npr.org/sections/alltechconsidered/2017/08/28/546831780/texas-police-and-residents-turn-to-social-media-to-communicate-amid-harvey
* https://www.wsj.com/articles/hurricane-harvey-victims-turn-to-social-media-for-assistance-1503999001
* https://time.com/4921961/hurricane-harvey-twitter-facebook-social-media/
* https://www.thebalance.com/hurricane-harvey-facts-damage-costs-4150087
* https://en.wikipedia.org/wiki/Hurricane_Harvey
* https://crisisnlp.qcri.org/
