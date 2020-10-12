---
title: A REST API by any other name
date: "2020-09-10T00:58:42Z"
description: "That's not a REST API. THIS is a rest API."
---

- [Introduction: What is REST?](#introduction-what-is-rest)
- [HATEOAS](#hateoas)
- [Rest without HATEOAS is not REST](#rest-without-hateoas-is-not-rest)
- [What is REST minus HATEOAS?](#what-is-rest-minus-hateoas)
- [What's next?](#whats-next)

## Introduction: What is REST?

There's a fundamental misunderstanding that is endemic in the software industry. Before continuing, please take a moment to answer this question:

> What defines a REST API?

Do you have an answer in mind? You most likely know it's an HTTP based web API. Maybe you know the acronym stands for "Representational State Transfer" and with that you know that data is communicated between the client and server in the form of "representations". Perhaps you included the very useful semantic use of HTTP verbs (getting data with HTTP GET vs. writing data with HTTP POST).

Quite often people incorrectly associate REST with JSON since the vast majority of REST API use JSON, but this is definitely not a prerequisite.

And just as often, many people forget, or intentionally omit, the final piece that the REST inventor claims is _fundamental to REST_. This missing piece has the difficult to pronounce acronym "HATEOAS" ("hay-dee-us"? "hate-oh-es"?) which stands for "Hypermedia as the Engine of Application State".

Several years back, when I was first exposed to REST, I squarely in the former camp. I implemented my "REST" API as an HTTP API using JSON and meaningful HTTP verbs. It was relatively simple to understand and simple to use. Then one day a coworker introduced the concept of HATEOAS and it was like the ground had dropped beneath my feet. Suddenly my simple pure data types had _links_ in them and what was worse is that I was being forced to make my client _discover_ server endpoints by following these links! 

What do you meant I can't use my hand crafted URLs? I knew how to construct the URLs by hand, why couldn't I let my program do the same?? If the client must discover the endpoint, does this mean the client must start at the root path and make N calls every time it needed to make a new action against the API?! Nothing made sense anymore!

Confounded, I set out to understand why my life had suddenly become 10x more complicated.

## HATEOAS

After a brief search, I found a few articles that helped provide context for HATEOAS and [one in particular by Martin Fowler](https://martinfowler.com/articles/richardsonMaturityModel.html) introduced me to the [Richardson Maturity Model (RMM) as originally presented by Leonard Richardson](https://www.crummy.com/writing/speaking/2008-QCon/act3.html).

The RMM is an easy to understand tiered list types of API and how they relate to parts of REST. It categorizes API by levels of maturity in terms of REST, each building on top of the previous:
- **Level 0: Single URI, single HTTP method**
  - This is the traditional XML-RPC and SOAP service design. Not often seen in new API today
- **Level 1: Many URIs, one HTTP method**
  - I've not seen many examples of this but Richardson does reference a few
- **Level 2: Many URIs, each supporting multiple HTTP methods**
  - This is seems to be the industry standard for "REST"
- **Level 3: Resources contain links that describe their capabilities and relationships**
  - The fabled HATEOAS that seems to be all too rare

Richardson provides some examples from Netflix and Amazon that demonstrate what it's like working with an API that's missing the HATEOAS aspects. It definitely seems like a public API that is self-documented and discoverable via hyperlinks would be incredibly helpful as the consumer. That said, I have personal experience with just how complicated requiring these hyperlinks can be. I am hardly surprised that many in the industry stop at Level 2. It's _so_ much easier to ignore Level 3 and push the workload onto the API consumers.

## Rest without HATEOAS is not REST
Roy Fielding is very clear in his opinion: ["... if the engine of application state (and hence the API) is not being driven by hypertext, then it cannot be RESTful and cannot be a REST API. Period."](https://roy.gbiv.com/untangled/2008/rest-apis-must-be-hypertext-driven)

I actually took some time to read over a few chapters from [Fielding's original thesis](https://www.ics.uci.edu/~fielding/pubs/dissertation/rest_arch_style.htm). Fielding sticks to diagrams and architectural theory rather than presenting coded examples. Likely as this was an academic thesis, not a technical white paper/specification. Because of this, it doesn't particularly help with how a REST API should be implemented. However, it does help define _why_ he feels so strongly about hypermedia driven API.

Fielding draws strong parallels between his REST API idea and web pages. He wants computer readable API that can be browsed naturally like a human would browse a web page. If you were browsing a news site, you wouldn't type an articles URL into the address bar each time you wanted to read a new article. You would browse to the root domain of the news site, then click on one of the many links (or links in a search result) and continue clicking on links as you browsed the page. Fielding's idea of REST was to [make API follow this pattern which had been tried and tested and had well established infrastructure support via the World Wide Web](https://www.ics.uci.edu/~fielding/pubs/dissertation/evaluation.htm#sec_6_1):

> The name "Representational State Transfer" is intended to evoke an image of how a well-designed Web application behaves: a network of web pages (a virtual state-machine), where the user progresses through the application by selecting links (state transitions), resulting in the next page (representing the next state of the application) being transferred to the user and rendered for their use.

## What is REST minus HATEOAS?
Okay, so we know what REST is and isn't, at least according to the creator and some other preeminent bloggers. But what about all these "RESTful" API that aren't apparently REST? They are certainly API; often successful ones at that. But if we can't call them REST, what can we call them?

Here's the crux of my current issue. Even without a name, I can easily recognize and categorize these API that are so widely adopted. They are usually "Level 2 REST API" according to the Richardson Maturity Model. But out of respect for Fielding, and for my own sanity in being precise when talking about API, I've tried to find a better name.

I've seen some people just call them "HTTP API" or "URL API" since clients are expected to know/construct URLs to use. Most recently I've started referring to them as "Open API" since it's catchy and many of these API have Open API documentation. In my current position, being able to differentiate between Open API and REST API has helped as I no longer feel forced to consider including HATEOAS or sticking to other REST fundamentals like having single resources per URL. (This may be an anti-pattern, but so far I've found accessing groups of resources on a single parameterized URL very liberating)

I recently found a great article from [Google Cloud](https://cloud.google.com/blog/products/api-management/understanding-grpc-openapi-and-rest-and-when-to-use-them) that goes into more detail about contrasts REST API and Open API, as well as gRPC which seems to be Google's chosen evolution in HTTP API.

## What's next?
I've started a project called [Battle of the API](https://github.com/aerotog/BattleOfTheApi) where I'm implementing various types of HTTP API. I plan to use this as a simple comparison tool between various HTTP API implementations with similar functionality/models.

The current implementations only include [Open API](http://spec.openapis.org/oas/v3.0.3), with built in Swagger UI, and [JSON API](https://jsonapi.org/) which is a framework that uses model type attributes to auto generates links that results in something resembling HATEOAS. (I would argue it's not "true" HATEOAS since it doesn't provide links for actions, only relations)

At work, I've started being more specific about the type of API I am implementing. I've stopped calling my API "REST" or "RESTful" if they don't contain hypermedia. I've opted to use "Open API" instead as we make liberal use of Open API documentation.

In the future, I hope to explore the use of gRPC and GraphQL as they have gained quite a following and provide more powerful options when designing API. It's always good to have more tools in the toolbox. It's a shame when you only have a hammer and some of your problems aren't nails.

~EOF~