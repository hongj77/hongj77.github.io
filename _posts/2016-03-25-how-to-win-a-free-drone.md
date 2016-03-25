---
layout: post
title: How to win a free drone.
comments: true
---

There are a few key advantages that come with going to an engineering school with a strong reputation:

1. <s>Tons and tons of work.</s>
2. <s>Each semester costs more than $25,000.</s>
3. ???
4. Okay, these weren't really advantages.

Joking aside, there are actually a few perks that all (CS) students have access to here at Cornell: tech companies recruit really, really hard. Around the beginning of each semester, companies come and throw events, give talks, and hold competitions in the hopes of becoming at least marginally more noticeable in the absolute <em>chaos</em> that is career fair. Have you ever tried to pass out 30 resumes in 3 hours? Exactly.

In those two weeks, however, you feel like a king. Not many days when someone actually wants to hear about that project you did that one time using Dockers and ECS. Let's not forget about the free food and swag. Last weekend, I happened to go to a talk by [Gigster](https://gigster.com/), and they had a machine learning workshop, which aimed to cover [scikit](http://scikit-learn.org/stable/), [pandas](http://pandas.pydata.org/), and [jupyter](http://jupyter.org/) (really cool stuff btw). To jumpstart their recruiting efforts, they had a weekend long machine learning competition, which I assume was to select the best and the brightest candidates at Cornell by looking at who won the ML challenge. Too bad I won by accident.

{% include image.html
            img="public/post_img/dilbert1.png"
            title="Dilbert Cartoon strip"
            url="http://dilbert.com/strip/2008-05-07" %}

You can check out the competition [here](https://inclass.kaggle.com/c/gigster-ml). The task was to predict the opening weekend revenues of major films released in 2008 and 2009, and the evaluation metric was Mean Absolute Error of all your predictions.

I'm going to preface this by saying I really like the data science stuff. When I was first learning ML (CS 4780), I wrote my own [NB regressor](https://github.com/hongj77/coding-practice/tree/master/codingchallenges/naive_bayes) to a SquareSpace coding challenge because I thought it was cool. I ended up getting rejected the next morning because apparently I had no idea what I was doing.. But with time, I naturally got more exposure to ML through taking natural language processing, computer vision, and joining a deep learning research lab.

So at this point, I knew enough to be able to have fun with the contest. I thought I would submit one or two different models to see how well they do, but I ended up getting completely absored and ended up submitting 37 different solutions. Suddenly, I realized I had no idea what I was doing and just decided to <s>yolo</s> average the result of 2000 different solutions using a random forest.

Besides the few lines for for cross validation and custom evaluation metrics, my entire code at the end of the night boiled down to these 3 lines:
{% highlight python %}
# random forest
from sklearn.ensemble import RandomForestRegressor
model = RandomForestRegressor(n_estimators=2000, max_depth=4)
y_hat = model.fit(X_train, y_train.values.flatten()).predict(X_test)
{% endhighlight %}

Next day, my random forest climbed to #1 and the contest ended. And just like that, I had robbed Gigster of a drone with a camera, a BB-8 toy, and a recruiting opportunity. The guy who won second place apparently was a guy from my research lab (aka he is actually competent). He approached me and asked what I used to jump the rankings, and all I could say was.... random forest. 

{% include image.html
            img="public/post_img/drone.JPG"
            title="Drone and BB-8 prize"
            %}

<b>Lesson learned here:</b> machine learning is fickle, I still don't know machine learning, when in doubt average a bunch of wrong solutions together to get the right solution. 


