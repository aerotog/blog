---
title: Adding comments to a Gatsby static blog
date: "2020-08-28T03:27:34Z"
description: "In and out, twenty minutes coding session"
---

_Six hours later..._

- Gittalk. Not linked b/c it requires exposing a Github API secret. Seems like a bad idea
    - Also it requires document/window in its script which are not available in Server Side Rending which Gatsby uses to generate static sites

- Utterances - comments using Github issues - clever
- Simply javascript... try to add to template, no joy
- Blog post how to add it to Gatsby page https://dev.to/creativcoder/how-to-add-comment-support-on-your-gatsby-blog-using-github-utterances-423n
- HOWEVER: Method only works in Develop mode
	- Why? Because hooks, useEffect() only runs in client render mode
	- Gatbsy static page uses Server Side Rendering (or Static Site Generation more specifically) and doesn't trigger hooks like afterLoaded, ... useEffect
- What do?
- Try to add JS to Gatsby template fails
- doesn't execute...
	- can't even do console.log??
- enter dangerouslySetInnerHTML
	- no execute locally, file:// doesn't match hosted for utterance script (local file vs web serve)
- safe-react? via stack overflow for SSR
- It works in Github!! Posted a comment! Then it fails to load... WTF?
- It works!!! Sometimes... Seems like the host might be flakey... Might be cache woes
- But safe-react is a not very popular thin wrapper around dangerouslySetInnerHTML. I prefer using standard system syntax