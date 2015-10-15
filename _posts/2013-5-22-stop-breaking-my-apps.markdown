---
layout: post
title: Stop Breaking My Apps
category: posts
---

APIs allow developers to integrate with sites in a way that allows for allowed or approved data sets to be retrieved and manipulated rather than scraping which can easily break with an update to an application.

The trend with APIs is that you should version them so that way developers that implement them are not susceptible to their applications breaking when the site that provides the APIs adds new features in a new version or update to their APIs.

The following companies I have worked with and have experienced issues when the API version was supposedly finalized and production ready and you would think my application would not break from integrating with them. My main reason for integrating was for providing a single sign on solution. You're signed in with one of these providers and you are one click away from logging into my application.

## Major API Providers

### GitHub

About 2 weeks ago GitHub login was broken in my application due to a **new** requirement from their already supposedly production API v3 to require a `User-Agent` header. I have a lot of respect for GitHub and the work they do for the open source community. Unfortunately PHP's implementation of cURL does not pass this along or they do not like the default values.

### Twitter

About a month ago I noticed Twitter login was broke on my applications. I dove in and checked to see what other developers were having the newly found response from the API calls when requesting a token. It turns out that Twitter forced a **new** requirement that required a `oauth_verifier` token to be passed when requesting a token in their API.

### Facebook

About 3 months ago my application stopped working with Facebook login. When I looked into the cause, many people reported the problem and the one solution was that Facebook had changed everyone's API secret and application keys to a **newly** required longer standard about a year ago or so and hadn't notified me.

## Bottom line

The changes from these very large API providers broke many applications across the web. Think about these things when you create a publicly accessible API and don't want to break backwards compatibility with existing applications. Rather than implementing theses new requirements on the existing API version, create a new version of your API and force this requirement from the beginning. Developers all over the web are really tired of their applications breaking, especially people who hire developers to implement APIs are tired of spending money and then having to spend more to fix the problems afterwards.

What can be better is a more open line of communication between API changes and the developers who work on the implementations. A blog post, while good, is not enough. Our critical applications need a better solution before they break. API providers should require an email address and notify it when potentially large changes are happening, but I don't think that should happen without a new version change.
