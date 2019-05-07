---
template: post
title: A billion requests per month
slug: a-billion-requests-per-month
draft: true
date: 2019-05-07T01:46:20.565Z
description: >-
  Geocodio is now geocoding more than a billion addresses every month. This is
  an overview of the infrastructure “under the hood”
category: Development
tags:
  - Development
  - Servers
  - Software
---

Last month, we answered the question: "What is the coordinates for this street addresses?" or "What is the address for these coordinates?" 1,079,278,538 times to be exact. This is an overview of the infrastructure that powers this.

## App layer

Geocodio primarily consists of two apps:

* **dash.geocod.io:** A [Laravel](https://laravel.com) app that allows customers to mange API keys, view usage and adjust billing details
* **api.geocod.io:** A [Laravel Lumen](https://lumen.laravel.com) app that has the sole purpose of serving the geocoding API and handling the actual geocoding process

Both of these apps rely on:

* [Redis](https://redis.io) for in-memory caching, queuing of asynchronous jobs and session management for the dashboard
* [MariaDB](https://mariadb.org) for permanent storage of user data, metadata for uploaded files, etc.
