---
title: "Transforming software testing from a bottleneck to an enabler: our
  investment in Launchable"
date: 2021-07-27T21:40:41.675Z
thumb_img_path: /images/c81f0422-993f-4fc7-9096-e6ad3a03ddcb.avif
excerpt: How the software testing market evolved, and how Launchable can help it
  become an enabler rather than a bottleneck.
template: post
---
*Originally posted on the 645 Ventures blog.*

The term “bug” as reference to an issue in a technological system first appeared in 1878 in [a letter](https://i.imgur.com/qDvEW4w.jpg) written by Thomas Edison as he was working on a telegraph system. As electronics became a bigger and bigger part of our infrastructure through phones, radios, etc, there was an increased focus on testing them to make sure they didn’t create issues. In the early 1900s, books like [“Testing Electrical Apparatus”](https://babel.hathitrust.org/cgi/pt?id=loc.ark:/13960/t53f5wb54&view=1up&seq=9), “The Testing of Electrical Machinery”, and “Load Testing Devices” were published by companies like General Electric and Western Electro-Mechanical Co.

The origins of software date back to the late 1940s, but “software testing” didn’t formally exist until 1957, when it was formally separated from the “debugging” of software (i.e. fixing a problem *after* it was discovered in the wild). Testing would usually fall within the scope of a “quality assurance” (QA) team, which was separated from the engineering team, and could also be non-technical. As development cycles and methodologies changed, so did the level of collaboration between developers and the QA team. In a [“waterfall”](https://www.umsl.edu/~hugheyd/is6840/waterfall.html) setting for example, development and QA work is fully separated, and there’s no testing done until all the work is done. At times, testing happens even after the software is delivered to customers, which overlaps with debugging. As companies transitioned to agile, this feedback loop started to become shorter; QA would come in after each sprint, testing tickets separately, and approving or rejecting them for the current release. While better, this still created a massive bottleneck for engineering productivity and product velocity, as testing after merges were done could require some major refactoring, or push back a release altogether.

In the early 2000s, more automation came into the testing space. The creation of open source libraries like [Selenium](https://github.com/SeleniumHQ/selenium) replaced the majority of manual tests with automated ones. Now instead of waiting until the QA cycle began, engineers could test their new code before it was merged in. In 2005, Kohsuke Kawaguchi released an open source project called “Hudson” (later renamed to [Jenkins](https://www.jenkins.io/)) which helped developers easily execute and schedule “builds” of their software, which would run all tests automatically to make sure the application still worked properly after making some changes. Kohsuke discussed [on this podcast](https://techleadjournal.dev/episodes/40/) about the frustration that breaking a build would cause, and how he just wanted to build something that allowed him to catch those issues earlier.

Jenkins is now one of the most popular open source projects ever, with more than 1.2 million nodes, and an iconic product in the Continuous Integration (“CI”) space, which has been growing quickly in the last decade. Cloudbees, the company commercializing Jenkins where Kohsuke served as CTO, was founded in 2010 and is now over $100M ARR. CircleCI, another player in the CI space, was started in 2011 and was just valued at $1.7B in their June 2021 fundraise. It’s clear that CI is becoming mainstream and gaining adoption in more and more engineering teams. We believe that this trend will only continue as more organizations start to rely on software, as we described in our [Engineering Value Chain Revolution](https://645ventures.com/engineering-value-chain-revolution) investment theme.

![image](https://super-static-assets.s3.amazonaws.com/673266ec-288a-4ac9-b926-e414026b82f1/images/5e3a132c-d53d-413e-8601-95b3ece84634.png?w=1500)

> Jenkins nodes growth from 0 in 2007 to 1.2 millions in June 2021

## **Testing as an engineering productivity bottleneck**

The growth of DevOps and CI as a quasi-standard industry practice has dramatically increased productivity of engineering teams. Rather than having to manually test software, it can now be done programmatically in the background. Kent Beck coined the “Continuous Integration” term in the context of “[Extreme Programming](http://www.extremeprogramming.org/)”, which also put forward a few core values around testing:

* All code must have unit tests.
* All code must pass all unit tests before it can be released.
* When a bug is found, tests are created.

As agile development became more prevalent, the speed of execution of a testing suite became one of the main bottlenecks for an engineering team. Unless there’s a green build (i.e. all tests are successful), developers cannot merge their pull requests and close their tickets. Tests usually run on each change added, so every time a piece of feedback has to be implemented, a design change needs to be done, which requires re-running the full test suite. In addition, each bug requires a new test to be created, further increasing the time it takes to run the suite.

OpenStack has a public CI dashboard that you can view [here](https://zuul.openstack.org/status); on the left side, you can see how long it takes for a single build to run. Depending on the project, builds can take between 1 hour and 4 hours. *Imagine being a developer on the project, and having to wait that long to have confirmation that your changes are good to go*. When speaking with engineering leaders at large organizations, we have heard run times ranging from 3 hours to overnight builds. I personally spent a lot of hours over my career improving RSpec and Capybara test suites, and I know how frustrating it is for engineers to do this rather than work on core product challenges.

Continuous Delivery is another important piece of this equation. As software deployment has become more automated (and complex), we have moved from manual releases to continuous delivery pipelines that push software to production once all checks are met. Once again, tests are a circuit breaker for this process, and will prevent code from going live. At times, especially when responding to live incidents, engineering teams resort to running subsets of tests before releasing but those are usually decisions made in a qualitative manner, not a quantitative one.

The cost of a slow testing suite is clear to engineering leaders. Deploying quality features at a higher velocity than competitors can be a great advantage, because it enables great products to be delivered to customers first. On the other hand, the cost of NOT running extensive tests is even higher, as production outages can lead to serious customers and revenue loss. Teams have found themselves between a rock and a hard place, having to pick between a fast-running test suite or a thorough one.

## **Testing as an engineering productivity enabler and our investment in Launchable**

One of the big advantages of testing is the institutionalization of knowledge around the behavior of your application. As a new engineer being onboarded on a team, I can make a change and then run the test suite to see all the ways in which it might affect the rest of the codebase. Without testing, I’d have to figure out where the code I’m modifying is being called, and what classes might inherit from it. The downside of this, as we mentioned, is that it can take a long time to run all of these tests.

Over the last few months we’ve had a chance to spend time with both Kohsuke Kawaguchi and Harpreet Singh, who worked with Kohsuke as VP Product Management and Design at Cloudbees. They recently started a new company called [Launchable](https://www.launchableinc.com/), which is creating a “testing intelligence platform”.

![image](https://super-static-assets.s3.amazonaws.com/673266ec-288a-4ac9-b926-e414026b82f1/images/56626b66-eb56-4994-a32a-94b492168c30.png?w=1500)

Today, CI platforms are all-or-nothing; they either run all tests, or they run none. They don’t have a way to pick which ones will be most predictive based on the changes made to the code. The smarter way to do testing would be to look at your changes, identify what potential areas of risk are, and then thoroughly test the at-risk parts in order to avoid delivering flawed software to your customers.

Launchable is building a product that sits at the CI-level through an [open source cli interface](https://github.com/launchableinc/cli)and records all test results from each build; this data is then used to train a machine learning model that powers the customer’s Launchable model. Developers can send them the code diff from their commit as well as a target confidence threshold, and in return they receive the smallest possible subset of tests that will achieve the level of confidence they requested, drastically reducing the runtime of their test suite without compromising on stability.

For example, one of Launchable’s customers is on track to cut \~15,600 hours of test time over a year, which is estimated to be worth \~$1M/year to the company. When you look at the cost of engineering salaries, as well as cloud compute to actually run the tests, you can start to understand the magnitude of the problem, and the amount of savings that a product like Launchable can bring to an engineering organization.

645 Ventures is excited to announce our lead investment in Launchable’s Series A, joining great partners in the syndicate such as Battery Ventures and Unusual Ventures, and an excellent group of angels including Sri Viswanath, CTO of Atlassian, Sacha Labourey, CEO of Cloudbees, and Al Zollar, former Head of IBM Tivoli and Board Member of Red Hat, and more exceptional operators. We believe Harpreet, Kohsuke, and the rest of the Launchable team can build an iconic developer tools company, and we’re excited to be in their corner from the early days of their journey.