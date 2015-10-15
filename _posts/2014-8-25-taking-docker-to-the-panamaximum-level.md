---
layout: post
title: Taking Docker to the Panamaximum Level
category: posts
---

Last year I dove into Vagrant and Chef to setup developer environments. For a while now I've been trying to wrap my head around Docker and why people are raving about it in the devops world so I decided try it more.

### Why Docker

[Docker](http://docker.com) is a very powerful tool to spin up isolated "containers" which are similar to virtual machines except that they aren't. They are built and ran as developers choose and every step inside a build file creates an image subset that can be used as a starting point in another image.

What does that mean? Well say you have 3 steps to setup a simple WordPress server.

* Install PHP/Apache/MySQL
* Setup Apache virtual host
* Create a MySQL database and user

You could do this with Vagrant and spend a while spinning up a server, but that is where Docker is different.

Now with Docker, say you now want to add Redis cache. The way Docker works is that you've already built an image with those commands up to that point in the Docker file so when you append the last step it can start at that point and build the new image from the subset of images above it. This makes Docker fast. You can destroy the image built from a Docker file and run it and it will be setup instantly.

The key difference is that with Vagrant you would have to recreate an entire VM from scratch to make the change and in addition Docker images are [shareable](https://registry.hub.docker.com/) so you can see how it was compiled with the Docker file instead of downloading a Vagrant box.

### Enter Panamax

I stumbled across [Panamax](http://panamax.io) recently and decided to try it out. Panamax takes Docker to a whole new level by managing containers for you and by essentially being the GUI around Docker's CLI toolset. It's [open source](https://github.com/CenturyLinkLabs/panamax-ui) and bridges the gap of managing Docker and setting up an infrastructure for you on AWS and other providers.

Panamax brings a lot of the Docker functionality like port binding, choosing images from the Docker hub and makes it as simple as a few button clicks to setup your application. They then took it even further by creating Panamax templates, which are applications that can be spun up really fast. They are reusable code files which setup any requirements for an application to run, this can be multiple docker containers (from images), setting up ports and volume mounts. You can even export your running application's settings as a template and spin up more based off it or contribute it back to the community.

Panamax lets you search for templates and see popular ones including projects like WordPress, Drupal, and my own [Laravel template](http://github.com/dmyers/panamax-contest-templates) to let you 1 click install on your infrastructure.

In summary, complex web applications that need to scale need to run more Docker instances and combine them together to build a complex setup that works together such as multiple web servers behind a load balancer and that's what Panamax is the ideal for.

*Disclaimer: This post was written for the Panamax contest.*