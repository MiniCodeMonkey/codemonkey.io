---
template: post
title: API Performance Tracking
slug: api-performance-tracking
draft: true
date: 2019-10-07T01:46:20.565Z
description: >-
  When average response time doesn't tell you everything
category: Development
tags:
  - Development
  - API
  - Software
---

Geocodio serves over 160 million successful API requests every month totalling over 1.3 billion address and coordinate lookups.

The API is the backbone of our business, so over the years we have continously worked to improve and ensure consistent performance with one of the key metrics being API response time.

This is how we use this data.

## Average response times

![Average response times](/media/api-response-times.jpg)

For the longest time, we focused on average response times. It is a quick and simple metric that you can quickly break down by API endpoint and time window -- What was the average response time the last 5 minutes veruss the last 5 hours?

While average response times has its place, it can also be deceptive. Take the following sample set of hypothetical response times in milliseconds for 10 tracked requests:

![Sample response times](/media/sample-response-times.png)

What is the average response time of these 10 requests? The answer is **122.4ms**. That doesn't sound too bad. But it completely hides the fact that one customer got a response in **642ms** which is significantly outside the "norm".

The larger the volume, the more this problem compounds. Luckily there is a solution: Percentiles

## Percentiles

