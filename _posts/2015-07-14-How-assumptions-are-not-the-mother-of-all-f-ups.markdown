---
layout: post
author: Niels Talens
description: With assumptions and continuous validation we can validate if our goals are reached.
---
<img src="{{ site.baseurl }}/images/blogpics/CD-is-the-start-skewd.png" class="fit image">
*The thing about trends is that they will come and they will go. So after the agile trend continuous delivery and devops are in line. I think in a way it is very nice to see that development craftsmanship practices are becoming more and more accepted. We can all benefit from this. Software is eating the world so let’s be damn sure that the software is good. But is it?*

Be honest. After the development of the first couple of versions. After adding new features for a while. What is the state of the product? Are the same assumptions holding up? Are your goals still the same? Did the world change? Or is it enough that you can deliver your software in a matter of seconds?

Often we think we are building software like this:
<img src="{{ site.baseurl }}/images/blogpics/What-we-think-we-make-700x442.png" class="fit image">

But we are doing this:
<img src="{{ site.baseurl }}/images/blogpics/What-we-really-make-700x397.png" class="fit image">

Let’s say we are still building the same crap but at least now we can deliver it faster and with fancier new tools.

Agile, continuous delivery and devops can make our processes and delivery easier. And we can do that in the cloud, with big data and microservices written in Elixir. But that is still only a part of creating software products. We have to look at software development as a whole again. Because that’s the only thing that really counts: making good products. And that does not only mean bug free or easy to deliver.

Why continuous delivery isn’t finished

The prerequisites didn’t change at all. With bad input and lack of validation the results are mediocre at best. It made my colleague Hylke Stapersma [@hylke1982](http://www.twitter.com/hylke1982) and me think about why continuous delivery isn’t finished and what we are missing. So we started experimenting with this. In the following blogs we will describe more of the technical journey. For now it’s about the concept.

**Step 1: Stories that don’t suck:**

Good story describes the goal a certain user wants to achieve with a piece of functionality (the why). It should be pretty functional. It works very well to add acceptance criteria (BDD/ATDD scenarios) in an early stage to fine-tune and make sure a functional validation is in place. Let’s say that’s all in order.

We now want to introduce another dimension to make sure we achieve our goals. We add something we called an experiment, which includes some assumptions, to an user story. These assumptions can be measured and will be automatically validated.

– And for me it is not about being SMART all the time. I’m definitely more of a DUMB guy. It is more about validating assumptions than the measurement in this case anyway.

Here is an example of a story we are using in our demo setup which contains both the BDD feature and an experiment:

<img src="{{ site.baseurl }}/images/blogpics/CD-is-the-start1.png" class="fit image">

**Step 2 – 8: Do the magic: build and deliver the best software ever seen.**

<img src="{{ site.baseurl }}/images/blogpics/CD-is-the-start.jpg" class="fit image">

For a more indepth explanation of this model please check this blog.

**Step 9: monitor assumptions.**

If the results of the validation are under expectation, these result should have impact on the backlog. In theory the result of the validation is more valuable than any new feature you were dying to implement. To be honest, the story in which the assumption was made was highly prioritized.

**Time.**

So one of the first things we saw is that in contrast to unit or acceptance tests we now have the time dimension. Our behaviour tests run a couple of time in the continuous delivery pipeline but never when the software is in production. There’s no need either because there are no changes there. In the case of the experiment we have a starting point, our baseline, and from there we will schedule a periodic validation of the assumptions we made. We can validate as often as we want. Why ever turn them off?

**Removing features is not a bad thing people.**

If you find out that something is rarely used please do not be afraid to remove it. That will make your product leaner and your codebase cleaner (there is a song in there). Here validating assumptions can also be very handy. Because we can measure over periods of time we just set a limit and everything below that we have to evaluate. I would like to know if something isn’t as valuable as expected. Often by adding a new feature an older one becomes unnecessary. No problem. Just remove it and try again.

**Impact mapping.**

If you take a look at impact mapping you see that assumptions are a big part of it. Those are the things we often can make measurable. In our case add them to an experiment and validate. Impact mapping is a great way for us to gain insight in the many assumptions we make. If you don’t know impact mapping I can recommend the book by Gojko Adzic.

**Non-functional stories.**

A story has to describe something that has value. But sometimes that value is easier to define than the functionality or the user. And what to do with some non-functional stories? I think we all have had experience with user stories that feel artificial. Like we can’t even describe a proper user for it. We just want to decrease the costs of operations with a piece of functionality for instance. Should we describe “ the members of the board” as users? It just feels artificial sometimes. I think in those cases an experiment/assumption could replace the story.

**Wishlist**

In the future we want to be able to also use information of tools like AppDynamics or Google Analytics. Those have so much information that will help the business in making good products. Performance and usage are definitely things that are key in that process.

So, in conclusion, contrary of an earlier blogpost of mine, in this case assumptions are not the mother of all f-ups. Assumptions are a step in completing the whole flow of software development.

We are currently implementing this idea and will share our findings and solutions in one or more follow-up blogs. Stay tuned!
