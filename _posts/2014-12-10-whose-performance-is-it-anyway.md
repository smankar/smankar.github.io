---
layout: post
title: "Whose Performance is it anyway?"
isHome: true
description: ""
category: 
tags: [Performance Testing]
---
{% include JB/setup %}


Last month, we finished an awesome [vodQA event](http://www.thoughtworks.com/insights/blog/vodqa-shots-pune-roundup) in our Thoughtworks Pune office.
During the event it was encouraging to see a lot of interest in Performance Testing. But slightly disappointing to see all of those discussions tending towards "Load Testing".

"Load Testing" typically gives us insight into server-side performance. But there is a lot more to performance testing than just measuring server-side performance.
Back in 2010 Steve Souders wrote about [frontend SPOF](http://www.stevesouders.com/blog/2010/06/01/frontend-spof/). He makes an important observation:

> ".. we've learned that 80% of the time users wait for a web page to load is the responsibility of the frontend."

Fast Forward to 2014 and the world has been moving towards even more distributed applications. Networks are being re-written and there is already a huge momentum behind Internet of Things (IOT).
Our Application's performance matters and it will do more so in the coming years. But If "Load Tests" are the only performance tests for our application, then you have a slim chance of identifying performance issues upfront.
Server-side performance is important but equally so is the performance of our client-side code, network, infrastructure and even the 3rd party libraries that you use.
On this journey to understand application performance, I would like to start with some very basic questions:

### 1. What really is well performing code?
The answer to this question lead me to the basics of computer science. And I came across some excellent examples in Princeton University's [Analysis of Algorithms](http://introcs.cs.princeton.edu/java/41analysis/).
So, how do we quantify code performance? well, the easiest measure for the performance of a program is its running time. And here's another quote:

> The total running time is determined by two primary factors:
>
>    1. The cost of executing each statement. (A property of the system)
>    2. The frequency of execution of each statement. (A property of the algorithm)

This means that the performance of code depends as much on the underlying system as its algorithmic efficiency.
And really, the underlying system is not mere a single computer. These days, it is made up of complex mix of multi-layered software code sitting on top of a variety of hardware systems which are interconnected via different network mediums.
And that leads me to the question that has been bugging me for a while..

### 2. Whose performance are we are trying to test?

I feel this is an important question to soak-in before we begin with any performance testing exercise.
With the complex and multi-layered systems that we work with today, there are different things that could hurt an applications performance.
Have a look at a sample web application architecture pictured below. And then its time for some examples...

![Image of a Sample Web Application Architecture](/assets/images/performance_10_12_2014.png "Web Application Architecture")

#### Examples:
1. Server-side code is sub-optimal but working fine.<br>
Going by the above picture, our server-side code has a lot of computing power at its disposal. And hence it should not have survival issues.
Typically, a good load testing exercise should point this out. But unless there are major defects, we might just decide to live on with some additional computing power.

2. Server-side code is super awesome but client-side code sucks.<br>
This is where we should be be shifting the focus of our performance tests. Tools like [YSlow](http://yslow.org/) and [PageSpeed](https://developers.google.com/speed/pagespeed/) should be able to get us started.

3. All our code is super awesome. But our servers are in a different country than our target audience.<br>
I feel the real question here is: How early can can we detect such issues? A simple [web page test](http://www.webpagetest.org/) should point this out.
But ideally we should create continuous probes from across the target locations to keep our web-application well performing.

4. Again, all our code is super awesome. But our audience only uses wireless networks to access the web-application.<br>
Is my website optimised for wireless access? With the mobile revolution around us, this is is another important aspect of our web-application performance.
Tools like [Mobitest](http://mobitest.akamai.com/m/index.cgi) are relatively new on the block. But surely worth a try.

To Summarize: it is really important that we look at all aspects of application performance before we try to measure it. And again a good way to get started is to ask some simple questions:

1. Are we trying to test the performance of the piece of code that we just wrote?
2. Do we want to test the code performance when it is deployed in an application or web server?
3. How do I get alerted when there is change in overall application performance due to the small code change that I made?
4. Are we trying to tweak our web or application server settings for faster response times?
5. Do we want to come up with some performance figures for Capacity planning?
6. How much peak load would the application handle? How does it scale?
7. Are we trying to monitor the performance of our live application?
8. Are we checking for bottlenecks in the Application Infrastructure?
9. Do we want to check for performance problems from an End User Perspective?
    - Validate that the application's response times are within the required threshold
    - Validate that the application's response times are similar across our target (audience) locations
    - Validate that the application's response times are similar when accessed from different network types

These are all important questions that try to address different aspects of application performance.
They should help us design specific testing experiments and in-turn help uncovering performance problems.
Essentially, I would classify these into 3 different categories:

  - Lower Level tests that are closer to code (Questions 1-3)
  - Higher Level tests that are more from the system perspective (Questions 4-6)
  - Real User Measurements (Questions 7-9)


As I next step, I plan to dig deeper into each of these aspects and come up with strategies and tooling. Thats for the next post though.
But, if you've got this far I would love to hear from you. Did I miss anything? Do you have better suggestions?
Please do leave your comments.....
