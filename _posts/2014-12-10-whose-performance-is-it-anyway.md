---
layout: post
title: "Whose Performance is it anyway?"
isHome: true
description: ""
category: 
tags: [Performance Testing]
---
{% include JB/setup %}


Last month we finished an awesome [vodQA event](http://www.thoughtworks.com/insights/blog/vodqa-shots-pune-roundup) in our Thoughtworks Pune office.
During the event it was encouraging to see a lot of interest in Performance Testing.
But I was also a bit disappointed to see all of the performance testing discussions tending towards "Load Testing".

"Load Testing" typically gives us insight into server-side performance. But there is a lot more to performance testing than just measuring server-side performance.
Back in 2010 Steve Souders wrote about [frontend SPOF](http://www.stevesouders.com/blog/2010/06/01/frontend-spof/). He makes an important observation:

> ".. we've learned that 80% of the time users wait for a web page to load is the responsibility of the frontend."

Fast Forward to 2014 and the world has been moving towards even more distributed applications. Networks are being re-written and there is already a huge momentum behind Internet of Things (IOT).
Your Application's performance matters and it will do more so in the coming years. But If "Load Tests" are the only performance tests for your application, then you have a slim chance of identifying performance issues upfront.
Server-side performance is important but equally so is the performance of your client-side code, network, infrastructure and even the 3rd party libraries that you use.
On this journey to understand application performance, I would like to start with some very basic questions:

### 1. What really is well performing code?
The answer to this question lead me to the basics of computer science. And I came across some excellent examples in Princeton University's [Analysis of Algorithms](http://introcs.cs.princeton.edu/java/41analysis/).
So, how do we quantify code performance? Well, the easiest measure for the performance of a program is its running time. And let me quote once again:

> The total running time is determined by two primary factors:
>
>    1. The cost of executing each statement. (property of the system)
>    2. The frequency of execution of each statement. (property of the algorithm)

This means that the performance of code depends as much on the underlying system as its algorithmic efficiency.
And really, the underlying system is not mere a single computer. These days, it is made up of complex mix of multi-layered software code sitting on top of a variety of hardware systems which are interconnected via different network mediums.
And that leads me to the question that has been bugging me for a while..

### 2. Whose performance are we are trying to test?
I feel this is an important question to soak-in before we begin with any performance testing exercise.
With the complex and multi-layered systems that we work with today, there are different things that could hurt an applications performance.
It is really important that we look at all aspects of application performance before we try to measure it. And again a good way to get started is to ask some simple questions:

1. Are we trying to test the performance of the piece of code that we just wrote?
2. Do we want to test the code performance when it is deployed in an application or web server?
3. How do I get alerted when there is change in overall application performance due to the small code change that I made?
4. Are we trying to tweak our web or application server settings for faster response times?
5. Do we want to come up with some performance figures for Capacity planning?
6. How much peak load would our application handle? How does it scale?
7. Are we trying to monitor the performance of our live application?
8. Are we checking for bottlenecks in your Application Infrastructure
9. Do we want to check for performance problems from an End User Perspective?
    - Validate that our applications response times are within the required threshold
    - Validate that our applications response times are similar across our target locations
    - Validate that our applications response times are similar when accessed from different network types

These are all important questions that try to address different aspects of application performance.
They should help us design specific testing experiments and in-turn help uncovering performance problems.
Essentially, I would classify these into 3 different categories:
  - Lower Level tests closer to code (1-3)
  - Higher Level tests which are more from the system perspective (4-6)
  - Real User Measurements (7-9)

The next step here is to come up with an effective performance test strategy based on these categories. I plan to write about it in my next blog post.
But, if you've got this far I would love to hear from you. Did I miss anything? Do you have better suggestions?
Please do leave your comments.....


