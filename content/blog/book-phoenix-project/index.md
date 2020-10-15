---
title: "Book Review from the Archives: The Phoenix Project"
date: "2020-10-15T04:13:08Z"
description: "\"Improving daily work is even more important than doing daily work.\""
---

Today I was talking to a dev on my team about the responsibilities of an engineer and how easy it is to get pigeonholed by others. If you're not careful, as soon as you prove yourself capable of solving a specific problem, everyone turns to you when they encounter a similar problem.

Some people are okay with this. Some may even prefer it! But it becomes an organizational anti-pattern when the rest of the team becomes dependent on a single person for a given problem. Suddenly this person gets stuck with the same work day after day, and all similar work is stuck with this person. When this happens, you have witnessed the birth of a "Brent".

[__The Phoenix Project__](https://www.amazon.com/Phoenix-Project-DevOps-Helping-Business/dp/0988262509) is a fictional novel which presents itself as a sort of allegory for how dysfunctional large software organizations can become when teams don't consider how their actions impact others. It shows how to correct this by introducing the concept of [The Three Ways](https://itrevolution.com/the-three-ways-principles-underpinning-devops/) which are essentially methods for improving work throughput by improving quality of work. Part of this effort is a focus on identifying bottlenecks so their throughput can be improved, and therefore the throughput of the whole is improved. As stated in the book:

> “Any improvements made anywhere besides the bottleneck are an illusion.”

This concept is adapted from the Lean Production [Theory of Constraints](https://www.leanproduction.com/theory-of-constraints.html). This rings true for any system design, software included! However, while technical bottlenecks are usually pretty obvious in a system, organizational bottlenecks can be harder to identify and thus harder to fix.

Enter "Brent".

In the book, Brent is an ace of an engineer. He's proven himself able to solve in record time every technical fire that comes across his desk. Unfortunately, there's only one of him and so many hours in a day, so he only gets the hardest problems to solve. This continues until such a time when he has multiple top priority needs all vying for his attention. Suddenly he's faced with the dilemma of whose work to prioritize and it really comes down to who talks loudest.

Inevitably, Brent makes a mistake. And since Brent is the only one who know how Brent operates, Brent is the only one who can fix Brent's mistake. Do you see the problem?

Brent has entered a never ending cycle of fires. And a single person handling a set of responsibilities like this cannot scale. Just like how the ideal microservice architecture should be able to scale horizontally, so too should organizational work assignments.

Once the bottleneck that Brent has become is exposed, the newly appointed VP of IT Operations, Bill Palmer, our protagonist, has other engineers shadow Brent so they can learn and help relieve Brent from some of his responsibilities. This frees up Brent from always putting out fires to spend time on improving his own work flow along with others with work he had been putting off due to lack of time. (Not to mention some peace of mind by not always being on the hook for every major outage)

I actively avoid the creation of single responsibility engineers mainly due to the risk involved with their unavailability causing a gigantic roadblock in future work. But even with them present and available, not having alternative workers for a given action can still be detrimental as scheduling becomes problematic. Thus I've actively tried to stop both myself and others from becoming a "Brent" by urging cross training and encouraging others to branch out as much as possible to learn a wide range of technologies rather than become overly specialized in a single area.

__The Phoenix Project__ does a great job of presenting a wide range of common pitfalls for large software teams. (I identified dozens of cases from the book that seemed to mirror my own past experience) And while it seems overly optimistic with how successful (and quickly!) the protagonist was able to correct his organization's behavior, it was nevertheless thought provoking in presenting new ways to conceptualize these shortcomings and the potential improvement of a well organized work force.

Overall, I highly recommend __The Phoenix Project__ for anyone who struggles with observed inefficiencies in their work place. It's especially helpful to provide context and understanding after having worked on a "failed" project and provides some ideas on how to improve these situations and avoid them in the future.

I look forward to reading the sequels by the same authors: [__The DevOps Handbook__](https://www.amazon.com/DevOps-Handbook-World-Class-Reliability-Organizations/dp/1942788002) and [__The Unicorn Project__](https://www.amazon.com/Unicorn-Project-Developers-Disruption-Thriving-ebook/dp/B07QT9QR41).

~EOF~