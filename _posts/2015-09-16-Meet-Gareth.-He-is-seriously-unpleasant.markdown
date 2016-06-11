---
layout: post
author: Niels talens
---

<img src="{{ site.baseurl }}/images/blogpics/screenshot-gareth.jpg" class="fit image">
Hello world, please meet Gareth. He can be seriously unpleasant. Trust me, we know. But he is becoming more and more indispensable. He will tell you clearly, without emotions, when your ideas are rubbish. He will certainly not hold back and he will give you the facts when your assumptions don’t hold up. He will keep validating that your business goals are reached. If not, he’ll let you know.

Gareth validates the Why, the reason certain functionality was built in the first place. He makes sure that the (business) goals are reached and keeps validating these goals. We all know that implementing one feature can affect another. This also has an impact on the success of the related goals.

Gareth loves business goals. He doesn’t want to talk about functionality. He wants clear assumptions like: the performance of feature x will be 25% better after implementing this change; feature y will decrease the usage of functionality z by at least 50% over the next 3 months, and so on.

<h2>Why we really need Gareth</h2>
There is a lot of focus on software craftsmanship and automation. We can build and deploy software very quickly with current technologies. However, it’s the post-deployment stage that worries us. How can we be sure that this new functionality has the impact the business needs?

We believe user stories and backlogs are too detailed and complex as an aid to communicating with stakeholders. We think it would be better to talk with them about goals and assumptions. What are the goals and how do we want to validate them?

We know the world changes, and so must our software. That’s another reason we need Gareth. It’s vital to know that your goals are still reached after changing parts of the software. Sometimes one feature makes another unneeded. If so, Gareth will let you know.



<h3>How Gareth works</h3>
We introduce validation as an extra dimension to an user story. We call it an experiment and it consists of:



**Experiment:** Name of the experiment<br />
**Baseline:** What is the initial state.<br />
**Assume:** Which impact do we hope/wish the software is going to have?<br />
**Time:** What is the interval and period of the experiment?<br />
**Action:** Which action does Gareth have to take when an experiment fails/succeeds?<br />

<h3>Let’s describe an example:</h3>

<h4>The story:</h4>
As the owner of the hotel booking site,<br />
I want the users to see the rooms with discount first,<br />
So that they will be booked first.<br />

<h4>The experiment could be:</h4>
Experiment: I want to validate that by showing the discounted rooms first, there will be an increase in booked rooms.

Baseline: Get the current number of discounted rooms booked per week.<br />
Assume: There will be an increase in bookings for discounted rooms of 25 per week in the first month.<br />
Time: 1 month.<br />
Success: Send email to the whole team with congratulations.<br />
Failure: Send an email to the Product Owner.<br />

Baseline: Get the number of discounted rooms booked in the last 6 months.<br />
Assume: After 6 months, bookings of discounted rooms have increased by 80%.<br />
Time: 6 months.<br />
Success: Send reminder to buy cake for the developers.<br />
Action: Create an investigative story on the backlog.<br />



Gareth will run these validations as often as described in the assumptions and take the appropriate action. It is a great way for a product owner to be sure the right things are being built and kept that way. This is what we want to communicate to our stakeholders.

It is also great for teams to see that not only code, but also business goals are validated continuously.

<img src="{{ site.baseurl }}/images/blogpics/Gareth Schema Business.png" class="fit image">

<h2>Get Gareth</h2>
Are you interested? Please be our guest and try Gareth. Gareth is open source (GNU General Public License v2.0) so that we all can benefit. Do you want to contribute in any way? Please let us know! We are really looking forward hearing from you.

Get Gareth: [github.com/craftsmenlabs](https://github.com/craftsmenlabs)

See Gareth:

<iframe width="420" height="400" src="https://www.youtube.com/embed/xWvc--BOtHo" frameborder="0" allowfullscreen></iframe>
