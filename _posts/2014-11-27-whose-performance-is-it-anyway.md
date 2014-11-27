---
layout: post
title: "Whose Performance is it anyway?"
description: ""
category: 
tags: [performance]
---
{% include JB/setup %}


Whose Performance is it anyway?

We recently finished an awesome vodQA event at Pune. It was encouraging for me to see a lot of interest around Performance Testing. The only disappointment being that most of the discussions I came across were regarding Load Testing.
Let me start with definition of Load Testing (from wikipedia): "Load testing is the process of putting demand on a system or device and measuring its response. Load testing is performed to determine a system's behaviour under both normal and anticipated peak load conditions." For a web application, typically this gives us an insight into the server-side performance.  But certainly three is a lot more to performance testing than measuring server-side performance. There have been a lot of developments in the client-side programming and the world is moving to a more distributed system. Steve Souders blogged about this in 2010: "Five years ago most of the attention on web performance was focused on the backend. Since then we've learned that 80% of the time users wait for a web page to load is the responsibility of the frontend...".
Come 2014 and we have seen an explosion in Mobile Devices; Networks are being re-written and there is already a huge momentum behind Internet of Things (IOT). Your Application's performance matters and it will do more so in the coming years. If "Load Tests" are the only real tests in your applications performance strategy then you better be in 2005. Server-side performance matters but so does the performance of your Client-Side code, Networks, Infrastructure and more importantly the 3rd Party services you are using.

Here's a list of things that you should consider while testing performance of an application:
Server Side Tests:
1. Data (Master and Transactional)
I have often made the mistake of focusing my server-side performance tests around Master Data. While it is important to test performance of your core business entities, you often tend to miss out on the fact that transactional data accrues over time to give you nasty surprises. Typically such
2. Caches
# TODO
3. Infrastructure
TODO
4. Compression, Translation and Security
TODO
5. Logging
TODO

Client Side Tests:
1. Rendering
TODO
2. Networks and Networking Protocols
Networks are changing! SDNs have become a reality. It is imperative that we start looking at network traffic as part of our performance testing initiatives.
Wireless networks should be the first to make it to your performance test plans. Further, with the advent of IOT there will be an enhance requirement to look at protocols other than TCP.
3. 3rd Party Services
The more distributed we get, the more we depend on 3rd party services. Unfortunately, as Steve mentions in his talk here --------------- INSERT LINK it has the potential to become a single point of failure and lead to larger performance issues.
4. Caches
TODO

So, what would my performance test strategy look like?
1. Add Performance Tests to your CI mechanism
    a. Performance validations at the UI layer of the application
        Use the web page rules provided by yahoo / google to test for performance regressions over time
    b. Performance validations at the API / Service layer of the application
        Assert for APIs response time in your functional test suite.
2. Nightly runs for the Long Running Load Tests
Run against a pre-fixed transaction data load and Re-Evaluate Load / Thresholds periodically. Ensure that you take each regression seriously.

3. Multi-Location performance tests using the cloud (wireless and wired networks?)

4. Live Performance Monitoring
Monitor the real user performance data and ensure they

5. Performance Tests on Target Devices


Resources :
http://www.stevesouders.com/
https://developers.google.com/speed
https://developer.yahoo.com/performance
http://techblog.netflix.com/search/label/performance
http://calendar.perfplanet.com









