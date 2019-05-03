---
layout: post
title: Building an Online Game With LoopBack 4 (Part 3)
date: 2019-05-08
author: Wenbo Sun
permalink: /strongblog/building-an-online-game-with-loopback-4-pt3/
categories:
  - How-To
  - LoopBack
published: false  
---

## Part 3: Customizing APIs in Controller

### Introduction

"Ready to build amazing things?" asks the LoopBack 4 homepage before encouraging you to try the open source framework.

"Try LoopBack 4 now."

In this series, I'm going to do exactly that! Join me as I create an API web game using LoopBack 4.

The main purpose of this series is to help you learn LoopBack 4 and how to use it to easily build your own API and web project. We'll do so by creating a new project I'm working on: an online web text-based adventure game. In this game, you can create your own account to build characters, fight monsters and find treasures. You will be able to control your character to take a variety of actions: attacking enemies, casting spells, and getting loot. This game should also allow multiple players to log in and play with their friends.

### Previously on Building an Online Game With LoopBack 4

In the last episode, we used a third-party library to generate UUID and built relations between `character`, `weapon`, `aromr`, and `skill`.

Here are the previous episodes:

* [Part 1: Building a Simple LoopBack Project With MongoDB](https://strongloop.com/strongblog/building-online-game-with-loopback-4-pt1/)
* [Part 2: Generating Universally Unique ID and Managing Models Relationships](https://strongloop.com/strongblog/building-online-game-with-loopback-4-pt2/)


<!--more-->

### In this episode

We already have some simply APIs in our project. They are all default CRUD(Create, Read, Update, and Delete) APIs that auto-generated by LoopBack 4. In this episode. we will create our own APIs to achieve following functions for character updating:

![models](https://github.com/gobackhuoxing/first-web-game-lb4/blob/master/picture/models.png)
* The ability for users to equip their character with weapon, armor, and skill. This function should also be able to allow users to change weapon, armor, and skill for their character. In any cases, we should update `defence` and `attack` accordingly.
* The ability for users to unequip their character. We also need to update `defence` and `attack`.
* The ability to levelup a character when it get enough experience. We should update `currentExp`, `nextLevelExp`, `level`, `maxHealth`, `currentHealth`, `maxMana`, `currentMana`, `attack`, and `defence`.
* The ability to check character's `weapon`, `aromr`, and `skill` information.