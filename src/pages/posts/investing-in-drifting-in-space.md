---
title: Investing in Drifting in Space
date: 2022-03-29T21:13:10.891Z
content_img_path: /images/download-3-.png
template: post
---
I made an angel investment in [Drifting in Space](https://driftingin.space/) coming out of the YC W22 batch. DIS is the company behind [Jamsocket](https://jamsocket.com/), an infrastructure provider for “session-lived backends” based on the open source project [Spawner](https://github.com/drifting-in-space/spawner). Paul and Taylor, founders of the company, previously spent time building data-heavy applications at great engineering orgs like Two Sigma and Datadog. 

Other than having really enjoyed my meetings with them, I think Jamsocket could be a core piece of software infrastructure for many applications going forward for a few reasons:

* As the industry moved from on-prem to cloud, the architectural design of the backend hasn’t drastically changed. We still mostly treat the cloud as a shared on-prem for all of our customers. Having to support all customers on the same backend leads to code that is highly over-engineered for the average use case, but necessary for the top percentile of users. There’s no easy way to separate the two.
* We have started to forget that there’s actual bare metal under the cloud, and not all hardware is built equally. For data-intensive applications, it actually does matter which parts are used, especially when it comes to GPUs. If you look at TensorFlow benchmarks for example, training a model on an A100 card instead of 1080 Ti is almost 5x as fast. As a customer, I should have the option to select the specs for my machine ([See Deepnote’s pricing page for an example](https://docs.deepnote.com/resources/pricing#machines-hardware)), and Jamsocket can make it easier to offer that option.
* Offering real-time collaboration on SaaS products has been a real differentiator for products like Google Docs, Figma, Miro, etc and I expect more products to offer this in the future. If you read [Figma’s CTO post on how their multiplayer tech works](https://www.figma.com/blog/how-figmas-multiplayer-technology-works/) you can see how hard it’d be for the average company to build this from scratch. 

I'm really excited to see the team execute on this!

This is part of a broader interest I have in “heterogeneous computing”, which I put in quotes because it’s not the traditional definition. For example, what if hardware selection was inferred by the type of compute that is going to be run, instead of being static? What if your ORM was routing your data to different databases based on the type of queries usually run on it? 

My email is on the homepage, always happy to chat about this stuff!