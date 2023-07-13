---
layout: post
title:  Unmasking the Hidden Leak
tagline: CodeGlass Case Study
date: 2023-07-13 09:01
categories: [Blog]
tags: [CodeGlass, Case Study]
image: img-01.jpg
---

Have you ever faced a performance issue that only shows up in production but never in development? This is a case study about such a 'phantom' issue and how CodeGlass came to the rescue.

Back in 2022, a software company approached us with this exact problem. Their application was suffering from a classic symptom of a performance leak - it would start off running smoothly, but over time, it would slow down, eventually requiring weekly restarts, while they wrestled with a mystery behind the scenes.

Despite their best efforts, the developers were not able to reproduce the issue in the development environment. They even went as far as copying and anonymizing the production database, but the slowdown remained elusive. The problem seemed to be tied not just to the data but also to the unique interactions of their customers in the production environment.

Having heard of our success with another client, they approached us for help. While CodeGlass can fully collect week-long data with minimal overhead, it was deemed inefficient to run continuously when only a few minutes of data were needed after a week. To address this, we developed the 'Soft off' feature, which can toggle the data collection of CodeGlass, resulting in near-full performance.

After a week of running in 'Soft off' mode, the developers turned CodeGlass back on and opened the 'real-time rendering' feature, which visualizes every code step the application takes. To their surprise, they saw code running that they had previously ruled out as a potential issue as it would not run on production. After letting CodeGlass collect data for a minute, they opened the 'statistics' feature, which confirmed that it was also causing the issue.

The troublesome code was a singleton service to validate that two data streams between two systems were correct. This service was only meant to run in development and should have been disabled in production. They ruled it out as an issue themselves, as the first instance of this service was indeed disabled. However, due to a fault in the code preventing the check on production, new instances kept being created on specific actions and were left triggering each time, leading to a gradual slowdown.

In software development, performance issues can often be elusive and challenging to diagnose, especially when they only surface in the production environment. This case study highlights the power of CodeGlass in uncovering such hidden performance issues. The software company had been grappling with a mysterious slowdown for months, spending countless hours trying to reproduce and diagnose the issue in a development environment. However, the problem was tied to unique circumstances in the production environment and could not be replicated in development.

With CodeGlass and its 'Soft off' feature, the team could efficiently collect the necessary data in the production environment without significantly impacting performance. When the issue surfaced, CodeGlass's 'real-time rendering' and 'statistics' features quickly pinpointed the problem - bad code continuously creating a service that should have been turned off in production, leading to a gradual slowdown.

Within minutes of using CodeGlass, the team identified the issue that had eluded them for months, demonstrating the tool's power and efficiency. This case study underlines the importance of having the right tools for diagnosing performance issues in production environments. With CodeGlass, developers can highlight the hidden issues affecting their applications, saving time and resources while ensuring a smooth user experience. It's not just about finding a needle in a haystack - it's about knowing where to look.

