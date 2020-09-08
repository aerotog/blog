---
title: A REST API by any other name
date: "2020-08-28T03:27:34Z"
description: "That's not a REST API. THIS is a rest API."
---

- [Introduction: What is REST?](#introduction-what-is-rest)
- [HATEOAS](#hateoas)
- [Rest without HATEOAS is not REST](#rest-without-hateoas-is-not-rest)
- [What is REST minus HATEOAS?](#what-is-rest-minus-hateoas)

## Introduction: What is REST?

There's a fundamental misunderstanding that is endemic in the software industry. Before continuing, please take a moment to mentally answer this question:

> What defines a REST API?

Do you have an answer in mind? You most likely know it's an HTTP based web API. Maybe you know the acronym stans for "Representational State Transfer" and with that you know that data is communicated between the client and server in the form of "representations". Perhaps you included the very useful semantic use of HTTP verbs (getting data with HTTP GET vs. writing data with HTTP POST).

Quite often people incorrectly associate REST with JSON since the vast majority of REST API use JSON, but this is definitely not a prerequisite.

And just as often, many people forget or intentionally omit the final piece that the REST inventor claims is fundamental to REST. This missing piece has the difficult to pronounce acronym "HATEOAS" and stands for "Hypermedia as the Engine of Application State".

Several years back, when I was first exposed to REST, I definitely started in the former camp. I implemented it as a HTTP API using JSON and meaningful HTTP verbs. It was relatively simple to understand and simple to use. Then one day a coworker introduced the concept of HATEOAS and it was like the ground had dropped beneath my feet. Suddenly my simple pure data types had _links_ in them and what was worse is that I was being forced to make my client _discover_ server endpoints by following these links! 

What do you meant I can't use my hand crafted URLs? I knew how to construct the URLs by hand, why couldn't I let my program do the same?? If the client must discover the endpoint, does this mean the client must start at the root path and make N calls every time it needed to make a new action against the API?! Nothing made sense anymore!

Confounded, I set out to understand why my life had become 10x more complicated overnight.

## HATEOAS

After a brief search, I found a few articles that helped provide context for HATEOAS and [one in particular by Martin Fowler](https://martinfowler.com/articles/richardsonMaturityModel.html) introduced me to the [Richardson Maturity Model (RMM)](https://www.crummy.com/writing/speaking/2008-QCon/act3.html).

The RMM is an easy to understand tiered list of aspects of REST API. It categorizes implementations of REST API by levels of maturity:
- Level 0: 


## Rest without HATEOAS is not REST

## What is REST minus HATEOAS?

https://cloud.google.com/blog/products/api-management/understanding-grpc-openapi-and-rest-and-when-to-use-them

- REST without HATEOS is not REST
- REST vs RESTful
- Martin Fowler levels of REST
- REST API without versions? Fielding seems to prefer
- What are RESTful API really? OpenAPI, Web API, JSON API??
