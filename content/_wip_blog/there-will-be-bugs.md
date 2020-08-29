---
title: There will be bugs
date: "2020-08-28T03:27:34Z"
description: "TODO"
---

- Management wants zero bugs in code
- Is that possible? Realistic?
- There will be bugs: If on average a developer introduces a bug once every two months (seems reasonable) a team of 8 developers will introduce a new bug every week (!)?
- Mitigation vs Ellimination
    - TDD
    - Roll forward/fast/agile reaction to bugs
    - Continuos deployment (allows devs to see code through to production, 12 factor app style) https://12factor.net/
    - Bug escape review
        - Why was it missed? What new testing could be added that would have caught it?
        - Swiss cheese security - every layer will have gaps, the more layers you have, the less likely you'll miss something (like a siv)