---
layout: post
author: Hylke Stapersma
---

Software development evolves at a rapid pace. Continuous delivery is the new black. With software being created and delivered faster than ever, we find that the input lags behind. We build software with a reason, usually to solve an existing problem or deliver more business value. Yet we notice that these reasons are hardly ever validated.

We need to validate that the software we built still has a reason to exist. That’s why we made Gareth. Gareth clarifies and validates the Why.

In this blog post we will show you how to use Gareth and make validating your business goals part of your development process. You will see how Gareth validates the entire lifecycle of a business goal, from inception of a user story right into production.

<h2>Inception</h2>
User stories are always written for a reason. Say we expect that a relevant FAQ page will reduce the number of customer support calls. This is a clear business goal and with Gareth we can make such goals — the Why — part of the process.

These business goals should be included in the roadmaps, features and user stories at an early stage, for by doing so these goals will become apparent for the team realizing the software and it also allows for reflection on the usefulness of the desired functionality. These goals, or Why’s, are described in the Gareth DSL. We introduce another dimension to a user story, which we will call an Experiment:

<h3>The story:</h3>

As the owner of the hotel booking site,<br />
I want the users to see the discounted rooms first,<br />
So that they will be booked first.<br />


<h3>The experiment could be:</h3>

Experiment: I want to validate that by showing the discounted rooms first, there will be an increase in booked rooms.

Baseline: Get the current number of discounted rooms booked.<br />
Assume: There will be an increase in bookings for discounted rooms of 25 per week.<br />
Time: 1 week<br />
Success: Send email to the whole team with congratulations<br />
Failure: Send an email to the Product Owner.<br />


We kept the language clean and readable to make it easy for a product owner to communicate with his or her stakeholders. Talking the same language throughout the business simplifies things, because a user story can often be interpreted in many different ways.

With Gareth the product owner describes the goal that should be achieved: the experiment. By setting a baseline (getting the current situation), an assumption (the desired future situation) and a time within which the goal should reached we have all the information needed to validate the goal. The final two parameters are the desired actions taken when an experiment fails or passes.

<h2>Development</h2>
A user story now consist of the story, the acceptance criteria and the experiment. This way it becomes clear for the team members what the product owner wants to achieve. The development team is now able to create definitions that can be ‘glued ’ to the experiment:

<script src="https://gist.github.com/Hylke1982/ef6c055cc3cecd0c638d.js"></script>

In this example you can see how every line in the experiment description in the Gareth DSL is mapped to methods in the ExperimentDefinition. The doBaseline method executes the code that looks up the number of rooms currently booked and the doAssume code will execute after one week, as defined in the doTime method. After the definition code is glued to the experiments defined by the product owner it is time to run the experiment in production. And to keep it running from there on.
<h2>Production</h2>
Bringing your experiment into production means that the experiment described in the Gareth DSL and the experiment definition are brought together. This is the moment that the product owner gets feedback if the user story really makes a difference or is just functionality that interferes with other business goals. The experiment and the experiment can be brought together with the following code.

<script src="https://gist.github.com/Hylke1982/c4c0fcea2779093edbf9.js"></script>

With the ExperimentEngineConfig you can load experiment descriptions and definitions. The ExperimentEngine will load this configuration. Afterwards you can start the engine and your experiment will be validated automatically.

<h2>Wrapup</h2>
<img src="{{ site.baseurl }}/images/explain/Cycle 3.png" class="lean-image-left">

Gareth makes it possible for a product owner to clearly communicate with stakeholders about the business goals and the results of the validation. “Yes we assumed that the effect of this was X but we found out that this assumption was wrong. Let’s find out why and get it right”. It clearly helps the stakeholders and the product owner to define the right functionality and validate these continuously. It is a great way to improve product definitions.

Gareth also helps software development teams become more aware as to which goals should be achieved when implementing a user story. This has a big impact on the design and functionality of the software.

<h2>Get Gareth</h2>
Are you interested? Please be our guest and try Gareth. Gareth is open source (GNU General Public License v2.0) so that we all can benefit. Do you want to contribute in any way? Please let us know! We are really looking forward to hearing from you.
