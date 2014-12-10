---
layout: post
title: "Whose Performance is it anyway?"
description: ""
category: 
tags: [Performance Testing]
---
{% include JB/setup %}


Last month we finished an awesome [vodQA event](http://www.thoughtworks.com/insights/blog/vodqa-shots-pune-roundup) at our Thoughtworks Pune office.
During the event it was encouraging to see a lot of interest in Performance Testing.
But I was also a bit disappointed to see all of the performance testing discussions limited to "Load Testing".

For a web application, "Load Testing" typically gives us an insight into the server-side performance. But three is a lot more to performance testing than just measuring server-side performance.
Back in 2010 Steve Souders wrote about [frontend SPOF](http://www.stevesouders.com/blog/2010/06/01/frontend-spof/). He makes an important observation:

> ".. we've learned that 80% of the time users wait for a web page to load is the responsibility of the frontend."

Back to 2014 and the world has been moving towards even more distributed applications. Networks are being re-written and there is already a huge momentum behind Internet of Things (IOT).
Your Application's performance matters and it will do more so in the coming years.
But If "Load Tests" are the only performance tests for your application, then you have a slim chance of identifying performance issues upfront.
Well, server-side performance is important but equally so is the performance of your client-side code, network, infrastructure and even the 3rd party libraries that you use.
Let us start with a very basic question.

### 1. What really is well performing code?
To answer this question, we need to look at the basics of computer science and I found a really good explanation [here](http://introcs.cs.princeton.edu/java/41analysis/).
If I try to summarize it in a simplistic context, I would say that code performance will be influenced by two primary factors:
1. Execution time for a piece of code - This will be dependent on the underlying system
2. Number of times a piece of code is executed - This will be dependent on the efficiency of the algorithm

Hence, Application Performance cannot be independent of the underlying system.
The important thing to realize here is that today the underlying system not just a single computer. It is in fact a complex mix of multi-layered software code sitting on top of a variety of hardware systems which are interconnected via different network mediums.
And that leads me to the question that has been bugging me for a while..

### 2. Whose performance are we are trying to test?
I feel this is an important question to ponder before we begin with any performance testing exercise.
With the complex and multi-layered systems that we work with today, there are different things that could hurt an applications performance.
Here are some of the questions I like to being with before really try:
1. Are we trying to test the performance of the piece of code that we just wrote?
2. Do we want to test the code performance when it is deployed in an application / web server?
3. Are we interested in monitoring the change in overall application performance for each code change?
4. Are we trying to tweak our web / application server settings for faster response times?
5. Trying to get some performance figures for Capacity planning?
6. How much peak load would our application handle? How does it scale?
7. Are we trying to monitor the performance of our live application?
8. Are we checking for bottlenecks in your Application Infrastructure
9. Do we want to check for performance problems from an End User Perspective?
    - Validate that our applications response times are within the required threshold
    - Validate that our applications response times are similar across your target locations
    - Validate that our applications response times are similar when accessed from different networks

These are all important questions that try to address different aspects of application performance.
I would ideally classify these into 3 different categories:
 - Lower Level tests closer to code (1-3)
 - Higher Level tests which are more from the system perspective (4-6)
 - Real User Measurements (7-9)

With this categorization in place, I feel well-equipped to start designing testing experiments for uncovering performance problems in each area.
I feel that the next step will be to come up with an effective performance test strategy. But thats for another post.

Since this is my first post, I would really like to hear your thoughts and suggestions. 
Please do leave your comments...









