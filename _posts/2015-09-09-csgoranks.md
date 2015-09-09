---
layout: post
title: Introducing csgoranks.org
---

![csgoranks.org top 10 placing](/assets/img/csgoelo.png)

## Introduction
I am a fervent follower of competitive Counter Strike, especially the newest edition Counter Strike: Global Offensive (CS:GO). As such I was always displeased that there did not exist a viable world ranking system for the top competitors. Actually there was one, [Thorins Top 10](http://www.goldper10.com/article/2279-thorins-csgo-top-10-world-rankings-24th-august-2015.html), which was pretty good and to my liking but still not good enough since it was not entirely objective and based on sole numbers.


This was mainly the reason why my mate [Christian](https://github.com/n2o) and I took the matter into or own hands during free hours after work. We started developing [csgoranks.org](csgoranks.org/ranking/). To explain why our site provides meaningful ratings I have to venture a little bit into the intricacies of competitive CS:GO.

The worldwide best teams usually employ salaried players, which compete in different online and LAN tournaments. Since online games add elements not inherent to the game like lag and netcode caused effects like [Peekers Advantage](http://gfycat.com/ImportantIllfatedCoati) LAN games are seen as the gold standard for competition. This is the reason why we only enter results from LAN tournaments into our database.
Now, not every LAN tournament is the same. Some are very small, local tournaments with little to no prize money while others are considered world championships, so called majors, with prize pools up to $250000 and audiences filling whole stadiums.
![ESL One Cologne Major 2015](/assets/img/esl_one_cologne.jpg)
If we would give the first place finish of a small tournament the same weight as winning a major the rankings would be hugely skewed. That is the reason why we only add tournaments with prize pools of $10000 upwards. Furthermore the tournaments are sorted in different tiers dependent on prize money, which give different amounts of ranking points.

We want the rankings to reflect the current team form as well, meaning teams that dominated the scene a year ago but been mediocre since, should not be placed into the top spots. To accomplish this we consider all tournaments younger than three month at the moment. This is not entirely ideal, which is why new algorithms are constantly tested by us. But so far we are at least satisfied to some extent because at least the top 10 are pretty similar to what Thorins applauded rankings, with the difference that our rankings can be reproduced.

## Technical Specifics
csgoranks.org is written on a python base and uses the [django web framework](https://www.djangoproject.com/). The csgoranks app we wrote for django uses an underlying sqlite database. Currently all games have to be added by hand by a maintainer (currently also me) - plans to automate the process with links from [HLTV.org](http://www.hltv.org/) are underway, but as you may know projects developed in free time tend to eat quite a chunk of the same.
The source code is currently not public, since we first want to perfect our algorithm before we start publishing it.

## Related and Future Work
After first version of csgoranks.org went online ESL developed a world ranking system as well, which received a lot of negative critique from the competitive CS:GO community, since it gave rating points not only to the competing players but also the organizations which paid their salary. Our system always gave points to players only, which is also one of the main differences to ESL's system.
Future Work will concentrate on a better scoring algorithm, automatic database filling and several flashy statistics and visual goodies.

If you have questions or just have a good idea how to better our little project, do not hesitate to shoot me an email.
