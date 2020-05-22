Live Leaderboard
=================

Using the Account Activity, Direct Message, and Post Tweet APIs, this Twitter chatbot listens for incoming scores, ranks them, and Tweets the rankings. This app supports public announcements and private data/vote submissions.

This example was written to keep golf scores, but the underlying patterns are general enough to serve many other use cases. 

**What does the bot do?**
+ Keeps track of all teams scores in real-time on Twitter
+ Tweets out updates (Leaderboards and Birdie Alerts!) 
+ Foster engagement and get people talking about the event and interacting with the scorer account. 

**To learn more about the event this pilot was developed for, see the following:** 
+ The use case inspiration for this code base is HERE [insights.twitter.com].
+ For more discussion of the code developed for this pilot, see HERE [dev.to/building-a-live-leaderboard-on-Twitter]

Getting started 
===============

So, here is what you'll need to get started:

+ Python3 environment with the Flask web framework.
+ Somewhere to host the app. For this project we used Heroku.
+ Twitter details:
+ Twitter Developer account: if you don’t have one already, you can apply for one [HERE]().
  + Create a Twitter App if you don't already have one.
  + Consumer API keys for your app. 
  + Get to know the Account Activity endpoint: https://developer.twitter.com/en/docs/accounts-and-users/subscribe-account-activity/guides/getting-started-with-webhooks
  + Have a Twitter account to host the scorer app, and register that account with the AAA. For this prototype we used the [@HackerScorer](https://twitter.com/HackerScorer) account. 

Using the Twitter chatbot
=========================

## Becoming a scorer

Follow the account of the event scorer. Learn how to submit scores, make updates, and be familiar with the FAQ section below. 

## Submitting a score

At the end of every hole, send the scorer account (e.g. @HackerScorer) a Direct Message (DM) with your team number, the hole you just completed, and the number of strokes needed to complete the hole. Say you are team 6, you just completed hole 12 in four strokes. This information should be formatted exactly like this: ```t6 h12 s4```

**Where:**  
+ *t# = Your team number.* This doesn't change. Your team number is indicated by the hole you started on. Team 6 started on hole 6.
+ *h# = Hole number you are reporting a score for*
+ *s# = Your score. The number of strokes.*

## Correcting a score

Mistakes happen. Typing with gloves on is problematic. So, what happens when an incorrect score is submitted? Well, you just send an ```update``` DM with the correct scoring. That's it. 

For example, you are on team 17 and your team got a birdie on the seventh hole, a 5-par hole. The team scorer incorrectly submitted a ```t17 h7 s5``` score. To correct this, the following DM is sent: ```t17 h7 s4```. 


# FAQ

**What if I forget to DM the bot after playing a hole?** 
That's ok! Just send a DM for any hole you forgot to submit. 

**What if I enter my score wrong?**
Try not to. Enter your team number, hole, and score very carefully. If you mess up, send an 'update' DM. For example, if you DM'ed ```t6 h4 s5``` but the correct score was ```4```, DM ```update t6 h4 s4```. 

**How do I know if I did it right?** 
A correctly formatted score receives a confirmation DM (currently 'Thanks, we got it!"), and if that is not received, then the score was not accepted. 

**I'm on a team of four, do we all have to do this?**
No. Designate one team mate to do this after each hole. Try to remind your team mate to do this!

**Should we remove par (over/under)?**
Submit the TOTAL number of strokes that your team took. Do NOT subtract par. For example, if your team hit 5 times on a par 3, your score is 5. NOT 2.

**Does our team still have to keep score with the paper scorecard?**
YES! This is your final scorecard for determining the winning team at the end. This bot is an experiment and for fun.





