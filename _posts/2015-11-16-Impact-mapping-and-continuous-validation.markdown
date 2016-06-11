---
layout: post
author: Niels Talens
description: Impact mapping and continuous validation have a lot in common. Where impact mapping is a great way to define products, continuous validation makes sure your assumptions are being validated.
---
<img src="{{ site.baseurl }}/images/blogpics/impact.jpg" class="fit image">
There is always a reason for making software. Let’s rephrase that: there should always be a reason, at least from a business perspective. How else could our products have any impact?

Whether we want to make an app that that seamlessly connects riders to drivers or build a community where you can hire and rent apartments while earning tons of money: it is basically all about adding value and solving problems from a software point of view.

<h2>Impact Mapping</h2>
Impact mapping is a technique that can be helpful in defining the impact you want your product to have with all that follows. Why are we doing this? You first define the desired impact with some criteria that you consider necessary to make this impact. These criteria stand for the how and the what.

The example below from by impactmapping.com illustrates how impact mapping works:

<img src="{{ site.baseurl }}/images/blogpics/im_example.png" class="fit image">

* We want to reach 1 million players on our platform.
* We think that there are three personas that can help us with that: players, internal employees and advertisers.
* We think we know how they can help us with that
* We think we know what will facilitate them on our platform.

The impact map cheat sheet made by [Craig Smith](http://craigsmith.id.au/) can be a helpful aid to keep everybody focused while doing the impact mapping:

<img src="{{ site.baseurl }}/images/blogpics/impact-map-cheat-sheet.jpg" class="lean-image-left">

<h2>Assumptions</h2>
<img src="{{ site.baseurl }}/images/blogpics/assumptions.png" class="fit image">
With impact mapping we make a lot of assumptions. In the example below we assume that the actor called Player can help us in making the desired impact (1 million users). We also assume that Player will do this by inviting friends, and we make the assumption that semi-automatic invites will help.

<h2>Following up on your stories</h2>
The thing I don’t see happening often is following up on the impact of a piece of functionality. We have a review or demo and sometimes we get feedback from users. Yet apart from some performance monitoring we do not really know a lot about the impact we are making. Did we make valid assumptions?

<h2>Continuous validation</h2>
With continuous validation we also make many assumptions. In contrast to automatic unit tests we want to keep validating the same assumptions in production as long as the functionality is alive, and not run it only once. It is very common that the impact of one feature is diminished by a newer one. To create great projects this is something you really want to know and should act on.

We introduce validation as an extra dimension to a user story. We call this an experiment. These experiments will run scheduled in production as long as the functionality is there. The experiment for the example above could be:

**Experiment:** By giving players the option to invite friends semi-automatically the number of players will increase.<br />
**Baseline:** Get the current amount players.<br />
**Assume:** There will be a 10% increase in new players.<br />
**Time:** 1 month.<br />
**Success:** Send cake to the whole team with congratulations.<br />
**Failure:** Push message to Product Owner.<br />

Other things I would like to know and want to create experiments for is how much the invite option is being used, who uses it, and what the assumed effect is after 6 months?

<h2>Impact mapping and continuous validation</h2>

In a sense continuous validation is the automation of impact mapping. Where impact mapping is a great way to define products, continuous validation makes sure your assumptions are being validated. Not once, but as long as the functionality is alive.

Creating great products is not only about adding new cool features. It is also about removing or changing existing features whose goals aren’t met. We know which impact we want to have. Are we in any way achieving this goal? Are our assumptions right? Is there functionality that is not contributing to our goal?

Manual monitoring of all the assumptions that were made is undoable most of the times. Working software must be delivered at an ever faster pace. That’s why after continuous integration there is continuous validation.

[Hylke staperma](https://twitter.com/hylke1982) and [myself](https://twitter.com/NielsTalens) are currently working on a continuous validation framework called Gareth [getgareth.io](http://www.getgareth.io) It is an open source project and we would really like to hear from you if you are interested in contributing, trying Gareth out or just discuss it. Fork us on [Github](https://github.com/craftsmenlabs)


<h2>More on:</h2>
Impact mapping:
[www.impactmapping.org](www.impactmapping.org)

Continuous validation:
[After continuous integration there is continuous validation](http://craftsmenlabs.github.io/gareth/2015/08/15/After-continuous-integration-there-is-continuous-validation.html)
