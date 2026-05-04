---
layout: post
title: I Thought I Understood the System
tags:
  - claude-code
  - ai
  - rant
  - work
---
I’ve been using Claude Code for almost a year now at work, and it’s become deeply integrated into how I build software.

I’ve used it to debug data issues through a custom-built MCP that exposes internal tools to the agent. I’ve used it to build a data reconciliation system between a legacy Postgres reporting database and newer DynamoDB-based systems. I built a data fixer framework to standardize how our team handles corrections. Right now, I’m using it to help implement a major new feature: Spanish assessments in Amira.

Up to this point, I'd say the experience has been overwhelmingly positive.

I spend far less time thinking about implementation details and shift more focus on requirements and constraints. I use my experience to guide the agent to generate a reasonable solution, even if I'm not scrutinizing every line of code. And here lies problem #1, there’s simply too much code being generated to hold it all in my head — and I’ve been okay with that.

The system behaves correctly. Tests pass. Staging validates the behavior. Everything looks good.

But that confidence started to break when I needed to modify the scoring pipeline to support Spanish activities.

The system is complex and sparsely documented. Even with full codebase access, Claude couldn’t reliably infer the architecture or the implicit assumptions baked into the pipeline. Which brings me to problem #2: I didn’t fully understand the system, I’d just been getting by with AI filling in the gaps.

The issue wasn’t that the AI made mistakes. Given the state of the system, that’s expected. The real issue is that I didn’t have a strong enough mental model to catch those mistakes early or confidently steer the solution.

It got to the point where we had to regroup as a team to realign on the architecture and technical direction. That’s a humbling moment as a senior engineer.

What this experience made clear to me is that there’s no substitute for system-level expertise.

AI will do what it do best: writing functions, wiring components, even building entire features when the boundaries are well understood. But it will not give you accurate system shape, historical context, implicit invariants, and architectural intent.

And those are exactly the areas where engineers are supposed to learn and extend.

You can’t rely on AI to “crawl the codebase” and fully understand your system. It can approximate. It can assist. But it cannot own the mental model. That responsibility is still yours.

Stay sharp out there friends!
