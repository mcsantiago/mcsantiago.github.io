---
layout: post
title: Agent Ash - A Reinforcement Learning Project
---

This is a side project that combines one of my favorite childhood games with one of my favorite machine learning techniques: Pokemon and Reinforcement Learning. 
This is my attempt on build an AI robot, who will be the very best that no one ever was!

## Some Background
For those who don't know, Pokemon is a turn-based strategy game where the
objective is to knock out all of your opponent's Pokemon. It is a strategy game
that tests your ability to exploit each Pokemon's weaknesses while optimizing
the advantage for your own. There are too many specifics to cover for a blog
post, so I will link to the [IGN Wiki for battling in Ruby and
Sapphire](https://www.ign.com/wikis/pokemon-ruby-sapphire-emerald-version/Battling),
which will more or less cover the mechanics for most of our platform.

To emulate this environment, I will be using [Pokemon
Showdown](https://github.com/smogon/pokemon-showdown) and the recently developed
[Poke Env](https://github.com/hsahovic/poke-env) as the OpenAI gym environment
to train our AI. This is actually a project I had on my radar for quite some
time, but never had a chance to work on it until now. Luckily, there's a whole
community of us [on Discord](https://discord.gg/VzrFGaaZhV).

## The Problem and The Approach
So what does it mean to be the very best that no one ever was? To me, it means
to be able to employ the optimal strategy for any given situation for the best
possible outcome. This means that for any given set of Pokemon in any state on
both teams, the agent will then derive the best strategy for this particular
game. However, with the total number of Pokemon supported in Pokemon Showdown,
and the large number of possible states, it is difficult to search our state
space efficiently. To make matters worse, the opponent's Pokemon are unknown
until they are drawn out.

One way to tackle this problem, is to play this game a ton of times and build a
sort-of understanding of the world, a.k.a the model. In this blog, we will use
[Deep Q-Learning] (https://www.tensorflow.org/agents/tutorials/0_intro_rl) in an
attempt to build such a model.
