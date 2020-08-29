---
title: That's not a REST API, THIS is a REST API
date: "2020-08-28T03:27:34Z"
description: "TODO"
---

- Estimation is a fool's game
- Estimating with hours is even worse
    - Friend who works for a company that assigned 40 hours of estimated work per week (120 hrs per sprint) for every engineer
    - Nightmare
    - Story points are relative, not absolute
        - Story Points Estimate Effort Not Just Complexity https://www.mountaingoatsoftware.com/blog/its-effort-not-complexity
            - So, story points are an estimate of the effort involved in doing something. That estimate should be based on a number of factors, including the volume of work, the risk or uncertainty inherent in the work, and the complexity of the work.
- https://en.wikipedia.org/wiki/Hofstadter%27s_law
    - Hofstadter's Law: It always takes longer than you expect, even when you take into account Hofstadter's Law.
- Projection is based on math
    - Velocity of team (V)
    - Velocity of New work per time (N)
    - Current count of Backlog work (B)
    - B + N\*t - V\*t = 0
    - B = Vt - Nt
    - t = B/(V- N) QED
- Projection requires established velocity
    - Can't project on day 1 of a new team, too many unknowns
- https://www.youtube.com/watch?v=QVBlnCTu9Ms
    - #NoEstimates
    - Can project based on ticket count (story point/size 1 for every ticket)
- Smaller tickets are easier to estimate
    - Estimating Epics will be less accurate than estimating tasks/stories
- Law of big numbers and moving averages
