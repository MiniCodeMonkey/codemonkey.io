---
template: post
title: How we collect metrics
slug: how-we-collect-metrics
draft: true
date: 2019-05-02T00:55:46.838Z
description: >-
  How we collect millions of events every day across ~100 servers for less than
  $60/month
category: Development
tags:
  - Development
  - Servers
---
At [Geocodio](https://www.geocod.io), we're now actively running close to 100 servers and the number keeps growing. 

Because of that, we decided to sit down and design a more robust system for collecting realtime metrics for each server, allowing us to monitor much more than just uptime. This is what we came up with.

