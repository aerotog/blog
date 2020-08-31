---
title: "Book Review from the Archives: Clean Series"
date: "2020-08-28T03:27:34Z"
description: "Keep it clean"
---

- [Introduction](#introduction)
- [Clean Code: A Handbook of Agile Software Craftsmanship](#clean-code-a-handbook-of-agile-software-craftsmanship)
  - [The Boy Scout rule](#the-boy-scout-rule)
  - [Meaningful names](#meaningful-names)
  - [Small functions/classes](#small-functionsclasses)
  - [Bad comments are worse than no comments](#bad-comments-are-worse-than-no-comments)
- [The Clean Coder: A Code of Conduct for Professional Programmers](#the-clean-coder-a-code-of-conduct-for-professional-programmers)
  - [Professionalism](#professionalism)
  - [TDD and Acceptance tests](#tdd-and-acceptance-tests)
  - [Estimation](#estimation)
  - [Mentoring and convincing people](#mentoring-and-convincing-people)
- [Clean Architecture: A Craftsman's Guide to Software Structure and Design](#clean-architecture-a-craftsmans-guide-to-software-structure-and-design)
  - [Why is good architecture important?](#why-is-good-architecture-important)
  - [SOLID](#solid)
  - [Low coupling, high cohesion](#low-coupling-high-cohesion)
  - ["Details" should not influence architecture](#details-should-not-influence-architecture)
  - [Hexagonal architecture](#hexagonal-architecture)
- [Conclusion](#conclusion)
# Introduction
While I am currently reading a few different books about software, I have a number of books I've read about which I want to record my thoughts. This post covers a trio of books that all share the same "Clean" prefix: _Clean Code_, _Clean Coder_, and _Clean Architecture_.

I have a fondness for the _Clean_ series of books by Robert "Uncle Bob" Martin. _Clean Code_ was one of the first books on professional software development recommended to me and I found it to be full of helpful guidelines and code examples. It was very useful as someone new to the industry, especially with a non-computer science background. (My degree being in Aerospace)

Since then, I've found a not uncommon negative sentiment for the book in the online community. The view seems to be that the book's suggestions, when overused by developers who don't know better, cause more problems than they solve. I've definitely seen cases where a developer tried to apply the rules with less than stellar results. But in general, I appreciate having a common basis of understanding/expectations from which more advanced design can grow.

I see far fewer discussions about the newer books in the series, _Clean Coder_ and _Clean Architecture_. Similar to _Code_, I found them quick and easy introductions to a number of important topics. I would recommend all three of the books to newly minted professional developers.

It's been a while since I've read the first two. I could easily spend an multiple posts on each book, but for now I've summarized a few of my most memorable points from each.

# [Clean Code: A Handbook of Agile Software Craftsmanship](https://www.amazon.com/dp/0132350882)
_Clean Code_ focuses on the tactical aspects of coding. It presents some easy to follow guidelines on how to avoid common pitfalls of what are often unintended consequences of honest efforts. 

After describing and providing context to the theory, the latter part of the book presents concrete code examples of how the theory can be applied via refactoring. Very much a "show vs. tell" way of teaching which while slower to get through, I find it often more memorable.

## The Boy Scout rule
**Leave the code better than you found it.** Having been a Boy Scout, I'm quite familiar with this idea and it's something I try to live by in other areas of life.

This simple concept has some parallels to the broken window theory from _Pragmatic Programmer_. Entropy will always increase. Without actively fighting against this, code will inevitably get worse with time.

Like Martin suggests, I've found the easiest way to counter this is to proactively take small steps in improving code each time you touch it. Every time you are in a code base making changes, consider adding unit test coverage or refactoring code to make it easier to grok.

## Meaningful names
I've seen something as innocuous as decisions about naming devolve into a hour long discussion in my team. Like the book, I prefer names with meaning over one off abbreviations and acronyms. But I've seen this taken to the extreme with hundred plus character long method names which I think is an anti-pattern. Names should optimize the signal to noise. They should be as short as possible while also providing sufficient information to the reader in a given context.

Going one step further, I try to follow the _Domain Driven Design_ paradigm of using the Domain defined language. This makes it easier to speak with business and domain specific teams as we use the same language for the same concepts.

## Small functions/classes
Somewhat surprisingly, there seems to be quite a lot of contention around this topic, but can we all agree god objects are bad? Martin does appear overly enthusiastic about single line functions, but on the spectrum of long vs. short modules, I'll almost always prefer shorter. They are usually easier to understand, test, and refactor.

That said, I recently read an [article](https://softwarebyscience.com/very-short-functions-are-a-code-smell-an-overview-of-the-science-on-function-length/) that showed evidence that longer functions actually result in fewer defects per line of code. I don't know if this is an artifact of the code being long or a direct result of the logic pathing being simpler to follow, but it's something to consider.

I feel the most important thing is keeping code logically grouped. If this means making your function run a bit long, it's probably okay.

## Bad comments are worse than no comments
_Code_ emphasizes self documenting code. The first team I worked with went so far as to say every in line comment was a code smell. This is one of those rules that I think will get you in trouble if you follow it too closely. What might make perfect sense while being written will often become confusing mazes to the your future self or another team member less knowledgeable with the problem space. Ideally, the purpose of code should be self evident based on how its written, but this lofty goal can't always be satisfied. 

As a general rule, if I'm ever being clever, I add a comment. If I am calling functions that are either obscure or misleading, I consider adding a comment. But I do prefer wrapping these calls in helper functions like Martin suggests.

One of my biggest notes from the book that has matched my personal experience is __comments lie__. Just like documentation, it's all too easy for comments to be forgotten and not updated while the code is actively changing. This is one of the main drivers for self documenting code. Code may be harder to read and sometimes misleading, but it doesn't lie.

# [The Clean Coder: A Code of Conduct for Professional Programmers](https://www.amazon.com/dp/0137081073)
_Clean Coder_ takes a step back from the technical aspects of engineering and focuses more on the soft skills. Without the low level technical details of the other books, this was a very easy read and I appreciated how it broadened the scope of an engineering job by considering a developers work in the context of the rest of the company: how a developer's efforts impact, and is impacted by, other positions and needs.

## Professionalism
The books starts out on a very broad topic: professionalism. It sets the tone for the rest of the book as the later chapters often pose their theories in the context of what being a professional means. This theme leads into a multitude of very important topics including: understanding business needs, communicating across and outside the team, generating quality work.

I think professionalism is one of those qualities that can benefit everyone by simply being mindful of it. In the ever evolving and relatively young industry of software engineering, it's all too easy to fall prey to the siren call of the casual office space. This risks losing sight of what it means to be a professional. While keeping a casual work environment is not a bad thing, it can be difficult to balance that with acting like a professional. This book serves as a good reminder of the benefits of professionalism. Like in most things, balance is important.

## TDD and Acceptance tests
I've been fortunate in that my teams, managers, and product managers have historically been supportive of the theory of Test Driven Development (TDD), even if they did not pursue/practice it on a daily basis. This has led to decent test coverage. I cannot say the same for acceptance tests.

I once worked with a team that ran "acceptance tests" against their product. (I include quotes as I don't think I would qualify the tests as such given my current understanding) For these tests, the team used a tool that was at the time two years past its end of life. It was a nightmare to maintain and the tests were incredibly flakey. The tests would often take 5 or more runs to get every assertion to pass, each an hour long, and the assertions rarely all passed in a single run so the artifact often had to be manually promoted in the end.

The product in question was being sunset, so the team decided not to invest the time and effort in improving the situation. Seeing the problems with these tests, the team moved away from acceptance testing altogether and instead opted for automated integration tests.

After reading _Clean Coder_ I now think this was a mistake. At the time, I didn't understand the purpose of acceptance tests and considered them little more than a nuisance. Now the purpose of acceptance tests makes much more sense. 

Acceptance tests, as they have specifications written in plain English, allow the product owner and QA teams to contribute test cases. As opposed to writing white paper specifications for a product, they can write test cases, that once passed, should mean the development team has successfully met the original requirements. __Acceptance tests allow for TDD at the product/team level.__ Without these types of tests, it's much harder for effective communication of requirement between product and dev and harder to prove the satisfaction of those same requirements.

## Estimation
As a scrum master, estimation is of utmost importance. I've seen what happens when estimates turn out to be accurate, and I've seen what happens when they are off by a wide margin. More often than not, it's the latter case.

_Coder_ focuses on how estimates are viewed differently by developers vs. clients/business teams. While developers often view estimates as a guess, what the other party often wants are commitments. Unfortunately, it's often impossible to make a commitment when first starting a project because their are too many unknown variables.

The book tries to emphasize as a professional, the developer should avoid making commitments before they are confident they can meet them. This would be nice, but it unfortunately seems a bit naive. I've seen time and time again where developers are asked to provide estimates for work that will take an unknown amount of effort which are immediately turned into commitments to the rest of the organization.

Personally, I've started focusing on __projections__ instead of estimates. I have a blog post in mind that would go into further detail. In short, by establishing a team's velocity and a fully estimated backlog of work, it becomes possible to project when the work will be completed. This seems obvious, but the catch is neither of these things can be known __until the project has already started__. And quite often, this is too late in the mind of management.

## Mentoring and convincing people
As I've gained seniority in my current position, being able to mentor and convince others has become increasingly more important. I feel like I do a decent job introducing and communicating concepts to members on my team but I'm still trying to improve my ability to influence the direction of projects.

Previously I mentioned how I now advocate for acceptance testing with product and QA being actively involved with their creation. I've not yet been able to convince the wider organization this is how we should be operating.

I originally tried to communicate the idea and convince the team to plan the work necessary. This did not succeed as we were focused on feature development. Now I'm trying to follow the book's advice and instead show rather than tell. __Actions (and results) speak louder than words.__

My new plan is to incorporate the new testing strategy into our new service/feature development. This will allow us to see if it actually improves our development pipeline without interfering too much with timelines. This is more difficult to manage as we'll have competing concerns from the broader scope of the project, but I think it's worth pursuing.

# [Clean Architecture: A Craftsman's Guide to Software Structure and Design](https://www.amazon.com/dp/0134494164)
_Clean Architecture_ dives back into the technical aspects of the job but mostly avoids code example and instead favors diagrams, the most common tool of the architect and what the book aptly describes as "drawing lines between boxes".

With its diagrams, it steadfastly argues for its Clean Architecture approach to system design. This mainly focuses on well defined boundaries between loosely coupled components and delaying decisions on what it calls "details" as long as possible, if not indefinitely.

## Why is good architecture important?
Before describing what makes good architecture, the book provides examples of _why_ good architecture is important. The gist is that code maintenance, including bug fixes and feature adds, far outweighs initial implementation in cost. While I had heard this before, I never really understood how/why that was true. The book makes a very salient point.

Quite often, product owners are a source of what they view as reasonable, similarly sized feature requests. But from the developers point of view, each subsequent feature is a puzzle piece that must be added to an every growing and ever more complex puzzle. Each individual piece may be similar in size, but it is inherently more difficult for each new piece.

The goal of good architecture is to make adding new puzzle pieces to the system easier. This minimizes cost of maintenance and delays the somewhat inevitable tipping point where costs outweigh the value of new feature additions.

Good architecture can be difficult to carry out since it quite often results in larger up front costs in terms of development time. Ultimately the architect must try to achieve sufficiently good architecture that will meet the future business needs without blowing up the project's budget and timeline.

## SOLID
If you spend any amount of time exploring popular software design best practices, you will inevitably stumble upon the [SOLID acronym](https://en.wikipedia.org/wiki/SOLID). As Martin's design philosophy is the origin of the SOLID principles, it's no surprise he often promotes the acronym in his books.

I didn't learn about SOLID from _Clean Architecture_ but the book does spend a separate chapter for each letter's namesake and provides some useful context to the theory behind the concepts.

## Low coupling, high cohesion
One of the trickiest things to balance as a software architect is coupling vs. cohesion. The two ideals are often at odds.

You can maximize cohesion by having a single "god class" but then suffer the consequences of highly coupled code. Alternatively, you can have tiny single purpose modules to maximally decouple things but suffer the consequence of hunting and navigating a complex file structure with very little cohesion.

Neither of these extremes are desireable. Instead a good architect should seek balance between the two. Knowing when to trade one for the other can be very difficult.

## "Details" should not influence architecture
The book separates code into two categories:
- Policies
- Details

It defines Policies as the business rules and procedures of the system whereas the Details are everything else that allows the outside world interact with the Policies. These Details include: IO devices, databases, web systems, etc. etc.

While I easily understand and agree with the premise that the external interactions should be decoupled and independent of the underlying business rules, the book goes so far as to say that the Details _don't matter_ and that decisions about them should be delayed until the last possible moment.

I get that delaying decisions allow designers the most time to gather information, but I question the practicality of this argument. Yes, sometimes the Details in question are eventually deemed unnecessary and by delaying their implementation can avoid unnecessary work. But quite often there are fundamental design/performance requirements that require these Details. Or alternatively, the existence or lack of a certain feature directly informs how much work the business rules will need to perform.

I do agree that the ideal design is one that codes against interface behind which the Details can be swapped at will, but I've found that quite often this forces the designer to make grave concessions by accounting for differences in the underlying Detail implementations. The concessions are not free and intentionally obfuscating these Details as "unimportant" seems questionable. But it is something I will keep in mind moving forward.

## Hexagonal architecture
__aka Ports and Adapters__
The book briefly mentions this a few times but spends quite a bit of time talking about ideas that closely align with this type of architecture.

I was already somewhat familiar with Hexagonal design as one of my coworkers tried introducing it a ways back. It did seem attractive in theory, but I never fully grasped how it could be implemented when I tried to apply it to our existing code base.

The later chapters, especially chapter 34 "The Missing Chapter" which is written by Simon Brown provide some examples of how this type of architecture can be achieved.

What I think was a key missing piece for my understanding was that __implementations do not own their interfaces__. That vast majority of interfaces that I have seen have lived in the same namespace as their implementations. This seems to go hand in hand with the very common top down Layered Architecture which, while relatively easy to understand, has some fundamental traps like forcing the business layer to depend on the persistence/DB layer.

By allowing the business/domain layer to control or own the interfaces it uses (including all IO and persistence interfaces) it makes the control flow much more intuitive. Instead of a top down control flow, the result is an "inside out" control flow.

The diagrams describing the control flow has greatly helped me understand how Hexagonal architecture can be implemented and I hope to put it to use in the near future.

# Conclusion
What did we learn? That I should avoid writing blog posts this long/dense. Oh, sorry, you meant the books.

What did we learn _about the books_?

In the _Clean_ series of books, Robert Martin does a great job introducing a broad range of fundamental topics to fresh eyes. He may not go into much detail for each topic, but the easy reads make it possible to get through all the material without getting fatigued.

_Clean Code_ presents a variety of code examples on how to avoid common pitfalls new developers often fall for. Some of these ideas can be abused so they must be thoughtfully applied rather than followed dogmatically.

_Clean Coder_ does a good job at focusing on the softer skills of the day to day responsibilities of a professional software engineer. It helps provided context and understanding of the needs outside the immediate surroundings of the ~~lowly code monkey~~, ahem, I mean software engineer.

_Clean Architecture_ provides a several methods of arriving at good system and code architecture. Some of these methods seem much easier to understand/quantify and implement than others.

Overall, I will continue to recommend all three books to new developers. Experienced devs may already know much of what the books have to say, but even so I think the books could serve as a quick, concise reminder for how to recognize and pursue best practices both in terms of code and in terms of human interactions.

__Result: 3x Recommended__

~EOF~