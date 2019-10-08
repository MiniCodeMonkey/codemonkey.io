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

The API is the backbone of our business, so over the years we have continously worked to improve and ensure consistent performance. We look at many parameters such as uptime and error rates, but one of the key metrics is API response time.

This is how we use this data.

## Average response times

![Average response times](/media/api-response-times.jpg)

For the longest time, we focused on average response times. It is a quick and simple metric that you can quickly break down by API endpoint and time window -- What was the average response time the last 5 minutes veruss the last 5 hours?

While average response times has its place, it can also be deceptive. Take the following sample set of hypothetical response times in milliseconds for 10 tracked requests:

![Sample response times](/media/sample-response-times.png)

What is the average response time of these 10 requests? The answer is **122.4ms**. That doesn't sound too bad. But it completely hides the fact that one customer got a response in **642ms** which is significantly outside the "norm".

> (52 + 61 + 72 + 59 + 64 + 68 + 78 + 63 + 65 + 642) / 10 = 122.4ms

The larger the volume, the more this problem compounds. Luckily there is a solution: Percentiles

## Percentiles

Using percentiles, you will be able to say: "X% of API calls have a response time of Y milliseconds or less".

To calculate the percentile, you first sort your set of response times:

> 52, 59, 61, 63, 64, 65, 68, 72, 78, 642

Let's say we want to calculate the 95th percentile:

```
totalNumbers = 10
percentile = 95

index = ceil(percentile / 100 * totalNumbers)
```

`index` is now `10`, which means that "95% of API calls have a response time of 642 milliseconds or less"

You will often want to calculate multiple percentiles:

* The 75th percentile is 72ms
* The 90th percentile is 360ms
* The 99th percentile is 642ms

To get the most out of this type of analysis, you will of course need a much larger set of data.

## Real world examples

Here are some real examples from the Geocodio API. Each of these reports are based on response times over a 6 hour period.

![Response time percentile reports](/media/percentile1.png)
![Response time percentile reports](/media/percentile2.png)
![Response time percentile reports](/media/percentile3.png)
