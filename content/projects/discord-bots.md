---
title: "Discord Bots"
date: 2025-08-21
draft: false
github_link: "https://github.com/AubreyFeldker/BattleBot"
author: "Aubrey Feldker"
badges:
    - "JavaScript"
    - "APIs"
image: "{{ .Site.Params.staticPath }}/images/projects/bots.png"
description: "Multiple interactive bots that utilize Discord's API to service information and fun activities to over 38,000 users."
---

Since 2020, I have spent a lot of my spare time developing user applications ('bots") for the social media platform Discord, utilizing their publicly available API. Each of them are written in JavaScript, utilizing public libraries to subscribe to queries made by users on the platform. Though I've worked on a couple over the past few years, there's two main bots I've continued to take care of.

### [BattleBot](https://github.com/AubreyFeldker/BattleBot)

Starting work on it in 2021, BattleBot is a general-purpose application for tracking user activity and event management on an officially partnered Discord server with over 38,000 users. Subscribing to Discord's API allows for each user's messages to be processed, giving them points for their activity, with roles being automatically updated on Discord at certain milestones. Several commands are available for users, with a convenient UI and graphics built through components to provide a convenient user experience.

### [HLTBot](https://github.com/AubreyFeldker/HLTBot)

Created in 2024, HLTBot accesses information from howlongtobeat.com and processes it into an accessible Discord command. With no public API, the information is instead accessed via scraping HTTP requests from the main page and procedurally finding the endpoint for searching information. This endpoint is frequently shuffled into paths such as `/api/ouch/78952b080bf5c22b`, but my application is able to find the new paths on change with minimal downtime. Testing for the bot heavily utilizes Postman.