---
layout: post
author: Niels Talens
---

It’s a funny thing to say that delivering business value is the most important thing when developing software. It doesn’t matter that a framework like Scrum is far from efficient, because we focus on value. We deliver business value. Working software. Every sprint. Period.

But in the end we often just don’t know the impact of the things we make. What do we really know about the business value we supposedly created? Is it a one-time validation? Is it a one-way validation?

We keep adding stuff to our products because that is what we are expected to do. We always need more features. But do we know the difference these features make, except that there are more features now? More stuff. What if one feature undoes the effect of another? Wouldn’t that be valuable to know? Wouldn’t it be nice to remove it?

Software development has everything to do with validations. There are at least three rounds of validation from ideas to maintaining the software in a production environment.

<h2>Validate your ideas and business goals</h2>
<img src="{{ site.baseurl }}/images/explain/Cycle 1.png" class="lean-image-left">


The first round of validation is about vision, business goals and problems to solve. Is the vision of the product (still) right? Are the right personas defined? Is the desired impact of the software defined? Are the right activities defined? Are the goals clear? What is the desired ROI?

<h2>Continuous Integration</h2>
<img src="{{ site.baseurl }}/images/explain/Cycle 2.png" class="lean-image-left">

The second round of validation is about technical and behavioural validation. Features are being designed, built, tested, accepted and deployed.


<h2>Continuous validation</h2>
<img src="{{ site.baseurl }}/images/explain/Cycle 3.png" class="lean-image-left">

**Hooray! Your software is live!** Well, let’s NOT sit back and relax. This is usually the moment where we tend to run back to the product backlog and get started on new features. Burn down those points! Move post-its around like there is no tomorrow! Like dropping your children off at school without ever speaking to the teachers.

Let’s make sure that this is what the world really needs. Let’s also make sure we keep it that way.

<h3>Proactive monitoring</h3>
Monitoring is often limited to raising the alarms when something is seriously wrong. With continuous validation you are monitoring something else entirely: you want to know the effects new features or changes have on the system and be able to act on them. Use the feedback you get from your users, that is, from the behaviour of your users. For instance:

* What is the performance of the most important business transactions? Do the new features affect these? If so, how do they over a period of time?
* What do heatmaps say about the assumptions you made earlier? Or the usage data? Do the users really use the new feature more than the older one? And what about over a period of time?
* What do the statistics say about the increase or decrease of a certain feature? Was that the intention?

<h3>Validate goals</h3>
You make your software with a purpose, right? You want to reach business goals or you want to solve problems. But to make sure your software achieves what you intended it to do and keeps doing you need to validate this continuously. If your goal was to sell more items and you implemented functionality to reach this goal, you’ll need to validate its effectiveness. And then you need to keep validating it because software is no concrete structure and will change.

<img src="{{ site.baseurl }}/images/blogpics/Fence.jpg" class="fit image">

I cannot emphasise this enough: remove functionality that doesn’t meet the criteria anymore. The world is full of bloated expanding products which become even bigger and unusable. Like the gate in the picture. I’m sure there was a good reason to make it and it worked very well when there was a fence. For now it only costs us because it needs maintenance.

Does your product have gates without fences? Are you aware? Not all as visible as the one in the picture I’m sure, but they’ll cost you money just the same.
