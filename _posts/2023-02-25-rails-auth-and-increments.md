---
layout: post
title: Rails Authentication and Small Increments
date: 2023-02-25 11:59:00-0400
description: I am building a small web app that will be used for tracking data around workouts. The first thing I want to build is user authentication, but there are an overwhelming number of options available. Thinking about what can be done now, and allow for future growth was a good exercise in context and incremental delivery.
categories: side-project
giscus_comments: true
---

I am starting working on a side project, a small web-app that I’ll use to track data from workouts. I have been documenting my workouts for years with pen and paper in journals, and that mostly works fine. 

I can write my plan for the current day, document what actually happens, and then see how things have gone in previous weeks, months, and years if I feel like sorting through them. There is a stack of these journals in my garage.

I want to digitize this process so that I can use less paper, and eventually do a little data analysis and graphing. There are tons of options out there, but I have been wanting to build something and this seems fun.

## First Use Case
The first thing I want to do (after getting my local environment setup with recent versions of Rails and Postgres) is create a notion of a user and figure out some way to authenticate a person.

There are tons of options for authentication for Rails apps, and sorting through them gets overwhelming quickly. Each time I read through a new gem, I thought to myself – that is pretty cool but it’s also time consuming to set up and manage and definitely overkill.

## Incremental Delivery
I think about the intersection of context and immediate value a lot at work. Lets say you’re building a home gym and want to mostly do barbell movements. You could get a mono-lift, a separate platform for deadlifts, a belt squat machine, and so on. I’d definitely like all of that. But I also want to start now.

So we have to think about the real problem: Justin wants to do squats and deadlift a few times a week, and doesn’t have time to spend driving to the gym.

What is the smallest thing we can do to help him get started?

There are lots of modular power racks available, he probably needs a barbell and some weight, and also a platform to set that equipment on. This can be purchased and built in a couple of days.

This setup is extensible with different attachments, and can grow over time as there is need and want.

## Back to Auth
So, what is the fastest way to get going with authentication? Token based auth. Rails supports this by default, and all it depends on is a User Model and a controller which finds a user and verifies there is a current token.

This approach took about an hour to set up, and when it’s no longer viable (maybe friends and family want to start logging in or I want to make the data more secure), there is always Devise and OAuth.

## Next
I don’t want to get too far without having CI set up, so the next thing I’ll be working on is getting something setup that will run tests. I’m think github actions or maybe a Travis CI at the moment.


